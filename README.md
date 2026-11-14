# Polish TTS Lab

Testy jakości polskiej syntezy mowy (Text-to-Speech): liczebniki, kwoty, wymowa spółgłosek miękkich i intonacja list numerowanych.

**Initial case:** funkcja **„Czytaj na głos”** (ikona głośnika pod odpowiedzią ChatGPT), zgłoszenie z 14 listopada 2026 r.

## Problem / Observed issue

Podczas odsłuchiwania polskich odpowiedzi w ChatGPT zaobserwowano:

- **Liczby zapisane słownie** bywają mniej zrozumiałe niż ich odpowiedniki zapisane cyframi.
- **Numeracja list Markdown** może powodować nagłe, nietypowe zmiany wysokości, barwy lub intonacji głosu. Anomalie były słyszane między innymi przy pozycjach 2 i 4; nie występują jednak niezmiennie w każdej próbie.
- W wyrażeniach zawierających polskie głoski miękkie i zmiękczenia mogą występować trudności artykulacyjne.

To **obserwacje odsłuchowe pojedynczego użytkownika**, a nie potwierdzona diagnoza mechanizmu TTS. Jedna z hipotez dotyczy obsługi polskich spółgłosek i ich zmiękczeń (np. **ś, ć, ź, dź, si, ci, zi, dzi**), inna — przetwarzania numeracji Markdown i prozodii. Nie ustalono jeszcze przyczyny.

## Jak odtworzyć / Reproduction

1. Otwórz odpowiedź ChatGPT zawierającą poniższe przykłady.
2. Kliknij ikonę głośnika („Czytaj na głos”) **pod odpowiedzią** — nie chodzi o rozmowę w trybie Voice.
3. Porównaj wymowę tekstów z cyframi, zapisu słownego oraz numerowanych pozycji.
4. Powtórz odsłuch i zapisz, czy błąd się powtarza; jeśli to możliwe, dołącz nagranie dźwięku.

### Test A — ceny kursów w liście numerowanej

1. Czternaście złotych i dwanaście groszy.
2. Trzynaście złotych i dwadzieścia dwa grosze.
3. Jedenaście złotych i osiemdziesiąt pięć groszy.
4. Dwadzieścia cztery złote i czterdzieści cztery grosze.
5. Trzydzieści pięć złotych i sześćdziesiąt sześć groszy.

### Test B — te same ceny zapisane cyframi

1. 14,12 zł.
2. 13,22 zł.
3. 11,85 zł.
4. 24,44 zł.
5. 35,66 zł.

### Test C — liczby zapisane cyframi

123

456

789

1234

12345

1234567

123456789

### Test D — liczby zapisane słownie

Sto dwadzieścia trzy.

Czterysta pięćdziesiąt sześć.

Siedemset osiemdziesiąt dziewięć.

Tysiąc dwieście trzydzieści cztery.

Dwanaście tysięcy trzysta czterdzieści pięć.

Milion dwieście trzydzieści cztery tysiące pięćset sześćdziesiąt siedem.

Sto dwadzieścia trzy miliony czterysta pięćdziesiąt sześć tysięcy siedemset osiemdziesiąt dziewięć.

### Test E — kontrola numeracji bez cen

1. Pierwszy punkt.
2. Drugi punkt.
3. Trzeci punkt.
4. Czwarty punkt.
5. Piąty punkt.

## Oczekiwane zachowanie / Expected behavior

Poprawna i zrozumiała wymowa polskich liczb i kwot, bez nagłych zmian barwy głosu, sztucznego pogłosu czy nietypowej intonacji podczas odczytu listy.

## Fakty, hipotezy i ograniczenia

- **Fakt zgłoszony przez testującego:** problem usłyszano w odczycie na głos odpowiedzi ChatGPT.
- **Hipoteza:** polska fonetyka (zwłaszcza spółgłoski miękkie i zmiękczenia) może być trudna dla syntezy.
- **Hipoteza:** parser list Markdown lub sposób przekazywania numeracji do TTS może wpływać na prozodię.
- **Do ustalenia:** powtarzalność, zależność od przeglądarki/urządzenia, wersji aplikacji, wybranego głosu i wariantu zapisu.

## English issue summary

**Polish Read Aloud TTS may mispronounce spelled-out numbers and change voice characteristics on numbered list markers.** Digits can sound clearer than the equivalent written-out Polish numbers. Some numbered list entries exhibit unusual pitch, timbre or prosody changes. The possible role of Polish palatalization/soft consonants and Markdown list handling requires investigation. Please consider review by Polish-language speech specialists.

## Cel projektu

Budowa otwartego zbioru przypadków testowych i porównywalnych próbek polskiego TTS. Projekt nie jest oficjalnym narzędziem OpenAI.

Feedback and reproducible test cases are welcome.
