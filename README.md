<!--lint disable awesome-git-repo-age-->

# Awesome KSeF [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Zbiór narzędzi, bibliotek i zasobów dla polskiego Krajowego Systemu e-Faktur (KSeF).

*A curated list of tools, libraries, and resources for Poland's mandatory e-invoicing system (KSeF).*

## Contents

- [Oficjalne zasoby](#oficjalne-zasoby)
- [Walidatory](#walidatory)
- [Oprogramowanie do fakturowania](#oprogramowanie-do-fakturowania)
- [Narzędzia dla programistów](#narzędzia-dla-programistów)
- [Agent Skills](#agent-skills)
- [Monitory i narzędzia pomocnicze](#monitory-i-narzędzia-pomocnicze)
- [Konwertery](#konwertery)
- [Zasoby edukacyjne](#zasoby-edukacyjne)

## Oficjalne zasoby

- [Aplikacja Podatnika KSeF 2.0](https://ap.ksef.mf.gov.pl) - Oficjalna webowa aplikacja Ministerstwa Finansów do wystawiania, odbierania i przeglądania faktur ustrukturyzowanych FA(3).
- [Aplikacja mobilna KSeF 2.0 (Android)](https://play.google.com/store/apps/details?id=pl.gov.mf.ksef) - Oficjalna aplikacja mobilna MF dla systemu Android do obsługi KSeF 2.0.
- [Aplikacja mobilna KSeF 2.0 (iOS)](https://apps.apple.com/app/id6478391157) - Oficjalna aplikacja mobilna MF dla systemu iOS do obsługi KSeF 2.0.
- [e-mikrofirma](https://e-mikrofirma.mf.gov.pl) - Oficjalna aplikacja MF dla mikroprzedsiębiorców i JDG, umożliwiająca wystawianie faktur w KSeF, ewidencję VAT i wysyłkę JPK.
- [Środowisko testowe KSeF 2.0](https://ap-test.ksef.mf.gov.pl) - Testowa wersja Aplikacji Podatnika KSeF 2.0 do weryfikacji integracji przed wdrożeniem produkcyjnym.
- [Portal dokumentacji KSeF](https://ksef.podatki.gov.pl) - Oficjalny portal MF z dokumentacją, instrukcjami, materiałami szkoleniowymi i odpowiedziami na pytania dotyczące KSeF 2.0.
- [Schemat FA(3) XSD](https://crd.gov.pl/wzor/2025/06/25/13775/schemat.xsd) - Oficjalny schemat XSD struktury logicznej faktury FA(3), obowiązujący od 1 lutego 2026 r.

## Walidatory

- [ksefuj.to](https://ksefuj.to) - Darmowy walidator FA(3) działający w całości w przeglądarce (WebAssembly). Sprawdza zgodność ze schematem XSD i regułami z broszury informacyjnej MF, a także kwoty VAT i sumy, kurs NBP i numer konta. Obsługuje wiele plików naraz, ma też podgląd PDF z kodem QR i kalkulator kursów NBP. Open source (Apache 2.0).
- [ksefwalidator.pl](https://ksefwalidator.pl) - Przeglądarkowy walidator XML FA(3) działający po stronie klienta; sprawdza zgodność z XSD, poprawność NIP oraz status podatnika na Białej Liście. Darmowy.
- [naprawksef.pl](https://naprawksef.pl) - Walidator FA(3)/FA(2) z unikalną funkcją automatycznej naprawy najczęstszych błędów w strukturze XML faktury. Freemium (3 walidacje dziennie za darmo).
- [Sorgera KSeF Validator](https://services.sorgera.com/ksef/validator) - Walidator FA(3) klasy enterprise z podświetlaniem błędów na poziomie linii XML i zaawansowanymi komunikatami diagnostycznymi. Darmowy.
- [fa3.site](https://fa3.site) - Przeglądarkowy walidator FA(3) z podglądem wizualizacji faktury, zbudowany w React. Darmowy.
- [KSeF Assistant](https://ksefu.pl) - Lokalny walidator XML z weryfikacją reguł biznesowych, sprawdzaniem NIP/IBAN i generowaniem raportów PDF. Freemium (10 walidacji miesięcznie za darmo).
- [KSeF Guard](https://www.ksefguard.pl) - Walidator FA(3) offline (aplikacja desktopowa dla Windows oraz CLI) weryfikujący zgodność z XSD oraz 128 regułami biznesowymi przed wysłaniem do KSeF. Freemium (10 plików dziennie za darmo).

## Oprogramowanie do fakturowania

- [ProFak](https://github.com/lkosson/profak) - Darmowy program do fakturowania dla mikroprzedsiębiorstw i JDG (Windows), obsługujący faktury VAT, JPK oraz integrację z KSeF 2.0. Darmowy.
- [KsefInvoice](https://ksefinvoice.pl) - Desktopowa aplikacja (Windows, Linux) do wystawiania faktur z integracją KSeF, weryfikacją kontrahentów i lokalnym przechowywaniem danych. Darmowy.
- [KSeFka](https://ksefka.com) - Desktopowa aplikacja (Windows, macOS, Linux) do fakturowania z pełną integracją KSeF, generowaniem PDF i lokalnym przechowywaniem danych. Darmowy.
- [Ksefi](https://www.ksefi.com.pl) - Webowy generator faktur ustrukturyzowanych XML FA(3) wspomagany przez AI, działający bez rejestracji. Darmowy.
- [OpenKSeF](https://github.com/open-ksef/open-ksef) - Aplikacja webowa i mobilna do automatycznej synchronizacji faktur z KSeF, powiadamiania o nowych dokumentach i zarządzania fakturami zakupowymi; przeznaczona do samodzielnego hostowania. Source-available (Elastic License 2.0).

## Narzędzia dla programistów

- [ksefuj/ksefuj](https://github.com/ksefuj/ksefuj) - Monorepo projektu ksefuj.to: aplikacja internetowa, pakiet npm `@ksefuj/validator` z CLI i generator wizualizacji PDF. Open source (Apache 2.0).
- [@ksefuj/validator](https://www.npmjs.com/package/@ksefuj/validator) - Pakiet npm i CLI (`ksef-validate`) do walidacji faktur FA(3) w Node.js i w przeglądarce, z typami TypeScript i opcjonalnym sprawdzaniem kursów NBP. Open source (Apache 2.0).

```sh
npx @ksefuj/validator faktura.xml
```

- [KSeF-GUI](https://github.com/marcinbojko/ksef-gui) - Fork kcksefcli z lokalnym interfejsem przeglądarkowym do pobierania faktur z KSeF, powiadomieniami (Slack, Teams, e-mail) i eksportem CSV; dostępny jako obraz Docker. Open source (GPL-3.0).
- [KSeFCLI (kcksefcli)](https://github.com/Kamilcuk/ksefcli) - Narzędzie CLI (C#) z ponad 30 komendami do zarządzania fakturami, certyfikatami i sesjami w KSeF API; binaria dla Linux x64 i Windows. Open source (GPL-3.0).

## Agent Skills

- [ksefuj/skills](https://github.com/ksefuj/skills) - Skille dla Claude'a (Claude Code i Claude.ai) do generowania plików XML faktur FA(3) (`ksef-invoice`) i faktur korygujących (`ksef-correction`). Obejmują m.in. WDT, eksport, odwrotne obciążenie, zwolnienia, zaliczki i procedurę marży. Open source (Apache 2.0).

## Monitory i narzędzia pomocnicze

- [KSeF Invoice Monitor](https://github.com/mlotocki2k/KSeF_Monitor) - Serwis Python/Docker do cyklicznego monitorowania faktur w KSeF API v2 z powiadomieniami przez 5 kanałów (Pushover, Discord, Slack, e-mail, webhook), generowaniem PDF i eksportem metryk Prometheus. Open source (MIT).
- [Weryfikator Kodów QR z KSeF](https://ai-gov.pl/ksef-qr) - Kliencka aplikacja webowa do weryfikacji kodów QR z e-faktur KSeF przez kamerę lub wgranie pliku graficznego; działa w całości po stronie przeglądarki. Darmowy.
- [KSeF View Dashboard](https://github.com/AlRbv/ksef_view_dashboard) - Lokalny dashboard Streamlit tylko do odczytu, który synchronizuje metadane faktur wystawionych i otrzymanych z KSeF API v2 do SQLite i pokazuje sumy brutto i VAT, trendy oraz największych kontrahentów. Open source (MIT).

## Konwertery

- [Wizualizator e-Faktur (XML→PDF)](https://github.com/niutech/ksef-xml-pdf) - Kliencka aplikacja webowa do generowania wizualizacji e-faktury z pliku XML do formatu PDF/A-3 z osadzonym XML; dane nie są przesyłane na serwer. Open source (GPL-3.0). [Demo](https://ai-gov.pl/ksef-pdf)
- [Pobieracz e-Faktur (PDF→XML)](https://github.com/niutech/ksef-pdf-xml) - Kliencka aplikacja webowa do pobierania pliku XML e-faktury z KSeF na podstawie kodu QR odczytanego z wizualizacji PDF; działa po stronie przeglądarki. Open source (GPL-3.0). [Demo](https://ai-gov.pl/ksef-xml)

## Zasoby edukacyjne

- [Pytania i odpowiedzi KSeF 2.0](https://ksef.podatki.gov.pl/pytania-i-odpowiedzi-ksef-20) - Oficjalne FAQ Ministerstwa Finansów dotyczące KSeF 2.0 — obowiązki, terminy, wyjątki i przypadki szczególne.
- [Portal KSeF — materiały szkoleniowe](https://ksef.podatki.gov.pl/materialy-szkoleniowe-ksef-20) - Instrukcje obsługi, nagrania webinarów i prezentacje przygotowane przez MF dla podatników i integratorów.

## Contributing

Przeczytaj [contributing.md](contributing.md) przed dodaniem wpisu. Jeden wpis na PR, tylko aktywnie utrzymywane narzędzia.

*Read contributing.md before submitting. One entry per PR, actively maintained tools only.*

## Footnotes

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0)

Na tyle, na ile pozwala prawo, autorzy zrzekają się wszelkich praw autorskich i pokrewnych do tej listy.
