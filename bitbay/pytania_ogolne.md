##  Pytania ogólne

#### 1. Jaka jest logiczna struktura waluty? Jak jest ona zbudowana?

Waluta EOS jest natywnym tokenem na blockchainie EOS. Patrząc z perspektywy technicznej nie jest ona wbudowana w kod zródłowy blockchaina, a jest jedynie smart-kontraktem na tym blockchainie - ale z punktu widzenia użytkownika nie ma to większego znaczenia.

W [tym dokumencie](https://github.com/EOSIO/eos/wiki/Local-Environment#1-getting-the-code) opisano proces kompilacji i instalacji:

* programu egzekucyjnego `nodeos`, którego instancje tworzą sieć EOSa (tzw. full-node)
* programu egzekucyjnego `cleos`, za pomocą którego można się komunikować z działającym full-nodem.

**UWAGA:** Blockchain EOS nie jeszcze jest live, najprawdopodobniej ruszy live w pierwszym tygodniu czerwca. To co mamy do dyspozycji w tej chwili to jedynie [testnet](https://github.com/EOSIO/eos/blob/master/testnet.md).

#### 2. Czy Wasza waluta bazuje na jakiejś innej, istniejącej? Czy dzieli swoje API z inną walutą?

EOS nie bazuje na żadnej istniejącej walucie i nie dzieli API z niczym istniejącym.

#### 3. Posiadamy giełdę kryptowalut oraz procesor płatności. Chcielibyśmy zintegrować walutę docelowo z obiema usługami. Czy macie jakieś sugestie, w jaki sposób powinniśmy używać waluty w zależności od typu usługi?

*Żeby móc lepiej zrozumieć istotę tego pytania potrzebowalibyśmy przykładu z innych powszechnie znanych walut, np. Bitcoin albo Ethereum. W jaki sposób różnicujecie użycie blockchaina Bitcoina albo Ethereum w tych dwóch typach usług?*

#### 4. Czy macie listę dobrych praktyk w kwestii integracji portfela Waszej waluty do obsługi wpłat i wypłat?

<https://github.com/EOSIO/eos/blob/slim/EXCHANGE_README.md#exchange-security>

#### 5. Zakładając, że mielibyśmy 10 mln użytkowników, ile instancji portfeli rekomendowalibyście nam do użycia? Czy powinniśmy według Was podzielić je w zależności od zadań (np. 1 do generowania adresów, drugi do obsługi wpłat, trzeci do wypłat)?

Rekomendujemy dwie instancje. Szczegóły omówimy na callu.

#### 6. Jakie parametry są rekomendowane w trakcie instalacji i późniejszego użytkowania portfela?

<https://github.com/EOSIO/eos/blob/slim/EXCHANGE_README.md#configuring-nodeos>

#### 7. Jakie wymagania sprzętowe stawia Wasz portfel?

32GB RAM, 2x vCPU, szybki lokalny storage.

#### 8. W jaki sposób odpowiednio tworzyć kopie zapasowe oraz odzyskiwać portfel?

Rekomendujemy standardowe rozwiązania w tym zakresie.

#### 9. Czy posiadacie jakieś znane ograniczenia lub problemy o których powinniśmy wiedzieć?

To co jest niestandardowe w EOSie (podobnie jak w BitShares i Steemie) to fakt, że konta mają nazwy literowe i nie można w łatwy i bezkosztowy sposób ich tworzyć. Oznacza to, że w przeciwieństwie do innych kryptowalut zalecanym rozwiązaniem jest prowadzenie przez giełdę pojedynczego konta, na które przyjmuje ona depozyty, a rozróżnianie pomiędzy rożnymi ich źródłami następuje poprzez pole `memo`, które jest związane z danym transferem i które użytkownik powinien wypełnić wpisując (jako jeden z parametrów transferu) podany przez giełdę unikalny ciąg znaków.

Drugą niestandardową właściwością EOSa jest brak opłat transakcyjnych. W zamian EOS stosuje tzw. rate-limiting, czyli do realizacji transakcji na blockchainie potrzebne jest posiadanie minimalnej liczby tokenów, a im intensywniej chcemy korzystać z blockchaina, tym więcej tych tokenów trzeba mieć. Trudno jest to w tej chwili dokładnie oszacować, ale można spokojnie przyjąć, że posiadanie tokenów EOSa o równowartości tysiąca USD powinno w zupełności wystarczyć do robienia transferów z częstotliwością jeden na sekundę. 

#### 10. W jaki sposób najlepiej zabezpieczyć portfel? Jakie zabezpieczenia według Was powinniśmy wdrożyć?

<https://github.com/EOSIO/eos/blob/slim/EXCHANGE_README.md#exchange-security>

#### 11. Czy posiadacie jakieś zamknięte miejsce, w którym moglibyśmy dowiedzieć się o ważnych aktualnościach związanych z walutą (nowe błędy, problemy, plany, usprawnienia)? Jeśli tak, to czy moglibyśmy uzyskać dostęp do tych zasobów?

Ponieważ blockchain nie jest jeszcze live, nie ma jeszcze takiego miejsca. Będziemy informować, gdy ono powstanie.

#### 12. Czy Wasza waluta obsługuje wysyłanie powiadomień o transakcjach przychodzących na adres URL (webhook)? 

Według naszej obecnej wiedzy nie ma tego rodzaju mechanizmu, ale jeszcze to potwierdzimy. Ponieważ bloki na EOSie są generowane w odstępie 500 ms prawdopodobnie tego rodzaju powiadomienia nie będą potrzebne. Zalecanym rozwiązaniem jest regularny "polling" full node'a EOSa, tj. programu `nodeos`.

#### 13. Ile potwierdzeń powinniśmy wymagać do akceptowania wpłat w bezpieczny sposób?

<https://github.com/EOSIO/eos/blob/slim/EXCHANGE_README.md#accepting-deposits>

#### 14. Czy miały miejsce próby ataków na sieć Waszej waluty? Udało się je odeprzeć? W jaki sposób?

Nie dotyczy ponieważ blockchain nie jest jeszcze live.

#### 15. Czy w najbliższym czasie planujecie jakieś istotne aktualizacje protokołu?

W ostatnim czasie aktualizacje występują prawie non-stop, ale spodziewamy się, że w momencie gdy zakończy się ICO (czyli po 02/06) i blockchain ruszy live, przez dłuższy czas nie będzie dalszych aktualizacji, poza tymi które będą wymuszone przez niespodziewane błędy w kodzie.

## Dodatkowe pytania

#### 15. W jaki sposób przyznawane będą środki dla klientów, którzy posiadali Wasze tokeny? 

???

#### 16. Słyszeliśmy o problemach związanych ze stabilnością nowej sieci (powstawanie wielu odłamów łańcuchów) - czy faktycznie obecnie jest z tym problem? Macie jakiś plan jak je rozwiązać?

Systemy będące prekursorami EOSa (tj. BitShares i Steem) nigdy nie doświadczyły niezamierzonego forku (tj. wszystkie forki jakie się wydarzyły były celowym upgradem systemu). Mechanizm konsensusu EOSa jest bardzo odporny na tego rodzaju problemy.

Może natomiast nastąpić sytuacja, że ruszy więcej niż jeden blockchain zbudowany z tego samego kodu źródłowego. Jednak firma będąca autorem kodu EOSa (i organizatorem ICO) otwarcie zapowiedziała, że wesprze tylko jeden z tych blockchainów, więc tylko jeden z nich uznany zostanie za "oficjalny".