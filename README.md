# 📋 Text Check PRO - Profesjonalna Porównywarka Wydruków

Zaawansowana aplikacja webowa do porównywania wydruków flexo. Porównuje **WSZYSTKO**: tekst, grafiki, kolory, layout!

## 🎯 Przeznaczenie

Stworzona dla drukarzy flexo do szybkiej kontroli jakości. Porównuj pełne wydruki z grafikami, zdjęciami produktów, logo i tekstem - wszystko w jednej aplikacji!

### Przykłady użycia:
- ✅ Opakowania z grafiką produktu + tekst ("Cukier królewski 1kg")
- ✅ Etykiety z logo + różne kolory + informacje
- ✅ Złożone wydruki (np. "Belbake mąka pszenna 1kg")
- ✅ Kontrola kolorów logo i zdjęć
- ✅ Weryfikacja tekstu (składniki, gramatura, etc.)

## ✨ MEGA Funkcje

### 🎯 3 Tryby Porównywania

**1. Hybrydowy (Najlepszy!)**
- Porównuje WSZYSTKO: grafiki + kolory + tekst
- Używa: Pixelmatch (60%) + OCR (40%)
- Idealny dla kompletnych wydruków z grafiką

**2. Tylko Grafika**
- Pixel-by-pixel comparison
- Heatmapa różnic (zielony→żółty→czerwony)
- Świetny dla sprawdzania kolorów i grafik
- Ignoruje tekst - szybszy!

**3. Tylko Tekst**
- OCR + LCS algorithm
- Fuzzy matching
- Idealny gdy jest dużo tekstu, mało grafiki
- Najszybszy tryb

### 🔥 Heatmapa Różnic (Visual Comparison)
- **Zielony** = Identyczne piksele
- **Żółty** = Małe różnice (tolerowane)
- **Czerwony** = Duże różnice! Wymaga sprawdzenia

### 🤖 Zaawansowane Algorytmy

**Pixelmatch:**
- Perceptual image diff
- Anti-aliasing detection
- YIQ color space comparison
- Profesjonalny algorytm używany przez Mapbox, Mozilla, etc.

**OCR + LCS:**
- Tesseract.js dla tekstu
- Longest Common Subsequence
- Radzi sobie z przesunięciami
- Fuzzy matching dla błędów OCR

### 📸 Funkcje Użytkowe
- **Kamera z overlay** - Półprzezroczyste pierwsze zdjęcie na podglądzie
- **Wizualne oznaczenia** - Czerwone prostokąty wokół różnic w tekście
- **Mobilny UI** - Duże przyciski, przyjazny dla telefonu
- **Działa offline** - Po pierwszym ładowaniu nie wymaga internetu
- **100% Prywatność** - Wszystko przetwarza się lokalnie w przeglądarce

## 🚀 Jak używać

### Wybierz tryb:
1. **🎯 Hybrydowy** - dla normalnych wydruków z grafiką i tekstem
2. **🖼️ Tylko grafika** - jeśli chcesz sprawdzić tylko kolory/logo
3. **📝 Tylko tekst** - jeśli interesuje Cię tylko tekst

### Dodaj zdjęcia:
**Opcja A: Z kamery** (zalecane)
1. "📷 Zrób foto" przy Proof
2. Zrób zdjęcie proof'u
3. "📷 Zrób foto" przy Maszynie
4. **Widzisz overlay!** - Dopasuj perspektywę
5. Zrób zdjęcie

**Opcja B: Z galerii**
1. "📁 Wybierz" i wgraj proof
2. "📁 Wybierz" i wgraj wydruk z maszyny

### Porównaj:
1. Kliknij **"Porównaj wydruki"**
2. Poczekaj (10-60 sekund)
3. Zobacz wyniki!

## 📊 Interpretacja Wyników

### Ogólne podobieństwo:
- **95-100%** ✅ - Praktycznie identyczne! Drukuj!
- **85-94%** ⚠️ - Małe różnice, sprawdź szczegóły
- **Poniżej 85%** ❌ - Duże różnice! Zatrzymaj druk!

### W trybie Hybrydowym:
- **Podobieństwo wizualne** - Jak podobne są grafiki/kolory (piksele)
- **Podobieństwo tekstu** - Jak podobny jest tekst (słowa)
- **Ogólne podobieństwo** - Kombinacja (60% visual + 40% text)

### Co sprawdzać:
1. **Heatmapę** - Czerwone obszary = problem
2. **Czerwone prostokąty** - Dokładnie gdzie jest różnica w tekście
3. **Szczegółowe różnice** - Lista co się zmieniło

## 🎨 Jak to działa

### Tryb Hybrydowy (Recommended):

**Krok 1: Porównanie wizualne**
1. Obrazy skalowane do tej samej wielkości
2. Algorytm Pixelmatch porównuje każdy piksel
3. Używa YIQ color space (jak ludzkie oko)
4. Tworzy heatmapę: zielony→żółty→czerwony
5. Zwraca % podobieństwa wizualnego

**Krok 2: Porównanie tekstowe**
6. OCR (Tesseract.js) rozpoznaje tekst i pozycje
7. Normalizacja (lowercase, no punctuation, etc.)
8. LCS algorithm znajduje wspólne słowa
9. Fuzzy matching toleruje błędy
10. Zaznacza różnice na zdjęciach
11. Zwraca % podobieństwa tekstowego

**Krok 3: Kombinacja**
12. Ogólne podobieństwo = Visual×60% + Text×40%
13. Pokazuje wszystkie wyniki

### Algorytm Pixelmatch:

```javascript
// Dla każdego piksela:
1. Oblicz różnicę kolorów w YIQ space
2. Sprawdź anti-aliasing
3. Jeśli różnica > threshold:
   - Oblicz intensywność różnicy
   - Zielony (OK) / Żółty (małe) / Czerwony (duże)
4. Zwróć heatmapę + % podobieństwa
```

### Algorytm LCS (Tekst):

```javascript
// Dla tekstu:
1. Podziel na słowa
2. Dynamic programming - LCS table
3. Backtrack żeby znaleźć różnice:
   - "delete" = jest w proof, brak w wydruku
   - "insert" = brak w proof, jest w wydruku
   - "equal" = identyczne (fuzzy match OK)
4. Zaznacz różnice na obrazach
```

## 🔧 Technologie

- **Pixelmatch** - Perceptual image diff algorithm
- **Tesseract.js** - OCR engine (Polski język!)
- **LCS Algorithm** - Longest Common Subsequence
- **YIQ Color Space** - Perceptual color comparison
- **Levenshtein Distance** - Fuzzy text matching
- **HTML5 Canvas** - Image processing & annotations
- **JavaScript ES6+** - All logic runs client-side

## 📱 Wskazówki

### Dla najlepszych wyników:

**Zdjęcia:**
- Dobre oświetlenie (równomierne, bez cieni)
- Ostre zdjęcia (nie poruszone)
- Podobna perspektywa (użyj overlay!)
- Caływydruk w kadrze

**Tryb Hybrydowy:**
- Użyj gdy masz grafiki + tekst
- Najdokładniejszy ale najdłuższy
- Sprawdzi WSZYSTKO

**Tryb Grafika:**
- Gdy chcesz sprawdzić tylko kolory/logo
- Ignoruje tekst - szybszy
- Zobacz heatmapę gdzie są różnice

**Tryb Tekst:**
- Gdy masz dużo tekstu, mało grafiki
- Najszybszy OCR
- Ignoruje kolory i grafiki

## ⚠️ Ograniczenia

**OCR:**
- Nie jest 100% dokładny
- Problemy: mały tekst, słaba jakość, specjalne fonty, odblaski

**Visual Comparison:**
- Wymaga podobnej perspektywy (użyj overlay!)
- Duże różnice w kącie mogą dawać fałszywe alarmy
- Zdjęcia muszą być tej samej orientacji

**Ogólne:**
- Pierwsze uruchomienie wymaga internetu (model OCR)
- Przetwarzanie: 10-60 sekund (zależy od rozmiaru)
- Duże zdjęcia = wolniejsze ale dokładniejsze

## 💡 Rozwiązywanie Problemów

**Heatmapa cała czerwona mimo że wydruki OK:**
- Zdjęcia z bardzo różnych kątów
- Użyj overlay przy drugim zdjęciu!
- Albo zmień tryb na "Tylko tekst"

**Niskie podobieństwo mimo że OK:**
- Sprawdź czy obrazy są tej samej orientacji
- OCR może mieć problem z fontem
- Sprawdź heatmapę/prostokąty gdzie dokładnie są różnice

**Za wolno:**
- Zmniejsz rozdzielczość zdjęć
- Użyj trybu "Tylko tekst" (najszybszy)
- Wyłącz inne aplikacje

**Kamera nie działa:**
- Sprawdź uprawnienia w przeglądarce
- Spróbuj opcji "Wybierz" zamiast kamery

**Overlay niewidoczny:**
- Zwiększ przezroczystość suwakiem
- Upewnij się że najpierw wgrałeś proof
- Overlay działa tylko przy drugim zdjęciu

## 🎓 FAQ

**Q: Który tryb wybrać?**
A: Hybrydowy dla normalnych wydruków. Grafika dla kolorów. Tekst gdy dużo tekstu.

**Q: Dlaczego 60% visual + 40% text?**
A: Grafika i kolory są ważniejsze (większy wpływ wizualny). Tekst można łatwiej poprawić.

**Q: Co to jest heatmapa?**
A: Kolorowa mapa pokazująca gdzie są różnice. Zielony=OK, Żółty=małe, Czerwony=duże różnice.

**Q: Pixelmatch vs OCR?**
A: Pixelmatch = piksele (kolory, grafiki). OCR = tekst. Hybrydowy = oba!

**Q: Czy mogę użyć na desktop?**
A: Tak! Działa wszędzie. Ale mobilny UI jest zoptymalizowany dla telefonu.

**Q: Czy można porównać skan vs zdjęcie?**
A: Tak! Pixelmatch radzi sobie z różnymi źródłami.

## 📝 Licencja

MIT License - możesz swobodnie używać i modyfikować

---

**Made with 💪 for flexo printers. Drukuj pewnie! 🖨️**
