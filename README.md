# 📋 Text Check - Porównywarka Wydruków

Aplikacja webowa do porównywania tekstu na zdjęciach wydruków. Stworzona specjalnie dla drukarzy flexo do szybkiego sprawdzania zgodności proof'u z wydrukiem maszynowym.

## 🎯 Przeznaczenie

Aplikacja rozwiązuje problem czasochłonnego ręcznego porównywania wydruków. Zamiast czytać każdą literę na obu wydrukach, wystarczy zrobić zdjęcia i pozwolić aplikacji znaleźć różnice.

## ✨ Funkcje

- **📷 Zdjęcia z kamery** - Rób zdjęcia bezpośrednio w aplikacji bez potrzeby galerii
- **🎯 Inteligentny overlay** - Przy robieniu drugiego zdjęcia widzisz półprzezroczyste pierwsze zdjęcie - łatwo dopasować perspektywę!
- **🤖 OCR (Rozpoznawanie tekstu)** - Automatyczne wykrywanie tekstu na zdjęciach używając Tesseract.js
- **🧠 Mądre porównywanie** - Fuzzy matching, ignorowanie wielkości liter i interpunkcji
- **🎨 Wizualizacja różnic** - Kolorowe oznaczenie tego co się różni
- **📊 Statystyki** - Procent podobieństwa, liczba różnic, itp.
- **💻 Działa w przeglądarce** - Nie wymaga instalacji, wszystko działa lokalnie
- **🔒 Prywatność** - Zdjęcia nie są wysyłane na żaden serwer, wszystko przetwarza się w Twojej przeglądarce

## 🚀 Jak używać

### Opcja A: Zdjęcia z kamery (zalecane na telefonie)

1. Otwórz aplikację w przeglądarce
2. Kliknij **"📷 Zrób zdjęcie"** przy "Proof (Wydruk komputerowy)"
3. Zrób zdjęcie proof'u i zatwierdź
4. Kliknij **"📷 Zrób zdjęcie"** przy "Wydruk z maszyny"
5. **WAŻNE:** Zobaczysz półprzezroczyste zdjęcie proof'u - dopasuj perspektywę!
   - Użyj suwaka aby dostosować przezroczystość overlay
   - Spróbuj ustawić kamerę tak, żeby wydruk z maszyny pokrywał się z podglądem proof'u
6. Zrób zdjęcie wydruku z maszyny
7. Kliknij **"Porównaj wydruki"**
8. Poczekaj na wyniki (OCR może potrwać 10-30 sekund)
9. Sprawdź wykryte różnice

### Opcja B: Upload zdjęć z galerii

1. Kliknij **"📁 Wybierz zdjęcie"** i wybierz zdjęcie proof'u
2. Kliknij **"📁 Wybierz zdjęcie"** i wybierz zdjęcie wydruku z maszyny
3. Kliknij **"Porównaj wydruki"**
4. Sprawdź wyniki

## 📱 Wskazówki dla najlepszych wyników

1. **Jakość zdjęć** - Rób zdjęcia w dobrym oświetleniu
2. **Ostrość** - Upewnij się że tekst jest ostry
3. **Kąt** - Nie martw się kątem, ale staraj się żeby tekst był czytelny
4. **Kontrast** - Im większy kontrast między tekstem a tłem, tym lepiej
5. **Rozdzielczość** - Wyższe zdjęcia dają lepsze wyniki, ale zajmują więcej czasu

## 🎨 Jak to działa

1. **Kamera z overlay** - Przy robieniu drugiego zdjęcia, pierwsze zdjęcie jest wyświetlane jako półprzezroczysta nakładka, co pozwala dopasować perspektywę
2. **OCR (Optical Character Recognition)** - Aplikacja używa Tesseract.js do rozpoznania tekstu na obu zdjęciach
3. **Zaawansowana normalizacja** - Tekst jest inteligentnie normalizowany:
   - Ignorowanie wielkości liter (A = a)
   - Usuwanie interpunkcji
   - Normalizacja podobnych znaków (O/0, I/1/l)
   - Usuwanie nadmiarowych białych znaków
4. **Fuzzy matching** - Algorytm toleruje drobne różnice w słowach (np. błędy OCR)
5. **Inteligentne dopasowanie** - Zaawansowany algorytm dopasowuje słowa nawet gdy są w różnej kolejności lub brakuje niektórych
6. **Wizualizacja** - Różnice są oznaczane kolorami:
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

**Kamera nie działa:**
- Upewnij się że przyznałeś przeglądarce uprawnienia do kamery
- Na telefonie: sprawdź czy nie masz zablokowanej kamery dla tej strony w ustawieniach
- Spróbuj użyć opcji "Wybierz zdjęcie" zamiast robienia zdjęcia

**Overlay nie jest widoczny przy drugim zdjęciu:**
- Upewnij się że najpierw zrobiłeś/wgrałeś zdjęcie proof'u
- Overlay pokazuje się tylko przy robieniu DRUGIEGO zdjęcia (wydruk z maszyny)
- Użyj suwaka przezroczystości aby dostosować widoczność

**OCR nie wykrywa tekstu:**
- Sprawdź jakość zdjęcia
- Spróbuj zrobić zdjęcie w lepszym oświetleniu
- Upewnij się że tekst jest ostry
- Użyj overlay przy drugim zdjęciu aby dopasować perspektywę

**Aplikacja się nie ładuje:**
- Sprawdź połączenie z internetem (potrzebne za pierwszym razem)
- Spróbuj odświeżyć stronę
- Sprawdź czy używasz nowoczesnej przeglądarki (Chrome, Firefox, Safari, Edge)

**Wyniki pokazują różnice mimo że wydruki są identyczne:**
- To normalne - OCR nie jest w 100% dokładny
- Sprawdź procent podobieństwa - powyżej 90% to bardzo dobry wynik
- Nowy algorytm fuzzy matching już ignoruje drobne różnice
- Porównaj ręcznie podświetlone fragmenty aby upewnić się czy są to prawdziwe różnice

## 📝 Licencja

MIT License - możesz swobodnie używać i modyfikować

## 🤝 Kontakt

Jeśli masz pytania lub sugestie, stwórz Issue w tym repozytorium.

---

**Powodzenia w druku! 🖨️**
