# DIV - Decentralized Identity Verification (Zdecentralizowana Weryfikacja Tożsamości)

## Wprowadzenie

Najogólniej mówiąc, w problemie weryfikacji tożsamości chodzi o to, w jaki sposób w warunkach online uzyskać pewność, że osoba (klient) podająca się jako K rzeczywiście jest tą osobą K.

Istotne jest tu to, że jest to sytuacja online, czyli NIE w realu. W sytuacji kontaktu w realu dokument ze zdjęciem wciąż można uznać za wystarczająco dobry sposób weryfikacji tożsamości, mimo swoich oczywistych wad: jest kosztowny w produkcji i fałszowalny - wszystko wisi na założeniu, że umiesz rozpoznać fałszywy dokument, co często nie jest prawdą (np. kto z nas wie jak powinna wyglądać odznaka policyjna?).

Znacznie większy problem pojawia się online, bo tutaj zdjęcie, które jest integralną częścią dokumentu tożsamości, przestaje być użyteczne, bo nie ma go z czym porównać.

Tradycyjne podejścia w sytuacji online są mniej więcej takie:

- Jesteś wypytywany o jakiś sekret (np. nazwisko panieńskie matki). Wada: tego rodzaju sekret dość łatwo się dewaluuje.
- Dostajesz esemesa z kodem. Wada: jest to relatywnie kosztowne i mało bezpieczne.
- Werifikujesz się poprzez narzędzie typu Google Authenticator. Wada: sekret w postaci klucza prywatnego jest współdzielony, więc teoretycznie może być wykradziony z firmy która cię weryfikuje.

Poza względami bezpieczeństwa, główny problem z tego rodzaju podejściem jest taki, że to się nie skaluje, bo przy pozyskaniu nowego klienta każda firma musi samodzielnie dokonać ustalenia jego tożsamości i zainicjować proces werfikacji tej tożsamości w przyszłości. Czyli ten sam kosztowny i czasochłonny proces jest wykonywany wielokrotnie przez różne firmy.

---

DIV (Decentralized Identity Verification) generalnie polega na tym, że informacja, która jednoznacznie identyfikuje osobę (klienta) K (np. jej PESEL), jest trzymana tylko przez tę osobę K (np. kryptograficznie zaszyfrowana w jej telefonie komórkowym), a firma F, która chce zweryfikować osobę K online, komunikuje się z jej telefonem, i ten telefon (za zgodą osoby K) wysyła podmiotowi F żądaną informację służącą do identyfikacji (czyli w tym przypadku PESEL).

Oczywiście gdybyśmy poprzestali tylko na tym co powyżej, to firma F nigdy nie mogłaby być pewna, że osoba, która próbuje się zidentyfikować jako K, rzeczywiście jest osobą K.

I tutaj pojawia się idealne pole do działania dla blockchaina.

Załóżmy, że osoba K chce skorzystać z jakiejś usługi oferowanej przez firmę F i w tym celu musi podać i uwiarygodnić firmie F swoją tożsamość.

Załóżmy też że:

- PESEL osoby K został w przeszłości zweryfikowany przez podmiot o wysokiej reputacji (któremu firma F ufa).
- Hash tego PESELa wraz z kluczem publicznym osoby K i podpisem powyższego podmiotu o wyskiej reputacji został umieszczony na blockchainie. To jest ważne: ten PESEL na blockchainie jest zahashowany, więc nie sposób odgadnąć jaki on jest.

Wówczas poprzez spojrzenie na zapis w blockchainie firma F jest w stanie stwierdzić, że osoba która przesłała jej PESEL osoby K, jednocześnie musi być osobą K. Wynika to z faktu, że tylko osoba K ma dostęp do klucza prywatnego, który pasuje do klucza publicznego w zapisie na blockchainie potwierdzającym wcześniej dokonaną weryfikację tego PESELa.

Innymi słowy, ten mechanizm pozwala na weryfikację danej osoby w warunkach online w analogiczny sposób jak czyni to dokument ze zdjęciem w realu. A nawet lepiej, bo dokument ze zdjęciem jest fałszowalny, a tego rodzaju cyfrowa weryfikacja jest chroniona kryptograficznie.

Czyli mamy mechanizm, który jest w stanie poświadczyć, że mówisz prawdę na temat siebie samego. Co ciekawe, tym samym traci sens wykradanie informacji celem kradzieży tożsamości, bo sama informacja nie wystarczy. Żeby być zweryfikowanym w tym nowym paradygmacie, oprócz samej informacji trzeba jeszcze mieć związany z tą informacją klucz prywatny poświadczony przez podmiot o wysokiej reputacji. Samo wyłudzenie od kogoś informacji nic nie daje.

Co więcej, DIV radykalnie obniża koszty, bo eliminuje problem powtarzalności procesu ustalania tożsamości nowego klienta. W tym nowym paradygmacie proces ten wykonywany jest raz, jego wynik zapisany jest na blockchainie i wszystkie pozostałe firmy mogą z tego zapisu skorzystać (bezpłatnie albo odpłatnie - ale to jest już problem monetyzacji, o czym poniżej).

---

Patrząc od strony samej koncepcji można powiedzieć, że DIV robi z informacją to co kryptowaluty robią z pieniądzem - informacja dotycząca danej osoby (w tym także informacja która ją w jednoznaczny sposób identyfikuje, np. PESEL) jest chroniona kluczem prywatnym, czyli traktowana podobnie jak kryptowaluta.

Oczywiście trzeba pamiętać, że w paradygmacie DIV informacja jest zawsze po stronie użytkownika - on jest jej strażnikiem. Więc wymaga to dbałości o backup klucza prywatnego na jakimś trwałym nośniku. Ale nie jest to aż tak krytyczne jak w przypadku pieniądza - tutaj zgubienie/kradzież klucza oznacza podobne zamieszanie co zgubienie tradcyjnych dokumentów (tj. da się to odtworzyć i też zablokować możliwość posługiwania się skradzionym kluczem).

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

Na pewno potrzebne będzie partnerstwo z jakąś większą instytucją finansową, np. bankiem. Każdy bank ma zweryfikowana tożsamość (w tym numer PESEL) każdego swojego klienta. Załóżmy, że jakiś bank uznałby, że nasz system nadaje się jako jego jeden z dwóch alternatywnych kanałów mocnej autoryzacji w PSD2 i zaleca swoim klientom użycie naszej aplikacji mobilnej do tego celu.

Co się wtedy dzieje?

Wtedy z automatu taki bank wprowadza nam do systemu tysiące swoich klientów i on sam staje się notariuszem, który poświadcza autentyczność PESELi swoich klientów na blockchainie EOSa.

Podsumowując: partner bankowy dostaje od nas system mocnej autoryzacji za darmo, a w zmian zasila nasz system dużą liczbą użytkowników.

#### Do przemyślenia

Procedura odzyskiwania zgubionego / skradzionego klucza prywatnego. Na pewno warto będzie tu wykorzystać możliwości EOSa w z tym zakresie.

## Rozszerzenie 1: Wpisy na blockchainie służące weryfikacji tożsamości

#### Proces

Na blockchainie dokonujemy wpisów potwierdzających tożsamość, np:

- *Posiadacz klucza publicznego Y ma PESEL 123456789*
- *Posiadacz klucza publicznego Y nazywa się Imię Nazwisko.*

Każdy wpis:

1. Ma przypisaną datę kiedy został dokonany.
2. Jest podpisany certyfikowanym podpisem elektronicznym banku B. W ten sposób bank B gwarantuje prawdziwość informacji zawartej w tym wpisie. 
3. Jest w postaci zahashowanej, tj. nieczytelnej dla osób trzecich. W ten sposób unikamy problemu z ochroną danych osobowych.

Te same informacje (bez hashowania) zostają umieszczone w aplikacji mobilnej klienta K.

W jaki sposób ten blockchainowy wpis może być użyty przez inne firmy do weryfikacji tożsamości swoich klientów w warunkach on-line?

Załóżmy, że firma F:

- potrzebuje dokonać weryfikacji KYC klienta K,
- ma zaufanie do banku B, tj. podpisane elektronicznie oświadczenia banku B w zakresie klienta K uznaje za prawdziwe.

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

- *Posiadacz klucza publicznego Y mieszka pod adresem A.*
- *Posiadacz klucza publicznego Y ukończył uczelnię U.*
- *Posiadacz klucza publicznego Y jest wspólnikiem w spółce S.*

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

- *Posiadacz klucza publicznego Y udziela pełnomocnictwa w zakresie reprezentowania spółki S posiadaczowi klucza publicznego Z.*
- *Posiadacz klucza publicznego Y sprzedaje udziały w spółce S posiadaczowi klucza publicznego Z.*

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

Taki smart-kontrakt wymaga jeszcze przemyślenia. Jego istotą byłoby pobieranie opłaty od firmy F (albo klienta K) na rzecz banku B (albo innej instytucji, która dokonała weryfikacji klienta K) za każdym razem gdy firma F korzysta z tego zapisu.

Głównym celem tego rodzaju opłat jest dobre zmotywowanie uczestników tego systemu, tak żeby korzyści finasowe miał ten podmiot, który popełnia wysiłek, a koszty ponosił ten podmiot, który ma korzyści. Dodanie do tego minimalnej marży dla nas (jako twórców tego smart-kontraktu) będzie relatywnie proste.

## Własny token?

Nasuwa się pytanie o możliwość wprowadzenia własnego tokenu do przeprowadzania powyższych rozliczeń między uczestnikami systemu. Ma to niewątpliwą zaletę w postaci możliwości przeprowadzenia ICO dla takiego tokenu. Wadą jest fakt, źe własny token oznacza, aby móc użyć systemu trzeba najpierw w niego zainwestować, co jest istotną barierą wejścia. Tym tropem idzie Civic.

Moim zdaniem lepiej jest uniknąć tego rodzaju rozwiązania i opłaty realizować w jakieś niezależnej stabilnej walucie, która zapewne powstanie na EOSie.

## Kontekst

Jest [masa projektów blockchainowych](https://github.com/peacekeeper/blockchain-identity), które podejmują rożne aspekty cyfrowej tożsamości. Najważniejsze to te dwa:

- Civic
  - Web: https://www.civic.com/
  - Whitepaper: https://tokensale.civic.com/CivicTokenSaleWhitePaper.pdf
- Decentralized Identity
  - Web: https://decentralized.id/
  - Whitepaper (biznesowy): https://decentralized.id/docs/DID-whitepaper.pdf
  - Whitepaper (techniczny): https://decentralized.id/docs/DID-tech.pdf

[Tutaj](https://www.scottbrady91.com/Blockchain-Identity/Technical-Review-of-Civics-Secure-Identity-Platform) jest dość wiarygodna recenzja Civica

Jest ona całkiem pozytywna, główny zarzut sprowadza się do krytyki odstąpienia od używania standardów na rzecz swoich własnych wynalazków:

> Civic really should have used OAuth and OpenID Connect, instead of rolling their own authentication protocol.

Czyli pomysł jest oceniany jako bardzo dobry, ale wykonanie jako dość niefortunne. Dodatkowo Civic bazuje na [RootStock](https://www.rsk.co/), czyli będzie się zmagał ze wszystkimi problemami jakie ma w sobie Bitcoin.

W przypadku projektu Decentralized Identity, też jest ciekawa sytuacja, bo wygląda na to, że oni doszli do ściany w zakresie możliwości Ethereum:

> We found Ethereum smart contracts unfit for computations that go beyond than the basics. While we understand that the technology is just growing up, we found that not being able to do computations (like hashing) on the Blockchain is a major drawback. The global computational power isn’t available for Dapps yet.

Ta deklaracja też jest intrygująca:

> At the time of writing, there exists no blockchain that is truly public and stateless. All current blockchain technologies intend to store data. We just want to store the receipt of an ID transfer; not the data. In the matter of transferring an ID token/nugget, we only require a decentralised transfer of data. The data structures used by current blockchain technologies is restrictive and do not allow for expansion or abstraction. We call for a new, stateless, public Blockchain.

W tym świetle wykonanie uproszczonej (tylko PESEL) wersji DIV, ma spory sens ponieważ:

- Działamy w cieniu firm dużo większych od nas (np. Civic, Decentralized Identity) - one już odwaliły sporo roboty za nas i dodatkowo uwiarygadniają sensowność tego całego przedsięwzięcia.
- Mamy precyzyjną specyfikację (ich kod źródłowy) i relatywnie małe zadanie (bo robimy tylko PESEL), więc dokładnie wiadomo co trzeba robić (nie tracimy czasu i kasy na eksperymentowanie).
- Mamy technologię (tj. EOS) która jest wyraźnie lepsza od tej, którą oni wybrali, i dodatkowo jest pozbawiona istotnych ograniczeń (np. opłaty transakcyjne, procedura odzyskiwania skradzionego/zgubionego klucza prywatnego).
- Tego rodzaju tematy jak cyfrowa tożsamość mają specyfikę lokalną, więc nasze położenie geograficzne daje nam przewagę w tym rejonie Europy. Możemy też podpatrzyć z kim Civic zawarł aliense biznesowe w USA i zrobić podobne układy lokalnie.
- Budujemy mechanizm, który będzie doskonałą alternatywą dla tradycyjnych rozwiązań w zakresie Strong Customer Athetication (SCA) w kontekście PSD2 

