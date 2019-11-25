---
title: 'Gewusst wie: Auswählen eines ML.NET-Algorithmus'
description: Erfahren Sie, wie Sie einen ML.NET-Algorithmus für Ihr Machine Learning-Modell auswählen.
author: natke
ms.topic: overview
ms.date: 06/05/2019
ms.openlocfilehash: 0721418d8b0b3c9ab645eb9885b0f4951c37762e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976696"
---
# <a name="how-to-choose-an-mlnet-algorithm"></a>Gewusst wie: Auswählen eines ML.NET-Algorithmus

Für jede [ML.NET-Aufgabe](resources/tasks.md) stehen mehrere Trainingsalgorithmen zur Auswahl. Welchen Sie auswählen, hängt von dem Problem ab, das Sie zu lösen versuchen, den Merkmalen Ihrer Daten und den Compute- und Speicherressourcen, die Ihnen zur Verfügung stehen. Beachten Sie unbedingt, dass das Trainieren von Machine Learning-Modellen ein iterativer Prozess ist. Sie müssen möglicherweise mehrere Algorithmen ausprobieren, um den am besten geeigneten herauszufinden.

Algorithmen arbeiten mit **Features**. Features sind numerische Werte, die aus Ihren Eingabedaten berechnet werden. Sie sind optimale Eingaben für Machine Learning-Algorithmen. Ihre Eingaberohdaten transformieren Sie mit einer oder mehreren [Datentransformationen](resources/transforms.md) in Features. Beispielsweise werden Textdaten in einen Satz von Wortzahlen und Wortkombinationszahlen umgewandelt. Sobald die Features mithilfe von Datentransformationen aus einem Rohdatentyp extrahiert worden sind, werden sie als **featureextrahiert** bezeichnet. Beispielsweise featureextrahierter Text, oder featureextrahierte Bilddaten.

## <a name="trainer--algorithm--task"></a>Trainer = Algorithmus + Aufgabe

Ein Algorithmus ist die Berechnung, die ausgeführt wird, um ein **Modell** zu erzeugen. Verschiedene Algorithmen schaffen Modelle mit unterschiedlichen Eigenschaften.

Mit ML.NET kann der gleiche Algorithmus für verschiedene Aufgaben angewendet werden. Beispielsweise kann ein stochastischer dualer koordinierter Anstieg für Binärklassifizierung, Multiklassenklassifizierung und Regression verwendet werden. Der Unterschied besteht darin, wie die Ausgabe des Algorithmus interpretiert wird, um der Aufgabe zu entsprechen.

Für jede Kombination von Algorithmus und Aufgabe bietet ML.NET eine Komponente, die den Trainingsalgorithmus und die Interpretation ausführt. Diese Komponenten werden als Trainer bezeichnet. <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer> verwendet z.B. den **StochasticDualCoordinatedAscent**-Algorithmus, der auf die **Regression**-Aufgabe angewendet wird.

## <a name="linear-algorithms"></a>Lineare Algorithmen

Lineare Algorithmen erzeugen ein Modell, das **Bewertungen** aus einer linearen Kombination der Eingabedaten und einem Satz von **Gewichtungen** berechnet. Die Gewichtungen sind Parameter des während des Trainings geschätzten Modells.

Lineare Algorithmen eignen sich gut für Features, die [linear separierbar](https://en.wikipedia.org/wiki/Linear_separability) sind.

Vor dem Training mit einem linearen Algorithmus sollten die Features normalisiert werden. Dies verhindert, dass ein Feature größeren Einfluss auf das Ergebnis hat als andere.

Im Allgemeinen sind lineare Algorithmen skalierbar und schnell sowie kostengünstig zu trainieren und vorherzusagen. Sie werden nach der Anzahl der Merkmale und ungefähr nach der Größe des Trainingsdatasets skaliert.

Lineare Algorithmen führen mehrere Durchläufe über die Trainingsdaten aus. Wenn Ihr Dataset in den Arbeitsspeicher passt, können Sie die Ausführung des Trainings beschleunigen, indem Sie Ihrer ML.NET-Pipeline vor dem Anfügen des Trainers einen [Cacheprüfpunkt](xref:Microsoft.ML.LearningPipelineExtensions.AppendCacheCheckpoint*) hinzufügen.

**Lineare Trainer**

|Algorithmus|Eigenschaften|Trainer|
|---------|----------|--------|
|Gemitteltes Perzeptron|Am besten geeignet zur Textklassifizierung|<xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>|
|Stochastischer dualer koordinierter Anstieg|Optimieren für gute Standardleistung nicht erforderlich|<xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer> <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer> <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer> <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>|
|L-BFGS|Wird verwendet, wenn die Anzahl der Features groß ist. Erstellt Trainingsstatistiken für die logistische Regression, aber skaliert nicht so gut wie der AveragedPerceptronTrainer|<xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>|
|Symbolischer stochastischer Gradientenabfall|Schneller und zuverlässiger präziser linearer Binärklassifizierungstrainer. Skaliert gut nach Anzahl der Prozessoren|<xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>|

## <a name="decision-tree-algorithms"></a>Entscheidungsstrukturalgorithmen

Entscheidungsstrukturalgorithmen erstellen ein Modell, das eine Reihe von Entscheidungen enthält: effektiv ein Flussdiagramm mit den Datenwerten.

Features müssen nicht linear separierbar sein, um diesen Typ des Algorithmus zu verwenden. Features müssen auch nicht normalisiert werden, da die einzelnen Werte im Featurevektor unabhängig voneinander im Entscheidungsprozess verwendet werden.

Entscheidungsstrukturalgorithmen sind in der Regel sehr genau.

Mit Ausnahme von Generalized Additive Models (GAMs) kann Strukturmodellen die Erklärbarkeit fehlen, wenn die Anzahl von Features groß ist.

Entscheidungsstrukturalgorithmen nehmen mehr Ressourcen in Anspruch und skalieren nicht so gut wie lineare. Sie funktionieren gut bei Datasets, die in den Arbeitsspeicher passen.

Verstärkte Entscheidungsstrukturen sind eine Gruppe kleiner Strukturen, wobei jede Struktur die Eingabedaten bewertet und das Ergebnis der nächsten Struktur übergibt, um ein besseres Ergebnis zu erzeugen, usw., wobei jede Struktur in der Gruppe das vorherige Ergebnis verbessert.

**Entscheidungsstrukturtrainer**

|Algorithmus|Eigenschaften|Trainer|
|---------|----------|--------|
|Machine für verstärkten leichten Anstieg|Schnellster und präzisester Trainer der Binärklassifizierungsstruktur. Hochgradig optimierbar|<xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>|
|Fast-Tree|Für featureextrahierte Bilddaten verwenden. Resilient gegenüber unausgewogenen Daten. Hochgradig optimierbar | <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>|
|Fast-Forest|Funktioniert gut mit störenden Daten|<xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>|
|Generalized Additive Model (GAM)|Am besten geeignet für Probleme, die gut mit Strukturalgorithmen bearbeitet werden, wo jedoch die Erklärbarkeit eine Priorität ist|<xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>|

## <a name="matrix-factorization"></a>Matrixfaktorisierung

|Eigenschaften|Trainer|
|----------|--------|
|Am besten bei kategorischen Daten mit geringer Dichte mit großen Datasets|<xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>|

## <a name="meta-algorithms"></a>Metaalgorithmen

Diese Trainer erstellen einen Multiklassentrainer aus einem binären Trainer. Verwenden mit <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>, <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>, <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>, <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>.

|Algorithmus|Eigenschaften|Trainer|
|---------|----------|--------|
|Einer gegen alle|Dieser Multiklassenklassifizierer trainiert einen binären Klassifizierer für jede Klasse, der diese Klasse von allen anderen Klassen unterscheidet. Ist in der Skalierung durch die Anzahl der zu kategorisierenden Klassen beschränkt|[OneVersusAllTrainer\<BinaryClassificationTrainer>](xref:Microsoft.ML.Trainers.OneVersusAllTrainer) |
|Paarweise Kopplung|Dieser Multiklassenklassifizierer trainiert einen binären Klassifizierungsalgorithmus g für jedes Paar von Klassen. Ist in der Skalierung durch die Anzahl der zu kategorisierenden Klassen begrenzt, da jede Kombination von zwei Klassen trainiert werden muss.|[PairwiseCouplingTrainer\<BinaryClassificationTrainer>](xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer)|

## <a name="k-means"></a>K-Means

|Eigenschaften|Trainer|
|----------|--------|
|Verwenden zum Clustering|<xref:Microsoft.ML.Trainers.KMeansTrainer>|

## <a name="principal-component-analysis"></a>Hauptkomponentenanalyse

|Eigenschaften|Trainer|
|----------|--------|
|Verwenden zur Anomalieerkennung|<xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>|

## <a name="naive-bayes"></a>Naive Bayes-Verfahren

|Eigenschaften|Trainer|
|----------|--------|
|Verwenden Sie diesen Multiklassenklassifizierungstrainer, wenn die Funktionen voneinander unabhängig sind und das Trainingsdataset klein ist.|<xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>|

## <a name="prior-trainer"></a>Vorheriger Trainer

|Eigenschaften|Trainer|
|----------|--------|
|Verwenden Sie diesen Binärklassifizierungstrainer, um eine Basis zum Messen der Leistung anderer Trainer zu erhalten. Um effektiv zu sein, sollten die Metriken der anderen Trainer besser sein als der vorherige Trainer. |<xref:Microsoft.ML.Trainers.PriorTrainer>|
