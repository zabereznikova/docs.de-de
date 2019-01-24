---
title: Machine Learning-Aufgaben – ML.NET
description: Untersuchen Sie die anderen in ML.NET unterstützten Machine Learning-Aufgaben und zugehörigen Aufgaben.
ms.custom: seodec18
ms.date: 01/15/2019
author: jralexander
ms.openlocfilehash: 02b454d18eca36c94c27ae15665af5df2ec87905
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415701"
---
# <a name="machine-learning-tasks-in-mlnet"></a>Machine Learning-Aufgaben in ML.NET

Wenn Sie ein Machine Learning-Modell erstellen, müssen Sie zuerst definieren, was Sie mit Ihren Daten erreichen möchten. Danach können Sie die richtige Machine Learning-Aufgabe für Ihren Zweck auswählen. In der folgenden Liste werden die verschiedenen Machine Learning-Aufgaben beschrieben, unter denen Sie auswählen können, und einige häufige Anwendungsfälle.

> [!NOTE]
> ML.NET ist derzeit als Vorschauversion verfügbar. Nicht alle Machine Learning-Aufgaben werden derzeit unterstützt. Um eine Anforderung für eine bestimmte Aufgabe zu übermitteln, öffnen Sie einen Fall im [dotnet/machinelearning-Repository](https://github.com/dotnet/machinelearning/issues).

## <a name="binary-classification"></a>Binäre Klassifizierung

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um vorherzusagen, zu welcher von zwei Klassen (Kategorien) eine Dateninstanz gehört. Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele, wo jede Bezeichnung entweder die Ganzzahl 0 oder 1 ist. Die Ausgabe eines binären Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen. Zu den Beispielen binärer Klassifizierungsszenarien zählen:

* [Verstehen des Standpunkts in Twitter-Kommentaren](../tutorials/sentiment-analysis.md) als „positiv“ oder „negativ“.
* Diagnostizieren, ob bei einem Patienten eine bestimmte Krankheit vorliegt oder nicht.
* Treffen einer Entscheidung, um eine E-Mail-Nachricht als „Spam“ zu markieren oder nicht.
* Bestimmen, ob ein Foto einen Hund oder Obst zeigt.

Weitere Informationen finden Sie auf Wikipedia im Artikel zur [binären Klassifizierung](https://en.wikipedia.org/wiki/Binary_classification).

Empfohlene Lernmodule für binäre Klassifizierung:

* AveragedPerceptronTrainer
* StochasticGradientDescentClassificationTrainer
* LightGbmBinaryTrainer
* FastTreeBinaryClassificationTrainer
* SymSgdClassificationTrainer

### <a name="binary-classification-learners"></a>Lernmodule für binäre Klassifizierung

Die folgenden Lernmodule sind für binäre Klassifizierungsaufgaben verfügbar:

* [AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.Online.AveragedPerceptronTrainer)
* [BinaryClassificationGamTrainer](xref:Microsoft.ML.Trainers.FastTree.BinaryClassificationGamTrainer)
* [FastForestClassification](xref:Microsoft.ML.Trainers.FastTree.FastForestClassification)
* [FastTreeBinaryClassificationTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer)
* [FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.FactorizationMachine.FieldAwareFactorizationMachineTrainer)
* [LightGbmBinaryTrainer](xref:Microsoft.ML.LightGBM.LightGbmBinaryTrainer)
* [LinearSvmTrainer](xref:Microsoft.ML.Trainers.Online.LinearSvmTrainer)
* [LogisticRegression](xref:Microsoft.ML.Learners.LogisticRegression)
* [PriorTrainer](xref:Microsoft.ML.Trainers.PriorTrainer)
* [RandomTrainer](xref:Microsoft.ML.Trainers.RandomTrainer)
* [StochasticGradientDescentClassificationTrainer](xref:Microsoft.ML.Trainers.StochasticGradientDescentClassificationTrainer)
* [SymSgdClassificationTrainer](xref:Microsoft.ML.Trainers.SymSgd.SymSgdClassificationTrainer)

## <a name="multiclass-classification"></a>Multiklassenklassifizierung

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um die Klasse (Kategorie) einer Dateninstanz vorherzusagen. Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele. Jede Bezeichnung beginnt normalerweise als Text. Sie wird dann über TermTransform ausgeführt, wodurch sie in den (numerischen) Schlüsseltyp konvertiert wird. Die Ausgabe eines Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen. Zu den Beispielen für Multiklassen-Klassifizierungsszenarien zählen:

* Ermitteln der Rasse eines Hundes als „Sibirischer Husky“, „Golden Retriever“, „Pudel“ usw.
* Verstehen von Filmkritiken als „positiv“, „neutral“ oder „negativ“.
* Kategorisieren von Hoteltests in „Lage“, „Preis“, „Sauberkeit“ usw.

Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Multiklassenklassifizierung](https://en.wikipedia.org/wiki/Multiclass_classification).

Empfohlene Lernmodule für Multiklassenklassifizierung:

* OVA-AveragedPerceptronTrainer
* SdcaMultiClassTrainer
* LightGbmMulticlassTrainer
* OVA-FastTreeBinaryClassificationTrainer

>[!NOTE]
>OVA und PKPD aktualisieren alle [Binärklassifizierungs-Lernmodule](#binary-classification), sodass sie Multiklassendatasets bearbeiten. Weitere Informationen finden Sie in [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).

### <a name="multiclass-classification-learners"></a>Multiklassenklassifizierungs-Lernmodule

Die folgenden Lernmodule sind für Multiklassenklassifizierungsaufgaben verfügbar:

* [LightGbmMulticlassTrainer](xref:Microsoft.ML.LightGBM.LightGbmMulticlassTrainer)
* [MetaMulticlassTrainer<TTransformer,TModel>](xref:Microsoft.ML.Learners.MetaMulticlassTrainer%602)
* [MultiClassNaiveBayesTrainer](xref:Microsoft.ML.Trainers.MultiClassNaiveBayesTrainer)
* [Ova](xref:Microsoft.ML.Trainers.Ova)
* [Pkpd](xref:Microsoft.ML.Trainers.Pkpd)
* [SdcaMultiClassTrainer](xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer)

## <a name="regression"></a>Regression

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, die verwendet wird, um den Wert der Bezeichnung aus einem Satz verwandter Features vorherzusagen. Die Bezeichnung kann einen realen Wert haben und stammt nicht aus einem endlichen Satz von Werten wie bei Klassifizierungsaufgaben. Regressionsalgorithmen modellieren die Abhängigkeit der Bezeichnung von den zugehörigen verwandten Features, um zu bestimmen, wie sich die Bezeichnung ändert, wenn die Werte der Features variiert werden. Die Eingabe eines Regressionsalgorithmus ist eine Reihe von Beispielen mit Bezeichnungen bekannter Werte. Die Ausgabe eines Regressionsalgorithmus ist eine Funktion, die Sie verwenden können, um den Bezeichnungswert für einen neuen Satz von Eingabefeatures vorherzusagen. Beispiele für Regressionsszenarien sind:

* Hauspreisvorhersagen basierend auf Hausattributen wie der Anzahl von Schlafzimmern, Lage und Größe.
* Vorhersagen zukünftiger Aktienkurse basierend auf historischen Daten und aktuellen Markttrends.
* Vorhersagen für den Verkauf eines Produkts basierend auf Werbebudgets.

Empfohlene Lernmodule für die Regression:

* FastTreeTweedieTrainer 
* LightGbmRegressorTrainer 
* SdcaRegressionTrainer 
* FastTreeRegressionTrainer

### <a name="regression-learners"></a>Regressionslernmodule

Die folgenden Lernmodule sind für Regressionsaufgaben verfügbar:

* [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer)
* [FastTreeTweedieTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer)
* [LightGbmRegressorTrainer](xref:Microsoft.ML.LightGBM.LightGbmRegressorTrainer)
* [OlsLinearRegressionTrainer](xref:Microsoft.ML.Trainers.HalLearners.OlsLinearRegressionTrainer)
* [OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.Online.OnlineGradientDescentTrainer)
* [PoissonRegression](xref:Microsoft.ML.Trainers.PoissonRegression)
* [RegressionGamTrainer](xref:Microsoft.ML.Trainers.FastTree.RegressionGamTrainer)
* [SdcaRegressionTrainer](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer)
* [FastTree.SingleTrainer](xref:Microsoft.ML.Trainers.FastTree.SingleTrainer)
* [LightGBM.SingleTrainer](xref:Microsoft.ML.LightGBM.SingleTrainer)

## <a name="clustering"></a>Clusterbildung

Eine [nicht überwachte Machine Learning](glossary.md#unsupervised-machine-learning)-Aufgabe, die verwendet wird, um Instanzen von Daten in Clustern zu gruppieren, die ähnliche Merkmale aufweisen. Die Clusterbildung kann auch zum Identifizieren von Beziehungen in einem Dataset verwendet werden, die Sie möglicherweise nicht logisch durch Durchsuchen oder einfache Beobachtung ableiten können. Die Eingaben und Ausgaben eines Clusterbildungsalgorithmus hängen von der ausgewählten Methodik ab. Sie können einen verteilungs-, schwerpunkt-, konnektivitäts- oder dichtebasierten Ansatz wählen. ML.NET unterstützt derzeit einen schwerpunktbasierten Ansatz bei Verwendung der K-Means-Clusterbildung. Beispiele für Clusterbildungsszenarien sind:

* Grundlegendes zu Segmenten von Hotelgästen basierend auf Gewohnheiten und Merkmalen der Hotelauswahl.
* Identifizieren von Kundensegmenten und demografischen Daten, um gezielte Werbekampagnen erstellen zu können.
* Kategorisieren des Lagerbestands basierend auf Produktionsmetriken.

### <a name="clustering-learners"></a>Clusteringlernmodule

Die folgenden Lernmodule sind für Clusteringaufgaben verfügbar:

* [KMeansPlusPlusTrainer](xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer)

## <a name="anomaly-detection"></a>Anomalieerkennung

Diese Aufgabe erstellt ein Anomalieerkennungsmodell mithilfe der Principal Component Analysis (PCA). Die Anomalieerkennung auf PCA-Basis unterstützt Sie beim Erstellen eines Modells in Szenarien, in denen mühelos Trainingsdaten aus einer Klasse, z.B. gültige Transaktionen, aber nur schwer ausreichende Beispiele für die gesuchten Anomalien zu erhalten sind.

Als bewährtes Verfahren im Machine Learning wird PCA häufig in der explorativen Datenanalyse verwendet, da es die innere Struktur der Daten zeigt und die Abweichung in den Daten erläutert. PCA arbeitet mit der Analyse von Daten, die mehrere Variablen enthalten. Das Verfahren sucht nach Korrelationen zwischen den Variablen und bestimmt die Kombination der Werte, die am besten Unterschiede in den Ergebnissen erfassen. Mit diesen kombinierten Featurewerten wird ein kompakterer Featurebereich erstellt, der als „Hauptkomponenten“ bezeichnet wird.

Die Anomalieerkennung umfasst viele wichtige Machine Learning-Aufgaben:

* Identifizieren potenziell betrügerischer Transaktionen.
* Erlernen von Mustern, die anzeigen, dass der Versuch unternommen wurde, in das Netzwerk einzudringen.
* Finden anomaler Patientencluster.
* Überprüfen von Werten, die in ein System eingegeben werden.

Da Anomalien laut Definition selten sind, kann es schwierig sein, eine repräsentative Stichprobe von Daten zu sammeln, die für die Modellierung verwendet werden können. Die Algorithmen, die zu dieser Kategorie gehören, wurden insbesondere daraufhin konzipiert, den wesentlichen Herausforderungen beim Erstellen und Trainieren von Modellen mithilfe von unausgeglichenen Datasets gerecht zu werden.

### <a name="anomaly-detection-learners"></a>Lernmodule zur Anomalieerkennung

Die folgenden Lernmodule sind für Anomalieerkennungsaufgaben verfügbar:

* [RandomizedPcaTrainer](xref:Microsoft.ML.Trainers.PCA.RandomizedPcaTrainer)

## <a name="ranking"></a>Rangfolge

Eine Rangfolgenaufgabe erstellt für einen Satz bezeichneter Beispiele eine Rangfolge. Dieser Beispielsatz besteht aus Instanzengruppen, die nach bestimmten Kriterien bewertet werden können. Die Rangfolgenbezeichnungen sind {0, 1, 2, 3, 4} für jede Instanz.  Die Rangfolgenfunktion wird dafür trainiert, neue Instanzengruppen mit unbekannten Bewertungen für jede Instanz in die Rangfolge einzuordnen. ML.NET-Rangfolgen-Lernmodule basieren auf [Machine Learning-Rangfolge](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-learners"></a>Rangfolgen-Lernmodule

Die folgenden Lernmodule sind für Rangfolgenaufgaben verfügbar:

* [FastTreeRankingTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer)
* [LightGbmRankingTrainer](xref:Microsoft.ML.LightGBM.LightGbmRankingTrainer)

## <a name="recommendation"></a>Empfehlung

Mit einer Empfehlungsaufgabe kann eine Liste empfohlener Produkte oder Dienste erstellt werden. ML.NET verwendet für Empfehlungen [Matrixfaktorisierung (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), einen Algorithmus für [kollaboratives Filtern](https://en.wikipedia.org/wiki/Collaborative_filtering), wenn Ihr Katalog Verlaufsproduktbewertungs-Daten enthält. Ihnen liegen z.B. Verlaufsfilmbewertungs-Daten Ihrer Benutzer vor, und Sie möchten andere Filme empfehlen, die sie wahrscheinlich als Nächstes sehen möchten.

### <a name="recommendation-learners"></a>Empfehlungslernmodule

Die folgenden Lernmodule sind für Empfehlungsaufgaben verfügbar:

* [MatrixFactorizationTrainer](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer)
* [MatrixFactorizationPredictionTransformer](xref:Microsoft.ML.Trainers.Recommender.MatrixFactorizationPredictionTransformer)
