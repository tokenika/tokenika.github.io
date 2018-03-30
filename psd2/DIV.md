# Autoryzacja w PSD2 poprzez kryptografię asymetryczną jako sposób na wprowadzenie skalowalnego KYC 

## Wprowadzenie

#### Jak weryfikować tożsamość online?

W sytuacji internetowej weryfikacji tożsamości chodzi o to, w jaki sposób w warunkach online uzyskać pewność, że osoba (klient) podająca się jako K rzeczywiście jest tą osobą K.

Istotne jest tu to, że jest to sytuacja online, czyli NIE w realu. W sytuacji kontaktu w realu dokument ze zdjęciem można uznać za wystarczająco dobry sposób weryfikacji tożsamości (mimo swoich oczywistych wad: jest kosztowny w produkcji i relatywnie łatwo może być podrobiony, zwłaszcza w sytuacji, gdy nie wiemy jak dokładnie powinien wyglądać oryginalny dokument, np. legitymacja policjanta).

Z oczywistych powodów w warunkach online zdjęcie, które jest integralną częścią dokumentu tożsamości, przestaje być użyteczne, bo nie ma go z czym porównać. 

#### Problem: nieskalowalność KYC

Wymogi KYC narzucają na firmy konieczność ustalenia tożsamości każdego nowego klienta.

Wszystkie obecne procedury KYC mają jedną istotną wadę: nie skalują się. Przy pozyskaniu nowego klienta każda firma, która podlega wymogom KYC, musi samodzielnie dokonać ustalenia jego tożsamości, co jest kosztowne i czasochłonne (dla obu stron: firmy i jej klienta). Tak więc ten sam kosztowny i czasochłonny proces jest wykonywany wielokrotnie przez różne firmy.

Warty podkreślenia jest fakt, że outsourcing procesu KYC do specjalistycznej firmy, która się tym zajmuje, nie rozwiązuje problemu skalowania KYC. Nawet jeśli podmiot specjalizujący się w KYC dostanie zlecenie weryfikacji klienta K, którego wcześniej weryfikował dla innej firmy, to i tak cały proces KYC będzie musiał być uruchomiony od nowa, bo nie ma żadnego formalnego dowodu, że w obu przypadkach jest to rzeczywiście ten sam klient K.

#### Co chcemy osiągnąć?

Szukamy rozwiązania dla procesu KYC, które:

- umożliwi skalowanie procedury KYC, czyli wyeliminuje konieczność powtarzania tego procesu przez kolejne firmy,
- będzie miało realną szansę na masową adopcję, zarówno po stronie biznesów jak i ich klientów,
- otworzy drogę na inne niż KYC zastosowania.

## Wprowadzenie skalowalnego KYC poprzez PSD2

Naszą intencją jest zbudowanie kanału mocnej autoryzacji transakcji bankowych w PSD2 poprzez zastosowanie kryptografii asymetrycznej, a następnie skorzystanie z faktu, że ten sam klucz prywatny (i mechanizm jego ochrony), który służy do autoryzacji w PSD2, może być użyty do skalowania procesu KYC, a także do wielu innym celów, np:

- kryptograficzna ochrona tożsamości i reputacji,
- cyfryzacja dokumentów,
- cyfryzacja aktów notarialnych.

Tak więc zbudowanie mechanizmu mocnej autoryzacji w PSD2 nie jest celem ostatecznym - bardziej pełni funkcję konia trojańskiego, który da użytkownikom istotny powód żeby posiadali (i chronili) w swoim telefonie swój unikalny klucz prywatny, ściśle związany z ich tożsamością / reputacją (podobnie jak PESEL, tyle że klucz prywatny jest z założenia niejawny).

Warte podkreślenia jest to, że:

1. Naszym zamiarem nie jest zbudowanie całego procesu autoryzacji w PSD2, a jedynie jednego z wymaganych dwóch niezależnych kanałów.
2. Bez problemu możemy wspierać elementy dynamicznie autoryzacji, tj. te łączące daną transakcję z określoną kwotą i określonym odbiorcą (np. ostatnie cyfry rachunku i kwota transakcji).

Innymi słowy, chcemy wykorzystać dogodną sytuację stworzoną przez PSD2 do wprowadzenia do powszechnego użycia mechanizmu ochrony klucza prywatnego po stronie użytkownika. Mając tego rodzaju mechanizm, masowo (i często) używany z racji PSD2, możemy wprowadzić skalowalny proces KYC, a także zacząć budować przeróżne produkty zmierzające do cyfryzacji "wszystkiego".

## Autoryzacja w PSD2 poprzez kryptografię asymetryczną

#### Istniejące rozwiązania

Obecne podejścia w zakresie mocnej autoryzacji transakcji bankowych są następujące:

- jesteś wypytywany o jakiś wcześniej ustalony przez obie strony sekret (np. nazwisko panieńskie matki),
- dostajesz esemesa z kodem,
- weryfikujesz się poprzez narzędzie typu Google Authenticator.

#### Proponowane rozwiązanie

Do autoryzacji transakcji bankowej w PSD2 użyjemy kryptografii asymetrycznej, tj, kombinacji klucza prywatnego X i sprzężonego z nim klucza publicznego Y. Generalnie sprowadza się to do tego, że generujemy dla klienta K klucz prywatny X i w przyszłości uznajemy, że posiadanie klucza X jest tożsame z byciem klientem K.

Chociaż do autoryzacji w PSD2 nie jest potrzebny blockchain, ze względu na dalsze potencjalne zastosowania naszego systemu, wygenerowane klucze będą kompatybilne z [publicznym blockchainem EOS](https://eos.io/).

#### Konfiguracja procesu autoryzacji

Konfiguracja (tj. setup) naszego procesu autoryzacji PSD2 dla nowego klienta wygląda następująco:

1. Klient K instaluje na swoim telefonie zrobioną przez nas aplikację mobilną, która generuje unikalną parę kluczy kryptograficznych: klucz prywatny X i klucz publiczny Y. 
2. Klucz prywatny X jest trzymany w telefonie i nigdy nikomu poza klientem K nie jest ujawniany (klucz prywatny jest chroniony PIN-em lub biometrycznie - być może da się tu sprytnie wykorzystać właściwości biometryczne EOSa).
3. Aplikacja przekazuje bankowi B klucz publiczny Y klienta K.

W wyniku tego procesu bank B może w swojej bazie danych przypisać tożsamość klienta K do jego klucza publicznego Y. Prawdopodobnie wymagało to będzie pewnego rodzaju procesu aktywacji (podobnie jak aktywujemy nowootrzymaną kartę debetową), tak żeby bank B miał pewność, że świeżo wygenerowany klucz publiczny rzeczywiście należy do klienta K.

Uwaga: Żeby dostawca technologii mógł uniknąć podejrzeń o nieuczciwość, kod źródłowy i dystrybucja wspomnianej wyżej aplikacji mobilnej musiałyby być pod kontrolą banku B.

#### Działanie procesu autoryzacji

Autoryzacja transakcji bankowej w PSD2 wygląda następująco:

1. Poprzez aplikację mobilną bank B wysyła do klienta K propozycję transakcji finansowej (ze wszystkimi potrzebnymi szczegółami typu adresat płatności i kwota).
2. Klient K wyraża zgodę na tę propozycję (tj. autoryzuje tę transakcję) poprzez podpisanie jej swoim kluczem prywatnym X.

Autoryzacja sprowadza się zatem do potwierdzenia, że klient K dysponuje kluczem prywatnym X, który odpowiada kluczowi publicznemu Y. W ten sposób bank B ma pewność, że propozycja transakcji finansowej została zatwierdzona przez klienta K, bo tylko on może być posiadaczem klucza prywatnego X, który odpowiada kluczowi publicznemu Y, przypisanemu w banku B klientowi K.

#### Korzyści

Autoryzacja poprzez kryptografię asymetryczną na pewno jest rozwiązaniem niegorszym niż alternatywne metody (np. esemesy lub Google Athenticator). Dodatkowe korzyści są takie:

1. Dzięki EOSowej funkcjonalności *account permissions* staje się możliwe zbudowanie po stronie użytkownika dowolnie złożonej struktury delegacji uprawnień w zakresie autoryzacji transakcji finansowych.
2. Bank B może łatwo uzyskać kryptograficzne potwierdzenie szczegółów transakcji podpisane kluczem prywatnym X klienta K - wtedy bank B ma oficjalny dowód na to, że klient K zgodził się na zaproponowaną mu transakcję. Według naszej wiedzy inne metody autoryzacji nie dają takiej opcji.

#### Problemy

Do przemyślenia pozostaje procedura odzyskiwania zgubionego / skradzionego klucza prywatnego. Na pewno warto będzie tu wykorzystać dość spektakularne (jak na blockchain) możliwości EOSa w tym zakresie.

## Wykorzystanie kryptografii asymetrycznej do skalowania procesu KYC

#### Koncepcja

Najogólniej mówiąc, skalowalny KYC polega na tym, że jeden podmiot (w naszym przypadku bank) przeprowadza weryfikację tożsamości danej osoby (klienta) K, następnie wynik tej weryfikacji umieszczamy na blockchainie, a kolejne firmy z tego blockchainowego zapisu korzystają (bezpłatnie albo odpłatnie), unikając tym samym konieczności powtarzania procesu KYC.

Innymi słowy, mechanizm skalowalnego KYC pozwala na weryfikację danej osoby w warunkach online w analogiczny sposób, jak czyni to w realu porównanie wyglądu twarzy ze zdjęciem w tradycyjnym dokumencie. Zamiast porównania widoku twarzy ze zdjęciem mamy tu porównanie deklarowanej tożsamości z podpisanym kryptograficznie zapisem na blockchainie.

Tym samym otrzymujemy mechanizm, który jest w stanie poświadczyć, że klient K mówi prawdę na temat siebie samego. Co ciekawe, traci wtedy sens kradzież danych osobowych celem kradzieży tożsamości, bo sama informacja do niczego się nie przyda. Żeby być zweryfikowanym w tym nowym paradygmacie, oprócz samej informacji trzeba jeszcze mieć związany z tą informacją klucz prywatny pasujący do blockchainowego zapisu, poświadczonego przez podmiot o wysokiej reputacji.

Patrząc od strony samej koncepcji można powiedzieć, że w paradygmacie skalowalnego KYC informacja dotycząca tożsamości staje się obiektem chronionym kluczem prywatnym, podobnie jak kryptowaluta w portfelu kryptowalutowym.

#### Strategia wdrożenia

Do wdrożenia naszego systemu autoryzacji w PSD2 na pewno potrzebne będzie partnerstwo z jakimś podmiotem bankowym.

Każdy bank ma zweryfikowaną tożsamość każdego swojego klienta. Załóżmy, że jakiś bank uznałby, że nasz system spełnia jego wymogi jako jeden z kanałów mocnej autoryzacji w PSD2 i rekomenduje swoim klientom użycie naszej aplikacji mobilnej do tego celu.

Co się wtedy dzieje?

Uzgadniamy z naszym partnerem bankowym, żeby umieszczał on w formie zapisów na blockchainie EOSa mapowanie *klucz publiczny vs. zahashowane dane osobowe wymagane w procesie KYC* dla wszystkich swoich klientów korzystających z naszego systemu autoryzacji. Musiałby to być zrobione automatycznie, tak żeby dane na blockchainie były zawsze aktulne.

Bardzo istotne jest tu, że dane te są w formie zashashowanej, a więc nieczytelnej dla osób trzecich (czyli odpada problem upublicznienia wrażliwych danych osobowych).

Tym samym bank wprowadza nam do naszego systemu skalowalnego KYC tysiące swoich klientów i on sam staje się gwarantem autentyczności informacji publikowanych blockchainie.

Podsumowując: partner bankowy dostaje od nas system mocnej autoryzacji za darmo, a w zmian zasila nasz system skalowalnego KYC dużą liczbą zweryfikowanych pod kątem KYC użytkowników.

#### Proces

Na blockchainie dokonujemy wpisu mapującego klucz publiczny X klienta K do jego danych osobowych wymaganych w procesie KYC

Każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym banku B. W ten sposób bank B gwarantuje prawdziwość informacji zawartej w tym wpisie. 
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych.

Te same dane osobowe (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

W jaki sposób ten blockchainowy wpis może być użyty przez inne firmy do weryfikacji KYC swoich nowych klientów?

Załóżmy, że firma F:

- potrzebuje dokonać weryfikacji KYC klienta K,
- ma zaufanie do banku B, tj. podpisane elektronicznie oświadczenia banku B w zakresie klienta K uznaje za prawdziwe.

Wtedy proces KYC może wyglądać następująco:

1. Za pomocą aplikacji mobilnej firma F uzyskuje zgodę klienta K na przesłanie jej danych osobowych wymaganych w procesie KYC.
2. Aplikacja mobilna klienta K wysyła firmie F wymagane dane osobowe, wraz z kryptograficznym dowodem posiadania klucza prywatnego X.
3. Firma F weryfikuje prawdziwość otrzymanych informacji poprzez zahashowanie otrzymanych danych i porównanie wyniku tego hashowania z wpisami na blockchainie dotyczącymi klucza publicznego Y.

W ten sposób firma F ma pewność, że klient K istotnie ma tożsamość zgodną z tym co deklaruje, bo tylko on może być posiadaczem klucza prywatnego X, który odpowiada kluczowi publicznemu Y, a otrzymane informacje hashują się do wyniku podpisanego elektronicznie przez zaufany bank B.

Uwaga: Oczywiście sposób hashowania musi być wystandaryzowany, tak żeby ewentualna niezgodność nie wynikała z użycia różnych metod hashowania. Może się też okazać, że ze względów bezpieczeństwa potrzebne będzie tzw. zasolenie hashowania, ale jest to jak najbardziej wykonalne - sól może dostarczać firmie F klient K. 

#### Korzyści

Firma F unika konieczności przeprowadzenia kosztownej i czasochłonnej procedury KYC, bo korzysta z wyników procedury KYC przeprowadzonej wcześniej przez zaufany bank B.

#### Legislacja

Wymagania legislacyjne są następujące:

1. Ustawa musi zapewnić, że korzystanie z wyników weryfikacji KYC, wykonanej uprzednio przez inny podmiot, jest wiarygodną formą weryfikacji KYC. Możemy przyjąć, że obecne ustawodawstwo już temu sprzyja, bo legalne jest zlecenie przeprowadzenia KYC innej firmie (tj. outsource'owanie KYC).
2. Ustawa musi zapewnić, że identyczność hashy dwóch plików tekstowych jest tożsama z identycznością zapisów w tych plikach. Z wstępnego rozeznania wynika. że może to być dość trudna przeszkoda do pokonania.

Alternatywnie, ustawa musi zapewnić, że udowodnienie posiadania przez klienta K klucza prywatnego X i  uzyskanie przez firmę F od banku B podpisanego elektronicznie potwierdzenia wykonania KYC dla klienta posługującego się kluczem publicznym Y, jest wystarczająco dobrą formą weryfikacji KYC. Gdyby udało się uzyskać tego rodzaju legislację, to powyższy proces można by radykalnie uprościć, bo nie było potrzebne umieszczanie na blockchainie zahashowanych danych osobowych klienta K.

## Rozszerzenie 1: Kryptograficzna ochrona tożsamości i reputacji

#### Koncepja

Wykorzystując fakt posiadania (z racji autoryzacji w PSD2) przez dużą liczbę użytkowników klucza prywatnego, łatwo jest zastąpić poprzez użycie kryptografii asymetrycznej funkcjonalność typu *zaloguj się przez Facebook*.

Usługa ta w swojej obecnej formie jest niczym innym niż wykorzystaniem reputacji (i/lub unikalnej tożsamości), którą dany użytkownik ma na jakimś znanym serwisie (typu Facebook, Twitter, Gmail, GitHub) do utworzenia unikalnej tożsamości (i w konsekwencji możliwości budowy reputacji wokół tej tożsamości) na jakimś innym, mniej popularnym serwisie S.

Przyczyna coraz większej popularności tego rodzaju mechanizmu jest oczywista: stwarza to łatwiejszą konwersję dla serwisu S i większą wygodę dla użytkownika. 

Warto podkreślić, że w tym przypadku rzeczywista (tj. zgodna z realem) tożsamość użytkownika nie jest konieczna (tj. proces KYC może nie być wymagany), liczy się tylko to, żeby serwis S mógł w swoim systemie przypisać danego użytkownika do jakiegoś unikalnego identyfikatora dostarczonego przez serwis typu Facebook.

#### Problem

W obecnej formie działania tego mechanizmu użytkownik w pełni powierza serwisowi typu Facebook swoją tożsamości na innych serwisach. Innymi słowy, tożsamość danego użytkownika na serwisie S nie należy do niego samego lecz do innego podmiotu. Firma typu Facebook ma pełną kontrolę na tą tożsamością i może zrobić dowolną rzecz uzurpując sobie tę tożsamość (w tym także kompletnie zniszczyć reputację danej osoby).

#### Korzyści

Przy użyciu klucza prywatnego do definiowania unikalnej tożsamości powyższy problem całkowicie znika. Właścicielem tożsamości jest zawsze właściciel klucza prywatnego i tylko on ma kontrolę nad reputacją związaną z tą tożsamością.

#### Proces

Mechanika działania kryptografii asymetrycznej w powyższym zakresie jest dobrze opisana w dokumentacji projektu [Jolocom](https://jolocom.com/).

## Rozszerzenie 2: Wpisy na blockchainie potwierdzające stan faktyczny

#### Proces

Na blockchainie dokonujemy wpisów stwierdzających stan faktyczny, który wynika z dokumentów istniejących w formie tradycyjnej, np:

- *Posiadacz klucza publicznego Y mieszka pod adresem A.*
- *Posiadacz klucza publicznego Y ukończył uczelnię U.*
- *Posiadacz klucza publicznego Y jest wspólnikiem w spółce S.*

Podobnie jak powyżej każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym notariusza N (czyli zamiast banku mamy tu notariusza albo jakąś inną instytucję zaufania publicznego). W ten sposób notariusz N gwarantuje prawdziwość informacji zawartej w tym wpisie. 
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną wrażliwych danych osobowych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

Użycie tego systemu przez podmioty trzecie jest analogiczne do wyżej opisanego przypadku weryfikacji KYC, czyli firma F otrzymuje informacje od klienta K, hashuje je, a następnie weryfikuje ich prawdziwość poprzez porównanie z hashem dostępnym na blockchainie.

#### Korzyści

Uzyskujemy dwojakiego rodzaju korzyści:

1. Następuje migracja informacji zawartych w tradycyjnych dokumentach papierowych do formy cyfrowej, co oczywiście oznacza redukcję kosztów i możliwości fałszowania.
2. Następuje przejęcie pełnej kontroli nad informacją przez podmiot, do której ona należy. W tym paradygmacie każdorazowo gdy informacja jest przekazywana osobie trzeciej, musi się na to zgodzić jej właściciel, tj. posiadacz klucza prywatnego. Możliwe staje się też przekazywanie minimalnej informacji jaka jest w danej sytuacji potrzebna, np. żeby udowodnić swoją pełnoletność nie trzeba przekazywać pełnej daty urodzenia, lecz fakt bycia starszym niż dany próg wiekowy.
3. Pełna kontrola posiadacza klucza prywatnego nad informacją otwiera także możliwość świadomego sprzedawania własnych danych demograficznych (których prawdziwość jest poświadczona kryptograficznie) podmiotom zainteresowanym tego rodzaju danymi.

#### Legislacja

Ustawa musi dać wsparcie dla wiarygodności tego typu dokumentów cyfrowych.

## Rozszerzenie 3: Wpisy na blockchainie o potwierdzające czynności prawne

#### Proces

Na blockchainie dokonujemy wpisów o charakterze notarialnym, tj. wszelkie czynności prawne, np:

- *Posiadacz klucza publicznego Y udziela pełnomocnictwa w zakresie reprezentowania spółki S posiadaczowi klucza publicznego Z.*
- *Posiadacz klucza publicznego Y sprzedaje udziały w spółce S posiadaczowi klucza publicznego Z.*

Podobnie jak w wersji weryfikującej tożsamość każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym notariusza N. W ten sposób notariusz N gwarantuje prawdziwość informacji zawartej w tym wpisie.
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych / poufnych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

Rola notariusza N wygląda następująco: weryfikuje on tożsamość swoich klientów w podobny sposób, jak firma F przeprowadza proces KYC, a następnie podpisuje swoim certyfikowanym podpisem elektronicznym i umieszcza na blockchainie (w formie zahashowanej) oświadczenia woli swoich klientów, poświadczając w ten sposób ich autentyczność.

Użycie tego systemu przez podmioty trzecie jest analogiczne do wyżej opisanego przypadku weryfikacji KYC, czyli firma F otrzymuje informacje od klienta K, hashuje je, a następnie weryfikuje ich prawdziwość poprzez porównanie z hashem dostępnym na blockchainie.

#### Korzyści

Otwieramy w ten sposób drogę dla internetowych kancelarii notarialnych. Notariusz N może zweryfikować tożsamość swoich klientów i przyjąć ich oświadczenia woli online, tj. bez konieczności organizacji fizycznego spotkania.

#### Legislacja

Ustawa musi dać wsparcie dla wiarygodności tego typu aktów notarialnych.

## Model ekonomiczny

#### Dlaczego certyfikat musi być na blockchainie?

Łatwo zauważyć, że stosowany w naszym rozwiązaniu zapis na blockchainie pełni rolę kryptograficznie podpisanego certyfikatu wydanego przez instytucję zaufania publicznego (np. bank, urząd, notariusz itp).  W paradygmacie podpisu cyfrowego taki certyfikat jest wydawany przez zaufany podmiot, a następnie zostaje przekazy osobie (lub firmie), której on dotyczy. Wtedy taka osoba (lub firma) może posługiwać się takim certyfikatem żeby udowodnić autentyczność swoich deklaracji / oświadczeń.

Tak więc teoretycznie wszystkie powyższe przypadki (tj. skalowanie KYC, kryptograficzna ochrona tożsamości & reputacji, cyfryzacja dokumentów & aktów notarialnych) można by zrealizować bez użycia blockchaina: zamiast być zapisem na blockchainie, taki certyfikat mógłby być w posiadaniu klienta K i być każdorazowo dostarczany przez niego innym podmiotom podczas interakcji z nimi.

Więc po jest nam blockchain?

Gdybyśmy wyeliminowali blockchain, wylądowalibyśmy w paradygmacie certyfikowanego podpisu cyfrowego, w którym koszt certyfikatu musi być poniesiony przez klienta K, co z kolei jest istotną barierą w masowej adopcji tego rodzaju systemu. Natomiast zastąpienie certyfikatu (będącego w posiadaniu klienta K) zapisem na blockchainie (dokonanym przez instytucję certyfikującą) pozwala na przeniesienie kosztu certyfikacji z klienta K, którego dotyczy proces KYC, na firmę F, która jest beneficjentem istotnej redukcji kosztów procesu KYC.

Dzięki użyciu blockchaina odwraca się zatem model ekonomiczny całego systemu: zapisany na blockchainie certyfikat przynosi dochody instytucji, która go wystawiła, a koszty ponosi firma F, która z niego korzysta, a nie klient K, jak to ma miejsce w tradycyjnym mechanizmie certyfikowanego podpisu cyfrowego.

Mamy więc subtelną, lecz istotną różnicę: wprowadzamy model ekonomiczny, który zdejmuje z użytkownika konieczność poniesienia kosztów uzyskania certyfikatu. Naszym zdaniem jest to warunek konieczny, żeby idea, którą proponujemy, miała szansę na masową adopcję.

#### Rola smart-kontraktu

Oczywiście wyżej opisane przepływy finansowe są możliwe przy założeniu, że certyfikat zapisany na blockchainie będzie obudowany odpowiednim smart-kontraktem, który te opłaty będzie implementował.

Istotą takiego smart-kontraktu jest pobieranie opłaty od firmy F (albo klienta K, bo taka sytuacja też ma czasem sens) na rzecz banku B (albo innej instytucji, która dokonała weryfikacji klienta K) za każdym razem, gdy firma F (albo klient K) jest beneficjentem tego udogodnienia.

Głównym celem tego rodzaju opłat jest dobre zmotywowanie uczestników tego systemu, tak żeby korzyści finansowe miał ten podmiot, który popełnia wysiłek, a koszty ponosił ten podmiot, który ma korzyści.

#### Monetyzacja systemu

Dodanie do powyższego smart-kontraktu minimalnej marży dla nas (jako twórców tego smart-kontraktu) wydaje się relatywnie proste. Ale może to nie być konieczne, bo alternatywną formą finansowania naszego systemu może być dochód z puli inflacyjnej EOSa - oczywiście przy założeniu, że nasz system będzie postrzegany jako *pro publico bono*.

#### Własny token?

Nasuwa się pytanie o możliwość wprowadzenia własnego tokenu do przeprowadzania powyższych rozliczeń między uczestnikami naszego systemu (tym tropem idzie Civic i inne podobne zdecentralizowane rozwiązania). Ma to niewątpliwą zaletę w postaci możliwości przeprowadzenia ICO dla takiego przedsięwzięcia. Natomiast nieusuwalną wadą jest to, że własny token oznacza, że aby móc użyć systemu trzeba najpierw zakupić jego tokeny, co jest istotną barierą w procesie adopcji. 

Ponieważ łatwa adopcja jest krytycznie ważna, naszym zdaniem lepiej jest uniknąć wprowadzania własnego tokenu i opłaty w smart-kontrakcie realizować albo w bardziej uniwersalnych tokenach EOSa albo w jakieś niezależnej, stabilnej walucie, która zapewne powstanie na EOSie.

## Szerszy kontekst: Digital Identity

To co robimy w zakresie wykorzystania kryptografii asymetrycznej do skalowania KYC to podzbiór większego zagadnienia znanego jako [Cyfrowa Tożsamość](http://di.com.pl/cyfrowa-tozsamosc-56607) (Digital Identity) albo, w przypadku użycia systemów rozproszonych, Zdecentralizowana Weryfikacja Tożsamości (Decentralized Identity Verification, w skrócie DIV).

W zakresie DIV pierwsze próby podjęcia tego tematu sięgają 2013 roku, np. Dan Larimer miał wtedy pomysł na systemem zdecentralizowanej tożsamości o nazwie [Keyhotee](https://www.youtube.com/watch?v=3pZaTdEtK-8).

Obecnie istnieje [spora liczba projektów blockchainowych](https://github.com/peacekeeper/blockchain-identity), które podejmują rożne aspekty cyfrowej tożsamości i jej weryfikacji. Najważniejsze naszym zdaniem są te dwa:

- [Civic](https://www.civic.com/) ([whitepaper)](https://tokensale.civic.com/CivicTokenSaleWhitePaper.pdf)
- [Decentralized Identity](https://decentralized.id/) ([whitepaper biznesowy](https://decentralized.id/docs/DID-whitepaper.pdf), [whitepaper techniczny](https://decentralized.id/docs/DID-tech.pdf))

Dostępna jest dość [wiarygodna recenzja systemu Civic](https://www.scottbrady91.com/Blockchain-Identity/Technical-Review-of-Civics-Secure-Identity-Platform). Jest ona całkiem pozytywna - główny zarzut sprowadza się do krytyki odstąpienia od używania standardów na rzecz swoich własnych wynalazków:

> Civic really should have used OAuth and OpenID Connect, instead of rolling their own authentication protocol.

Tak więc pomysł jest oceniany jako bardzo dobry, ale wykonanie jako dość niefortunne. Dodatkowo Civic bazuje na [RootStock](https://www.rsk.co/), czyli będzie się zmagał ze wszystkimi problemami jakie ma w sobie Bitcoin.

W przypadku projektu Decentralized Identity, też jest ciekawa sytuacja, bo wygląda na to, że oni doszli do ściany w zakresie możliwości Ethereum:

> We found Ethereum smart contracts unfit for computations that go beyond than the basics. While we understand that the technology is just growing up, we found that not being able to do computations (like hashing) on the Blockchain is a major drawback. The global computational power isn’t available for Dapps yet.

Ta deklaracja też jest intrygująca:

> At the time of writing, there exists no blockchain that is truly public and stateless. All current blockchain technologies intend to store data. We just want to store the receipt of an ID transfer; not the data. In the matter of transferring an ID token/nugget, we only require a decentralised transfer of data. The data structures used by current blockchain technologies is restrictive and do not allow for expansion or abstraction. We call for a new, stateless, public Blockchain.

## Pozycja konkurencyjna

Nasza pozycja konkurencyjna wygląda dość korzystnie ponieważ:

- Działamy w cieniu firm dużo większych od nas (np. Civic, Decentralized Identity) - one już wykonały sporo roboty za nas i dodatkowo uwiarygadniają sensowność naszego przedsięwzięcia.
- Mamy precyzyjną specyfikację (ich kod źródłowy) i relatywnie małe zadanie (bo w pierwszym etapie zajmujemy się tylko KYC), więc dokładnie wiadomo co trzeba robić i nie tracimy czasu i kasy na eksperymentowanie.
- Mamy technologię (EOS), która jest wyraźnie lepsza od tej, którą wybrali inni, bo jest pozbawiona istotnych ograniczeń (np. opłaty transakcyjne, niewydolność i powolność procesowania transakcji), a dodatkowo zawiera sprzyjające nam funkcjonalności (np. procedura odzyskiwania skradzionego / zgubionego klucza prywatnego i jego biometrycza ochrona).
- Tego rodzaju tematy jak cyfrowa tożsamość mają specyfikę lokalną, więc nasze położenie geograficzne daje nam przewagę w tym rejonie Europy. Możemy też podpatrzyć z kim Civic zawarł alianse biznesowe w USA i zrobić podobne układy lokalnie.

