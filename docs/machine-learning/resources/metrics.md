---
title: ML.NET-Metriken
description: Verstehen Sie die Metriken, die verwendet werden, um die Leistung eines ML.NET-Modells auszuwerten.
ms.date: 12/17/2019
ms.openlocfilehash: 046e0a3feea2da702dfef5ca9ce4f498fce5fb26
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91804821"
---
# <a name="evaluate-your-mlnet-model-with-metrics"></a>Auswerten des ML.NET-Modells mit Metriken

Verstehen der Metriken, die zum Auswerten eines ML.NET-Modells verwendet werden.

Auswertungsmetriken sind spezifisch für den Typ der Machine Learning-Aufgabe, die ein Modell ausführt.

Beispielsweise wird für die Klassifizierungsaufgabe das Modell ausgewertet, indem gemessen wird, wie gut eine vorhergesagte Kategorie mit der tatsächlichen Kategorie übereinstimmt. Bei Clustering basiert die Auswertung darauf, wie nahe die gruppierten Elemente beieinander liegen und wie viel Trennung zwischen den Clustern vorhanden ist.

## <a name="evaluation-metrics-for-binary-classification"></a>Auswertungsmetriken für binäre Klassifizierung

| Metriken   |      BESCHREIBUNG      |  Suchen nach |
|-----------|-----------------------|-----------|
| **Genauigkeit** |  [Accuracy](https://en.wikipedia.org/wiki/Accuracy_and_precision#In_binary_classification) Dies ist der Anteil der korrekten Vorhersagen mit einem Testdataset. Es ist das Verhältnis zwischen der Anzahl der korrekten Vorhersagen und der Gesamtzahl der Eingangsstichproben. Dies funktioniert gut, wenn es zu jeder Klasse eine ähnliche Anzahl von Stichproben gibt.| **Je näher der Wert an 1,00 liegt, desto besser**. Aber ein Wert von genau 1,00 zeigt ein Problem an (häufig: Bezeichnung-Ziel-Verlust, Überanpassung oder Test mit Trainingsdaten). Wenn die Testdaten unausgewogen sind (wobei die meisten Instanzen zu einer der Klassen gehören), das Dataset klein ist oder die Werte auf 0,00 oder 1,00 ansteigen, dann wird die Effektivität eines Klassifikators nicht wirklich erfasst, und Sie müssen zusätzliche Metriken überprüfen. |
| **AUC** |    [aucROC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic) oder *Area under the curve* (Fläche unter der Kurve) ist die Messung der Fläche unter der Kurve, die durch Abgleichen der True Positive-Rate mit der False Positive-Rate generiert wird.  |   **Je näher der Wert an 1,00 liegt, desto besser**. Der Wert muss größer als 0,50 sein, damit ein Modell akzeptabel ist. Ein Modell mit einem AUC-Wert von 0,50 oder weniger ist wertlos. |
| **aucPR** | aucPR oder *Area under a Precision-Recall curve* (Fläche unter der Precision-Recall-Kurve): Ein nützliches Maß für den Erfolg der Vorhersage, wenn die Klassen unausgewogen sind (stark verzerrte Datasets). |  **Je näher der Wert an 1,00 liegt, desto besser**. Hohe Werte nahe 1,00 zeigen, dass der Klassifikator sowohl genaue Ergebnisse liefert (hohe Präzision) als auch einen Großteil aller positiven Ergebnisse liefert (hohe Wiedererkennung). |
| **F1-score** | [F1-score](https://en.wikipedia.org/wiki/F1_score) auch bezeichnet als *„balanced F-score“ oder F-Maß*. Dies ist das harmonische Mittel zwischen Präzision und Wiedererkennung. F1 Score ist hilfreich, wenn das Verhältnis zwischen Präzision und Wiedererkennung ausgeglichen sein soll.| **Je näher der Wert an 1,00 liegt, desto besser**.  Ein F1-Score erreicht seinen besten Wert bei 1,00 und den schlechtesten bei 0,00. Daran erkennen Sie, wie präzise Ihr Klassifizierer ist. |

Weitere Informationen zu binären Klassifizierungsmetriken finden Sie in den folgenden Artikeln:

- [Accuracy, Precision, Recall or F1?](https://towardsdatascience.com/accuracy-precision-recall-or-f1-331fb37c5cb9) (Genauigkeit, Präzision, Wiedererkennung oder F1?)
- [Binary Classification Metrics class](xref:Microsoft.ML.Data.BinaryClassificationMetrics) (Metrikklassen für die binäre Klassifizierung)
- [The Relationship Between Precision-Recall and ROC Curves](http://pages.cs.wisc.edu/~jdavis/davisgoadrichcamera2.pdf) (Das Verhältnis zwischen Precision-Recall- und ROC-Kurven)

## <a name="evaluation-metrics-for-multi-class-classification"></a>Auswertungsmetriken für mehrklassige Klassifizierung

| Metriken   |      BESCHREIBUNG      |  Suchen nach |
|-----------|-----------------------|-----------|
| **Micro-Accuracy** |  Die [durchschnittliche Mikrogenauigkeit](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MicroAccuracy) aggregiert die Beiträge aller Klassen zur Berechnung der durchschnittlichen Metrik. Es ist der Anteil der korrekt vorhergesagten Instanzen. Der Mikrodurchschnitt berücksichtigt nicht die Klassenzugehörigkeit. Jedes Beispiel/Klasse-Paar trägt grundsätzlich zu gleichen Teilen zur Genauigkeitsmetrik bei. | **Je näher der Wert an 1,00 liegt, desto besser**. In einer Aufgabe für die Multiklassenklassifizierung ist die Mikrogenauigkeit der Makrogenauigkeit vorzuziehen, wenn Sie vermuten, dass es ein Klassenungleichgewicht geben könnte (d.h. Sie haben viel mehr Beispiele für eine Klasse als für andere Klassen).|
| **Macro-Accuracy** | Die [durchschnittliche Makrogenauigkeit](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.MacroAccuracy) ist die durchschnittliche Genauigkeit auf Klassenebene. Die Genauigkeit für jede Klasse wird berechnet, und die Makrogenauigkeit ist der Durchschnitt dieser Genauigkeiten. Grundsätzlich trägt jede Klasse zu gleichen Teilen zur Genauigkeitsmetrik bei. Minderheitsklassen werden gleich wie größere Klassen gewichtet. Die Metrik gibt jeder Klasse die gleiche Gewichtung, unabhängig davon, wie viele Instanzen aus dieser Klasse das Dataset enthält. |  **Je näher der Wert an 1,00 liegt, desto besser**.  Sie berechnet die Metrik unabhängig für jede Klasse und ermittelt dann den Durchschnitt (daher werden alle Klassen gleich behandelt). |
| **Log-loss**| Der logarithmische Verlust misst die Leistung eines Klassifizierungsmodells, wobei die Vorhersageeingabe ein Wahrscheinlichkeitswert zwischen 0,00 und 1,00 ist. Der Wert steigt, wenn die vorhergesagte Wahrscheinlichkeit von der tatsächlichen Bezeichnung abweicht. | **Je näher der Wert an 0,00 liegt, desto besser**. Bei einem perfekten Modell liegt der Wert bei 0,00. Ziel unserer Machine Learning-Modelle ist es, diesen Wert zu minimieren.|
| **Log-Loss Reduction** | Die [logarithmische Verlustreduzierung](xref:Microsoft.ML.Data.MulticlassClassificationMetrics.LogLossReduction) kann als Vorteil des Klassifizierers gegenüber einer Zufallsvorhersage interpretiert werden.| **Liegt zwischen [-inf, 1.00], wobei „1.00“ perfekte Vorhersagen und „0.00“ durchschnittliche Vorhersagen bedeutet.** Wenn der Wert beispielsweise 0,20 beträgt, kann er als „die Wahrscheinlichkeit einer korrekten Vorhersage ist 20 % besser als eine zufällige Schätzung“ interpretiert werden.|

Die Mikrogenauigkeit ist im Allgemeinen besser auf die Geschäftsanforderungen der ML-Vorhersagen ausgerichtet. Wenn Sie eine einzelne Metrik für die Auswahl der Qualität einer Aufgabe für die Multiklassenklassifizierung auswählen, sollte dies in der Regel die Mikrogenauigkeit sein.

Beispiel für eine Aufgabe zur Klassifizierung von Supporttickets: (ordnet eingehende Tickets den Support-Teams zu)

- Mikrogenauigkeit – wie oft wird ein eingehendes Ticket dem richtigen Team zugeordnet?
- Makrogenauigkeit für dein durchschnittliches Team – wie oft ist ein eingehendes Ticket das richtige Ticket für das Team?

Die Makrogenauigkeit gewichtet in diesem Beispiel kleine Teams zu hoch: Ein kleines Team, das nur 10 Tickets pro Jahr erhält, zählt ebenso viel wie ein großes Team mit 10.000 Tickets pro Jahr. Die Mikrogenauigkeit korreliert in diesem Fall besser mit der Geschäftsanforderung: „Wie viel Zeit/Geld kann das Unternehmen durch die Automatisierung meines Prozesses für die Ticketweiterleitung sparen“.

Weitere Informationen zu Metriken für die Multiklassenklassifizierung finden Sie in den folgenden Artikeln:

- [Micro- and Macro-average of Precision, Recall and F-Score](https://rushdishams.blogspot.com/2011/08/micro-and-macro-average-of-precision.html) (Mikro- und Makrodurchschnitt von Präzision, Wiedererkennung und F-Score)
- [Multiclass Classification with Imbalanced Dataset](https://towardsdatascience.com/machine-learning-multiclass-classification-with-imbalanced-data-set-29f6a177c1a) (Multiklassenklassifizierung mit unausgeglichenen Datasets)

## <a name="evaluation-metrics-for-regression-and-recommendation"></a>Auswertungsmetriken für Regression und Empfehlung

Sowohl die Regressions- als auch die Empfehlungsaufgabe prognostizieren eine Zahl. Im Fall von Regression kann die Zahl jede Ausgabeeigenschaft sein, die von den Eingabeeigenschaften beeinflusst wird. Bei der Empfehlung ist die Zahl in der Regel ein Bewertungswert (z. B. zwischen 1 und 5) oder eine Ja/Nein-Empfehlung (dargestellt durch 1 bzw. 0).

| Metrik   |      BESCHREIBUNG      |  Suchen nach |
|----------|-----------------------|-----------|
| **R-squared** |  [R-squared (R2)](https://en.wikipedia.org/wiki/Coefficient_of_determination) oder *Bestimmtheitsmaß* stellt die Vorhersageleistung des Modells als Wert zwischen -inf und 1,00 dar. 1,00 bedeutet, dass das Modell perfekt geeignet ist. Die Eignung kann aber auch willkürlich schlecht sein, sodass die Werte negativ sein können. Ein Score von 0,00 bedeutet, dass das Modell den erwarteten Wert für die Bezeichnung schätzt. R2 misst, wie nah die tatsächlichen Testdatenwerte an den vorhergesagten Werten liegen. | **Je näher der Wert an 1,00 liegt, desto besser ist die Qualität des Modells**. Manchmal können jedoch niedrige R-squared-Werte (z.B. 0,50) ganz normal oder gut genug für Ihr Szenario sein, und hohe R-squared-Werte sind nicht immer gut und möglicherweise verdächtig. |
| **Absolute-loss** |  [Absolute-loss](https://en.wikipedia.org/wiki/Mean_absolute_error) oder *Mittlerer absoluter Fehler (MAE)* misst, wie nah die Vorhersagen an den tatsächlichen Ergebnissen liegen. Damit wird der Durchschnitt aller Modellfehler angegeben, wobei ein Modellfehler die Differenz zwischen dem vorhergesagten Wert für die Bezeichnung und dem korrekten Wert für die Bezeichnung ist. Dieser Vorhersagefehler wird für jeden Datensatz des Testdatasets berechnet. Abschließend wird der Mittelwert für alle erfassten absoluten Fehler berechnet.| **Je näher der Wert an 0,00 liegt, desto besser ist die Qualität des Modells**. Der mittlere absolute Fehler verwendet die gleiche Staffelung wie die zu messenden Daten (ist nicht für einen bestimmten Bereich normalisiert). „Absolute-loss“, „Squared-loss“ und „RMS-loss“ können nur zum Vergleich von Modellen für dasselbe Dataset oder Datasets mit einer ähnlichen Bezeichnung-Wert-Verteilung verwendet werden. |
| **Squared-loss** |  [Squared-loss](https://en.wikipedia.org/wiki/Mean_squared_error) oder *Mittlerer quadratischer Fehler (Mean Squared Error, MSE)*, auch *Mittlere quadratische Abweichung (Mean Squared Deviation, MSD)* genannt, gibt an, wie nahe eine Regressionslinie an einer Reihe von Testdatenwerten liegt, indem die Abstände der Punkte zur Regressionslinie (diese Abstände sind die Fehler E) ermittelt und ins Quadrat erhoben werden. Durch das Quadrieren wird größeren Unterschieden eine höhere Gewichtung zugewiesen. | Der Wert ist immer nicht negativ, und **Werte, die näher an 0,00 liegen, sind besser**. In Abhängigkeit von Ihren Daten kann es unmöglich sein, für den mittleren quadratischen Fehler einen sehr kleinen Wert zu erhalten.|
| **RMS-loss** |  [RMS-loss](https://en.wikipedia.org/wiki/Root-mean-square_deviation) oder *Wurzel aus dem mittleren quadratischen Fehler (Root Mean Squared Error, RMSE)* (auch als *Wurzel aus der mittleren quadratischen Abweichung [Root Mean Square Deviation, RMSD*]), misst die Differenz zwischen den von einem Modell vorhergesagten Werten und den beobachteten Werten aus der zu modellierenden Umgebung. „RMS-loss“ ist die Quadratwurzel von „Squared-loss“ und verwendet, ähnlich wie „Absolute-loss“ dieselben Einheiten wie die Bezeichnung, weist jedoch größeren Unterschieden mehr Gewichtung zu. Die Wurzel aus dem mittleren quadratischen Fehler wird häufig in der Klimatologie, für Vorhersagen und Regressionsanalyse verwendet, um experimentelle Ergebnisse zu überprüfen. | Der Wert ist immer nicht negativ, und **Werte, die näher an 0,00 liegen, sind besser**. RMSD ist ein Maß für die Genauigkeit, um Vorhersagefehler verschiedener Modelle für ein bestimmtes Dataset zu vergleichen und nicht für verschiedene Datasets, da der Wert staffelungsabhängig ist.|

Weitere Informationen zu Regressionsmetriken finden Sie in den folgenden Artikeln:

- [Regression Analysis: How Do I Interpret R-squared and Assess the Goodness-of-Fit?](https://blog.minitab.com/blog/adventures-in-statistics-2/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit) (Regressionsanalyse: Interpretieren von „R-squared“ und Bewerten der Anpassungsgüte)
- [How To Interpret R-squared in Regression Analysis](https://statisticsbyjim.com/regression/interpret-r-squared-regression) (Interpretieren von „R-squared“ in der Regressionsanalyse)
- [R-Squared Definition](https://www.investopedia.com/terms/r/r-squared.asp) (R-Squared-Definition)
- [Mean Squared Error Definition](https://www.statisticshowto.datasciencecentral.com/mean-squared-error/) (Definition des mittleren quadratischen Fehlers)
- [What are Mean Squared Error and Root Mean Squared Error?](https://www.vernier.com/til/1014/) (Was sind der mittlere quadratische Fehler und die Wurzel aus dem mittleren quadratischen Fehler?)

## <a name="evaluation-metrics-for-clustering"></a>Auswertungsmetriken für Clustering

| Metrik   |      BESCHREIBUNG      |  Suchen nach |
|----------|-----------------------|-----------|
|**Durchschnittlicher Abstand**|Der Durchschnitt des Abstands zwischen Datenpunkten und der Mitte des zugewiesenen Clusters. Der mittlere Abstand ist ein Maß für die Nähe der Datenpunkte zu den Clusterschwerpunkten. Es ist ein Maß dafür, wie „dicht“ der Cluster ist.|Werte, die näher an **0** liegen, sind besser. Je näher an Null der mittlere Abstand liegt, desto stärker sind die Daten gruppiert. Beachten Sie jedoch, dass diese Metrik abnimmt, wenn die Anzahl der Cluster erhöht wird, und im Extremfall (wenn jeder einzelne Datenpunkt einen eigenen Cluster darstellt) gleich Null ist.
|**Davies-Bouldin-Index**|Das durchschnittliche Verhältnis der Abstände innerhalb der Cluster zu den Abständen zwischen den Clustern. Je dichter der Cluster und je weiter die Cluster voneinander entfernt sind, desto niedriger ist dieser Wert.|Werte, die näher an **0** liegen, sind besser. Cluster, die weiter auseinander liegen und weniger verstreut sind, führen zu einer besseren Bewertung.|
|**Normalized Mutual Information (normalisierte Transinformation)**|Kann verwendet werden, wenn die Trainingsdaten, mit denen das Clusteringmodell trainiert wird, auch mit Ground Truth-Bezeichnungen versehen sind (d. h. überwachtes Clustering). Die Metrik „Normalized Mutual Information“ misst, ob ähnliche Datenpunkte demselben Cluster zugewiesen werden und unterschiedliche Datenpunkte verschiedenen Clustern zugewiesen werden. „Normalized Mutual Informationen“ ist ein Wert zwischen 0 und 1.|Werte, die näher an **1** liegen, sind besser.|

## <a name="evaluation-metrics-for-ranking"></a>Auswertungsmetriken für Rangfolge

| Metrik   |      BESCHREIBUNG      |  Suchen nach |
|----------|-----------------------|-----------|
|**Discounted Cumulative Gains (diskontierte kumulative Zuwächse)**|Discounted Cumulative Gain (DCG) ist ein Maß für Rangfolgequalität. Diese Metrik wird von zwei Annahmen abgeleitet. Annahme 1: Besonders relevante Elemente sind nützlicher, wenn Sie höher in der Rangfolge erscheinen. Annahme 2: Nützlichkeit folgt Relevanz: Je höher die Relevanz, desto nützlicher ist ein Element. DCG wird für eine bestimmte Position in der Rangfolge berechnet. Die Metrik summiert die Relevanzbewertung, dividiert durch den Logarithmus des Rangfolgeindexes bis zur gewünschten Position. Die Berechnung erfolgt mit $\sum_{i=0}^{p} \frac {rel_i} {\log_{e}{i+1}}$. Relevanzgrade werden einem Rangfolge-Trainingsalgorithmus als Ground Truth-Bezeichnungen zur Verfügung gestellt. Ein DCG-Wert wird für jede Position in der Rangfolgetabelle bereitgestellt, daher der Name „Discounted Cumulative **Gains**“. |**Höhere Werte sind besser**|
|**Normalized Discounted Cumulative Gains (normalisierte diskontierte kumulative Zuwächse)**|Durch die Normalisierung von DCG kann die Metrik für Rangfolgelisten mit unterschiedlicher Länge verglichen werden.|**Werte, die näher an 1 liegen, sind besser**|

## <a name="evaluation-metrics-for-anomaly-detection"></a>Auswertungsmetriken für Anomalieerkennung

| Metrik   |      BESCHREIBUNG      |  Suchen nach |
|----------|-----------------------|-----------|
|**Area Under ROC Curve (Bereich unter der ROC-Kurve)**|Der Bereich unter der Empfängeroperatorkurve misst, wie gut das Modell anormale und normale Datenpunkte trennt.|**Werte, die näher an 1 liegen, sind besser**. Nur Werte größer als 0,5 veranschaulichen die Effektivität des Modells. Werte von 0,5 oder niedriger weisen darauf hin, dass das Modell nicht besser ist als das zufällige Zuordnen der Eingaben zu anormalen und normalen Kategorien.|
|**Detection Rate At False Positive Count (Erkennungsrate bei falsch positiver Anzahl)**|Die Erkennungsrate bei falsch positiver Anzahl ist das Verhältnis zwischen der Anzahl der richtig identifizierten Anomalien und der Gesamtzahl der Anomalien in einem Testsatz, indiziert durch die einzelnen falsch positiven Elemente. Das heißt, es gibt einen Wert für die Erkennungsrate bei falscher positiver Anzahl für jedes falsch positive Element.|**Werte, die näher an 1 liegen, sind besser**. Wenn keine falsch positiven Elemente vorliegen, ist dieser Wert 1.|
