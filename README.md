# Raport dotyczący wyborów prezydenckich w USA w 2020 roku

<div align="center">

  

  ### [📈 Zobacz interaktywny raport 📈](https://app.powerbi.com/view?r=eyJrIjoiYzc4Y2Y5M2UtY2FjMC00NzY4LTkyYjMtOTdiYjFjMGM1MmNmIiwidCI6IjNkZmU5YWI2LTgxYmYtNDkxYy1iNjcwLTAxYzgyNGEwOWUxOSJ9)

  

</div>

<div align="center">

  

  ### Raport utworzony: 11.2024

  

</div>



### Problem analityczny

Celem projektu było stworzenie narzędzia analitycznego do analizy wyborów prezydenckich w USA 2020, które umożliwiałoby:

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



3. **Electoral voices.xlsx** - informacje o podziale głosów elektorskich



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

   - Usunięcie duplikatów



2. **Tworzenie dodatkowych kolumn**:

   - Kategoryzacja poziomów wykształcenia (niski, średni, wysoki)

   - Wyliczenie frekwencji wyborczej

   - Uproszczenie kategorii rasowych dla celów wizualizacji

   - Dodanie kolumny Index



## 📊 5. Model danych



### Struktura modelu

Model został zbudowany w architekturze gwiazdy, składającej się z następujących tabel:



#### Information (tabela faktów)

- 2020 Democrat vote % i raw

- 2020 Republican vote % i raw

- 2020 other vote % i raw

- State Population vote %



####  Education (tabela wymiarów)

- Associates Degree

- Bachelors Degree

- Graduate or professional degree

- High School graduate and equivalent

- Population with 9th to 12th grade education, no diploma

- Population with less than 9th grade education

- Some College No Degree



####  Electorate Votes (tabela wymiarów)

- Electoral Votes

- Result

- State



####  Race (tabela wymiarów)

- American Indian and Alaska Native percentage

- Asian percentage 

- Black percentage

- Hispanic or Latino percentage

- Native Hawaiian and Other Pacific Islander percentage

- Some Other Race percentage

- Two or More Races percentage

- White percentage



####  Job (tabela wymiarów)

- Percentage engaged in Management, business, science, and arts occupations

- Percentage engaged in Resources and Construction

- Percentage engaged in Sales and Office

- Percentage engaged in Service Occupations

- Percentage engaged in Transportation



####  Income and Income Inequality

- Area in square km

- Density per square km

- Gini Index

- Median income (dollars)

- Mean income (dollars)

- Total Population



####  Estimated Eligible Voters

- Estimated Eligible Voters (OUM)

- State



### Relacje w modelu

- Relacje między tabelami oparte są na wspólnych polach, takich jak stan czy hrabstwo

- Wykorzystano relacje jeden-do-wielu dla optymalnej wydajności zapytań

- Zastosowano jednokierunkowe filtrowanie od tabel wymiarów do tabeli faktów

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



####  Karty z kluczowymi wskaźnikami

- Całkowita populacja: 331 mln

- Liczba uprawnionych do głosowania: 238 mln

- Liczba głosów oddanych na Demokratów: 81 mln (51,21%)

- Liczba głosów oddanych na Republikanów: 74 mln (46,92%)

- Frekwencja wyborcza: 66,53%

- Liczba głosów elektorskich: 306 (Demokraci) vs 232 (Republikanie)



####  Wykresy

- Mapa wyników wyborów według stanów

- Wykres kołowy rozkładu głosów

- Wykres słupkowy poziomu wykształcenia w stanach

- Wykres słupkowy średnich dochodów w stanach

- Diagram kołowy struktury zatrudnienia

- Diagram kołowy składu rasowego



####  Mapy

- Mapa gęstości zaludnienia

- Mapa wyników wyborów w poszczególnych stanach



### Interaktywność

- Filtry stanów dostępne na wszystkich stronach

- Przycisk "Clear All Slicers" do resetowania filtrów

- Cross-filtering między wizualizacjami

- Menu nawigacyjne do przełączania między stronami



## 💡 Wnioski i rekomendacje



### Kluczowe obserwacje



####  Wyniki wyborów

- Joe Biden zwyciężył zdobywając 81 mln głosów (51,21%) i 306 głosów elektorskich

- Donald Trump uzyskał 74 mln głosów (46,92%) i 232 głosy elektorskie

- Pozostali kandydaci otrzymali łącznie 3 mln głosów (1,87%)



#### Wykształcenie i dochody

- Struktura wykształcenia w USA:

  - Niski poziom: 11,65%

  - Średni poziom: 55,25%

  - Wysoki poziom: 33,11%

- Wskaźnik Giniego wynosi średnio 0,45

- Mediana dochodów: $62 tys.

- Średnia dochodów: $83 tys.

- Widoczna korelacja między wyższym poziomem wykształcenia i dochodów a poparciem dla Demokratów



#### Struktura zatrudnienia i rasowa

- Największy sektor zatrudnienia: zarządzanie, biznes, nauka i sztuka (34,18%)

- Dominująca grupa rasowa: biali (74,15%)

- Mniejszości etniczne: Latynosi (9,79%), Czarni (8,58%), inne rasy (7,48%)

- Widoczne różnice preferencji wyborczych między grupami rasowymi



## ⚙️ Aspekty techniczne



### Zastosowane funkcje DAX



```dax

Total Population = CALCULATE(SUM('Income and income inequality'[Total Population]))



Number of voters = 

CALCULATE(

    SUM('Information'[2020 Democrat vote raw]) 

    + 

    SUM('Information'[2020 Republican vote raw])

    +

    SUM('Information'[2020 other vote raw]))



Voter turnout = 

DIVIDE([Number of voters],SUM('Estimated Eligible Voters'[Estimated Eligible Voters (CVAP)]))



Low level of education =

CALCULATE (

    AVERAGE ( Education[Population with 9th to 12th grade education, no diploma] )

        + AVERAGE ( Education[Population with less than 9th grade education] )

)



Medium Education Level =

CALCULATE (

    AVERAGE ( Education[High School graduate and equivalent] )

        + AVERAGE ( Education[Some College,No Degree] )

)



High Education Level =

CALCULATE (

    AVERAGE ( Education[Associates Degree] )

        + AVERAGE ( Education[Bachelors Degree] )

        + AVERAGE ( Education[Graduate or professional degree] )

)

```



## 📝 Podsumowanie



Projekt dostarcza kompleksowej analizy wyborów prezydenckich w USA w 2020 roku, umożliwiając badanie wyników oraz ich korelacji z różnorodnymi czynnikami demograficznymi i ekonomicznymi. Interaktywny charakter raportu pozwala użytkownikom na samodzielne eksplorowanie danych i wyciąganie wniosków.



Analiza ujawnia zależności między poziomem wykształcenia, dochodami, strukturą zatrudnienia i składem rasowym a preferencjami wyborczymi.
