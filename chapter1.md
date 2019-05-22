---
title: 'Teaching Case: Kundendaten analysieren'
description: 'Unternehmen xy'
free_preview: true
---

## Einstieg/Problemstellung

```yaml
type: VideoExercise
key: 53fc87b3e9
xp: 50
```

`@projector_key`
9436e4b892a60157f6c0d6eeefacb82f

---

## Lasst uns anfangen

```yaml
type: NormalExercise
key: 03845bca80
xp: 100
```

Erste Schritte, um R 'hands-on' zu lernen und anzuwenden.
Hier sehen Sie den Data Science Zyklus. Diesen werden wir Schritt für Schritt anhand der Datensätze von Kundendaten aus zwei verschiedenen Datenbanken des Informationssystems der Firma XY durchgehen.

![1](https://assets.datacamp.com/production/repositories/4810/datasets/82d92f41d7649657073e1e2e0b813011ecc4973a/Data_Science_Explore.png)

(Quelle: Wickham/Grolemund 2018, S.XI)

`@instructions`
Willkommen in der Programmierumgebung DataCamp. Lassen Sie uns nun direkt mit dem Importieren der Datensätze loslegen. 

Datensätze können in R auf verschiedenste Weise importiert werden. Um Daten aus Exceltabellen, die als csv-Dateien abgespeichert werden und csv-Dateien zu importieren, gibt es zwei gängige Möglichkeiten: 

1) read.csv 	(Komma 		(,) separierte Dateien)

2) read.csv2 	(Semikolon  (;) separierte Dateien)

Zuerst lesen Sie das zu bearbeitende Datenset ein. Es liegt unter diesem Pfad semikolongetrennt ab: 

"https://assets.datacamp.com/production/repositories/4810/datasets/b0a840d5f44b82de92a6ef65ca83a4f605c27c95/Kundendaten1.csv"

`@hint`
Nutze die Funktion #read.csv2() (Mithilfe dieser Funktion lesen Sie den externen Datensatz ein, der mit Semikolon getrennt vorliegt)

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Bitte Daten einlesen

# Speichert den Datensatz in die Variable Kundendaten:

```

`@solution`
```{r}
# Bitten Datensatz Kundendaten einlesen:
read.csv2("https://assets.datacamp.com/production/repositories/4810/datasets/b0a840d5f44b82de92a6ef65ca83a4f605c27c95/Kundendaten1.csv")
# Speichert den Datensatz in die Variable Kundendaten:
Kundendaten <- read.csv2("https://assets.datacamp.com/production/repositories/4810/datasets/b0a840d5f44b82de92a6ef65ca83a4f605c27c95/Kundendaten1.csv")
```

`@sct`
```{r}

```

---

## Daten erkunden

```yaml
type: TabExercise
key: 0d46e0ab5e
xp: 100
```

Schauen Sie sich die Daten zuerst an und verschaffen Sie sich einen Überblick, was an Datentypen und Werten vorliegt.

Nützliche Funktionen für die Datenerkundung in R sind:
- **nrow()** | **ncol()**: nrow and ncol gibt die Anzahl der Zeilen und Spalen in x zurück. Nrow und ncol behandeln einen Vektor genauso wie eine 1-spaltige Matrix.
- **names()**: Funktionen zum Abrufen oder Einstellen der Namen eines Objekts.
- **colnames()**: Abrufen oder setzen der Zeilen- oder Spaltennamen eines matrixartigen Objekts.
- **head()** | **tail()**: Liefert den ersten oder letzten Teil eines Vektors, einer Matrix, einer Tabelle, eines Datenrahmens oder einer Funktion.
- **str()**: Erstellt eine kompakte Darstellung der internen Struktur eines R-Objekts.
- **summary()**: Ist eine generische Funktion, um Ergebniszusammenfassungen zu erstellen.

(Quelle: R Dokumentation)

`@pre_exercise_code`
```{r}
Kundendaten <- read.csv2("https://assets.datacamp.com/production/repositories/4810/datasets/b0a840d5f44b82de92a6ef65ca83a4f605c27c95/Kundendaten1.csv")
```

***

```yaml
type: NormalExercise
key: 1f782c2882
xp: 35
```

`@instructions`
Wie viele Zeilen gibt es? Wie viele Spalten sind im Datensatz vorhanden?

`@hint`
Nutzen Sie bitte die Funktionen nrow() und ncol()

`@sample_code`
```{r}
# 1.Wie viele Zeilen gibt es?

# 2.Wie viele Spalten gibt es?

```

`@solution`
```{r}
# 1.Wie viele Zeilen gibt es?
nrow(Kundendaten)
# 2.Wie viele Spalten gibt es?
ncol(Kundendaten)
```

`@sct`
```{r}
ex() %>% check_code("nrow(Kundendaten)", fixed=TRUE, missing_msg= "Da stimmt etwas bei dem Code für die Zeilen nicht!")
success_msg("Super, es liegen 100 Zeilen vor!")
ex() %>% check_code("ncol(Kundendaten)", fixed=TRUE, missing_msg= "Da stimmt etwas bei dem Code für die Spalten nicht!")
success_msg("Super, es liegen 4 Zeilen vor!")
```

***

```yaml
type: NormalExercise
key: 575b66e79b
xp: 35
```

`@instructions`
Jetzt wissen Sie, wie groß der Datensatz ist. Verschaffen Sie sich bitte einen Überblick über die obersten und untersten Werte, die in den Kundendaten enthalten sind, um sich einen Überblick zu verschaffen und mögliche Ausreißer, besonders profitable bzw. unprofitable Kunden zu identifizieren.

`@hint`
Nutzen Sie die Funktionen **head()** und **tail()**

`@sample_code`
```{r}
# Obersten Werte



# Untersten Werte



```

`@solution`
```{r}
# Obersten Werte
head(Kundendaten)
# Untersten Werte
tail(Kundendaten)
```

`@sct`
```{r}
ex() %>% check_code("head(Kundendaten)", fixed=TRUE, missing_msg= "Da stimmt etwas bei dem Code für die obersten Werte nicht!")
success_msg("Richtig gecodet!")
ex() %>% check_code("tail(Kundendaten)", fixed=TRUE, missing_msg= "Da stimmt etwas bei dem Code für die untersten Werte nicht!")
success_msg("Richtig gecodet!") 
```

***

```yaml
type: NormalExercise
key: 9a4a85ca58
xp: 30
```

`@instructions`


`@hint`


`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```
