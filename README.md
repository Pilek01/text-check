# 📋 Text Check - Porównywarka Wydruków

Aplikacja webowa do porównywania tekstu na zdjęciach wydruków. Stworzona specjalnie dla drukarzy flexo do szybkiego sprawdzania zgodności proof'u z wydrukiem maszynowym.

## 🎯 Przeznaczenie

Aplikacja rozwiązuje problem czasochłonnego ręcznego porównywania wydruków. Zamiast czytać każdą literę na obu wydrukach, wystarczy zrobić zdjęcia i pozwolić aplikacji znaleźć różnice.

## ✨ Funkcje

- **OCR (Rozpoznawanie tekstu)** - Automatyczne wykrywanie tekstu na zdjęciach używając Tesseract.js
- **Inteligentne porównywanie** - Działa nawet gdy zdjęcia są zrobione pod różnymi kątami
- **Wizualizacja różnic** - Kolorowe oznaczenie tego co się różni
- **Statystyki** - Procent podobieństwa, liczba różnic, itp.
- **Działa w przeglądarce** - Nie wymaga instalacji, wszystko działa lokalnie
- **Prywatność** - Zdjęcia nie są wysyłane na żaden serwer, wszystko przetwarza się w Twojej przeglądarce

## 🚀 Jak używać

### Metoda 1: GitHub Pages (Najprostsza)

1. Otwórz aplikację w przeglądarce: `https://[twoja-nazwa-użytkownika].github.io/text-check/`
2. Zrób zdjęcie proof'u (wydruku komputerowego)
3. Zrób zdjęcie wydruku z maszyny
4. Wgraj oba zdjęcia do aplikacji
5. Kliknij "Porównaj wydruki"
6. Poczekaj na wyniki (OCR może potrwać 10-30 sekund)
7. Sprawdź wykryte różnice

### Metoda 2: Lokalne uruchomienie

1. Pobierz plik `index.html` z tego repozytorium
2. Otwórz go w przeglądarce (Chrome, Firefox, Safari, Edge)
3. Użyj jak opisano powyżej

## 📱 Wskazówki dla najlepszych wyników

1. **Jakość zdjęć** - Rób zdjęcia w dobrym oświetleniu
2. **Ostrość** - Upewnij się że tekst jest ostry
3. **Kąt** - Nie martw się kątem, ale staraj się żeby tekst był czytelny
4. **Kontrast** - Im większy kontrast między tekstem a tłem, tym lepiej
5. **Rozdzielczość** - Wyższe zdjęcia dają lepsze wyniki, ale zajmują więcej czasu

## 🎨 Jak to działa

1. **OCR (Optical Character Recognition)** - Aplikacja używa Tesseract.js do rozpoznania tekstu na obu zdjęciach
2. **Normalizacja** - Tekst jest normalizowany (usuwane są nadmiarowe spacje)
3. **Porównanie** - Algorytm Levenshtein Distance porównuje oba teksty
4. **Wizualizacja** - Różnice są oznaczane kolorami:
   - 🔴 Czerwony = usunięte (jest w proof, brak w wydruku)
   - 🟢 Zielony = dodane (brak w proof, jest w wydruku)
   - ⚪ Szary = bez zmian

## 📊 Interpretacja wyników

- **95-100% podobieństwa** ✅ - Praktycznie identyczne, możesz kontynuować drukowanie
- **85-94% podobieństwa** ⚠️ - Niewielkie różnice, sprawdź szczegóły
- **Poniżej 85%** ❌ - Znaczące różnice, należy sprawdzić dokładnie

## 🔧 Technologie

- **Tesseract.js** - OCR engine do rozpoznawania tekstu
- **JavaScript (ES6+)** - Logika aplikacji
- **HTML5 + CSS3** - Interface użytkownika
- **Algorytm Levenshtein** - Porównywanie tekstów

## ⚠️ Ograniczenia

- OCR nie jest w 100% dokładny - może mieć problemy z:
  - Bardzo małym tekstem
  - Niskiej jakości zdjęciami
  - Specjalnymi fontami
  - Odblaskami lub cieniami
- Pierwsze uruchomienie wymaga połączenia z internetem (pobieranie modelu OCR)
- Przetwarzanie może zająć 10-60 sekund w zależności od rozmiaru zdjęć

## 💡 Rozwiązywanie problemów

**OCR nie wykrywa tekstu:**
- Sprawdź jakość zdjęcia
- Spróbuj zrobić zdjęcie w lepszym oświetleniu
- Upewnij się że tekst jest ostry

**Aplikacja się nie ładuje:**
- Sprawdź połączenie z internetem (potrzebne za pierwszym razem)
- Spróbuj odświeżyć stronę
- Sprawdź czy używasz nowoczesnej przeglądarki

**Wyniki są nieprawidłowe:**
- Porównaj ręcznie kilka fragmentów
- OCR może mieć problem z nietypowymi czcionkami
- Spróbuj lepszych zdjęć

## 📝 Licencja

MIT License - możesz swobodnie używać i modyfikować

## 🤝 Kontakt

Jeśli masz pytania lub sugestie, stwórz Issue w tym repozytorium.

---

**Powodzenia w druku! 🖨️**
