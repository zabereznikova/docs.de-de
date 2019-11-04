---
title: 'Gewusst wie: Verwenden der automatisierten ML-API von ML.NET'
description: Die automatisierte ML-API von ML.NET automatisiert das Erstellen von Modellen und generiert ein zur Bereitstellung geeignetes Modell. Erfahren Sie, welche Optionen Sie verwenden können, um automatisierte Machine Learning-Aufgaben zu konfigurieren.
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: bb1cd66e7341f2ada57d533d8b2dcbb48f08f726
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774550"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a>Gewusst wie: Verwenden der automatisierten ML-API von ML.NET

Automatisiertes Machine Learning (AutoML) automatisiert den Prozess der Anwendung von Machine Learning auf Daten. Mit einem Dataset können Sie ein AutoML-**Experiment** ausführen, um unterschiedliche Datenfeaturebereitstellungen, Machine Learning-Algorithmen und Hyperparameter zu durchlaufen, um das beste Modell auszuwählen.

> [!NOTE]
> In diesem Thema wird die automatisierte Machine Learning-API für ML.NET behandelt, die sich derzeit in der Vorschauphase befindet. Änderungen am Material vorbehalten.

## <a name="load-data"></a>Laden von Daten

Automatisiertes Machine Learning unterstützt das Laden eines Datasets in eine [IDataView](xref:Microsoft.ML.IDataView). Daten können in Form durch Tabstopp getrennter Dateien (TSV) und durch Trennzeichen getrennter Dateien (CSV) vorliegen.

Beispiel:

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a>Auswählen des Machine Learning-Aufgabentyps
Bevor Sie ein Experiment erstellen, ermitteln Sie die Art des Machine Learning-Problems, das Sie lösen möchten. Automatisiertes Machine Learning unterstützt die folgenden ML-Aufgaben:

* Binäre Klassifizierung
* Multiklassenklassifizierung
* Regression

## <a name="create-experiment-settings"></a>Erstellen von Experimenteinstellungen

Erstellen Sie Experimenteinstellungen für den bestimmten ML-Aufgabentyp:

* Binäre Klassifizierung

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* Multiklassenklassifizierung

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* Regression

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a>Konfigurieren von Experimenteinstellungen

Experimente sind hochgradig konfigurierbar. In der [AutoML-API-Dokumentation](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) finden Sie eine vollständige Liste der Konfigurationseinstellungen.

Beispiele:

1. Geben Sie die maximale Ausführungsdauer für das Experiment an.

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. Verwenden Sie ein Abbruchtoken, um das Experiment vor dem geplanten Endzeitpunkt abzubrechen.

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. Geben Sie eine andere Optimierungsmetrik an.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. Die `CacheDirectory`-Einstellung ist ein Zeiger auf ein Verzeichnis, in dem alle während der AutoML-Aufgabe trainierten Modelle gespeichert werden. Wenn `CacheDirectory` auf NULL festgelegt ist, werden Modelle im Arbeitsspeicher gehalten und nicht auf den Datenträger geschrieben.

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. Weisen Sie das automatisierte ML an, bestimmte Trainer nicht zu verwenden.

    Je Aufgabe wird eine Standardliste mit Trainern zum Optimieren untersucht. Diese Liste kann für jedes Experiment geändert werden. Trainer, die bei Ihrem Dataset langsam ausgeführt werden, können beispielsweise aus der Liste entfernt werden. Rufen Sie zum Optimieren mit einem bestimmten Trainer `experimentSettings.Trainers.Clear()` auf, und fügen Sie dann den Trainer hinzu, den Sie verwenden möchten.

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

Die Liste der pro ML-Aufgabe unterstützten Trainer finden Sie unter dem entsprechenden nachstehenden Link:

* [Unterstützte Algorithmen für binäre Klassifizierung](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [Unterstützte Algorithmen für Multiklassenklassifizierung](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [Unterstützte Regressionsalgorithmen](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a>Metrikoptimierung

Die Metrikoptimierung, wie im obigen Beispiel dargestellt, bestimmt, welche Metrik während des Modelltrainings optimiert werden soll. Welche Metrikoptimierung Sie auswählen können, richtet sich nach der Art der ausgewählten Aufgabe. Es folgt eine Liste der verfügbaren Metriken.

|[Binäre Klassifizierung](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [Multiklassenklassifizierung](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[Regression](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|Genauigkeit| LogLoss | RSquared
|AreaUnderPrecisionRecallCurve | LogLossReduction | MeanAbsoluteError
|AreaUnderRocCurve | MacroAccuracy | MeanSquaredError
|F1Score | MicroAccuracy | RootMeanSquaredError
|NegativePrecision | TopKAccuracy
|NegativeRecall |
|PositivePrecision
|PositiveRecall

## <a name="data-pre-processing-and-featurization"></a>Datenvorverarbeitung und Featurebereitstellung

> [!NOTE]
> Die Featurespalte unterstützt nur die Typen <xref:System.Boolean>, <xref:System.Single> und <xref:System.String>.

Die Datenvorverarbeitung erfolgt standardmäßig, und die folgenden Schritte werden automatisch für Sie ausgeführt:

1. Löschen von Features ohne nützliche Informationen

    Löschen Sie Features ohne nützliche Informationen aus den Trainings- und Validierungsdatasets. Dazu gehören Features, denen alle Werte fehlen, die denselben Wert in allen Zeilen oder eine sehr hohe Kardinalität aufweisen (z.B. Hashes, IDs oder GUIDs).

1. Fehlende Wertangabe und -imputation

    Füllen Sie fehlende Wertzellen mit dem Standardwert für den Datentyp auf. Fügen Sie Indikatorfeatures mit der gleichen Anzahl von Slots wie die Eingabespalte an. Der Wert in den angefügten Indikatorfeatures ist `1`, falls der Wert in der Eingabespalte fehlt, und andernfalls `0`.

1. Generieren zusätzlicher Features

    Für Textfeatures: Bag-of-Word-Features mit Monogrammen und Trigrammen.

    Für kategorische Features: One-Hot-Codierung für Features mit niedriger Kardinalität Funktionen und One-Hot-Hash-Codierung für kategorische Features mit hoher Kardinalität.

1. Transformationen und Codierungen

    Textfeatures mit sehr wenigen eindeutigen Werten, transformiert in kategorische Features. Führen Sie abhängig von der Kardinalität von kategorischen Features eine One-Hot-Codierung oder One-Hot-Hashcodierung durch.

## <a name="exit-criteria"></a>Beendigungskriterien

Definieren Sie die Kriterien, um Ihre Aufgabe abzuschließen:

1. Beenden nach einer bestimmten Zeitspanne – mit `MaxExperimentTimeInSeconds` in den Einstellungen Ihres Experiments können Sie in Sekunden definieren, wie lange eine Aufgabe noch ausgeführt werden soll.

1. Beenden bei Abbruchtoken – Sie können ein Abbruchtoken verwenden, mit dem Sie die Aufgabe vor dem geplanten Ende abbrechen können.

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a>Erstellen eines Experiments

Nachdem Sie die Experimenteinstellungen konfiguriert haben, können Sie das Experiment erstellen.

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a>Ausführen des Experiments

Das Ausführen des Experiments löst Datenvorverarbeitung, Auswahl des Lernalgorithmus und Optimieren von Hyperparametern aus. AutoML generiert weiterhin Kombinationen von Featurebereitstellung, Lernalgorithmen und Hyperparametern, bis `MaxExperimentTimeInSeconds` erreicht ist oder das Experiment beendet wird.

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

Untersuchen Sie andere Überladungen für `Execute()`, wenn Validierungsdaten, Spalteninformationen zur Angabe des Spaltenzwecks oder Prefeaturizers übergeben werden sollen.

## <a name="training-modes"></a>Trainingsmodi

### <a name="training-dataset"></a>Trainingsdataset

AutoML bietet eine Methode zur Ausführung eines überladenen Experiments, mit der Sie Trainingsdaten bereitstellen können. Die automatisierte ML unterteilt die Daten intern in „Trainieren-Überprüfen“-Unterteilungen.

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a>Benutzerdefiniertes Validierungsdataset

Verwenden Sie benutzerdefinierte Validierungsdatasets, wenn die Zufallsaufteilung nicht akzeptabel ist, was in der Regel auf Zeitreihendaten zutrifft. Sie können Ihr eigenes Validierungsdataset angeben. Das Modell wird anhand des angegebenen Validierungsdatasets anstatt eines oder mehrerer zufälliger Datasets ausgewertet.

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a>Untersuchen von Modellmetriken

Nach jeder Iteration eines ML-Experiments werden die mit dieser Aufgabe im Zusammenhang stehenden Metriken gespeichert.

Beispielsweise können wir auf Validierungsmetriken aus der besten Ausführung zugreifen:

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

Im Folgenden finden Sie alle verfügbaren Metriken pro ML-Aufgabe:

* [Metriken zur binären Klassifizierung](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [Metriken zur Multiklassenklassifizierung](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [Regressionsmetriken](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a>Siehe auch

Vollständige Codebeispiele und mehr finden Sie im GitHub-Repository [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state).
