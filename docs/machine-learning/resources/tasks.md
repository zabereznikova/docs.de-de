---
title: Machine Learning-Aufgaben
description: Untersuchen Sie die anderen in ML.NET unterstützten Machine Learning-Aufgaben und zugehörigen Aufgaben.
ms.date: 12/23/2019
ms.openlocfilehash: badb096ab3e7fbd575d8594b4fbd0e2ebaf63820
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739628"
---
# <a name="machine-learning-tasks-in-mlnet"></a>Machine Learning-Aufgaben in ML.NET

Bei einer Machine Learning-Aufgabe handelt es sich um den Typ der Vorhersage oder Rückschlüsse, basierend auf dem Problem oder der Frage, das bzw. die gestellt wird, und den verfügbaren Daten. Beispielsweise ordnet die Klassifizierungsaufgabe Daten Kategorien zu, und die Clusteringaufgabe gruppiert Daten nach ihrer Ähnlichkeit.

Machine Learning-Aufgaben basieren auf Mustern in den Daten, anstatt explizit programmiert zu werden.

In diesem Artikel werden die verschiedenen Machine Learning-Aufgaben beschrieben, unter denen Sie in ML.NET auswählen können, sowie einige häufige Anwendungsfälle.

Nachdem Sie entschieden haben, welche Aufgabe auf Ihr Szenario zutrifft, müssen Sie den besten Algorithmus zum Trainieren Ihres Modells auswählen. Die verfügbaren Algorithmen sind im Abschnitt zur jeweiligen Aufgabe aufgeführt.

## <a name="binary-classification"></a>Binäre Klassifizierung

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um vorherzusagen, zu welcher von zwei Klassen (Kategorien) eine Dateninstanz gehört. Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele, wo jede Bezeichnung entweder die Ganzzahl 0 oder 1 ist. Die Ausgabe eines binären Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen. Zu den Beispielen binärer Klassifizierungsszenarien zählen:

* [Verstehen des Standpunkts in Twitter-Kommentaren](../tutorials/sentiment-analysis.md) als „positiv“ oder „negativ“.
* Diagnostizieren, ob bei einem Patienten eine bestimmte Krankheit vorliegt oder nicht.
* Treffen einer Entscheidung, um eine E-Mail-Nachricht als „Spam“ zu markieren oder nicht.
* Ermitteln, ob ein Foto ein bestimmtes Element, z. B. einen Hund oder eine Frucht, enthält oder nicht

Weitere Informationen finden Sie auf Wikipedia im Artikel zur [binären Klassifizierung](https://en.wikipedia.org/wiki/Binary_classification).

### <a name="binary-classification-trainers"></a>Trainer für die binäre Klassifizierung

Sie können ein binäres Klassifizierungsmodell mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>
* <xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer>
* <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>
* <xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>
* <xref:Microsoft.ML.Trainers.PriorTrainer>
* <xref:Microsoft.ML.Trainers.LinearSvmTrainer>

### <a name="binary-classification-inputs-and-outputs"></a>Eingaben und Ausgaben für die binäre Klassifizierung

Für optimale Ergebnisse bei der binären Klassifizierung sollten die Trainingsdaten ausgeglichen sein (d.h. eine gleiche Anzahl von positiven und negativen Trainingsdaten). Fehlende Werte sollten vor dem Training bearbeitet werden.

Die Daten in der Spalte für die Eingabezeichnung müssen <xref:System.Boolean> sein.
Die Daten in der Spalte für die Eingabefeatures müssen ein Vektor fester Größe von <xref:System.Single> sein.

Diese Trainer geben die folgenden Spalten aus:

| Name der Ausgabespalte | Spaltentyp | Beschreibung|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Die vom Modell berechnete unformatierte Bewertung|
| `PredictedLabel` | <xref:System.Boolean> | Der vorhergesagte Bezeichnung, basierend auf dem Abzeichnen der Bewertung. Eine negative Bewertung wird `false` und eine positive Bewertung wird `true` zugeordnet.|

## <a name="multiclass-classification"></a>Multiklassenklassifizierung

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, um die Klasse (Kategorie) einer Dateninstanz vorherzusagen. Die Eingabe eines Klassifizierungsalgorithmus ist ein Satz bezeichneter Beispiele. Jede Bezeichnung beginnt normalerweise als Text. Sie wird dann über TermTransform ausgeführt, wodurch sie in den (numerischen) Schlüsseltyp konvertiert wird. Die Ausgabe eines Klassifizierungsalgorithmus ist ein Klassifizierer, den Sie verwenden können, um die Klasse der neuen nicht bezeichneten Instanzen vorherzusagen. Zu den Beispielen für Multiklassen-Klassifizierungsszenarien zählen:

* Ermitteln der Rasse eines Hundes als „Sibirischer Husky“, „Golden Retriever“, „Pudel“ usw.
* Verstehen von Filmkritiken als „positiv“, „neutral“ oder „negativ“.
* Kategorisieren von Hoteltests in „Lage“, „Preis“, „Sauberkeit“ usw.

Weitere Informationen finden Sie auf Wikipedia im Artikel zur [Multiklassenklassifizierung](https://en.wikipedia.org/wiki/Multiclass_classification).

>[!NOTE]
>One-vs-All (OvA) aktualisiert alle [Binärklassifizierungs-Lernmodule](#binary-classification), sodass sie Multiklassendatasets bearbeiten. Weitere Informationen finden Sie in [Wikipedia] (https://en.wikipedia.org/wiki/Multiclass_classification#One-vs.-rest).

### <a name="multiclass-classification-trainers"></a>Trainer für die Multiklassenklassifizierung

Sie können ein Modell zur Multiklassenklassifizierung mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>
* <xref:Microsoft.ML.Trainers.OneVersusAllTrainer>
* <xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer>

### <a name="multiclass-classification-inputs-and-outputs"></a>Eingaben und Ausgaben für die Multiklassenklassifizierung

Die Daten in der Spalte für die Eingabezeichnung müssen vom Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) sein.
Die Featurespalte muss ein Vektor fester Größe von <xref:System.Single> sein.

Der Trainer gibt folgende Daten aus:

| Ausgabename | Typ | Beschreibung|
| -- | -- | -- |
| `Score` | Vektor von <xref:System.Single> | Die Bewertungen aller Klassen. Ein höherer Wert bedeutet eine höhere Wahrscheinlichkeit, in die zugehörige Klasse zu fallen. Wenn das i-te Element den größten Wert hat, wäre der vorhergesagte Bezeichnungsindex i. Beachten Sie, dass „i“ ein nullbasierter Index ist. |
| `PredictedLabel` | Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) | Der Index der vorhergesagten Bezeichnung. Wenn sein Wert i ist, wäre die eigentliche Bezeichnung die i-te Kategorie des Typs der Schlüssel-Wert-Eingabebezeichnung. |

## <a name="regression"></a>Regression

Eine [überwachte Machine Learning](glossary.md#supervised-machine-learning)-Aufgabe, die verwendet wird, um den Wert der Bezeichnung aus einem Satz verwandter Features vorherzusagen. Die Bezeichnung kann einen realen Wert haben und stammt nicht aus einem endlichen Satz von Werten wie bei Klassifizierungsaufgaben. Regressionsalgorithmen modellieren die Abhängigkeit der Bezeichnung von den zugehörigen verwandten Features, um zu bestimmen, wie sich die Bezeichnung ändert, wenn die Werte der Features variiert werden. Die Eingabe eines Regressionsalgorithmus ist eine Reihe von Beispielen mit Bezeichnungen bekannter Werte. Die Ausgabe eines Regressionsalgorithmus ist eine Funktion, die Sie verwenden können, um den Bezeichnungswert für einen neuen Satz von Eingabefeatures vorherzusagen. Beispiele für Regressionsszenarien sind:

* Hauspreisvorhersagen basierend auf Hausattributen wie der Anzahl von Schlafzimmern, Lage und Größe.
* Vorhersagen zukünftiger Aktienkurse basierend auf historischen Daten und aktuellen Markttrends.
* Vorhersagen für den Verkauf eines Produkts basierend auf Werbebudgets.

### <a name="regression-trainers"></a>Regressionstrainer

Sie können ein Regressionsmodell mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>
* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer>
* <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>
* <xref:Microsoft.ML.Trainers.OlsTrainer>
* <xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>

### <a name="regression-inputs-and-outputs"></a>Eingaben und Ausgaben für die Regression

Die Daten in der Spalte für die Eingabezeichnung müssen <xref:System.Single> sein.

Die Trainer für diese Ausgabe geben folgende Daten aus:

| Ausgabename | Typ | Beschreibung|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Die vom Modell vorhergesagte unformatierte Bewertung |

## <a name="clustering"></a>Clusterbildung

Eine [nicht überwachte Machine Learning](glossary.md#unsupervised-machine-learning)-Aufgabe, die verwendet wird, um Instanzen von Daten in Clustern zu gruppieren, die ähnliche Merkmale aufweisen. Die Clusterbildung kann auch zum Identifizieren von Beziehungen in einem Dataset verwendet werden, die Sie möglicherweise nicht logisch durch Durchsuchen oder einfache Beobachtung ableiten können. Die Eingaben und Ausgaben eines Clusterbildungsalgorithmus hängen von der ausgewählten Methodik ab. Sie können einen verteilungs-, schwerpunkt-, konnektivitäts- oder dichtebasierten Ansatz wählen. ML.NET unterstützt derzeit einen schwerpunktbasierten Ansatz bei Verwendung der K-Means-Clusterbildung. Beispiele für Clusterbildungsszenarien sind:

* Grundlegendes zu Segmenten von Hotelgästen basierend auf Gewohnheiten und Merkmalen der Hotelauswahl.
* Identifizieren von Kundensegmenten und demografischen Daten, um gezielte Werbekampagnen erstellen zu können.
* Kategorisieren des Lagerbestands basierend auf Produktionsmetriken.

### <a name="clustering-trainer"></a>Trainerclustering

Sie können ein Modell zur Clusterbildung mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.KMeansTrainer>

### <a name="clustering-inputs-and-outputs"></a>Eingaben und Ausgaben für das Clustering

Die Daten der Eingabefeatures müssen <xref:System.Single> sein. Es sind keine Bezeichnungen erforderlich.

Der Trainer gibt folgende Daten aus:

| Ausgabename | Typ | Beschreibung|
| -- | -- | -- |
| `Score` | Vektor von <xref:System.Single> | Die Abstände der angegebenen Daten weisen auf die Schwerpunkte aller Cluster hin. |
| `PredictedLabel` | Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) | Der Index des nächsten Clusters, der durch das Modell vorhergesagt wird. |

## <a name="anomaly-detection"></a>Anomalieerkennung

Diese Aufgabe erstellt ein Anomalieerkennungsmodell mithilfe der Principal Component Analysis (PCA). Die Anomalieerkennung auf PCA-Basis unterstützt Sie beim Erstellen eines Modells in Szenarien, in denen mühelos Trainingsdaten aus einer Klasse, z.B. gültige Transaktionen, aber nur schwer ausreichende Beispiele für die gesuchten Anomalien zu erhalten sind.

Als bewährtes Verfahren im Machine Learning wird PCA häufig in der explorativen Datenanalyse verwendet, da es die innere Struktur der Daten zeigt und die Abweichung in den Daten erläutert. PCA arbeitet mit der Analyse von Daten, die mehrere Variablen enthalten. Das Verfahren sucht nach Korrelationen zwischen den Variablen und bestimmt die Kombination der Werte, die am besten Unterschiede in den Ergebnissen erfassen. Mit diesen kombinierten Featurewerten wird ein kompakterer Featurebereich erstellt, der als „Hauptkomponenten“ bezeichnet wird.

Die Anomalieerkennung umfasst viele wichtige Machine Learning-Aufgaben:

* Identifizieren potenziell betrügerischer Transaktionen.
* Erlernen von Mustern, die anzeigen, dass der Versuch unternommen wurde, in das Netzwerk einzudringen.
* Finden anomaler Patientencluster.
* Überprüfen von Werten, die in ein System eingegeben werden.

Da Anomalien laut Definition selten sind, kann es schwierig sein, eine repräsentative Stichprobe von Daten zu sammeln, die für die Modellierung verwendet werden können. Die Algorithmen, die zu dieser Kategorie gehören, wurden insbesondere daraufhin konzipiert, den wesentlichen Herausforderungen beim Erstellen und Trainieren von Modellen mithilfe von unausgeglichenen Datasets gerecht zu werden.

### <a name="anomaly-detection-trainer"></a>Trainer für die Anomalieerkennung

Sie können ein Anomalieerkennungsmodell mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>

### <a name="anomaly-detection-inputs-and-outputs"></a>Eingaben und Ausgaben für die Anomalieerkennung

Die Eingabefeatures müssen ein Vektor fester Größe von <xref:System.Single> sein.

Der Trainer gibt folgende Daten aus:

| Ausgabename | Typ | Beschreibung|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Die nicht-negative, unbegrenzte Bewertung, die durch das Anomalieerkennungsmodell berechnet wurde. |
| `PredictedLabel` | <xref:System.Boolean> | Ein TRUE/FALSE-Wert, der angibt, ob es sich bei der Eingabe um eine Anomalie (PredictedLabel=true) oder um keine Anomalie (PredictedLabel=false) handelt. |

## <a name="ranking"></a>Rangfolge

Eine Rangfolgenaufgabe erstellt für einen Satz bezeichneter Beispiele eine Rangfolge. Dieser Beispielsatz besteht aus Instanzengruppen, die nach bestimmten Kriterien bewertet werden können. Die Rangfolgenbezeichnungen sind {0, 1, 2, 3, 4} für jede Instanz.  Die Rangfolgenfunktion wird dafür trainiert, neue Instanzengruppen mit unbekannten Bewertungen für jede Instanz in die Rangfolge einzuordnen. ML.NET-Rangfolgen-Lernmodule basieren auf [Machine Learning-Rangfolge](https://en.wikipedia.org/wiki/Learning_to_rank).

### <a name="ranking-training-algorithms"></a>Trainingsalgorithmen für Rangfolge

Sie können ein Rangfolgemodell mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>
* <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>

### <a name="ranking-input-and-outputs"></a>Eingaben und Ausgaben für die Rangfolge

Der Datentyp für die Eingabebezeichnung muss ein Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) oder <xref:System.Single> sein. Der Wert der Bezeichnung bestimmt die Relevanz, wobei höhere Werte eine höhere Relevanz anzeigen. Wenn die Bezeichnung vom Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) ist, dann ist der Schlüsselindex der Relevanzwert, wobei der kleinste Index der am wenigsten relevante ist. Wenn die Bezeichnung ein <xref:System.Single> ist, zeigen höhere Werte eine höhere Relevanz an.

Die Featuredaten müssen ein Vektor mit fester Größe von <xref:System.Single> sein, und die Gruppenspalte der Eingabezeilen muss vom Typ [key](xref:Microsoft.ML.Data.KeyDataViewType) sein.

Der Trainer gibt folgende Daten aus:

| Ausgabename | Typ | Beschreibung|
| -- | -- | -- |
| `Score` | <xref:System.Single> | Die unbegrenzte Bewertung, die vom Modell berechnet wurde, um die Vorhersage zu bestimmen. |

## <a name="recommendation"></a>Empfehlung

Mit einer Empfehlungsaufgabe kann eine Liste empfohlener Produkte oder Dienste erstellt werden. ML.NET verwendet für Empfehlungen [Matrixfaktorisierung (MF)](https://en.wikipedia.org/wiki/Matrix_factorization_%28recommender_systems%29), einen Algorithmus für [kollaboratives Filtern](https://en.wikipedia.org/wiki/Collaborative_filtering), wenn Ihr Katalog Verlaufsproduktbewertungs-Daten enthält. Ihnen liegen z.B. Verlaufsfilmbewertungs-Daten Ihrer Benutzer vor, und Sie möchten andere Filme empfehlen, die sie wahrscheinlich als Nächstes sehen möchten.

### <a name="recommendation-training-algorithms"></a>Trainingsalgorithmen für Empfehlung

Sie können ein Empfehlungsmodell mithilfe der folgenden Algorithmen trainieren:

* <xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer>
