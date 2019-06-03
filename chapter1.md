---
title: 'Teaching Case: Kundendaten analysieren'
description: 'Unternehmen xy'
free_preview: true
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

Lesen Sie bitte zuerst das zu bearbeitende Datenset ein. Es liegt unter diesem Pfad semikolongetrennt ab: 

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
ex() %>% check_code(read.csv2("https://assets.datacamp.com/production/repositories/4810/datasets/b0a840d5f44b82de92a6ef65ca83a4f605c27c95/Kundendaten1.csv")), fixed=TRUE, missing_msg= "Verwenden Sie bitte den Link aus der Instruktionsbox und weisen Sie ihn bitte zu")
success_msg("Super - weiter geht´s, wir haben keine Zeit zu verlieren!")
```

---

## Daten erkunden

```yaml
type: TabExercise
key: 0d46e0ab5e
xp: 100
```

Schauen Sie sich die Daten zuerst an und verschaffen Sie sich einen Überblick, was an Datentypen und Werten vorliegt. Schauen Sie sich bitte die Ausgabe in der Console genau an.

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
Wir sind immer noch in dem Schritt, die Daten genau zu erkunden, um einen Überblick zu gewinnen und zu schauen, in welcher Qualität die Daten vorliegen. Welche der Funktionen, die vorgestellt wurden, eignen sich dafür zum Abschluss noch?

`@hint`
Um Ergebniszusammenfassungen zu bekommen eigent sich die Funktion: **summary()** oder alternativ auch **str()**

`@sample_code`
```{r}
# Gesamtüberblick

```

`@solution`
```{r}
# Gesamtüberblick
summary(Kundendaten)
```

`@sct`
```{r}
#ex() %>% check_object(summmary()) %>% check_equal(summary(Kundendaten))
ex() %>% check_code(c("summary(Kundendaten)", "str(Kundendaten)"), fixed = TRUE, missing_msg= "Da stimmt etwas mit Ihrer Codeeingabe nicht!")
success_msg("Glückwunsch, jetzt müssten Sie einen Überblick über die Daten bekommen haben!")
```

---

## Check: Auffälligkeiten entdeckt?

```yaml
type: PureMultipleChoiceExercise
key: 058cc56f4a
xp: 50
```

Der Chef von Ihnen fragt Sie, ob Sie Auffälligkeiten entdeckt haben oder der Datensatz zu weiteren Analyse schon verwendbar sei.
Was sagen Sie Ihm?
Achtung: Es ist nur **eine** Möglichkeit richtig! Lesen Sie bitte genau und wählen danach eine Antwort aus.

- 1 : Ja, der Datensatz Kundendaten ist für die Analyse fertig bereinigt und enthält keine Auffälligkeiten
- 2 : Nein, es sind fehlende Werte enthalten
- 3 : Nein, es gibt Ausreißerwerte bei dem Umsatz, die kommen mir nicht realistisch vor.
- 4 : Nein, es gibt unrealistische Werte bei dem Umsatzdaten einzelner Kunden und es sind fehlende Werte im Datensatz enthalten.
- 5 : Sorry Chef, ich habe keinen Überlick gewonnen und bin mir nicht sicher.

`@hint`


`@possible_answers`
- 1
- 2
- 3
- [4]
- 5

`@feedback`
- "Nein, da haben Sie viele Werte und Auffälligkeiten übersehen. Sie müssen genauer arbeiten.
- "Nein. Sie liegen schon richtig, nur haben Sie eine Kombination übersehen. Es liegen zusätzlich Umsatzausreißer vor."
- "Nein. Sie liegen schon richtig, nur haben Sie eine Kombination übersehen. Es liegen zusätzlich fehlende Werte vor."
- "Ja, sehr gut! Sie haben sehr aufmerksam die Daten erkundet."
- "Naja, dann aber beim nächsten mal bitte genauer!""

---

## Daten bereinigen

```yaml
type: NormalExercise
key: 5320ec596c
xp: 100
```

Das Aufräumen bzw. **bereinigen** Ihrer Daten bedeutet, sie in einer konsistenten Form zu speichern, die der Semantik des Datensatzes mit der Art der Speicherung entspricht. Kurz gesagt, wenn Ihre Daten bereinigt sind, ist jede Spalte eine Variable und jede Zeile ist eine Beobachtung. Das Bereinigen (tidying) ist wichtig, weil die einheitliche Struktur es Ihnen ermöglicht Ihren Fokus auf die Fragen zu den Daten zu konzentrieren 
(Wickham/Grolemund 2018, S.X).

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Transformieren

```yaml
type: NormalExercise
key: 92e156a006
xp: 100
```

Der nächste übliche Schritt nach der Bereinigung der Daten (Tidying) ist es, die Daten zu **transformieren**. Dazu gehört die Einschränkung des Datensatzes auf das Analyseinteresse, die Erstellung neuer Variablen, die Funktionen bestehender Variablen sind und die Berechnung eines Satzes von zusammenfassenden Statistiken (counts, means, ...).
(Wickham/Grolemund 2018, S.X)

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Visualisieren

```yaml
type: NormalExercise
key: b7d775e42f
xp: 100
```

Die **Visualisierung** ist eine grundlegende menschliche Aktivität und zeigt Ihnen Erkenntnisse, die Sie nicht erwartet hatten oder lässt Sie neue Fragen an die Daten stellen.Eine gute Visualisierung könnte auch darauf hinweisen, dass Sie die falschen Fragen stellen oder dass Sie andere Daten sammeln müssen. Die Visualisierung lässt Sie Daten besser interpretieren, jedoch skaliert sie nicht immer gut, da sie von Menschen in den häuftigsten Fällen für kontextbasierte und individuelle Sachverhalte angefragt wird.
(Wickham/Grolemund 2018, S.X)

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## (Modellieren)

```yaml
type: NormalExercise
key: ed35be43fd
xp: 100
```

**Modelle** sind ergänzende Werkzeuge zur Visualisierung. Wenn Sie Ihre Fragen ausreichend präzise (mathematisch) formuliert haben, können Sie sie mit einem Modell beantworten. Modelle skalieren den Wert, weil sie Rechenwerkzeuge sind. Aber jedes Modell beinhaltet Annahmen und von Natur aus kann ein Modell seine eigenen Annahmen nicht in Frage stellen. Das bedeutet, dass ein Model Sie nicht fudamental überraschen kann.
(Wickham/Grolemund 2018, S.X)

`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

```

---

## Welche Erkenntnisse durch die Datenanalyse haben Sie gewonnen?

```yaml
type: PureMultipleChoiceExercise
key: 8d0168008a
xp: 50
```



`@hint`


`@possible_answers`


`@feedback`


---

## Kommunizieren: Führungskräftemeeting

```yaml
type: PureMultipleChoiceExercise
key: c8e7e2efe2
xp: 50
```

Der letzte Schritt eines Data Science Projektes ist die **Kommunikation**. Ein absolut erfolgskritischer Teil eines jeden Datenanalyseprojektes. Es spielt keine Rolle, wie gut Ihre Modelle und Visualisierungen Sie dazu gebracht haben, die Daten zu verstehen, es sei denn, Sie können die Ergebnisse auch an andere verständlich weitergeben und (ökonomischen) Wert damit generieren.
(Quelle: Wickham/Grolemund 2018, S.X)

`@hint`


`@possible_answers`


`@feedback`
