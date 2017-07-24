## Tezos to zdecentralizowana platforma smart-kontraktowa z formalnie weryfikowalnym językiem programowania i ze zintegrowanym systemem samorządności. 

Najlepiej zacząć od [krótkiej prezentacji promocyjnej Tezosa](https://www.youtube.com/watch?v=7m7EU4JWI88), dostępnej na YouTubie.

Tezos jest niezależny od innych blockchainów, a jego kod źródłowy zbudowano od zera (czyli nie jest to klon innego projektu). Do tworzenia kontraktów wymagane jest użycie specjalnego języka skryptowego (odpowiednik języka *Solidity* na ETH).

Czym się Tezos chce wyróżnić? Mamy trzy główne aspekty:
- Sformalizowany system samorządności
- Sformalizowany system weryfikacji smart-kontraktów
- Modułowa architektura

#### Sformalizowany system samorządności

> Unlike other smart contract platforms, Tezos has a formal governance mechanism on the blockchain itself.

Rzeczywiście, kwestia sprawności podejmowania decyzji (tzw. *governance issue*) jest mocno zaniedbana w świecie blockchainowym, choć jest ona krytycznie ważna. Chodzi tu o dwojakiego typu sytuacje:
- decyzje strategiczne (tj. istotna zmiana w protokole, np. znany spór wielkość bloku w BTC, albo zapowiadane przejście z POW do POS w przypadku ETH)
- obsługa nietypowych wydarzeń (np. słynne fiasko *The DAO* na ETH).

W tej chwili jedynie blockchainy oparte na DPOS (Delegated Proof of Stake), mają powyższy problem w miarę zaadresowany. Można też przyjąć, że blockchainy, w których istnieją dwie warstwy *node*'ów, (np. Dash ze swoimi *master nodes*), również w jakimś stopniu są zdolne do sprawnego podejmowania decyzji. Natomiast wszystkie pozostałe blockchainy są niebezpiecznie bezbronne w aspekcie *governance issue* i zapewne prędzej czy później poniosą negatywne konsekwencje tego faktu. Albo będą tkwiły w decyzyjnej stagnacji.

Wracając do Tezosa - to zatem duży atut, że troska o *governance issue* leży u samych podstaw tej technologii.

> We enable token holders to make decisions about how the protocol should evolve. All decisions are made transparently on the blockchain. (...) It can even change the rules for decision-making.

Czyli nawet będą reguły pozwalające zmienić reguły tworzenia reguł. To jest analogiczne do artykułu w konstytucji o trybie, w jakim mogą być dokonywane zmiany w konstytucji. Duży plus.

#### Sformalizowany system weryfikacji smart-kontraktów

> Formal verification has been used in the aerospace industry, in medical devices, and other instances where the stakes are too high to fail. It can ensure the security of the platform by proving the correctness of its code.

To jest mega ważna sprawa. Bo to pozwala w dużym stopniu mieć pewność, że smart-kontrakt nie zachowa się wbrew intencjom jego twórców. Czyli np. *The DAO* prawdopodobnie nie przeszłoby takiej weryfikacji, więc na Tezosie nie doszłoby do katastrofy, jaka miała miejsce na ETH.

> To mitigate that risk, the development team designed our smart contract language with correctness and formal verification in mind.

No i tu widzimy cenę, jaką płacimy za tę podwyższoną odporność na błędy - Tezos wprowadza swój własny język skryptowy (o nazwie *Michelson*), który jest dość restrykcyjny i nieelastyczny, co powoduje, że pojawia się dodatkowa bariera dla developerów. 

> Tezos is written in OCaml, a statically-typed functional programming language.

Ważne rozróżnienie: platforma Tezos jest napisana w języku programowania [OCaml](https://en.wikipedia.org/wiki/OCaml), którego nie należy mylić z językiem skryptowym *Michelson*, który ma służyć do pisania smart-kontraktów na Tezosie. OCaml uchodzi za bardzo solidny, ale też trudny w użyciu i stosunkowo mało rozpowszechniony, co będzie miało wpływ na przyszłe tempo rozwoju ekosystemu wokół Tezosa.  

Istotna sprawa: Tezos nie daje 100% gwarancji wykrycia błędu w kodzie smart-kontraktu, daje jedynie zestaw narzędzi, które w sposób istotny zmniejszają możliwość powstania takiego błędu. Projektem, który ma ambicję osiągnąć 100% takiej gwarancji, jest [TauChain/Agoras](http://www.idni.org/), ale póki co nie wiadomo, czy to się uda.

#### Modułowa architektura

> Because Tezos starts with a unique modular design, with cleanly separated layers, upgrading the protocol is as simple as changing out one layer for another.

Bez zaglądania do kodu źródłowego trudno zweryfikować, ile jest w tym prawdy. Wiadomo że architektura modułowa jest czymś bardzo pożądanym, bo daje elastyczność w zakresie modyfikacji i rozbudowy systemu.

> There is no need need for hard forks.

To jest ciekawa rzecz. Na razie nie mam pojęcia, jakim cudem Tezos będzie w stanie unikąć hard forków. Być może chodzi o to, że hard forki będą, tyle że nigdy nie będzie niebezpieczeństwa splitu (jak np. miało to miejsce w przypadku ETH i ETC).

> Tezos not only comes to consensus about state, like BTC or ETH. It also comes to consensus about how the protocol and the nodes should adapt and upgrade.

Brzmi to dość intrygująco, ale brak jest wyjaśnień w jaki sposób zostało to osiągnięte, i czy zostało to przetestowane w praktyce.

#### Kim są ludzie którzy za tym stoją?

Zlokalizowani we Francji, co jest dość nietypowe. Na pierwszy rzut oka [zespół nie wygląda imponująco](https://www.tezos.com/team). Dodatkowo nie podano, jakie są role poszczególnych osób.

> Most of our developers have Ph.Ds in Computer Science and expertise in programming language theory.

Poza powyższą ogólną deklaracją brak dokładniejszych informacji biograficznych. Są tylko imiona + nazwiska i zdjęcia i nic więcej.

> Arthur Breitman had worked at the high frequency trading desk at Goldman Sachs and was an options market maker at Morgan Stanley, while Kathleen Breitman is a former management associate at Bridgewater Associates, the world's largest hedge fund.

Wyraźnie brakuje tu dużego kalibru developera, a CEO Arthur Breitman nie ma namacalnego doświadczenia w zakresie technologii blockchainowych.

Obszerny [wywiad Breitmana dla Epicenter](https://www.youtube.com/watch?v=3mgaDpuMSc0) też nie zrobił na mnie wrażenia. Breitman mówi słuszne rzeczy, ale brakuje w tym większego insight'u.

#### Whitepaper

Z [whitepaperem](https://www.tezos.com/static/papers/white_paper.pdf) jest dość dziwnie: jest on całkiem dobrze napisany, ale osoba zadeklarowana jako jego autor (L.M Goodman) nie należy do zespołu Tezosa. Dodatkowo whitepaper jest mocno nieświeży: widnieje na nim data September 2014. Więc w sumie wygląda to dość podejrzanie i niepoważnie.

#### Parametry blockchaina

Mechanizm konsensusu to DPOS (Delegated Proof of Stake), czyli twórcy Tezosa idą śladami koncepcji Dana Larimera. To jest korzystne, bo to rozwiązanie sprawdziło się całkiem nieźle w praktyce.

Nie znalazłem informacji o docelowej inflacji. W zakresie opłat transakcyjnych (w tym opłat za procesowanie smart-kontraktów) - wygląda na to, że Tezos zastosuje model podobny do ETH (chociaż nigdzie nie jest powiedziane, w jaki sposób opłaty transakcyjne zostaną odseparowane od wahań ceny tokena Tezosa).

#### Roadmap

> The development goals of Tezos follow five axes: security, scaling, privacy, usability, and features.

Roadmap jest na poziomie postulatów - całkiem słusznych, ale bez konkretów.

> Unproven systems ought to innovate at the leaves, while tried-and-true features ought to have a way to make the network more valuable by integrating at the protocol level. Thus, if an application is particularly valuable to the network, we believe it should be folded into the protocol.

Widać w tym podejście podobne do tego, które reprezentuje EOS, czyli docelowo ma to być blockchainowy system operacyjny, w którym najbardziej podstawowe funkcjonalności są wbudowane w bazowy protokół. Tyle że ma to być osiągane stopniowo: na początku będzie "goły" system w rodzaju ETH i stopniowo będzie ewoluować w "bogaty" system w rodzaju EOSa.

> Features likely to be voted into the protocol level by the network include: prediction markets, DNS systems, on-chain node identity, debt networks (à la Stellar), decentralized exchanges, file storage, and cloud computing.

Wygląda na to, że w swoich planach Tezos idzie nawet dalej niż EOS. Jeśli te wyżej wymienione funkcjonalności będą docelowo wbudowane w system to nasuwa się pytanie, czy nie będzie to ewoluować w stronę monolitu, w przeciwieństwie do takiej przestrzeni jak ETH, gdzie jest nieograniczona konkurencja między aplikacjami.

#### Planowane uruchomienie

Nie podano żadnych konkretnych terminów. Z opisu fundraisera wynika, że tempo i rozmach dalszych działań w duże mierze zależą od kwoty uzyskanej podczas ICO - a jest ono bez górnego limitu.

#### Podsumowując
Tezos idzie w stronę obsługi smart-kontraktów, które wymagają największego stopnia bezpieczeństwa. Nie idzie więc w masowość i efektywność procesowania, w zamian stawia na jakość. Czyli pozycjonuje się jako najwyższa półka wśród platform smart-kontraktowych. Na drugim biegunie jest Lisk - ten nie przejmuje się zbytnio bezpieczeństwem i stawia na masowo znany z zastosowań webowych JavaScript.

Tezos ma jeden duży minus: tworzenie nietrywialnych smart-kontraktów jest samo w sobie piekielnie trudne, a Tezos dodatkowo istotnie zwiększa tę trudność. No ale z drugiej strony można założyć, że ludzie, którzy są w stanie tworzyć smart-kontrakty, prawdopodobnie są też w stanie posługiwać się trudniejszymi językami programowania.

Drugi duży minus to zaskakująco niskie doświadczenie ludzi, którzy za tym stoją. Więc jest niebezpieczeństwo, że mimo dobrych chęci ten zespół nie będzie w stanie osiągnąć zadeklarowanych celów. Wygląda to na przewagę hype'u nad meritum.

Jedna z opinii [wyrażona na serwisie Reddit](https://np.reddit.com/r/ethtrader/comments/6am251/what_are_everyones_thoughts_on_tezos_coinss_ico/dhhemcg/):
> The scope of their roadmap is ridiculous and belies that investors should not have confidence that the team will use the raised money well. The plans are massive and random and the team doesn't have the necessary expertise to handle the variety. Scope is way too big. This looks like empire building and it's frankly, an unfocused, shoddy plan.

Moje wrażenia nie są aż tak negatywne, ale podzielam powyższy sentyment. Tezos trochę wygląda jak gigant na glinianych nogach: bardzo ambitne plany ale mocno nieprecyzyjne i bez umocowania w praktyce.

![](concorde.jpg)

Tezos kojarzy mi się to z [samolotem Concorde](https://en.wikipedia.org/wiki/Concorde) - ambitny design i niezły wyczyn inżynieryjny ale w sumie może się okazać niepraktyczny w użyciu. Francuzi mają skłonność do tego rodzaju rzeczy.

#### Oficjalne źródła

[Tezos - official website](https://www.tezos.com/)

[Tezos - fundraiser overview](https://www.tezos.com/static/papers/Tezos_Overview.pdf)

[Tezos - main repository](https://github.com/tezos)

#### Inne źródła

[Tezos Token Sale: A smart contract platform with formal verification and a self-amending protocol](https://www.smithandcrown.com/sale/tezos/)

[Billionaire investor Draper to participate in blockchain token sale for first time](http://www.reuters.com/article/us-tezos-blockchain-draper-idUSKBN181250)

[A questionable story about Tezos](https://steemit.com/tezos/@kyle.anderson/we-don-t-need-to-hardfork-a-questionable-story-about-tezos-ico-july-1st)

