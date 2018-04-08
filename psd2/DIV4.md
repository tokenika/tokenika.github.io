# Sygnet - skalowanie procesu KYC poprzez bankowe poświadczenie tożsamości klienta

Wersja 4.0 (06/04/2018)

**Proponujemy rozwiązanie w zakresie KYC, które bazując na legislacji PSD2 umożliwia wykorzystanie, będącej w posiadaniu banku, informacji o tożsamości klienta. Skalowanie procesu KYC uzyskujemy poprzez wykorzystanie kryptograficznego poświadczenia tożsamości klienta uzyskane od jego banku. Dzięki temu bank, oprócz świadczenia usług finansowych, jest w stanie radykalnie ułatwić swoim klientom proces weryfikacji KYC w sytuacji, gdy chcą oni skorzystać z usług innych podmiotów w branży FinTech (zarówno bankowych jak i niebankowych), a w dalszej konsekwencji, staje się dla nich generatorem ich cyfrowej tożsamości w internecie.**

## 1. Wprowadzenie

#### 1.1 Jak weryfikować tożsamość online?

Internetowa weryfikacja tożsamości to próba rozwiązania następującego problemu: w jaki sposób w warunkach online uzyskać pewność, że osoba (klient) podająca się jako K rzeczywiście jest tą osobą K?

Istotne jest tu to, że jest to sytuacja online, czyli *nie* w realu. W sytuacji kontaktu w realu dokument ze zdjęciem można uznać za wystarczająco dobry sposób weryfikacji tożsamości (mimo swoich oczywistych wad: jest kosztowny w produkcji i relatywnie łatwo może być podrobiony, zwłaszcza w przypadku, gdy nie wiemy jak dokładnie powinien wyglądać oryginalny dokument, np. dowód tożsamości obcokrajowca).

Z oczywistych powodów w warunkach online zdjęcie, które jest integralną częścią dokumentu tożsamości, przestaje być użyteczne, bo nie ma go z czym porównać. 

#### 1.2 Problem: nieskalowalność KYC

Wymogi KYC narzucają na firmy konieczność ustalenia tożsamości każdego nowego klienta.

Wszystkie obecne procedury KYC mają jedną istotną wadę: nie skalują się. Przy pozyskaniu nowego klienta każda firma, która podlega wymogom KYC, musi samodzielnie dokonać ustalenia jego tożsamości, co jest kosztowne i czasochłonne (dla obu stron: firmy i jej klienta). Tak więc w obecnie istniejącym paradygmacie ten sam kosztowny i czasochłonny proces musi być wykonywany wielokrotnie przez kolejne firmy.

Jedynym znanym nam sposobem na skalowanie KYC jest wykorzystanie procedury tzw. testowego przelewu, który polega na tym, że klient poświadcza swoją tożsamość poprzez wykonanie przelewu ze swojego rachunku w innym banku do banku, który chce dokonać weryfikacji KYC. Oczywiste są wady tego rozwiązania:

* nie rozwiązuje to problemu dla podmiotów niebankowych,
* nie skaluje się więcej niż raz (bo nie można w ten sposób potwierdzić tożsamości w kolejnym banku),
* wymaga to od klienta dodatkowego wysiłku.

Niemniej tego rodzaju kombinowanie (tj. używanie przelewu bankowego do innych celów niż cel finansowy) pokazuje, że problem nieskalowalności KYC rzeczywiście istnieje.

Warty podkreślenia jest fakt, że outsourcing procesu KYC do specjalistycznej firmy, która się tym zajmuje, nie rozwiązuje problemu skalowania KYC. Nawet jeśli podmiot specjalizujący się w KYC dostanie zlecenie weryfikacji klienta K, którego wcześniej weryfikował dla innej firmy, to i tak cały proces KYC będzie musiał być uruchomiony od nowa, bo nie ma żadnego formalnego dowodu, że w obu przypadkach jest to rzeczywiście ten sam klient K.

#### 1.3 Co chcemy osiągnąć?

Szukamy rozwiązania dla procesu KYC, które:

- umożliwi skalowanie procedury KYC, czyli wyeliminuje konieczność powtarzania tego procesu przez kolejne firmy,
- będzie działać dla wszystkich firm, które podlegają wymogom KYC (tj. nie tylko dla podmiotów bankowych),
- będzie miało realną szansę na masową adopcję, zarówno po stronie biznesów jak i ich klientów,
- otworzy drogę na inne niż KYC zastosowania, w szczególności do rozpowszechnienia koncepcji cyfrowej tożsamości.

## 2. Skalowalny proces KYC

#### 2.1 Koncepcja

Najogólniej mówiąc, skalowalny KYC polega na tym, że jeden podmiot (w naszym przypadku bank) przeprowadza weryfikację tożsamości danej osoby (klienta) K, a następnie wynik tej weryfikacji jest udostępniany innym podmiotom (bankowym i niebankowym).

Do konstrukcji skalowalnego KYC wykorzystujemy następujący zestaw założeń:

- (niemal) każdy dorosły człowiek ma konto w banku,
- każdy bank zna tożsamość każdego swojego klienta,
- w ramach PSD2 możliwe jest wydobywanie z banku informacji dotyczących tożsamości danego klienta,
- każdy bank dysponuje [kwalifikowanym podpisem elektronicznym](https://pl.wikipedia.org/wiki/Podpis_kwalifikowany).

Naturalną konsekwencją wydaje się zatem istnienie możliwości zrobienia użytku z informacji o tożsamości klientów bankowych (tj. informacji, które banki i tak posiadają) w celu radykalnego usprawnienia procesu KYC.

#### 2.2 System Sygnet

Idąc tym tropem, proponujemy mechanizm, który nazywać będziemy systemem Sygnet. Nazwa ta w zamierzeniu kojarzyć się ma z własnoręcznym podpisem i ma nawiązywać do czegoś, co służy do potwierdzania jego tożsamości i autoryzacji różnego rodzaju działań

> Signet - a small seal, especially one set in a ring, used instead of or with a signature to give authentication to an official document.

System Sygnet umożliwia klientowi K dostarczenie dowolnej firmie F podpisanego elektronicznie przez wiarygodny podmiot (w naszym przypadku bank B) certyfikatu poświadczającego jego (tj. klienta K) tożsamość.

**W systemie Sygnet skalowanie procesu KYC uzyskujemy więc poprzez wykorzystanie kryptograficznego poświadczenia tożsamości klienta uzyskane od jego banku.**

Oznacza to, że nasz pomysł w zakresie KYC sprowadza się *de facto* do tego: w kontrolowany sposób wyprowadzamy na zewnątrz informacje, które do tej pory leżały bezużytecznie (z perspektywy świata zewnętrznego) w systemie bankowym. Dzięki temu bank, oprócz świadczenia usług finansowych, staje się generatorem cyfrowej tożsamości swoich klientów.

#### 2.3 Wymagania

Żeby powyższy mechanizm KYC mógł funkcjonować potrzebne będzie spełnienie następujących warunków:

1. Wymagane jest żeby nasz partner bankowy zgodził się kryptograficznie podpisywać informacje udostępniane w ramach API, o którym mowa w PSD2 (w szczególności chodzi nam o informacje dotyczące tożsamości danego klienta).
2. Integralną częścią naszej aplikacji musi być możliwość weryfikacji certyfikowanego podpisu elektronicznego banku, tak żeby firma F mogła w łatwy sposób uzyskać pewność, że otrzymane od banku B informacje na temat klienta K rzeczywiście zostały przez ten bank wygenerowane i nie zostały zmodyfikowane po ich podpisaniu. Jest to funkcjonalność podobna do tej, która jest oferowana przez powszechnie dostępne serwisy internetowe, np. [MadKom](https://madkom.pl/weryfikacja-podpisu-elektronicznego/).
3. Ponieważ my, jako twórcy i operatorzy aplikacji mobilnej będącej w posiadaniu klienta K, pełnimy rolę TPP (Third Party Provider), musimy być podmiotem zarejestrowanym w KNF zgodnie z wymagami PSD2. Wydaje się, że licencja AIS (Account Information Service) w tym przypadku będzie wystarczająca.

#### 2.4 Proces

Załóżmy, że firma F potrzebuje dokonać weryfikacji KYC klienta K i ma zaufanie do banku B, tj. podpisane elektronicznie oświadczenia banku B w zakresie tożsamości klienta K uznaje za prawdziwe.

Wtedy proces KYC, inicjowany przez firmę F, może wyglądać następująco:

1. Klient K chcący skorzystac z usługi firmy F, potwierdza, że ma konto w banku, który jest wspierany przez system Sygnet i wybiera ten system jako mechanizm weryfikacji tożsamości w procesie KYC.
2. Klient K jest przekierowywany na stronę webową systemu Sygnet. Przekierowanie zawiera wygnerowany przez firmę F unikalny identyfikator żądania weryfikacji.
3. Poprzez system Sygnet klient K loguje się do swojego banku B, a następnie autoryzuje wygenerowane przez system Sygnet zapytanie do bankowego API. Zapytanie to dotyczy danych osobowych klienta K, które są wymagane w procesie weryfikacji KYC i także zawiera unikalny idetyfikator otrzymany we wcześniejszym kroku od firmy F.
4. W odpowiedzi na wyżej opisane zapytanie, bank B zwraca podpisany elektornicznie pakiet zawierający wymagane dane osobowe klienta oraz identyfikator żądania.
5. Po weryfikacji podpis banku B firma F uznaje uzyskane od banku dane osobowe klienta K za prawdziwe i aktualne, i tym samym spełniające kryteria KYC.

## 3. Uogolnienie systemu

Możemy łatwo pokazać, że system Sygnet może nie tylko służyć do skalowania procecu KYC, ale także funkcjonować jako mechanzm podpisywania  przez bank w imieniu swojego klienta (i na jego żądanie) dowolnego dokumentu.

Ogólny schemat systemu Sygnet jest następujący: klient K przekazuje do banku B dowolny ciąg znaków, a bank B zwraca podpisany elektornicznie pakiet zwierający dwa elementy:

* powyższy ciąg znaków,
* dane osobowe klienta K, które pozwalają na jego jednoznaczną idetyfikację (np. imię, nazwisko, nr dowowdu osobistego albo PESEL)

Zauważmy że powyżsy ciąg znaków może być losowo wygenerówanym przez zewnętrzny podmiot identyfikatorem żądania, tak jak to ma miejsce w przypadku KYC. Ale może także być hashem dowlnego dokumentu.

Jeśli jest to hash dokumentu, np. oświadczenia woli albo umowy cywilno-prawnej, to uzyskujemy de facto ten sam efekt, ktory mielibyśmy gdyby klient używał certyfikowanego podpisu elektronicznego. Tyle że w naszym podejściu nie wymagamy aby klient posiadał klucz prywatny (co jest istotą podpisu elektornicznego) bo w naszym schemacie to bank podpisuje się w imieniu i na żadanie klienta.

Oczywistym niebezpieczeństwem jest to, że bank może uzurpować sobie tożsamość klienta (tj. podpisać się pod czymkolwiek za niego bez jego wiedzy), ale taki jest nieusuwalny trade-off tego rozwiązania.

Gdybśmy chcieli usunąć ten trade-off, system Sygnet w wersji "profesjonalej" może wygenerować dla klienta K uniklany klucz prywatny i odpoiwadajćy mu klicz publiczny, a następnie w ramach dodatkowej usługi poprosić bank o wydanie elektornicznie podpisanego certyfikatu który łączyłby tosamośc klienta K z jego klluczem publicznym. Posiadając taki certyfikat, klient K mógłby posługiwac się nim w podobny sposób jak działa certfikowany podpis elektoniczny - oczywiście przy założeniu że uznajmy bank B za wiarygodne zródło certyfikikacji tożsamości klienta K.

## 4. Czym nasze rozwiązanie różni się od profilu zaufanego?

Wedle [dokumentacji](https://www.gov.pl/cyfryzacja/profil-zaufany-ego-) Ministerstwa Cyfryzacji profil zaufany to bezpłatna metoda potwierdzania tożsamości obywatela w systemach elektronicznej administracji.

> Profil zaufany działa jak odręczny podpis. Możesz dzięki niemu wysyłać przez internet dokumenty i wnioski do różnych urzędów (np. wnieść podanie, odwołanie, skargę). Profil zaufany potwierdza tożsamość obywatela  — podpis potwierdzony profilem zaufanym, podobnie jak kwalifikowany podpis elektroniczny, skutecznie zastępuje w kontaktach z podmiotami publicznymi podpis własnoręczny.

Na pierwszy rzut oka profil zaufany wygląda na rozwiązanie bardzo podobne do naszego. Co więcej, podobnie jak w naszym podejściu jednym z podmiotów zdolnych do wygenerowania takiego profilu dla użytkownika jest serwis bankowy. Kilka banków w Polsce oferuje taką usługę.

Jest jednak istotna różnica: zastosowanie profilu zaufanego jest ograniczone do serwisów państwowych. Ograniczenie to wynika ze sposobu działania tego systemu: polega on na tym, że po założeniu profilu zaufanego użytkownik uzyskuje dostęp do wspólnego dla systemów państwowych mechanizmu logowania, lecz nie jest to równoważne z uzyskaniem uniwersalnej cyfrowej tożsamości. Tak więc profil zaufany z założenia nie może być rozszerzony na sferę niepaństwową i tym samym nie rozwiązuje problemu KYC dla firm.

Niemniej porównanie naszego rozwiązania do profilu zaufanego wydaje się jak najbardziej uzasadnione. Można nawet powiedzieć, że nasz system oferuje biznesom rozwiązanie w zakresie KYC analogiczne do tego, jakie profil zaufany oferuje urzędom państwowym w zakresie mechanizmu logowania, tj. weryfikacji tożsamości obywatela w warunkach online.

## 5. Monetyzacja systemu

1. Dostarczenie bankom możliwości monetyzowania informacji o tożsamości ich klientów, z wykorzystaniem mechanizmów autoryzacji, które muszą zostać dostarczone na potrzeby TPP (wymaganie PSD2). Inwestycją ze strony banków byłoby dostarczenie dodatkowego (nie wymaganego przez PSD2) API.
2. Dostarczenie wszystkim podmiotom, które podlegają pod KYC mechanizmu szybkiej weryfikacji tożsamości klientów, który skróci czas od zainteresowania klienta ofertą do faktycznej sprzedaży towaru lub usługi, tym samym eliminując okazje do rozmyślenia się przed zakupem i potencjalnie zwiększając zyski.
3. Konsument nie jest rozpraszany formalnymi wymogami i może się skoncentrować na tym co dla niego ważne - konsumpcji.
4. Tokenika występuje w roli pośrednika między bankiem a firmą. Firma nie musi być TPP, ponieważ Tokenika taką rolę pełni. Firma nie musi się integrować ze wszystkimi bankami, ponieważ Tokenika to robi.

W tym modelu, każda ze strony musi swoje zrobić:
1. Bank - udostępnić dodatkowe (niewymagane przez PSD2) API, do którego dostęp będzie autoryzowany zgodnie z wymaganiami PSD2
2. Tokenika - zintegrować się z bankami (nie jest dla mnie jasne, czy PSD2 standaryzuje API, które banki muszą udostępnić, czy nakłada jedynie wymagania funkcjonalne, techniczne aspekty pozostawiając do decyzji poszczególnych banków; zakładam, że to drugie i że roboty będzie tutaj dużo), spełnić wymagania TPP, ułatwić integrację firmom
3. Firma - zintegrować się z systemem Tokeniki (dzięki Tokenice nie musi być TPP, ani integrować się z każdym bankiem osobno)

W zamian za ten wysiłek:
1. Bank - monetyzuje posiadaną informację
2. firmy - zwiększają sprzedaż i potencjalnie oszczędzają na kosztownym procesie weryfikacji klienta
3. Tokenika - pobiera prowizję

Można sobie wyobrazić, że firma A po uzyskaniu certyfikatu przekazuje go firmie B wraz z unikalnym identyfikatorem żądania. Można sobie wyobrazić modyfikacje schematu, która uniemożliwia (czyni nieopłacalnym) przekazywanie certyfikatów:

1. Oprócz unikalnego identyfikatora żądania, firma wysyła do Tokeniki swój klucz publiczny
2. Taka para jest przekazywana do banku. Bank generuje certyfikat w sposób analogiczny, ale przed podpisaniem go własnym kluczem, szyfruje kluczem publicznym firmy.
3. Firma po otrzymaniu certyfikatu jest wstanie go odkodować i zweryfikować prawdziwość podanych przez konsumenta danych.
4. Przekazanie certyfikatu firmie B bez klucza prywatnego umożliwiającego rozkodowanie (do czego firma A raczej skłonna nie będzie) nie ma większego sensu.

## 6. Disclaimer

Niniejszy dokument jest tylko wstępnym zarysem pomysłu (można go potraktować jako tekst wizjonerski). W swojej obecnej formie nie wyczerpuje on wszystkich tematów, które będą wymagać analizy zanim zdecydujemy się na pójście z propozycją do potencjalnego partnera bankowego i ostatecznie uznamy, że opisane rozwiązanie jest warte wdrożenia.

1. W aspekcie biznesowym brakuje nam analizy w zakresie:

   * Jakie podmioty w Polsce (i Europie) potrzebują weryfikować swoich klientów w zakresie KYC? Jak dużo ich jest?
   * Jakie koszty ponoszą podmioty (zarówno bankowe jak i niebankowe) w związku z KYC?
   * Jak powszechne jest korzystanie z usług finansowych oferowanych przez firmy zagraniczne (z UE i spoza UE)?
   * Jak dużym problemem jest przeprowadzanie KYC dla klientów z innych niż siedziba firmy krajów?
   * W jakim kierunku będzie się zmieniać zapotrzebowanie na KYC w przyszłości?

2. W aspekcie prawnym brakuje nam analizy w zakresie:

   * Jakie dokładnie są wymogi KYC finansowego w Polsce (i Europie)? Jakie są wymogi w przypadku stosowania outsourcingu KYC?
   * Jakie są wymogi w zakresie KYC dla klientów zagranicznych (z UE i spoza UE)?

3. W aspekcie technologicznym brakuje nam analizy w zakresie:

   * Jak trudna dla nas jest implementacja naszego rozwiązania?
   * Jak trudna dla banku jest adaptacja do proponowanego przez nas rozwiązania?

4. Czy udostępnianie danych osobowych klienta jest zgodne z PSD2?

   ​

5. Ustawa musi zapewnić, że korzystanie z wyników weryfikacji KYC, wykonanej uprzednio przez inny podmiot, jest wiarygodną formą weryfikacji KYC. Możemy przyjąć, że obecne ustawodawstwo już temu sprzyja, bo legalne jest zlecenie przeprowadzenia KYC innej firmie (tj. outsource'owanie KYC).

6. Ustawa musi zapewnić, że podpisane kryptograficznie oświadczenie banku odnośnie tożsamości jego klienta jest wiarygodną formą weryfikacji KYC. Możemy wstępnie przyjąć, że będzie to możliwe, skoro już teraz wyżej opisany przelew testowy jest uznawany za wiarygodną formę weryfikacji KYC, a nasza metoda na pewno nie jest mniej wiarygodna.

   ​

7. Czy banki będą skore do wdrożenia dodatkowego API? Wiadomo, że i tak muszą przygotować API spełniające wymagania PSD2, więc potencjalnie dodatkowy endpoint  nie powinien być kłopotliwy, niemniej jednak przed przystąpieniem do prac warto zbadać ich zainteresowanie oraz jakie są ich oczekiwane zyski, tj.  czy korzystanie z systemu będzie się opłacało drugiej stronie, zwłaszcza kiedy doliczymy zyski Tokeniki (może się okazać, że banki nie wchodzą w inwestycje, które nie zwracają się w ciągu określonego czasu).

8. Ile banków musiałoby wejść do systemu, aby firmy widziały sens w integracji  z systemem. Może się okazać, że dopiero udział dwóch, trzech dużych banków  da nam możliwość weryfikacji tożsamości wystarczająco dużej liczby  potencjalnych klientów, żeby taka integracja przyniosła wymierne oszczędności pozwalające na wystarczająco szybkie odzyskanie poniesionych nakładów.

9. Jakie są odpowiedzi na te pytania jeżeli chcemy przenieść ten mechanizm do innych krajów UE?

10. Jakie będą prawne uwarunkowania? Wiadomo, że w tej chwili można delegować weryfikację tożsamości i że banki robią to za pomocą przelewów weryfikacyjnych, ale wiadomo też że KNF nakłada na ten drugi mechanizm pewne ograniczenia (nie można wykonać przelewu weryfikacyjnego z konta, które zostało założone za pomocą takiego przelewu). Można zakładać, że i tutaj pewne ograniczenia będą nałożone.

11. Jakie techniczne wymagania nałożą banki na TPP? Na ile podobne będą mechanizmy autoryzacji dostępu do API w różnych bankach? Od tego zależy ile pracy trzeba będzie włożyć w opracowanie systemu, a tym samym jego opłacalność.

12. Jakie są wymagania dotyczące prywatności. Banki mogą nie być skore do udostępniania danych klientów, ale mogą zgodzić się na podpisanie skrótu tych danych (tak jak to zasugerowano w opisie procesu).