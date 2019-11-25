---
title: Maschinelles Lernen – Glossar
description: Ein Glossar mit wichtigen Begriffen aus dem Machine Learning-Bereich, die Sie bei der Erstellung benutzerdefinierter Modelle unterstützen.
ms.custom: seodec18
ms.topic: reference
ms.date: 07/31/2019
ms.openlocfilehash: bd4f2db701f537d5c87529115a6bd44035432534
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977286"
---
# <a name="machine-learning-glossary-of-important-terms"></a>Machine Learning-Glossar mit wichtigen Begriffen

Die folgende Liste ist eine Zusammenstellung wichtiger Begriffe aus dem Machine Learning-Bereich, die Sie bei der Erstellung benutzerdefinierter Modelle in ML.NET unterstützen.

## <a name="accuracy"></a>Genauigkeit

Bei der [Klassifizierung](#classification) ist die Genauigkeit die Anzahl der korrekt klassifizierten Elemente dividiert durch die Gesamtzahl der Elemente in der Testgruppe. Sie reicht von 0 (ungenau) bis 1 (am genauesten). Die Genauigkeit ist eine der Auswertungsmetriken für die Leistung Ihres Modells. Betrachten Sie sie in Verbindung mit [Präzision](#precision), [Wiedererkennung](#recall) und [F-Wertung](#f-score).

## <a name="area-under-the-curve-auc"></a>Fläche unter der Kurve (Area under the curve, AUC)

Bei der [binären Klassifizierung](#binary-classification) ist diese Auswertungsmetrik der Wert der Fläche unter der Kurve, der das Verhältnis der richtig positiven Ergebnisse (auf der Y-Achse) zu den falsch positiven Ergebnissen (auf der X-Achse) darstellt. Er reicht von 0,5 (schlechteste) bis 1 (beste). Auch bekannt als die Fläche unter der ROC-Kurve, d.h. unter der Grenzwertoptimierungskurve (Receiver Operating Characteristic Curve). Weitere Informationen finden Sie auf Wikipedia im Artikel zu [Receiver Operating Characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic).

## <a name="binary-classification"></a>Binäre Klassifizierung

Ein [Klassifizierungsfall](#classification), bei dem die [Bezeichnung](#label) nur eine von zwei Klassen ist. Weitere Informationen finden Sie im Abschnitt [Binäre Klassifizierung](tasks.md#binary-classification) des Artikels [Machine Learning-Aufgaben](tasks.md).

## <a name="calibration"></a>Kalibrierung

Die Kalibrierung ist der Prozess der Zuordnung einer unformatierten Bewertung zu einer Klassenzugehörigkeit für die binäre und Multiklassenklassifizierung. Einige ML.NE-Trainer haben ein `NonCalibrated`-Suffix. Diese Algorithmen erzeugen eine unformatierte Bewertung, die dann einer Klassenwahrscheinlichkeit zugeordnet werden muss.

## <a name="catalog"></a>Catalog

In ML.NET ist ein Katalog eine Sammlung von Erweiterungsfunktionen, die nach einem gemeinsamen Zweck gruppiert sind.

Jede Machine Learning-Aufgabe (binäre Klassifizierung, Regression, Bewertung usw.) besitzt einen Katalog mit verfügbaren Machine Learning-Algorithmen (Trainer). Der Katalog für die Trainer der binären Klassifizierung ist: <xref:Microsoft.ML.BinaryClassificationCatalog.BinaryClassificationTrainers>.

## <a name="classification"></a>Klassifizierung

Wenn die Daten zur Vorhersage einer Kategorie verwendet werden, wird der [überwachte Task für maschinelles Lernen](#supervised-machine-learning) als Klassifizierung bezeichnet. Die [binäre Klassifizierung](#binary-classification) bezieht sich auf die Vorhersage von nur zwei Kategorien (z.B. die Klassifizierung eines Bilds als Bild einer „Katze“ oder eines „Hunds“). Die [Multiklassenklassifizierung](#multiclass-classification) bezieht sich auf die Vorhersage mehrerer Kategorien (z.B. bei der Klassifizierung eines Bilds als Bild einer bestimmten Hunderasse).

## <a name="coefficient-of-determination"></a>Bestimmtheitsmaß

Bei der [Regression](#regression) gibt diese Auswertungsmetrik an, wie gut Daten in ein Modell passen. Die Werte liegen zwischen 0 und 1. Ein Wert von 0 bedeutet, dass die Daten zufällig sind oder nicht an das Modell angepasst werden können. Ein Wert von 1 bedeutet, dass das Modell exakt mit den Daten übereinstimmt. Dies wird oft als r<sup>2</sup>, R<sup>2</sup> oder R-Quadrat bezeichnet.

## <a name="data"></a>Daten

Daten sind für alle Machine Learning-Anwendungen von zentraler Bedeutung. In ML.NET werden Daten durch <xref:Microsoft.ML.IDataView>-Objekte dargestellt. Datenansichtsobjekte:

- bestehen aus Zeilen und Spalten
- werden verzögert ausgewertet, d.h. Daten werden nur geladen, wenn sie durch einen Vorgang aufgerufen werden
- enthalten ein Schema, das den Typ, das Format und die-Länge der einzelnen Spalten definiert

## <a name="estimator"></a>Estimator

Eine Klasse in ML.NET, die die <xref:Microsoft.ML.IEstimator%601>-Schnittstelle implementiert.

Ein Estimator ist eine Spezifikation einer Transformation (sowohl Transformation der Datenaufbereitung als auch Transformation des Machine Learning-Modells). Estimators können zu einer Pipeline von Transformationen verkettet werden. Die Parameter eines Estimators oder einer Estimatorpipeline werden gelernt, wenn <xref:Microsoft.ML.IEstimator`1.Fit*> aufgerufen wird. Das Ergebnis des <xref:Microsoft.ML.IEstimator`1.Fit*> ist ein [Transformator](#transformer).

## <a name="extension-method"></a>Erweiterungsmethode

Eine.NET-Methode, die zu einer Klasse gehört, aber außerhalb der Klasse definiert ist. Der erste Parameter einer Erweiterungsmethode ist ein statischer `this`-Verweis auf die Klasse, zu der die Erweiterungsmethode gehört.

Erweiterungsmethoden werden in ML.NET häufig verwendet, um Instanzen von [Estimators](#estimator) zu konstruieren.

## <a name="feature"></a>Feature

Eine messbare Eigenschaft des zu messenden Phänomens, typischerweise ein numerischer Wert (double). Mehrere Funktionen werden als **Funktionsvektor** bezeichnet und typischerweise als `double[]` gespeichert. Funktionen definieren die wichtigen Eigenschaften des zu messenden Phänomens. Weitere Informationen finden Sie auf Wikipedia im Artikel zum Thema [Funktion](https://en.wikipedia.org/wiki/Feature_(machine_learning)).

## <a name="feature-engineering"></a>Funktionsentwicklung

Als Funktionsentwicklung wird der Prozess bezeichnet, bei dem eine Reihe von [Funktionen](#feature) definiert und eine Software entwickelt wird, die aus den verfügbaren Phänomendaten Funktionsvektoren erzeugt, auch Funktionsextraktion genannt. Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Funktionsentwicklung](https://en.wikipedia.org/wiki/Feature_engineering).

## <a name="f-score"></a>F-Wertung

Bei der [Klassifizierung](#classification) ist dies eine Auswertungsmetrik, die [Präzision](#precision) und [Wiedererkennung](#recall) ausgleicht.

## <a name="hyperparameter"></a>Hyperparameter

Ein Parameter eines Algorithmus für maschinelles Lernen. Beispiele sind die Anzahl der zu erlernenden Bäume in einem Entscheidungswald oder die Schrittgröße in einem Gradientenverfahrenalgorithmus. Werte von *Hyperparametern* werden vor dem Training des Modells festgelegt und regeln die Suche nach Parametern der Vorhersagefunktion, z.B. der Vergleichspunkte in einem Entscheidungsbaum oder der Gewichtungen in einem linearen Regressionsmodell. Weitere Informationen finden Sie auf Wikipedia im Artikel zum Thema [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)).

## <a name="label"></a>Bezeichnung

Das Element, das mit dem Modell für maschinelles Lernen vorhergesagt werden soll. Zum Beispiel die Hunderasse oder ein zukünftiger Aktienkurs.

## <a name="log-loss"></a>Protokollverlust

Bei der [Klassifizierung](#classification) charakterisiert diese Auswertungsmetrik die Genauigkeit eines Klassifikators. Je geringer der Protokollverlust, desto genauer ist ein Klassifikator.

## <a name="loss-function"></a>Verlustfunktion

Eine Verlustfunktion ist die Differenz zwischen den Werten der Trainingsbezeichnung und der Vorhersage des Modells. Die Parameter des Modells werden durch Minimierung der Verlustfunktion geschätzt.

Verschiedene Trainer können mit unterschiedlichen Verlustfunktionen konfiguriert werden.

## <a name="mean-absolute-error-mae"></a>Mittlerer absoluter Fehler (Mean Absolute Error, MAE)

Bei der [Regression](#regression) ist dies eine Auswertungsmetrik, die den Durchschnitt aller Modellfehler angibt, wobei ein Modellfehler die Differenz zwischen dem vorhergesagten Wert für die [Bezeichnung](#label) und dem korrekten Wert für die Bezeichnung ist.

## <a name="model"></a>Modell

In der Regel handelt es sich hierbei um die Parameter für die Vorhersagefunktion. Zum Beispiel die Gewichtungen in einem linearen Regressionsmodell oder die Entscheidungspunkte in einem Entscheidungsbaum. In ML.NET enthält ein Modell alle Informationen, die zur Vorhersage der [Bezeichnung](#label) eines Domänenobjekts (z.B. Bild oder Text) notwendig sind. Dies bedeutet, dass ML.NET-Modelle sowohl die notwendigen Schritte zur Funktionsbereitstellung als auch die Parameter für die Vorhersagefunktion enthalten.

## <a name="multiclass-classification"></a>Multiklassenklassifizierung

Ein [Klassifizierungsfall](#classification), bei dem die [Bezeichnung](#label) nur eine von mindestens drei Klassen ist. Weitere Informationen finden Sie im Abschnitt [Multiklassenklassifizierung](tasks.md#multiclass-classification) des Artikels [Machine Learning-Aufgaben](tasks.md).

## <a name="n-gram"></a>N-gram

Ein Funktionsextraktionsschema für Textdaten: jede Sequenz von N Wörtern wird in einen [Funktionswert](#feature) umgewandelt.

## <a name="normalization"></a>Normalisierung

Normalisierung ist der Prozess der Skalierung von Gleitkommadaten in Werte zwischen 0 und 1. Viele der in ML.NET verwendeten Trainingsalgorithmen erfordern das Normalisieren von Merkmalseingabedaten. ML.NET stellt eine Reihe von [Transformationen für die Normalisierung](transforms.md#normalization-and-scaling) bereit.

## <a name="numerical-feature-vector"></a>Numerischer Funktionsvektor

Ein Vektor aus [Funktionen](#feature) besteht ausschließlich aus numerischen Werten. Dies ist vergleichbar mit `double[]`.

## <a name="pipeline"></a>Pipeline

Alle Vorgänge, die zur Anpassung eines Modells an einen Datensatz erforderlich sind. Eine Pipeline besteht aus Datenimport, Transformation, Funktionsbereitstellung und Lernschritten. Ist eine Pipeline einmal trainiert, wird sie zum Modell.

## <a name="precision"></a>Genauigkeit

Bei der [Klassifizierung](#classification) steht die Genauigkeit für eine Klasse für die Anzahl der Elemente, die korrekt als zu dieser Klasse gehörend vorhergesagt werden, geteilt durch die Gesamtzahl der Elemente, die als zu dieser Klasse gehörend vorhergesagt werden.

## <a name="recall"></a>Wiedererkennung

Bei der [Klassifizierung](#classification) steht die Wiedererkennung für eine Klasse für die Anzahl der Elemente, die korrekt als zu dieser Klasse gehörend vorhergesagt werden, geteilt durch die Gesamtzahl der Elemente, die tatsächlich zu dieser Klasse gehören.

## <a name="regularization"></a>Regularisierung

 Die Regularisierung ahndet, wenn ein lineares Modell zu kompliziert ist. Es gibt zwei Arten von Regularisierung:

- $L_1$-Regularisierung setzt die Gewichtungen für unwichtige Features auf Null. Die Größe des gespeicherten Modells kann nach dieser Art der Regularisierung kleiner werden.
- $L_2$-Regularisierung minimiert den Gewichtungsbereich für unwichtige Merkmale. Dies ist ein allgemeinerer Prozess, der weniger empfindlich für Ausreißer ist.

## <a name="regression"></a>Regression

Ein Task für [überwachtes maschinelles Lernen](#supervised-machine-learning), durch den ein reeller Wert, z.B. „double“, ausgegeben wird. Ein gutes Beispiel ist die Vorhersage von Aktienkursen. Weitere Informationen finden Sie im Abschnitt [Regression](tasks.md#regression) des Artikels [Machine Learning-Aufgaben](tasks.md).

## <a name="relative-absolute-error"></a>Relativer absoluter Fehler

Bei der [Regression](#regression) steht diese Auswertungsmetrik für die Summe aller absoluten Fehler geteilt durch die Summe der Differenzen zwischen korrekten [Bezeichnungswerten](#label) und dem Durchschnitt aller korrekten Bezeichnungswerte.

## <a name="relative-squared-error"></a>Relativer quadratischer Fehler

Bei der [Regression](#regression) steht diese Auswertungsmetrik für die Summe aller absoluten quadratischen Fehler geteilt durch die Summe der Differenzen zwischen korrekten [Bezeichnungswerten](#label) und dem Durchschnitt aller korrekten Bezeichnungswerte.

## <a name="root-of-mean-squared-error-rmse"></a>Wurzel des mittleren quadratischen Fehlers (Root of mean squared error, RMSE)

Bei der [Regression](#regression) steht diese Auswertungsmetrik für die Quadratwurzel aus dem Durchschnitt der Quadrate der Fehler.

## <a name="scoring"></a>Bewertung

Bewertung ist der Prozess, bei dem neue Daten auf ein trainiertes Machine Learning-Modell angewendet und Vorhersagen generiert werden. Bewertung wird auch als Rückschluss bezeichnet. Abhängig vom Modelltyp kann die Bewertung ein Rohwert, eine Wahrscheinlichkeit oder eine Kategorie sein.

## <a name="supervised-machine-learning"></a>Überwachtes maschinelles Lernen

Eine Unterklasse des maschinellen Lernens, in der ein gewünschtes Modell die Bezeichnung für noch unbekannte Daten vorhersagt. Beispiele hierfür sind Klassifizierung, Regression und strukturierte Vorhersage. Weitere Informationen finden Sie auf Wikipedia im Artikel [Überwachtes Lernen](https://en.wikipedia.org/wiki/Supervised_learning).

## <a name="training"></a>Aus- und Weiterbildung

Der Prozess der Identifizierung eines [Modells](#model) für einen bestimmten Trainingsdatensatz. Für ein lineares Modell bedeutet dies, die Gewichtung zu finden. Bei einem Baum geht es darum, die Entscheidungspunkte zu identifizieren.

## <a name="transformer"></a>Transformator

Eine ML-NET-Klasse, die die <xref:Microsoft.ML.ITransformer>-Schnittstelle implementiert.

Ein Transformator transformiert eine <xref:Microsoft.ML.IDataView> in eine andere. Ein Transformator wird durch das Training eines [Estimators](#estimator) oder einer Estimatorpipeline erstellt.

## <a name="unsupervised-machine-learning"></a>Unüberwachtes maschinelles Lernen

Eine Unterklasse des maschinellen Lernens, in der ein gewünschtes Modell versteckte (oder latente) Strukturen in Daten findet. Beispiele hierfür sind Clustering, Themenmodellierung und Dimensionsreduktion. Weitere Informationen finden Sie auf Wikipedia im Artikel [Unüberwachtes Lernen](https://en.wikipedia.org/wiki/Unsupervised_learning).
