# Kwestie do zbadania

## 1. Aspekty rynkowe

1. Jakie podmioty w Polsce (i Europie) potrzebują weryfikować swoich klientów w zakresie KYC? Jak dużo ich jest?
2. Jakie koszty ponoszą podmioty (zarówno bankowe jak i niebankowe) w związku z KYC?
3. W jakim kierunku będzie się zmieniać zapotrzebowanie na KYC w przyszłości?

## 2. Aspekty prawne

#### 2.1 PSD2

1. Czy wedle PSD2 bank ma obowiązek udostępnić w swoim API informacje dotyczące danych osobowych klienta?
2. Czy PSD2 standaryzuje API, które banki muszą udostępnić, czy nakłada jedynie wymagania funkcjonalne, a techniczne aspekty pozostawia do decyzji poszczególnych banków?
3. Czy autoryzacja poprzez esemes spełnia wymogi mocnej autoryzacji wymaganej przez PSD2? Czy wątpliowści wyrażone w [tym artykule](https://blog.vasco.com/application-security/psd2/) są zasadne.
4. Jeśli tak, to czy w zakresie mocnej autoryzacji wymaganej przez PSD2, wystarczające jest użycie następującej kombinacji: hasło wpisywane do interfejsu plus PIN otrzymany esemesem?

#### 2.2 AML/KYC

1. Jakie dokładnie są wymogi KYC finansowego w Polsce (i Europie)? Jakie są wymogi w przypadku stosowania outsourcingu KYC?
2. Czy uzyskanie kryptograficznie poświadczonych przez bank danych osobowych klienta ma szansę być uznane za dopuszczalną formę weryfikacji KYC? (albo dopuszczalną formę outsource'owania KYC?)

#### 2.3 RODO/GDPR

1. Jakie są restrykcje prawne nałożone na banki w zakresie udostępniania danych osobowych swoich klientów? Czy słuszne jest założenie, że TPP działając w imieniu klienta może uzyskać od banku dane osobowe, które dotyczą tego klienta? Jeśli przewidujemy z tym problem, to czy udostępnienie przez bank tych danych w formie zahashowanej coś ułatwia?

## 3. Aspekty biznesowe

1. Czy banki będą skore do wdrożenia dodatkowego API? Wiadomo, że i tak muszą przygotować API spełniające wymagania PSD2, więc potencjalnie dodatkowy *endpoint* nie powinien być kłopotliwy, niemniej jednak przed przystąpieniem do prac warto zbadać ich zainteresowanie, w tym także jakie są ich oczekiwania wobec przychodów z udziału w tym przedsięwzięciu.
2. Jakie techniczne wymagania nałożą banki na TPP? Na ile podobne będą mechanizmy autoryzacji dostępu do API w różnych bankach? Od tego zależy ile pracy trzeba będzie włożyć w opracowanie systemu Sygnet, i tym samym determinują jego opłacalność.
3. Ile banków musiałoby wejść do systemu Sygnet, aby firmy widziały sens w integracji z tym systemem. Może się okazać, że dopiero udział dwóch lub trzech dużych banków da nam możliwość weryfikacji tożsamości wystarczająco dużej liczby potencjalnych klientów, żeby taka integracja przyniosła wymierne oszczędności pozwalające na wystarczająco szybkie odzyskanie poniesionych nakładów.
4. W jaki sposób banki segregują klientów na tych mocniej i słabiej zweryfikowanych? (np. ci co fizycznie przyszli do oddziału w momencie zakładania rachunku vs. ci co założyli konto metodą on-line i zweryfikowali się poprzez przelew testowy)
5. Jakie są odpowiedzi na te pytania jeżeli chcemy przenieść ten mechanizm do innych krajów UE?

# Materiały źródłowe

#### 1. Rodo a PSD2: Niejednozna­czne przepisy dotyczące przenoszenia danych

> Innym istotnym aspektem zastosowania art. 20 Rozporządzenia jest jego relacja do nowego rodzaju instytucji płatniczych, opierających zasadniczą część swoich usług na przetwarzaniu danych klientów. Mowa tu o TPP (Third Party Providers) - czyli dostawcach usług płatniczych, którzy na mocy nowej Dyrektywy PSD2 oferować będą usługi płatnicze polegające na inicjowaniu płatności - PIS (Payment Initiation Service) oraz zapewnianiu dostępu do informacji o rachunku - AIS (Account Information Service). W szczególności usługa AIS swym charakterem zbliżona jest raczej do usług, których przedmiotem jest przetwarzanie danych osobowych aniżeli do typowych usług płatniczych, jak np. usługa wykonania transakcji płatniczej.

> W tym kontekście - pojawia się pytanie: komu i jaki zakres danych o kliencie powinien być przekazywany zgodnie z żądaniem klienta (art. 20 Rozporządzenia) i w jaki sposób przekazywane powinny być dane stanowiące tajemnicę bankową.

https://www2.deloitte.com/pl/pl/pages/doradztwo-prawne/articles/ochrona-danych-osobowych/ochrona-danych-osobowych-psd2.html

#### 2. dLK Legal: Wsparcie w strategiach i regulacjach PSD2

> Coraz wyraźniej krystalizuje się wizja, aby - co najmniej w usługach finansowych - dane klienta, które zostały zgromadzone u jego dostawcy, nie mogły być "aktywem" i przewagą konkurencyjną tego dostawcy, ale muszą być udostępnione innym dostawcom. W zakresie osób fizycznych obowiązek "dzielenia się" danymi o kliencie jest nawet szerszy niż w PSD2 na skutek uchwalonego w 2016 Rozporządzenia EU o ochronie danych osobowych wymagającego przekazania podmiotowi wskazanemu przez klienta zgromadzonych danych w rozpowszechnionym formacie pliku.

http://www.dlklegal.com/psd2-9

#### 3. PSD2: Is this the End of SMS-based Authentication?

> We are still waiting for the final requirements on Strong Customer Authentication under PSD2. However if nothing changes compared to the current proposal, it is quite clear that [SMS-based authentication](https://www.vasco.com/products/two-factor-authenticators/software/sms/virtual-digipass.html) will have a hard time meeting the requirements, especially those related to approving payments.

https://blog.vasco.com/application-security/psd2/