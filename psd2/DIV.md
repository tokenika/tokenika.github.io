## DIV - Decentralized Identity Verification (Zdecentralizowana Weryfikacja Tożsamości)

Najogólniej mówiąc, w problemie weryfikacji tożsamości chodzi o to, w jaki sposób w warunkach online uzyskać pewność, że osoba podająca się jako X rzeczywiście jest tą osobą X.

Istotne jest tu to, że jest to sytuacja online, czyli NIE w realu. W sytuacji kontaktu w realu dokument ze zdjęciem, wciąż można uznać za wystarczająco dobry sposób weryfikacji tożsamości, mimo swoich oczywistych wad: jest kosztowny w produkcji i fałszowalny - wszystko wisi na założeniu, że umiesz rozpoznać fałszywy dokument, co często nie jest prawdą.

Znacznie większy problem pojawia się online, bo tutaj zdjęcie, które jest integralną częścią dokumentu tożsamości, przestaje być użyteczne, bo nie ma go z czym porównać.

Tradycyjne podejścia w sytuacji online są mniej więcej takie:

- Jesteś wypytywany o jakiś sekret (np. nazwisko panieńskie matki). Wada: tego rodzaju sekret dość łatwo się dewaluuje.
- Dostajesz ememesa z kodem. Wada: jest to relatywnie kosztowne i mało bezpieczne.
- Werifikujesz się poprzez narzędzie typu Google Authenticator. Wada: sekret w postaci klucza prywatnego jest współdzielony, więc teoretycznie może być wykradziony z firmy która cię weryfikuje.

Poza względami bezpieczeństwa, główny problem z tego rodzaju podejściem jest taki, że to się nie skaluje, bo przy pozyskaniu nowego klienta każda firma musi samodzielnie dokonać ustalenia jego tożsamości i zainicjować proces werfikacji tej tożsamości w przyszłości. Czyli ten sam kosztowny i czasochłonny proces jest wykonywany wielokrotnie przez różne firmy.

---

DIV (Decentralized Identity Verification) generalnie polega na tym, że informacja, która jednoznacznie identyfikuje osobę X (np. jej PESEL), jest trzymana tylko przez tę osobę X (np. kryptograficznie zaszyfrowana w jej telefonie komórkowym), a firma F, która chce zweryfikować osobę X online, komunikuje się z jej telefonem, i ten telefon (za zgodą osoby X) wysyła podmiotowi F żądaną informację służącą do identyfikacji (czyli w tym przypadku PESEL).

Oczywiście gdybyśmy poprzestali tylko na tym co powyżej, to firma F nigdy nie mogłaby być pewna, że osoba, która próbuje się zidentyfikować jako X, rzeczywiście jest osobą X.

I tutaj pojawia się idealne pole do działania dla blockchaina.

Załóżmy, że osoba X chce skorzystać z jakiejś usługi oferowanej przez firmę F i w tym celu musi podać i uwiarygodnić firmie F swoją tożsamość.

Załóżmy też że:

- PESEL osoby X został w przeszłości zweryfikowany przez podmiot o wysokiej reputacji (któremu firma F ufa).
- Hash tego PESELa wraz z kluczem publicznym osoby X został umieszczony na blockchainie (to jest ważne: ten PESEL na blockchainie jest zahashowany, więc nie sposób odgadnąć jaki on jest).

Wówczas poprzez spojrzenie na zapis w blockchainie firma F jest w stanie stwierdzić, że osoba która przesłała jej PESEL osoby X, jednocześnie musi być osobą X. Wynika to z faktu, że tylko osoba X ma dostęp do klucza prywatnego, który pasuje do klucza publicznego w zapisie na blockchainie potwierdzającym wcześniej dokonaną weryfikację tego PESELa.

Innymi słowy, ten mechanizm pozwala na weryfikację danej osoby w warunkach online w analogiczny sposób jak dokument ze zdjęciem robi to w realu. A nawet lepiej, bo dokument ze zdjęciem jest fałszowalny, a tego rodzaju cyfrowa weryfikacja jest chroniona kryptograficznie.

Czyli mamy mechanizm, który jest w stanie poświadczyć, że mówisz prawdę na temat siebie samego. Co ciekawe, tym samym traci sens wykradanie informacji celem kradzieży tożsamości, bo sama informacja nie wystarczy - żeby być zweryfikowanym w tym nowym paradygmacie, oprócz samej informacji trzeba jeszcze mieć związany z tą informacją klucz prywatny poświadczony przez podmiot o wysokiej reputacji. Samo wyłudzenie od kogoś informacji nic nie daje - czyli dokładanie na odwrót niż obecnym świecie.

Co więcej, DIV eliminuje problem powtarzalności procesu ustalania tożsamości nowego klienta. W tym nowym paradygmacie proces ten wykonywany jest raz, jego wynik zapisany jest na blockchainie i wszystkie pozostałe firmy mogą z tego zapisu skorzystać (bezpłatnie albo odpłatnie - ale to jest już problem monetyzacji, o czym poniżej).

---

Idąc tym tropem, powyższy mechanizm można też zastosować dla innych niż PESEL informacji (np. dokumenty typu prawo jazdy, polisa OC, dyplom uczelni itd), ale na razie proponowałbym w to nie wchodzić, bo wówczas mamy dodatkową komplikację - problem aktualności tych informacji. PESEL ma tę zaletę, że nigdy nie traci ważności i jednoznacznie identyfikuje każdego człowieka.

Więc wykorzystując mechanizm DIV w jego najprostszej formie (czyli tylko PESEL) dostajemy narzędzie które:

- Doskonale nadaje się jako jeden z kanałów w mocnej autoryzacji dla PSD2, co było naszym pierwotnym celem.
- Istotnie wspomaga systemy online, w których szybka i niezawodna weryfikacja tożsamości jest konieczna i dodatkowo uwalnia te systemy od potrzeby przechowywania sporej części danych osobowych (bo w tym nowym paradygmacie te dane zawsze są po stronie użytkownika).
- Otwiera możliwość migracji do wersji online rzeczy, które do tej pory były praktycznie niewykonalne w wersji online, np. wybory parlamentarne.

A w wersji rozszerzonej (czyli nie tylko PESEL) mechanizm ten otwiera możliwość ostatecznej cyfryzacji wszystkiego: wszystkie dokumenty państwowe, dokumentacja medyczna, cała branża notarialna, itp.

No i oczywiście tożsamość cyfrowa otwiera drogę do reputacji cyfrowej, bo czasem ważniejsze jest to jaką masz przeszłość, niż to kim dokładnie jesteś, a ten sam klucz prywatny może chronić obie te rzeczy jednocześnie.

---

Patrząc od strony samej koncepcji można powiedzieć, że DIV robi z informacją to co kryptowaluty robią z pieniądzem - informacja dotycząca danej osoby (w tym także informacja która ją w jednoznaczny sposób identyfikuje, np. PESEL) jest chroniona kluczem prywatnym, czyli traktowana podobnie jak kryptowaluta.

Oczywiście trzeba pamiętać, że w paradygmacie DIV informacja jest zawsze po stronie użytkownika - on jest jej strażnikiem. Więc wymaga to dbałości o backup klucza prywatnego na jakimś trwałym nośniku. Ale nie jest to aż tak krytyczne jak w przypadku pieniądza - tutaj zgubienie/kradzież klucza oznacza podobne zamieszanie co zgubienie tradcyjnych dokumentów (tj. da się to odtworzyć i też zablokować możliwość posługiwania się skradzionym kluczem).

---

Jest [masa projektów blockchainowych](https://github.com/peacekeeper/blockchain-identity), które podejmują rożne aspekty cyfrowej tożsamości. Warto je kiedyś wszystkie przejrzeć (zadanie dla Wojtka?) jednak na tym etapie możemy ograniczyć się do tych najważniejszych (moim zdaniem), które zajmują się dokładnie tym co nas interesuje, tj. stricte DIV:

* Civic
  * Web: https://www.civic.com/
  * Whitepaper: https://tokensale.civic.com/CivicTokenSaleWhitePaper.pdf
* Decentralized Identity (DID)
  * Web: https://decentralized.id/
  * Whitepaper (biznesowy): https://decentralized.id/docs/DID-whitepaper.pdf
  * Whitepaper (techniczny): https://decentralized.id/docs/DID-tech.pdf

---

Tu jest dość wiarygodna recenzja Civica:

<https://www.scottbrady91.com/Blockchain-Identity/Technical-Review-of-Civics-Secure-Identity-Platform>

Jest ona całkiem pozytywna, główny zarzut sprowadza się do krytyki odstąpienia od używania standardów na rzecz swoich własnych wynalazków:

> Civic really should have used OAuth and OpenID Connect, instead of rolling their own authentication protocol.

Czyli pomysł jest oceniany jako bardzo dobry, ale wykonanie jako dość niefortunne. Dodatkowo Civic bazuje na [RootStock](https://www.rsk.co/), czyli będzie się zmagał ze wszystkimi problemami jakie ma w sobie Bitcoin.

---

W przypadku projektu Decentralized Identity (DID), też jest ciekawa sytuacja, bo wygląda na to, że oni doszli do ściany w zakresie możliwości Ethereum:

> We found Ethereum smart contracts unfit for computations that go beyond than the basics. While we understand that the technology is just growing up, we found that not being able to do computations (like hashing) on the Blockchain is a major drawback. The global computational power isn’t available for Dapps yet.

Ta deklaracja też jest intrygująca:

> At the time of writing, there exists no blockchain that is truly public and stateless. All current blockchain technologies intend to store data. We just want to store the receipt of an ID transfer; not the data. In the matter of transferring an ID token/nugget, we only require a decentralised transfer of data. The data structures used by current blockchain technologies is restrictive and do not allow for expansion or abstraction. We call for a new, stateless, public Blockchain.

---

W tym świetle wykonanie uproszczonej (tylko PESEL) wersji DIV, ma spory sens ponieważ:

- Działamy w cieniu firm dużo większych od nas - one już odwaliły sporo roboty za nas i dodatkowo uwiarygadniają sensowność tego całego przedsięwzięcia.
- Mamy precyzyjną specyfikację (ich kod źródłowy) i relatywnie małe zadanie (bo robimy tylko PESEL), więc dokładnie wiadomo co trzeba robić (nie tracimy czasu i kasy na eksperymentowanie).
- Mamy technologię (tj. EOS) która jest wyraźnie lepsza od tej, którą oni wybrali, i dodatkowo jest pozbawiona istotnych ograniczeń (np. opłaty transakcyjne, procedura odzyskiwania skradzionego/zgubionego klucza prywatnego).
- Tego rodzaju tematy jak cyfrowa tożsamość mają specyfikę lokalną, więc nasze położenie geograficzne daje nam przewagę w tym rejonie Europy.
- Budujemy mechanizm, który będzie doskonałą alternatywą dla tradycyjnych rozwiązań w zakresie Strong Customer Athetication (SCA) w kontekście PSD2 

---

Celowo pomijam na tym etapie problem monetyzacji tego całego zagadnienia. Wychodzę tu z założenia, że pierwszym problemem, który trzeba rozwiązać, to zdobycie dużej liczby użytkowników (zarówno po stronie osób fizycznych jak i firm), a w momencie, gdy to nastąpi, dopiero będzie można myśleć o monetyzacji. 

Monetyzacja jest na pewno wykonalna, bo na tym bazuje Civic.

---

Proponowany plan działania:

- Zrobić MVP (łącznie z aplikacją mobilną).

- Zebrać duży kapitał i błogosławieństwo aparatu państwowego.

Tutaj akurat ICO miałoby duży sens, bo potrzebne jest maksymalnie dużo rozgłosu i dużo kapitału, który trzeba rozdać użytkownikom żeby bootstrapować tego rodzaju system. To jest machina, którą trudno uruchomić, ale jak to się uda to reszta dzieje się sama.

Wtedy można zastosować strategię PayPala: rozdawać tokeny (swoje własne lub EOSa, np. równowartość kilku USD) w zamian za poddanie się procesowi ucyfrowienia swojego PESELa w naszym systemie DIV. Będzie to kosztowne ale przynajmniej pozbawione przekrętów, bo z automatu mamy pewność, że jedna osoba tylko raz może się zarejestrować i pobrać przysługujące jej tokeny.

To co niewątpliwie ułatwia sprawę w zakresie zebrania kapitału to fakt, że temat DIV dość mocno przemawia do wyobraźni, bo każdy z nas czuje jak anachroniczny jest obecny system przepytywania o nazwisko panieńskie matki albo urzędowe pieczątki na papierze.

Mi się wydaje, że DIV raczej na pewno będzie w przyszłości standardem - jego zalety są niezaprzeczalne. Pytanie jest tylko kto to zrobi i kiedy.