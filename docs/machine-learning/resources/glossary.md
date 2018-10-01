---
title: Maschinelles Lernen – Glossar
description: Ein Glossar von Begriffen aus dem Bereich des maschinellen Lernens.
author: jralexander
ms.author: johalex
ms.date: 05/31/2018
ms.topic: conceptual
ms.openlocfilehash: 6b175a8e89479dae81a7e5769e8d10c09a193898
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081097"
---
# <a name="machine-learning-glossary"></a>Maschinelles Lernen – Glossar

Die folgende Liste ist eine Zusammenstellung wichtiger Begriffe aus dem Bereich des maschinellen Lernens, die Ihnen bei der Erstellung benutzerdefinierter Modelle nützlich sind.

## <a name="accuracy"></a>Genauigkeit

Bei der [Klassifizierung](#classification) ist die Genauigkeit die Anzahl der korrekt klassifizierten Elemente dividiert durch die Gesamtzahl der Elemente in der Testgruppe. Sie reicht von 0 (ungenau) bis 1 (am genauesten). Die Genauigkeit ist eine der Auswertungsmetriken für die Leistung Ihres Modells. Betrachten Sie sie in Verbindung mit [Präzision](#precision), [Wiedererkennung](#recall) und [F-Wertung](#f-score).

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.BinaryClassificationMetrics.Accuracy?displayProperty=nameWithType>.

## <a name="area-under-the-curve-auc"></a>Fläche unter der Kurve (Area under the curve, AUC)

Bei der [binären Klassifizierung](#binary-classification) ist diese Auswertungsmetrik der Wert der Fläche unter der Kurve, der das Verhältnis der richtig positiven Ergebnisse (auf der Y-Achse) zu den falsch positiven Ergebnissen (auf der X-Achse) darstellt. Er reicht von 0,5 (schlechteste) bis 1 (beste). Auch bekannt als die Fläche unter der ROC-Kurve, d.h. unter der Grenzwertoptimierungskurve (Receiver Operating Characteristic Curve). Weitere Informationen finden Sie auf Wikipedia im Artikel zu [Receiver Operating Characteristic](https://en.wikipedia.org/wiki/Receiver_operating_characteristic).

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.BinaryClassificationMetrics.Auc?displayProperty=nameWithType>.

## <a name="binary-classification"></a>Binäre Klassifizierung

Ein [Klassifizierungsfall](#classification), bei dem die [Bezeichnung](#label) nur eine von zwei Klassen ist. Weitere Informationen finden Sie im Abschnitt [Binäre Klassifizierung](tasks.md#binary-classification) des Artikels [Machine Learning-Aufgaben](tasks.md).

## <a name="classification"></a>Klassifikation

Wenn die Daten zur Vorhersage einer Kategorie verwendet werden, wird der [überwachte Task für maschinelles Lernen](#supervised-machine-learning) als Klassifizierung bezeichnet. Die [binäre Klassifizierung](#binary-classification) bezieht sich auf die Vorhersage von nur zwei Kategorien (z.B. die Klassifizierung eines Bilds als Bild einer „Katze“ oder eines „Hunds“). Die [Multiklassenklassifizierung](#multiclass-classification) bezieht sich auf die Vorhersage mehrerer Kategorien (z.B. bei der Klassifizierung eines Bilds als Bild einer bestimmten Hunderasse).

## <a name="coefficient-of-determination"></a>Bestimmtheitsmaß

Bei der [Regression](#regression) gibt diese Auswertungsmetrik an, wie gut Daten in ein Modell passen. Die Werte liegen zwischen 0 und 1. Ein Wert von 0 bedeutet, dass die Daten zufällig sind oder nicht an das Modell angepasst werden können. Ein Wert von 1 bedeutet, dass das Modell exakt mit den Daten übereinstimmt. Dies wird oft als r<sup>2</sup>, R<sup>2</sup> oder R-Quadrat bezeichnet.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.RegressionMetrics.RSquared?displayProperty=nameWithType>.

## <a name="feature"></a>Feature

Eine messbare Eigenschaft des zu messenden Phänomens, typischerweise ein numerischer Wert (double). Mehrere Funktionen werden als **Funktionsvektor** bezeichnet und typischerweise als `double[]` gespeichert. Funktionen definieren die wichtigen Eigenschaften des zu messenden Phänomens. Weitere Informationen finden Sie auf Wikipedia im Artikel zum Thema [Funktion](https://en.wikipedia.org/wiki/Feature_(machine_learning)).

## <a name="feature-engineering"></a>Funktionsentwicklung

Als Funktionsentwicklung wird der Prozess bezeichnet, bei dem eine Reihe von [Funktionen](#feature) definiert und eine Software entwickelt wird, die aus den verfügbaren Phänomendaten Funktionsvektoren erzeugt, auch Funktionsextraktion genannt. Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Funktionsentwicklung](https://en.wikipedia.org/wiki/Feature_engineering).

## <a name="f-score"></a>F-Wertung

Bei der [Klassifizierung](#classification) ist dies eine Auswertungsmetrik, die [Präzision](#precision) und [Wiedererkennung](#recall) ausgleicht.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.BinaryClassificationMetrics.F1Score?displayProperty=nameWithType>.

## <a name="hyperparameter"></a>Hyperparameter

Ein Parameter eines Algorithmus für maschinelles Lernen. Beispiele sind die Anzahl der zu erlernenden Bäume in einem Entscheidungswald oder die Schrittgröße in einem Gradientenverfahrenalgorithmus. Werte von *Hyperparametern* werden vor dem Training des Modells festgelegt und regeln die Suche nach Parametern der Vorhersagefunktion, z.B. der Vergleichspunkte in einem Entscheidungsbaum oder der Gewichtungen in einem linearen Regressionsmodell. Weitere Informationen finden Sie auf Wikipedia im Artikel zum Thema [Hyperparameter](https://en.wikipedia.org/wiki/Hyperparameter_(machine_learning)).

## <a name="label"></a>Bezeichnung

Das Element, das mit dem Modell für maschinelles Lernen vorhergesagt werden soll. Zum Beispiel die Hunderasse oder ein zukünftiger Aktienkurs.

## <a name="log-loss"></a>Protokollverlust

Bei der [Klassifizierung](#classification) charakterisiert diese Auswertungsmetrik die Genauigkeit eines Klassifikators. Je geringer der Protokollverlust, desto genauer ist ein Klassifikator.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.BinaryClassificationMetrics.LogLoss?displayProperty=nameWithType>.

## <a name="mean-absolute-error-mae"></a>Mittlerer absoluter Fehler (Mean Absolute Error, MAE)

Bei der [Regression](#regression) ist dies eine Auswertungsmetrik, die den Durchschnitt aller Modellfehler angibt, wobei ein Modellfehler die Differenz zwischen dem vorhergesagten Wert für die [Bezeichnung](#label) und dem korrekten Wert für die Bezeichnung ist.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.RegressionMetrics.L1?displayProperty=nameWithType>.

## <a name="model"></a>Modell

In der Regel handelt es sich hierbei um die Parameter für die Vorhersagefunktion. Zum Beispiel die Gewichtungen in einem linearen Regressionsmodell oder die Entscheidungspunkte in einem Entscheidungsbaum. In ML.NET enthält ein Modell alle Informationen, die zur Vorhersage der [Bezeichnung](#label) eines Domänenobjekts (z.B. Bild oder Text) notwendig sind. Dies bedeutet, dass ML.NET-Modelle sowohl die notwendigen Schritte zur Funktionsbereitstellung als auch die Parameter für die Vorhersagefunktion enthalten.

## <a name="multiclass-classification"></a>Multiklassenklassifizierung

Ein [Klassifizierungsfall](#classification), bei dem die [Bezeichnung](#label) nur eine von mindestens drei Klassen ist. Weitere Informationen finden Sie im Abschnitt [Multiklassenklassifizierung](tasks.md#multiclass-classification) des Artikels [Machine Learning-Aufgaben](tasks.md).

## <a name="n-gram"></a>N-gram

Ein Funktionsextraktionsschema für Textdaten: jede Sequenz von N Wörtern wird in einen [Funktionswert](#feature) umgewandelt.

## <a name="numerical-feature-vector"></a>Numerischer Funktionsvektor

Ein Vektor aus [Funktionen](#feature) besteht ausschließlich aus numerischen Werten. Dies ist vergleichbar mit `double[]`.

## <a name="pipeline"></a>Pipeline

Alle Vorgänge, die zur Anpassung eines Modells an einen Datensatz erforderlich sind. Eine Pipeline besteht aus Datenimport, Transformation, Funktionsbereitstellung und Lernschritten. Ist eine Pipeline einmal trainiert, wird sie zum Modell.

## <a name="precision"></a>Genauigkeit

Bei der [Klassifizierung](#classification) steht die Genauigkeit für eine Klasse für die Anzahl der Elemente, die korrekt als zu dieser Klasse gehörend vorhergesagt werden, geteilt durch die Gesamtzahl der Elemente, die als zu dieser Klasse gehörend vorhergesagt werden.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.BinaryClassificationMetrics.NegativePrecision?displayProperty=nameWithType>, <xref:Microsoft.ML.Models.BinaryClassificationMetrics.PositivePrecision?displayProperty=nameWithType>.

## <a name="recall"></a>Wiedererkennung

Bei der [Klassifizierung](#classification) steht die Wiedererkennung für eine Klasse für die Anzahl der Elemente, die korrekt als zu dieser Klasse gehörend vorhergesagt werden, geteilt durch die Gesamtzahl der Elemente, die tatsächlich zu dieser Klasse gehören.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.BinaryClassificationMetrics.NegativeRecall?displayProperty=nameWithType>, <xref:Microsoft.ML.Models.BinaryClassificationMetrics.PositiveRecall?displayProperty=nameWithType>.

## <a name="regression"></a>Regression

Ein Task für [überwachtes maschinelles Lernen](#supervised-machine-learning), durch den ein reeller Wert, z.B. „double“, ausgegeben wird. Ein gutes Beispiel ist die Vorhersage von Aktienkursen. Weitere Informationen finden Sie im Abschnitt [Regression](tasks.md#regression) des Artikels [Machine Learning-Aufgaben](tasks.md).

## <a name="relative-absolute-error"></a>Relativer absoluter Fehler

Bei der [Regression](#regression) steht diese Auswertungsmetrik für die Summe aller absoluten Fehler geteilt durch die Summe der Differenzen zwischen korrekten [Bezeichnungswerten](#label) und dem Durchschnitt aller korrekten Bezeichnungswerte.

## <a name="relative-squared-error"></a>Relativer quadratischer Fehler

Bei der [Regression](#regression) steht diese Auswertungsmetrik für die Summe aller absoluten quadratischen Fehler geteilt durch die Summe der Differenzen zwischen korrekten [Bezeichnungswerten](#label) und dem Durchschnitt aller korrekten Bezeichnungswerte.

## <a name="root-of-mean-squared-error-rmse"></a>Wurzel des mittleren quadratischen Fehlers (Root of mean squared error, RMSE)

Bei der [Regression](#regression) steht diese Auswertungsmetrik für die Quadratwurzel aus dem Durchschnitt der Quadrate der Fehler.

Verwandte ML.NET-API: <xref:Microsoft.ML.Models.RegressionMetrics.Rms?displayProperty=nameWithType>.

## <a name="supervised-machine-learning"></a>Überwachtes maschinelles Lernen

Eine Unterklasse des maschinellen Lernens, in der ein gewünschtes Modell die Bezeichnung für noch unbekannte Daten vorhersagt. Beispiele hierfür sind Klassifizierung, Regression und strukturierte Vorhersage. Weitere Informationen finden Sie auf Wikipedia im Artikel [Überwachtes Lernen](https://en.wikipedia.org/wiki/Supervised_learning).

## <a name="training"></a>Aus- und Weiterbildung

Der Prozess der Identifizierung eines [Modells](#model) für einen bestimmten Trainingsdatensatz. Für ein lineares Modell bedeutet dies, die Gewichtung zu finden. Bei einem Baum geht es darum, die Entscheidungspunkte zu identifizieren.

## <a name="transform"></a>Transformation

Eine [Pipelinekomponente](#pipeline), die Daten transformiert. Zum Beispiel transformiert sie Text in einen Zahlenvektor.

## <a name="unsupervised-machine-learning"></a>Unüberwachtes maschinelles Lernen

Eine Unterklasse des maschinellen Lernens, in der ein gewünschtes Modell versteckte (oder latente) Strukturen in Daten findet. Beispiele hierfür sind Clustering, Themenmodellierung und Dimensionsreduktion. Weitere Informationen finden Sie auf Wikipedia im Artikel [Unüberwachtes Lernen](https://en.wikipedia.org/wiki/Unsupervised_learning).
