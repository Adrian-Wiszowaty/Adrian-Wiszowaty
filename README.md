**🇵🇱 Polski** | [🇬🇧 English](README.en.md)

# Cześć, jestem Adrian

Od czterech lat pracuję jako full-stack developer w firmie pożyczkowej. Piszę backend w PHP i Symfony, czasem frontend w Angularze, wszystko w środowisku, które pilnują KNF i RODO.

Po godzinach programuję w Pythonie. Zwykle zaczyna się tak, że mam konkretny problem, szukam gotowego narzędzia, nie znajduję i piszę własne. Tak powstały dwa projekty, które trzymam tutaj na GitHubie.

Więcej o mnie na [adrianwiszowaty.pl](https://adrianwiszowaty.pl/).

## Moje projekty w Pythonie

### OLX Finder

`Python` · `Selenium` · `LLM` · `CLI` · `pytest` · `GitHub Actions`

Narzędzie w terminalu. Wklejasz link do wyników OLX, mówisz czego szukasz, a ono pobiera wszystkie ogłoszenia razem z pełnymi opisami i układa z nich ranking. Model językowy sam decyduje, jakie cechy porównywać: przy komputerze będzie to procesor, karta i RAM, przy kurtce materiał i rozmiar. Na koniec można dopytywać o wyniki normalnym językiem.

Napisałem to, bo chciałem kupić używany komputer, a na OLX wisiało kilkaset ofert i porównywanie podzespołów z opisów zajęłoby cały dzień. Dostawca LLM i sam portal aukcyjny siedzą za wspólnymi interfejsami (`LLMClient`, `OlxScraper`), więc dołożenie drugiego modelu albo innego serwisu to napisanie jednej klasy.

[Interaktywne demo w przeglądarce](https://adrianwiszowaty.pl/olx-finder.html)

### Find Crypto Wallets

`Python` · `Etherscan V2 API` · `ttkbootstrap` · `GUI` · `openpyxl` · `pytest` · `GitHub Actions`

Aplikacja okienkowa do tokenów ERC-20 na ETH, BSC i Base. Odpowiada na pytanie, kto z pierwszych kupujących faktycznie w token zainwestował, a kto sprzedał po kilku minutach. Pobiera transfery z zadanego okna czasowego, odrzuca boty po częstotliwości transakcji, sprawdza kto utrzymał pozycję, wycenia salda w dolarach i zapisuje ranking do Excela.

Wcześniej robiłem to ręcznie w Etherscanie i przy setkach transferów było to zwyczajnie męczące. Kod dzieli się na warstwy: pobieranie danych, analiza portfeli, wycena, raport. Klient API jest wstrzykiwany do serwisów, więc każdą warstwę da się testować osobno. Definicje sieci leżą w jednym pliku, dodanie kolejnego łańcucha to jeden wpis w `network_constants.py`. Salda liczę na `Decimal`, bo przy 18 miejscach po przecinku `float` zaczyna gubić grosze.

[Interaktywne demo w przeglądarce](https://adrianwiszowaty.pl/find-crypto-wallets.html)

## Jak je piszę

Robię je dla siebie, ale pilnuję w nich tych samych standardów co w pracy:

- podział na warstwy i wstrzykiwanie zależności, żeby dało się testować bez odpytywania prawdziwych API
- testy w pytest, uruchamiane w GitHub Actions przy każdym pushu
- klucze API siedzą w `.env`, w repo leży tylko `.env.example` z pustymi polami
- ponawianie zapytań i obsługa limitów, bo scraping i darmowe klucze API potrafią się wysypać

## Praca zawodowa

Capital Service S.A., instytucja finansowa zajmująca się pożyczkami i płatnościami. Zaczynałem w 2022 jako tester, potem młodszy programista, od 2025 programista. Rzeczy, przy których pracowałem:

- mikroserwis weryfikacji dokumentów pisany od zera w Symfony i PHP 8.4 (DDD, RabbitMQ, Docker): wyciąganie tekstu z PDF, wersjonowanie dokumentów, porównywanie ich zawartości z danymi w CRM
- integracje zewnętrzne: antyfraud Nethone wpięty w scoring kredytowy, biuro kredytowe CRIF, biura informacji gospodarczej BIG, open banking przez Kontomatik
- raportowanie wpłat pod wymogi KNF na kolejkach RabbitMQ oraz API rachunków płatniczych w Javie i Spring Boocie
- restrukturyzacja pożyczek w monolicie CRM: aneksy, ugody, prolongaty, dni opóźnienia, wyliczanie kwot do spłaty, kreator umów po stronie backendu i frontu
- RODO: usuwanie i anonimizacja danych osobowych w kilku systemach naraz plus migracje bazy
- jakość kodu: PHPUnit, PHPStan, Rector, php-cs-fixer, hooki pre-commit, testy integracyjne

## Czym się posługuję

**Python:** Selenium, API modeli językowych, API blockchain, tkinter i ttkbootstrap, openpyxl, pytest

**Backend:** PHP 8.4, Symfony, Zend Framework, Doctrine ORM, API Platform, podstawy Javy ze Spring Bootem

**Frontend:** Angular, TypeScript, JavaScript, HTML, CSS, WCAG

**Bazy danych:** MySQL, Redis, Elasticsearch, MongoDB

**Integracje:** REST, SOAP, GraphQL, RabbitMQ

**Architektura:** mikroserwisy, DDD, Clean Architecture, SOLID, wzorce projektowe

**Narzędzia:** Docker, Jenkins, GitHub Actions, Git, Xdebug, Jira, YouTrack

## Kontakt

- [kontakt@adrianwiszowaty.pl](mailto:kontakt@adrianwiszowaty.pl)
- [linkedin.com/in/adrian-karol-wiszowaty](https://linkedin.com/in/adrian-karol-wiszowaty)
- [adrianwiszowaty.pl](https://adrianwiszowaty.pl/)
