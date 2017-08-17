# What is EOS?

In a nutshell, EOS is the blockchain for building commercial scale decentralized applications that are indistinguishable from centralized alternatives.

# Why EOS?

Five reasons why choosing EOS makes sense:

#### 1. Ogromna wydajność

Podczas gdy inne rozwiązanie wymagają drugiej warstwy procesowania, aby być w stanie obsłużyć popyt na procesowanie transakcji w warunkach produkcyjnych (czyli odpowiednik Lightening Network w Bitcoinie albo Plasmy w Ethereum), EOS osiąga gigantyczną wydajność w swojej warstwie podstawowej. Wynika to z następujących powodów:

* DPOS daje stałą liczbę producentów bloków. Dzięki temu interwały między blokami są na poziomie 3 sekund (a przy lepszej infrastrukturze serwerowej mogą być jeszcze krótsze). Warto dodać że mimo tej skończonej liczby producentów bloków, DPOS jest najbardziej zdecentralizowanym systemem jaki istnieje - oczywiście jeśli zastosujemy racjonalnie uzasadnioną metodę pomiaru stopnia zdecentralizowania. [Tutaj](http://bytemaster.github.io/article/2015/01/13/Decentralization-of-Nxt-vs-BitShares/) jest to dokładniej wyjaśnione.
* Blockchain EOSa (podobnie jak BitShares i Steem) stosuje podejście *consensus over events* zamiast standardowego *consensus over state*. W wyniku tego wprawdzie dłużej trwa uruchomienie nowego node'a, ale w zamian szybciej działa bieżące procesowanie transakcji. Jest to bardzo korzystny trade-off, bo uruchamianie nowego node'a zdarza się rzadko, a wydajne procesowanie transakcji potrzebne jest non-stop. [Tutaj](https://steemit.com/eos/@iang/the-message-is-the-medium) jest to dokładniej wyjaśnione.
* Architektura EOSa od samego początku została tak zaprojektowana żeby możliwe było procesowanie wielowątkowe. Póki co żaden inny blockchain tego nie potrafi. Więcej szczegółów [tutaj](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#deterministic-parallel-execution-of-applications).
* EOS umożliwia procesowanie podzbioru transakcji, tj. tylko tych którymi dany node jest zainteresowany - tym samym możliwe jest ignorowanie wszystkich pozostałych transakcji. Więcej szczegółów [tutaj](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md#partial-evaluation-of-blockchain-state).

#### 2. Znacznie szerszy kontekst

EOS traktuje kwestię smart-kontraktów znacznie szerzej niż Ethereum. W założeniu EOSa błędy w kodzie smart-kontraktów są nieuniknione, więc zostały wbudowane w blockchain mechanizmy, które adresują ten problem: konstytucja, arbitraż w przypadku sporów, głosowanie w zakresie decyzji. Gdyby przypadek *The DAO* wydarzył się na EOSie, byłaby klarowna procedura rozwiązania tego problemu. Widać w tym dużą mądrość i dobre wyczucie potrzeb poważnych biznesów: posiadanie z góry zdefiniowanej drogi ewakuacyjnej w przypadku katastrofy jest fundamentalnie istotne.

#### 3. Kompletny system operacyjny

EOS pozycjonuje się nie jako rozproszony komputer lecz bardziej jako rozproszony system operacyjny. Oznacza to że na poziomie blockchaina dostępne są wszystkie funkcjonalności które są niezbędne dla każdej zaawansowanej aplikacji, np. databases, account permissions, account recovery, scheduling, authentication, inter-app communication. Czyli developerzy smart-kontraktów EOSa mają za zadanie zakodować tylko to co jest unikalne dla danej aplikacji, podczas gdy cała reszta jest dostarczona na poziomie samego blockchaina.

#### 4. Brak opłat transakcyjnych (z punktu widzenia użytkownika końcowego)

EOS wychodzi z założenia, że najważniejszym kryterium są wymagania biznesowe a nie ograniczenia technologii. Z punktu widzenia biznesu nie ma racji bytu paradygmat, w którym użytkownik końcowy jest zmuszony do płacenia za sam fakt interakcji z daną aplikacją, tak jak jest to teraz standardem w świecie kryptowalut. Aplikacja taka jak Steem nie mogłaby istnieć w takim modelu. EOS proponuje rozwiązanie, które powszechnie funkcjonuje w normalnym świecie: problem finansowania danego biznesu jest po stronie dawcy usługi (tj. twórcy smart-kontraktu) a nie po stronie jego klienta - ten defaultowo powinien mieć dostęp darmowy (no chyba że twórca smart-kontraktu postanowi inaczej - ważne jest żeby był możliwy wybór dowolnej strategii).

#### 5. Koncepcja zweryfikowana w praktyce

Wszystkie inne niż EOS platformy smart-kontraktowe są budowane jako rozwiązanie generyczne. Czyli zaczynamy od abstrakcji a celem jest zbudowanie przestrzeni do implementacji konkretnych aplikacji. EOS idzie w odwrotnym kierunku: od implementacji do abstrakcji. Twórcy EOSa mają w swoim dorobku dwa działające blockchainy (BitShares i Steem), które w sumie procesują więcej transakcji niż Bitcoin i Ethereum. Tym samym EOS jest uogólnieniem dwóch konkretnych (i bardzo różnych) implementacji. Daje to duże prawdopodobieństwo, że EOS będzie czymś co rzeczywiście sprawdza się w praktyce.

# Known limitations

While we are not hinding our strong commtiment for EOS, stil we aim to remain objective. Below are there are things you need to be aware of:

* When compared to Ethereum, at the current stage EOS is not widely popular among developers and blochchain start-ups. There is still a lot that needs to be done in this area in order to raise awareness and atract businesses to experiment with EOS. 
* EOS is not live yet. The testnet is about to be launched, and the ETA for live version is June 2018.

Odnośnie terminu live, informację tę warto interpretować następująco: Steem powstał z kodu BitShares w ciągu 3 miesięcy, co oznacza że zespół deweloperów EOSa działa bardzo sprawnie. Długi okres testów EOSa sugeruje że priorytetem jest jakość i że w momencie pójścia live EOS prawdopodobnie będzie bardzo zaawansowanym i stabilnym systemem. 

# Current status

The testnet is about to be launched, and the ETA for live version is June 2018.

# News



# Roadmap

##### Phase 1 - Minimal Viable Testing Environment - Summer 2017

- Standalone Node
- Native Contracts
- RPC Interface
- Command line Tools
- Basic Developer Documentation

##### Phase 2 - Minimal Viable Test Network - Fall 2017

- P2P Network Code
- WASM Sanitation & CPU Sandboxing
- Resource Usage Tracking & Rate Limiting
- Genesis Import Testing
- Interblockchain Communication

##### Phase 3 - Testing & Security Audits - Winter 2017, Spring 2018

- Develop Example Applications
- Bounties for Successfully Attacking Network
- Language Support
- Documentation & Tutorials

##### Phase 4 - Parallel Optimization - Summer / Fall 2018

##### Phase 5 - Cluster Implementation - The Future

<span style="color:silver;font-size:11px">Source: [github.com](https://github.com/EOSIO/Documentation/blob/master/Roadmap.md), June 2017</span>

# Executive summaries



# Buissness blog



# Developer blog



# EOS tools



# About us



# Contact

