[🇵🇱 Polski](README.md) | **🇬🇧 English**

# Hi, I'm Adrian

I've spent the last four years as a full-stack developer at a lending company. I write backend code in PHP and Symfony, sometimes frontend in Angular, all of it in an environment watched over by the Polish financial regulator and GDPR.

After hours I write Python. It usually starts the same way: I have a specific problem, I look for a tool that solves it, I don't find one, so I write my own. That's how the two projects I keep here on GitHub came about.

More about me at [adrianwiszowaty.pl](https://adrianwiszowaty.pl/).

## My Python projects

### OLX Finder

`Python` · `Selenium` · `LLM` · `CLI` · `pytest` · `GitHub Actions`

A terminal tool. You paste a link to OLX search results, say what you're after, and it pulls every listing with its full description and ranks them. The language model decides on its own which attributes matter: for a PC that's the processor, graphics card and RAM, for a jacket the fabric and size. When it's done you can ask follow-up questions in plain language.

I wrote it because I wanted to buy a used PC and there were several hundred listings on OLX. Comparing specs pulled out of free-text descriptions would have taken a whole day. The LLM provider and the marketplace itself sit behind shared interfaces (`LLMClient`, `OlxScraper`), so adding a second model or a different site means writing one class.

[Interactive browser demo](https://adrianwiszowaty.pl/en/olx-finder.html)

### Find Crypto Wallets

`Python` · `Etherscan V2 API` · `ttkbootstrap` · `GUI` · `openpyxl` · `pytest` · `GitHub Actions`

A desktop app for ERC-20 tokens on ETH, BSC and Base. It answers one question: which of the early buyers actually invested in the token, and who sold it a few minutes later. It fetches transfers from a given time window, drops bots based on how often they transact, checks who held their position, values the balances in dollars and writes the ranking to Excel.

I used to do this by hand in Etherscan, and with hundreds of transfers it was simply tiring. The code is split into layers: fetching data, analysing wallets, valuation, reporting. The API client is injected into the services, so each layer can be tested on its own. Network definitions live in one file, and adding another chain is a single entry in `network_constants.py`. Balances are computed with `Decimal`, because with 18 decimal places `float` starts losing pennies.

[Interactive browser demo](https://adrianwiszowaty.pl/en/find-crypto-wallets.html)

## How I build them

I build them for myself, but I hold them to the same standards as my work code:

- layered code and dependency injection, so tests can run without calling real APIs
- pytest suites running in GitHub Actions on every push
- API keys live in `.env`, the repo only carries `.env.example` with the fields left blank
- retries and rate-limit handling, because scraping and free API keys fall over often enough

## Day job

Capital Service S.A., a financial institution doing loans and payments. I started there in 2022 as a tester, then junior developer, and since 2025 developer. Things I've worked on:

- a document verification microservice built from scratch in Symfony and PHP 8.4 (DDD, RabbitMQ, Docker): pulling text out of PDFs, versioning documents, comparing their contents against CRM data
- external integrations: Nethone anti-fraud wired into credit scoring, the CRIF credit bureau, BIG debtor registries, open banking via Kontomatik
- payment reporting for the regulator over RabbitMQ queues, plus a payment accounts API in Java and Spring Boot
- loan restructuring in the CRM monolith: annexes, settlements, deferrals, days past due, payoff calculations, a contract wizard on both backend and frontend
- GDPR work: deleting and anonymising personal data across several systems at once, plus database migrations
- code quality: PHPUnit, PHPStan, Rector, php-cs-fixer, pre-commit hooks, integration tests

## What I work with

**Python:** Selenium, LLM APIs, blockchain APIs, tkinter and ttkbootstrap, openpyxl, pytest

**Backend:** PHP 8.4, Symfony, Zend Framework, Doctrine ORM, API Platform, basics of Java with Spring Boot

**Frontend:** Angular, TypeScript, JavaScript, HTML, CSS, WCAG

**Databases:** MySQL, Redis, Elasticsearch, MongoDB

**Integrations:** REST, SOAP, GraphQL, RabbitMQ

**Architecture:** microservices, DDD, Clean Architecture, SOLID, design patterns

**Tooling:** Docker, Jenkins, GitHub Actions, Git, Xdebug, Jira, YouTrack

## Contact

- [kontakt@adrianwiszowaty.pl](mailto:kontakt@adrianwiszowaty.pl)
- [linkedin.com/in/adrian-karol-wiszowaty](https://linkedin.com/in/adrian-karol-wiszowaty)
- [adrianwiszowaty.pl](https://adrianwiszowaty.pl/)
