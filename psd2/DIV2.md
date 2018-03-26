Idąc tym tropem, powyższy mechanizm można też zastosować dla innych niż PESEL informacji (np. dokumenty typu prawo jazdy, polisa OC, dyplom uczelni itd), ale na razie proponowałbym w to nie wchodzić, bo wówczas mamy dodatkową komplikację - problem aktualności tych informacji. PESEL ma tę zaletę, że nigdy nie traci ważności i jednoznacznie identyfikuje każdego człowieka.

Więc wykorzystując mechanizm DIV w jego najprostszej formie (czyli tylko PESEL) dostajemy narzędzie które:

- Doskonale nadaje się jako jeden z kanałów w mocnej autoryzacji dla PSD2, co było naszym pierwotnym celem.
- Istotnie wspomaga systemy online, w których szybka i niezawodna weryfikacja tożsamości jest konieczna i dodatkowo uwalnia te systemy od potrzeby przechowywania sporej części danych osobowych (bo w tym nowym paradygmacie te dane zawsze są po stronie użytkownika).
- Otwiera możliwość migracji do wersji online rzeczy, które do tej pory były praktycznie niewykonalne w wersji online, np. wybory parlamentarne.

A w wersji rozszerzonej (czyli nie tylko PESEL) mechanizm ten otwiera możliwość ostatecznej cyfryzacji wszystkiego: wszystkie dokumenty państwowe, dokumentacja medyczna, cała branża notarialna, itp.

No i oczywiście tożsamość cyfrowa otwiera drogę do reputacji cyfrowej, bo czasem ważniejsze jest to jaką masz przeszłość, niż to kim dokładnie jesteś, a ten sam klucz prywatny może chronić i uwiarygadniać obie te informacje jednocześnie.

---

Proponowany plan działania:

- Zrobić MVP (łącznie z aplikacją mobilną).
- Zebrać duży kapitał i błogosławieństwo aparatu państwowego.

Tutaj akurat ICO miałoby duży sens, bo potrzebne jest maksymalnie dużo rozgłosu i dużo kapitału, który trzeba rozdać użytkownikom żeby bootstrapować tego rodzaju system. To jest machina, którą trudno uruchomić, ale jak to się uda to reszta dzieje się sama.

Dysponując dużym kapitałem można zastosować strategię PayPala: rozdawać tokeny (swoje własne lub EOSa, np. równowartość kilku USD) w zamian za poddanie się procesowi ucyfrowienia swojego PESELa w naszym systemie DIV. Będzie to kosztowne, ale przynajmniej pozbawione przekrętów, bo z automatu mamy pewność, że jedna osoba tylko raz może się zarejestrować i pobrać przysługujące jej tokeny.

To co niewątpliwie ułatwia sprawę w zakresie zebrania kapitału to fakt, że temat DIV dość mocno przemawia do wyobraźni, bo każdy z nas czuje jak anachroniczny jest obecny system przepytywania o nazwisko panieńskie matki albo urzędowe pieczątki na papierze.

Mi się wydaje, że DIV raczej na pewno będzie w przyszłości standardem - jego zalety są niezaprzeczalne. Pytanie jest tylko kto to zrobi i kiedy.



## Mocna autoryzacja w PSD2

#### Konfiguracja procesu

1. Poprzez aplikację webową banku B klient K instaluje na swoim telefonie aplikację mobilną, która generuje unikalną parę kluczy kryptograficznych: klucz prywatny X i klucz publiczny Y. 
2. Klucz prywatny X jest trzymany w telefonie i nigdy nikomu poza klientem K nie jest ujawniany (klucz prywatny jest chroniony PIN-em lub biometrycznie - być może można będzie wykorzystać właściwości biometryczne EOSa).
3. Aplikacja przekazuje bankowi B klucz publiczny Y klienta K.

W wyniku tego procesu bank B przypisuje tożsamość klienta K do jego klucza publicznego Y (podobnie jak jego numer numer telefonu, PESEL, adres zamieszkania i inne dane klienta K, którymi bank B dysponuje).

#### Autoryzacja transakcji finansowej

1. Poprzez aplikację mobilną bank B wysyła do klienta K propozycję transakcji finansowej, wraz z losową liczbą L zaszyfrowaną kluczem publicznym Y.
2. Klient K wyraża zgodę na tę propozycję (tj. autoryzuje tę transakcję) poprzez odszyfrowanie losowej liczby L swoim kluczem prywatnym X, a następnie jej odesłanie do banku B.
3. Bank B upewnia się, że jest to ta sama liczba, która została pierwotnie wysłana w formie zaszyfrowanej do klienta K.

Autoryzacja sprowadza się zatem do potwierdzenia, że klient K dysponuje kluczem prywatnym X, który odpowiada kluczowi publicznemu Y. W ten sposób bank B ma pewność, że propozycja transakcji finansowej została zatwierdzona przez klienta K, bo tylko on może być posiadaczem klucza prywatnego X, który odpowiada kluczowi publicznemu Y, przypisanemu w banku B klientowi K.

#### Korzyści

1. Dzięki EOSowej funkcjonalności *account permissions* staje się możliwe zbudowanie po stronie użytkownika dowolnie złożonej struktury delegacji uprawnień w zakresie autoryzacji transakcji finansowych.
2. Bank B może łatwo uzyskać kryptograficzne potwierdzenie szczegółów transakcji podpisane kluczem prywatnym X klienta K - wtedy bank B ma oficjalny dowód na to, że klient K zgodził się na zaproponowaną mu transakcję. Według naszej wiedzy inne metody autoryzacji nie dają takiej opcji.
3. To podejście otwiera drogę do istotnego rozbudowania funkcjonalności systemu w zakresie:(a) internetowej weryfikacji tożsamości, (b) cyfryzacji dokumentów i (c) cyfryzacji aktów notarialnych. Ten sam klucz prywatny (i mechanizm jego ochrony), który służy do autoryzacji PSD2, może służyć wielu innym celom.

#### Strategia

Na pewno potrzebne będzie partnerstwo z jakąś większą instytucją finansową, np. bankiem. Wtedy partner bankowy dostaje od nas system mocnej autoryzacji za darmo, a w zmian zasila nasz system dużą liczbą użytkowników.

#### Do przemyślenia

Procedura odzyskiwania zgubionego / skradzionego klucza prywatnego. Na pewno warto będzie tu wykorzystać możliwości EOSa w z tym zakresie.

## Rozszerzenie 1: Wpisy na blockchainie służące weryfikacji tożsamości

#### Proces

Na blockchainie dokonujemy wpisów potwierdzających tożsamość, np:

* *Posiadacz klucza publicznego Y ma PESEL 123456789*
* *Posiadacz klucza publicznego Y nazywa się Imię Nazwisko.*

Każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym banku B. W ten sposób bank B gwarantuje prawdziwość informacji zawartej w tym wpisie. 
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

W jaki sposób ten blockchainowy wpis może być użyty przez inne firmy do weryfikacji tożsamości swoich klientów w warunkach on-line?

Załóżmy, że firma F:

* potrzebuje dokonać weryfikacji KYC klienta K,
* ma zaufanie do banku B, tj. podpisane elektronicznie oświadczenia banku B w zakresie klienta K uznaje za prawdziwe.

Wtedy proces KYC może wyglądać następująco:

1. Za pomocą aplikacji mobilnej firma F zadaje klientowi K pytania dotyczące jego tożsamości: np. imię, nazwisko i PESEL. Dodatkowo przesyła też liczbę losową L.
2. Klient K w aplikacji mobilnej potwierdza chęć udzielenia firmie F odpowiedzi na te pytania.
3. Aplikacja mobilna klienta K wysyła firmie F jego klucz publiczny Y oraz odpowiedzi na pytania dotyczące jego tożsamości, wraz z wcześniej otrzymaną liczbą losową L, wszystko zaszyfrowane kluczem prywatnym X.
4. Firma F weryfikuje prawdziwość otrzymanych informacji poprzez:
   - odszyfrowanie tych informacji kluczem publicznym Y
   - upewnienie się że liczba losowa L zgadza się z tą pierwotnie wysłaną klientowi K,
   - zahashowanie otrzymanych odpowiedzi i porównanie wyniku tego hashowania z wpisami na blockchainie dotyczącymi klucza publicznego Y.

W ten sposób firma F ma pewność, że klient K istotnie ma tożsamość zgodną z tym co deklaruje, bo tylko on może być posiadaczem klucza prywatnego X, który odpowiada kluczowi publicznemu Y, a otrzymane informacje hashują się do wyniku podpisanego elektronicznie przez zaufany bank B.

#### Korzyści

Firma F unika konieczności przeprowadzenia kosztownej i czasochłonnej procedury KYC, bo korzysta z wyników weryfikacji tożsamości klienta K przeprowadzonej wcześniej przez zaufany bank B.

#### Legislacja

Ustawa musi zapewnić, że korzystanie z wyników weryfikacji KYC, wykonanej uprzednio przez inny podmiot, jest równie wiarygodne jak konwencjonalna weryfikacja KYC.

## Rozszerzenie 2: Wpisy na blockchainie potwierdzające stan faktyczny

#### Proces

Na blockchainie dokonujemy wpisów stwierdzających stan faktyczny, który wynika z dokumentów istniejących w formie tradycyjnej, np:

* *Posiadacz klucza publicznego Y mieszka pod adresem A.*
* *Posiadacz klucza publicznego Y ukończył uczelnię U.*
* *Posiadacz klucza publicznego Y jest wspólnikiem w spółce S.*

Podobnie jak powyżej każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym notariusza N (czyli zamiast banku mamy tu notariusza albo jakąś inną instytucję zaufania publicznego). W ten sposób notariusz N gwarantuje prawdziwość informacji zawartej w tym wpisie. 
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych / poufnych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

Użycie tego systemu przez podmioty trzecie jest analogiczne do wyżej opisanego przypadku weryfikacji KYC, czyli firma F otrzymuje informacje od klienta K, hashuje je, a następnie weryfikuje ich prawdziwość poprzez porównanie z hashem dostęnym na blockchainie.

#### Korzyści

Migracja dokumentów istniejących w formie tradycyjnej do formy cyfrowej.

#### Legislacja

Ustawa musi dać wsparcie dla wiarygodności tego typu dokumentów cyfrowych.

## Rozszerzenie 3: Wpisy na blockchainie o charakterze notarialnym

#### Proces

Na blockchainie dokonujemy wpisów o charakterze notarialnym, tj. oświadczenia woli i umowy cywilne, np:

* *Posiadacz klucza publicznego Y udziela pełnomocnictwa w zakresie reprezentowania spółki S posiadaczowi klucza publicznego Z.*
* *Posiadacz klucza publicznego Y sprzedaje udziały w spółce S posiadaczowi klucza publicznego Z.*

Podobnie jak w wersji weryfikującej tożsamość każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym notariusza N. W ten sposób notariusz N gwarantuje prawdziwość informacji zawartej w tym wpisie.
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych / poufnych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

Rola notariusza N wygląda następująco: weryfikuje on tożsamość swoich klientów w podobny sposób, jak firma F przeprowadza KYC, a następnie podpisuje swoim certyfikowanym podpisem elektronicznym i umieszcza na blockchainie (w formie zahashowanej) oświadczenia woli tych klientów, poświadczając w ten sposób ich prawdziwość.

Użycie tego systemu przez podmioty trzecie jest analogiczne do wyżej opisanego przypadku weryfikacji KYC, czyli firma F otrzymuje informacje od klienta K, hashuje je, a następnie weryfikuje ich prawdziwość poprzez porównanie z hashem dostępnym na blockchainie.

#### Korzyści

Notariusz N może przyjąć oświadczenia woli on-line, tj. bez organizacji fizycznego spotkania ze swoimi klientami.

#### Legislacja

Ustawa musi dać wsparcie dla wiarygodności tego typu aktów notarialnych.*

## Model ekonomiczny

Zapis na blockchainie pełni rolę kryptograficznie podpisanego certyfikatu wydanego przez instytucję zaufania publicznego (np. bank, notariusz itp). Tak więc wszystkie powyższe przypadki (tj. weryfikacja tożsamości, cyfryzacja dokumentów i cyfryzacja notarialna) można by zrealizować bez użycia blockchaina: zamiast być zapisem na blockchainie, taki certyfikat mógłby być w posiadaniu klienta K i dostarczany przez niego innym podmiotom, jako dowód, że mówi on prawdę. 

Więc po jest nam blockchain? Bo bez blockchaina mielibyśmy sytuację analogiczną do mechanizmu certyfikowanego podpisu cyfrowego, z jego główną wadą w postaci konieczności poniesienia kosztów takiego certyfikatu przez klienta K, co jest istotną barierą w masowej adopcji podpisu cyfrowego.

Zastąpienie certyfikatu (będącego w posiadaniu klienta K) zapisem na blockchainie (dokonanym przez instytucję certyfikującą) pozwala na przeniesienie kosztu certyfikacji z klienta K, którego dotyczy proces KYC, na firmę F, która jest beneficjentem istotnej redukcji procesu KYC. Dzięki użyciu blockchaina odwraca się model ekonomiczny podpisu cyfrowego: zapisany na blockchainie certyfikat przynosi dochody instytucji, która go wystawiła, a koszty ponosi firma F, która z niego korzysta, a nie klient K, jak to ma miejsce w tradycyjnym mechanizmie podpisu cyfrowego. Oczywiście przy założeniu, że zapis na blockchainie będzie obudowany odpowiednim smart-kontraktem.

Taki smart-kontrakt wymaga jeszcze przemyślenia. Jego istotą byłoby pobieranie opłaty od firmy F na rzecz banku B (albo innej instytucji, która dokonała weryfikacji klienta K) za każdym razem gdy firma F korzysta z tego zapisu.