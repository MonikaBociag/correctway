# Correct Way — strona internetowa

Statyczna strona (czysty HTML + CSS, minimalny JavaScript). Bez procesu budowania,
bez zależności — wystarczy wgrać pliki.

Treści i stronę przygotowała [Kocia Korektorka](https://www.kociakorektorka.pl/).

## Zawartość

```
index.html              strona główna (hero, opinie, oferta, proces, portfolio → link, FAQ, blog, kontakt)
portfolio.html          podstrona z realizacjami
logo.png                logo marki
portret.webp            zdjęcie w sekcji hero
o-mnie.webp             zdjęcie w sekcji „O mnie”
poza-horyzontem.webp    okładka tomiku (portfolio)
planeta-mepli.webp      okładka magazynu (portfolio)
favicon.png             ikona karty przeglądarki (64 px)
apple-touch-icon.png    ikona ekranu startowego iOS (180 px)
og-image.png            miniatura przy udostępnianiu linku (1200 × 630 px)
robots.txt              zgoda na indeksowanie + wskazanie sitemapy
sitemap.xml             lista adresów strony
```

Wszystkie pliki muszą leżeć w jednym katalogu — odwołania w kodzie są względne.

## Wdrożenie na Vercelu

1. Utwórz repozytorium na GitHubie i wgraj zawartość tego katalogu.
2. W Vercelu: **Add New → Project → import repozytorium**. Framework preset: **Other**.
3. Podepnij domenę w **Settings → Domains**.
4. **Jeśli domena będzie inna niż `correctway.pl`**, podmień ten adres w czterech plikach:
   `index.html`, `portfolio.html`, `robots.txt`, `sitemap.xml`. Najprościej: funkcja
   „znajdź i zamień” w edytorze, szukając `correctway.pl`. Adres występuje w znaczniku
   canonical, w danych Open Graph i w danych strukturalnych — wszystkie muszą wskazywać
   tę samą domenę.

Uwaga: subdomena `*.vercel.app` celowo nie indeksuje się w Google — to normalne do czasu
podpięcia własnej domeny.

Każdy zapis zmian na GitHubie uruchamia wdrożenie automatycznie. Do bieżącej edycji
treści panel Vercela nie jest potrzebny.

## Do uzupełnienia przed premierą

- [x] **Formularz kontaktowy** — podłączony do Formspree (`xbgrylzr`). Wysyłka odbywa się
      w tle, podziękowanie pojawia się pod formularzem. Po wdrożeniu wyślij testowe
      zgłoszenie: Formspree przy pierwszym zgłoszeniu prosi o potwierdzenie adresu
      odbiorcy, a warto też sprawdzić, czy wiadomość nie wpada do spamu.
- [ ] **Polityka prywatności** — plik `polityka-prywatnosci.html` (linki w stopce i pod
      formularzem już do niego prowadzą). Musi zawierać dane administratora danych,
      bo formularz zbiera dane osobowe. Wymagana od dnia premiery.
- [ ] **Sekcja bloga** — trzy karty zapowiadają artykuły, które jeszcze nie istnieją,
      i prowadzą do `#`. Przed premierą: napisać teksty albo zakomentować całą sekcję
      `<section id="blog">` wraz z linkiem „Blog” w nawigacji.
- [ ] **Poufność w FAQ** — odpowiedź „Co z poufnością moich materiałów?” czeka na
      decyzje o czasie przechowywania plików, możliwości podpisania NDA i polityce
      użycia narzędzi AI.
- [ ] **Portfolio** — pozycje „Mój kumpel kapsel” i „Chłopiec, którego nie było”
      (Piotrek Cajdler) są w prostej liście „Pozostałe realizacje”. Po zebraniu zakresu
      pracy, wydawnictwa, roku i okładek można przenieść je do pełnych kart
      `<article class="work">`.
- [ ] **Zgody** na publikację okładek (DC Books, Planeta Mepli) i pełnego nazwiska
      w opinii.
- [ ] **Przykład „przed i po”** w sekcji „Warsztat” jest demonstracyjny — nie pochodzi
      od klienta. Można podmienić na własny fragment.

## Po wdrożeniu

1. Google Search Console — weryfikacja rekordem DNS, zgłoszenie `sitemap.xml`.
2. Rich Results Test — sprawdzenie danych strukturalnych (`ProfessionalService`,
   `FAQPage`, `CollectionPage` z realizacjami).
3. `Ctrl+U` na opublikowanej stronie — cała treść jest w źródle, więc widzą ją także
   crawlery modeli językowych (istotne dla widoczności w AI).

## Uwagi techniczne

- Logo w nagłówku to plik PNG. Gdy grafik dostarczy finalny SVG, podmiana to jedna linia
  w `index.html` i `portfolio.html`.
- Zdjęcia są w formacie WebP; obrazy poza pierwszym ekranem mają `loading="lazy"`.
- Menu mobilne, karuzela opinii i rozwijane FAQ nie wymagają żadnych bibliotek.
- Animacje respektują systemowe ustawienie ograniczonego ruchu.
- Paleta, kroje pisma i parametry interfejsu są zgodne z mini brandbookiem Correct Way
  (wersja 1.0) i siedzą w zmiennych CSS w sekcji `:root` — podmiana koloru to jedna linia.
