Mocna autoryzacja w PSD2

Inicjacja procesu autoryzacji

\1. Poprzez aplikację webową banku B klient K instaluje na swoim telefonie aplikację mobilną, która generuje mu parę kluczy kryptograficznych: klucz prywatny X i klucz publiczny Y. 

\2. Klucz prywatny X jest trzymany w telefonie i nigdy nikomu poza klientem K nie jest ujawniany (aplikacja mobilna jest chroniona PIN-em lub odciskiem palca).

\3. Aplikacja przekazuje bankowi B klucz publiczny Y klienta K.

W ten sposób bank B może łatwo przypisać tożsamość klienta K do jego klucza publicznego Y (podobnie jak jego numer numer telefonu, PESEL, adres zamieszkania i inne dane klienta K, którymi bank B dysponuje).

Autoryzacja transakcji finansowej

\1. Poprzez aplikację mobilną bank B wysyła do klienta K propozycję transakcji finansowej, wraz z losową liczbą L zaszyfrowaną kluczem publicznym Y.

\2. Klient K wyraża zgodę na tę propozycję (tj. autoryzuje tę transakcję) poprzez odszyfrowanie losowej liczby L swoim kluczem prywatnym X, a następnie odesłanie do banku B otrzymanej wcześniej losowej liczby L, tym razem zaszyfrowanej swoim kluczem prywatnym X.

\3. Bank B odszyfrowuje otrzymaną liczbę L kluczem publicznym Y i upewnia się że jest to ta sama liczba, która została pierwotnie wysłana do klienta K.

Innymi słowy, autoryzacja polega na potwierdzeniu, że klient K dysponuje kluczem prywatnym X, który odpowiada kluczowi publicznemu Y. Dodatkowo możemy tu wykorzystać fakt, że bank B może łatwo uzyskać potwierdzenie szczegółów transakcji podpisane kluczem prywatnym X klienta K.

W ten sposób bank B ma pewność, że propozycja transakcji finansowej została zatwierdzona przez klienta K, bo tylko on może być posiadaczem klucza prywatnego X, który odpowiada kluczowi publicznemu Y, przypisanemu w banku B klientowi K.

Korzyści

\1. Dzięki EOSowej funkcjonalności *account permissions* staje się możliwe zbudowanie po stronie użytkownika dowolnie złożonej struktury delegacji uprawnień w zakresie autoryzacji transakcji finansowych.

\2. To podejście otwiera drogę do istotnego rozbudowania funkcjonalności systemu: internetowa weryfikacja tożsamości, cyfryzacja dokumentów i cyfryzacja aktów notarialnych. Ten sam klucz prywatny, który służy do autoryzacji PSD2, może służyć wielu innym celom.

Strategia

Partner bankowy dostaje od nas system mocnej autoryzacji za darmo, a w zmian zasila nasz system dużą liczbą użytkowników.

Do przemyślenia

Procedura odzyskiwania zgubionego / skradzionego klucza prywatnego.

Wpisy na blockchainie weryfikujące tożsamość

Na blockchainie dokonujemy wpisów potwierdzających tożsamość, np:

*Posiadacz klucza publicznego Y ma PESEL 123456789*

*Posiadacz klucza publicznego Y nazywa się Imię Nazwisko.*

Każdy wpis:

\1. Ma przypisaną datę kiedy został dokonany.

\2. Jest podpisany certyfikowanym podpisem elektronicznym banku B. W ten sposób bank B gwarantuje prawdziwość informacji zawartej w tym wpisie. 

\3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

Użycie przez podmioty trzecie

Załóżmy że firma F potrzebuje dokonać weryfikacji KYC klienta K.

Załóżmy też że firma F ma zaufanie do banku B, tj. podpisane elektronicznie oświadczenia banku B w zakresie klienta K uznaje za prawdziwe.

Wtedy proces KYC wygląda następująco:

1. Za pomocą aplikacji mobilnej firma F zadaje klientowi K pytania dotyczące jego tożsamości: np. imię, nazwisko i PESEL. Dodatkowo przesyła też liczbę losową L.

\2. Klient K w aplikacji mobilnej potwierdza chęć udzielenia firmie F odpowiedzi na te pytania.

\3. Aplikacja mobilna klienta K wysyła firmie F jego klucz publiczny Y oraz odpowiedzi na pytania dotyczące jego tożsamości, wraz z wcześniej otrzymaną liczbą losową L, wszystko zaszyfrowane kluczem prywatnym X.

\4. Firma F weryfikuje prawdziwość otrzymanych informacji poprzez:

(a) odszyfrowanie tych informacji kluczem publicznym Y,

(b) upewnienie się że liczba losowa L zgadza się z tą pierwotnie wysłaną,

(c) zahashowanie otrzymanych odpowiedzi,

(d) porównanie wyniku tego hashowania z wpisami na blockchainie dotyczącymi klucza publicznego Y.

W ten sposób firma F ma pewność, że klient K istotnie ma tożsamość zgodną z tym co deklaruje, bo tylko on może być posiadaczem klucza prywatnego X, który odpowiada kluczowi publicznemu Y, a otrzymane informacje hashują się do wyniku podpisanego elektronicznie przez zaufany bank B.

Korzyści: firma F unika konieczności przeprowadzenia kosztownej i czasochłonnej procedury KYC, bo korzysta w weryfikacji tożsamości klienta K przeprowadzonej wcześniej przez zaufany bank B.

Potencjalny problem legislacyjny: ustawa musi zapewnić, że korzystanie z wyników weryfikacji KYC, wykonanej wcześniej przez inny podmiot, jest tożsame z konwencjonalną weryfikacją KYC.

Rozszerzenie 1: wpisy na blockchainie potwierdzające stan faktycznyNa blockchainie dokonujemy wpisów stwierdzających stan faktyczny, który wynika z dokumentów istniejących w formie tradycyjnej, np:*Posiadacz klucza publicznego Y mieszka pod adresem A.**Posiadacz klucza publicznego Y ukończył uczelnię U.**Posiadacz klucza publicznego Y jest wspólnikiem w spółce S.*
Podobnie jak powyżej każdy wpis:1. Ma przypisaną datę kiedy został dokonany.2. Jest podpisany certyfikowanym podpisem elektronicznym notariusza N (czyli zamiast banku mamy notariusza albo jakąś inną instytucje zaufania publicznego). W ten sposób notariusz N gwarantuje prawdziwość informacji zawartej w tym wpisie. 
\3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych.
Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.
Użycie przez podmioty trzecie jest analogiczne jak wyżej opisany przypadek weryfikacji KYC, czyli firma F otrzymuje informacje od klienta K, hashuje je, a następnie weryfikuje ich prawdziwość poprzez porównanie z hashem tych informacji na blockchainie.
Korzyści: Migracja dokumentów istniejących w formie tradycyjnej do formy cyfrowej.
Rozszerzenie 2: wpisy na blockchainie o charakterze notarialnymNa blockchainie dokonujemy wpisów o charakterze notarialnym, tj. oświadczenia woli i umowy cywilne, np:*Posiadacz klucza publicznego Y udziela pełnomocnictwa posiadaczowi klucza publicznego Z.**Posiadacz klucza publicznego Y* sprzedaje udziały w spółce S *posiadaczowi klucza publicznego Z.* 
*Podobnie jak w wersji weryfikującej tożsamość każdy wpis:1. Ma przypisaną datę kiedy został dokonany.2. Jest podpisany certyfikowanym podpisem elektronicznym notariusza N. W ten sposób notariusz N gwarantuje prawdziwość informacji zawartej w tym wpisie. 3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych.Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.Użycie przez podmioty trzecie jest analogiczne jak wyżej opisany przypadek weryfikacji KYC, czyli firma F otrzymuje informacje od klienta K, hashuje je, a następnie weryfikuje ich prawdziwość poprzez porównanie z hashem tych informacji na blockchainie.Korzyści: Notariusz N może przyjąć oświadczenia woli on-line, tj. bez organizacji fizycznego spotkania z swoimi klientami. W tym celu weryfikuje on tożsamość klientów w podobny sposób jak firma F przeprowadza KYC, a następnie podpisuje swoim certyfikowanym podpisem elektronicznym oświadczenia woli swoich klientów.*