# 📊 Dokumentacja raportu analizy wyborów prezydenckich w USA 2020
<div align="center">
  
  ### [📈 Zobacz interaktywny raport 📈]()
  
</div>
<div align="center">
  
  ### Raport utworzony: 11.2024
  
</div>

### Problem analityczny
Celem projektu było stworzenie kompleksowego narzędzia analitycznego do analizy wyborów prezydenckich w USA 2020, które umożliwiałoby:
- Przegląd wyników wyborczych na poziomie stanów i hrabstw
- Analizę korelacji między wynikami wyborów a czynnikami demograficznymi
- Wizualizację zależności między poziomem wykształcenia, dochodami a preferencjami wyborczymi
- Zbadanie struktury zatrudnienia i składu rasowego w kontekście wyników wyborczych

### Główne pytania analityczne
1. Jak kształtowała się frekwencja wyborcza i jak rozkładały się głosy między głównych kandydatów?
2. Jaki był rozkład głosów wyborczych i elektorskich w poszczególnych stanach?
3. Jakie korelacje istnieją między poziomem wykształcenia a wynikami wyborów?
4. Czy istnieje związek między poziomem dochodów a preferencjami wyborczymi?
5. Jak struktura zatrudnienia i skład rasowy wpływały na wyniki wyborów?

## 💾 Źródła danych

### Opis danych
Głównymi źródłami danych były pliki:

1. **US_Election_dataset_v1.csv** - główny zbiór danych zawierający:
   - Dane wyników wyborów na poziomie hrabstw
   - Informacje demograficzne
   - Wskaźniki ekonomiczne
   - Poziomy wykształcenia
   - Dane o strukturze zatrudnienia i rasowej

2. **Estimated Eligible Voters.xlsx** - dane o liczbie uprawnionych do głosowania

3. **Głosy elektorskie.xlsx** - informacje o podziale głosów elektorskich

### Najważniejsze zmienne w zbiorze danych
- county, state - nazwy hrabstw i stanów
- 2020 Democrat/Republican vote raw/% - liczby i procenty głosów
- Population with various education levels - dane o poziomach wykształcenia
- Gini Index - wskaźnik nierówności dochodów
- Median/Mean income - dane o dochodach
- Total Population - całkowita populacja
- Percentage engaged in various occupations - struktura zatrudnienia
- Racial composition percentages - struktura rasowa

## 🔄 Proces przygotowania danych

### Transformacje w Power Query
1. **Czyszczenie danych**:
   - Standaryzacja nazw stanów i hrabstw
   - Konwersja formatów liczbowych
   - Usunięcie duplikatów i obsługa wartości null
   - Agregacja danych na poziomie stanów

2. **Tworzenie dodatkowych kolumn**:
   - Kategoryzacja poziomów wykształcenia (niski, średni, wysoki)
   - Wyliczenie frekwencji wyborczej
   - Uproszczenie kategorii rasowych dla celów wizualizacji

### Model danych
Model zawiera następujące główne tabele:

#### 🗳️ US_Election (tabela faktów)
- Dane wyborcze
- Wskaźniki demograficzne
- Dane ekonomiczne

#### 🏛️ States (tabela wymiarów)
- State
- Electoral Votes
- Region

#### 📚 Education_Levels (tabela wymiarów)
- Education Level Group
- Description

#### 👥 Race_Categories (tabela wymiarów)
- Race Category
- Description

Model wykorzystuje schemat gwiazdy dla optymalnej wydajności i elastyczności analitycznej.

## 📈 Wizualizacje i analizy

### Struktura raportu
Raport składa się z 6 głównych stron:

1. **Landing Page (LP)** - strona nawigacyjna z logo i przyciskami
2. **Basic information** - podstawowe wskaźniki dotyczące populacji i wyborów
3. **A short profile of the candidates** - profile Joe Bidena i Donalda Trumpa
4. **Election results** - szczegółowa analiza wyników wyborów
5. **Education level and income** - analiza poziomu wykształcenia i dochodów
6. **Employment structure and racial composition** - analiza struktury zatrudnienia i składu rasowego

### Kluczowe wizualizacje

#### 📊 Karty z kluczowymi wskaźnikami
- Całkowita populacja: 331 mln
- Liczba uprawnionych do głosowania: 238 mln
- Liczba głosów oddanych na Demokratów: 81 mln (51,21%)
- Liczba głosów oddanych na Republikanów: 74 mln (46,92%)
- Frekwencja wyborcza: 66,53%
- Liczba głosów elektorskich: 306 (Demokraci) vs 232 (Republikanie)

#### 📉 Wykresy
- Mapa wyników wyborów według stanów
- Wykres kołowy rozkładu głosów
- Wykres słupkowy poziomu wykształcenia w stanach
- Wykres słupkowy średnich dochodów w stanach
- Diagram kołowy struktury zatrudnienia
- Diagram kołowy składu rasowego

#### 🗺️ Mapy
- Mapa gęstości zaludnienia
- Mapa wyników wyborów w poszczególnych stanach

### Interaktywność
- Filtry stanów dostępne na wszystkich stronach
- Przycisk "Clear All Slicers" do resetowania filtrów
- Cross-filtering między wizualizacjami
- Menu nawigacyjne do przełączania między stronami

## 💡 Wnioski i rekomendacje

### Kluczowe obserwacje

#### 🗳️ Wyniki wyborów
- Joe Biden zwyciężył zdobywając 81 mln głosów (51,21%) i 306 głosów elektorskich
- Donald Trump uzyskał 74 mln głosów (46,92%) i 232 głosy elektorskie
- Pozostali kandydaci otrzymali łącznie 3 mln głosów (1,87%)

#### 📚 Wykształcenie i dochody
- Struktura wykształcenia w USA:
  - Niski poziom: 11,65%
  - Średni poziom: 55,25%
  - Wysoki poziom: 33,11%
- Wskaźnik Giniego wynosi średnio 0,45
- Mediana dochodów: $62 tys.
- Średnia dochodów: $83 tys.
- Widoczna korelacja między wyższym poziomem wykształcenia i dochodów a poparciem dla Demokratów

#### 👥 Struktura zatrudnienia i rasowa
- Największy sektor zatrudnienia: zarządzanie, biznes, nauka i sztuka (34,18%)
- Dominująca grupa rasowa: biali (74,15%)
- Mniejszości etniczne: Latynosi (9,79%), Czarni (8,58%), inne rasy (7,48%)
- Widoczne różnice preferencji wyborczych między grupami rasowymi

### Rekomendacje

#### 📋 Dla analityków politycznych
- Pogłębienie analizy na poziomie hrabstw w kluczowych swing states
- Zbadanie zmian preferencji wyborczych w porównaniu z poprzednimi wyborami
- Analiza wpływu pandemii COVID-19 na frekwencję i preferencje wyborcze

#### 🏬 Dla strategów kampanii
- Dostosowanie komunikacji do specyfiki demograficznej poszczególnych stanów
- Skupienie uwagi na grupach o niższej frekwencji wyborczej
- Wykorzystanie danych o strukturze zatrudnienia i wykształcenia do lepszego targetowania przekazów

#### 🚀 Dla rozwoju modelu
- Włączenie danych z wcześniejszych wyborów dla analizy trendów
- Dodanie danych o wydatkach kampanijnych
- Rozbudowanie analizy o dane z mediów społecznościowych

## ⚙️ Aspekty techniczne

### Zastosowane funkcje DAX

```dax
Total Population = SUM(US_Election[Total Population])

Total Votes = SUM(US_Election[2020 Democrat vote raw]) + SUM(US_Election[2020 Republican vote raw]) + SUM(US_Election[2020 other vote raw])

Voter Turnout % = DIVIDE([Total Votes], [Estimated Eligible Voters], 0) * 100

Low Education Level % = 
    SUMX(
        US_Election,
        VALUE(SUBSTITUTE(US_Election[Population with less than 9th grade education], ",", "")) +
        VALUE(SUBSTITUTE(US_Election[Population with 9th to 12th grade education, no diploma], ",", ""))
    ) / [Total Population] * 100

Medium Education Level % = 
    SUMX(
        US_Election,
        VALUE(SUBSTITUTE(US_Election[High School graduate and equivalent], ",", "")) +
        VALUE(SUBSTITUTE(US_Election[Some College,No Degree], ",", "")) +
        VALUE(SUBSTITUTE(US_Election[Associates Degree], ",", ""))
    ) / [Total Population] * 100

High Education Level % = 
    SUMX(
        US_Election,
        VALUE(SUBSTITUTE(US_Election[Bachelors Degree], ",", "")) +
        VALUE(SUBSTITUTE(US_Election[Graduate or professional degree], ",", ""))
    ) / [Total Population] * 100
```

### Optymalizacja wydajności
1. Zastosowanie schematu gwiazdy
2. Tworzenie miar zagregowanych
3. Efektywne wykorzystanie kontekstu filtra
4. Utworzenie indeksów dla najczęściej filtrowanych kolumn

## 📝 Podsumowanie

Projekt dostarcza kompleksowej analizy wyborów prezydenckich USA 2020, umożliwiając badanie wyników oraz ich korelacji z różnorodnymi czynnikami demograficznymi i ekonomicznymi. Interaktywny charakter raportu pozwala użytkownikom na samodzielne eksplorowanie danych i wyciąganie wniosków.

Analiza ujawnia interesujące zależności między poziomem wykształcenia, dochodami, strukturą zatrudnienia i składem rasowym a preferencjami wyborczymi. Raport stanowi cenne narzędzie dla analityków politycznych, badaczy, dziennikarzy oraz wszystkich zainteresowanych zrozumieniem dynamiki amerykańskich wyborów prezydenckich.

Przyszłe rozwinięcia projektu mogłyby obejmować analizę historyczną trendów wyborczych, modelowanie predykcyjne na potrzeby przyszłych wyborów oraz pogłębione analizy konkretnych grup demograficznych i geograficznych.
