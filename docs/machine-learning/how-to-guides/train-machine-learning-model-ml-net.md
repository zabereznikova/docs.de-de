---
title: Trainieren und Auswerten eines Modells
description: Erfahren Sie, wie Sie mit ML.NET Machine Learning-Modelle erstellen, Metriken erfassen und die Leistung messen können. Ein Machine Learning-Modell identifiziert Muster innerhalb von Trainingsdaten, um anhand von neuen Daten Vorhersagen zu treffen.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 0e0f43225b9bf243c31b3095817bdcbdb3123012
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976762"
---
# <a name="train-and-evaluate-a-model"></a>Trainieren und Auswerten eines Modells

Erfahren Sie, wie Sie mit ML.NET Machine Learning-Modelle erstellen, Metriken erfassen und die Leistung messen können. Obwohl dieses Beispiel ein Regressionsmodell trainiert, sind die Konzepte für einen Großteil der anderen Algorithmen anwendbar.

## <a name="split-data-for-training-and-testing"></a>Aufteilen von Daten für Training und Tests

Mit einem Machine Learning-Modell sollen Muster innerhalb von Trainingsdaten erkannt werden. Diese Muster werden zum Treffen von Vorhersagen mit neuen Daten verwendet.

Die Daten können durch eine Klasse wie `HousingData` modelliert werden.

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

Dafür müssen die folgenden Daten vorhanden sein, die in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden.

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

Verwenden Sie die [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*)-Methode, um die Daten in Trainings- und Testsätze aufzuteilen. Das Ergebnis ist ein [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData)-Objekt, das zwei [`IDataView`](xref:Microsoft.ML.IDataView)-Member enthält, eines für den Trainings- und das andere für den Testsatz. Der Prozentsatz der Datenaufteilung wird durch den `testFraction`-Parameter bestimmt. Der folgende Ausschnitt enthält 20 Prozent der Originaldaten für den Testsatz.

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a>Vorbereiten der Daten

Die Daten müssen vor dem Training eines Machine Learning-Modells vorverarbeitet werden. Weitere Informationen zur Datenaufbereitung finden Sie im [Anleitungsartikel für die Datenaufbereitung](prepare-data-ml-net.md) sowie in [`transforms page`](../resources/transforms.md).

Bei ML.NET-Algorithmen gibt es Einschränkungen hinsichtlich der Eingabespaltentypen. Außerdem werden für Ein- und Ausgabespaltennamen Standardwerte verwendet, wenn keine Werte angegeben werden.

### <a name="working-with-expected-column-types"></a>Arbeiten mit erwarteten Spaltentypen

Die Machine Learning-Algorithmen in ML.NET erwarten als Eingabe einen Float-Vektor mit bekannter Größe. Wenden Sie das [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute)-Attribut auf Ihr Datenmodell an, wenn alle Daten bereits im numerischen Format vorliegen und gemeinsam verarbeitet werden sollen (z.B. Bildpunkte).

Wenn die Daten nicht alle numerisch sind und Sie unterschiedliche Datentransformationen auf jede der Spalten einzeln anwenden möchten, verwenden Sie die [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*)-Methode, nachdem alle Spalten verarbeitet wurden, um alle einzelnen Spalten zu einem einzigen Featurevektor zu kombinieren, der an eine neue Spalte ausgegeben wird.

Das folgende Ausschnitt kombiniert die Spalten `Size` und `HistoricalPrices` zu einem einzigen Featurevektor, der in eine neue Spalte namens `Features` ausgegeben wird. Da es einen Unterschied in den Skalierungen gibt, wird [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) auf die Spalte `Features` angewendet, um die Daten zu normalisieren.

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a>Arbeiten mit standardmäßigen Spaltennamen

ML.NET-Algorithmen verwenden standardmäßige Spaltennamen, wenn keine Namen angegeben sind. Alle Trainer haben einen Parameter namens `featureColumnName` für die Eingaben des Algorithmus und gegebenenfalls auch einen Parameter für den erwarteten Wert namens `labelColumnName`. Standardmäßig sind das die Werte `Features` bzw. `Label`.

Durch die Verwendung der [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*)-Methode während der Vorverarbeitung zum Erstellen einer neuen Spalte mit dem Namen `Features` muss der Name der Featurespalte nicht in den Parametern des Algorithmus angegeben werden, da er bereits in der vorverarbeiteten `IDataView` vorhanden ist. Die Bezeichnungsspalte ist `CurrentPrice`, aber da das [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut im Datenmodell verwendet wird, benennt ML.NET die `CurrentPrice`-Spalte in `Label` um, sodass der `labelColumnName`-Parameter dem Estimator des Machine Learning-Algorithmus nicht mehr bereitgestellt werden muss.

Wenn Sie die standardmäßigen Spaltennamen nicht verwenden möchten, übergeben Sie die Namen der Feature- und Bezeichnungsspalten als Parameter bei der Definition des Estimators des Maschine Learning-Algorithmus, wie im nachfolgenden Ausschnitt gezeigt:

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a>Trainieren des Machine Learning-Modells

Sobald die Daten vorverarbeitet sind, verwenden Sie die [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*)-Methode, um das Machine Learning-Modell mit dem [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer)-Regressionsalgorithmus zu trainieren.

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a>Extrahieren von Modellparametern

Nachdem das Modell trainiert wurde, extrahieren Sie die gelernten [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) zur Überprüfung oder für das erneute Training. Die [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) stellen den den Trend und die erlernten Koeffizienten oder Gewichtungen des trainierten Modells bereit.

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> Andere Modelle haben für ihre Aufgaben spezifische Parameter. So stellt beispielsweise der [K-Means-Algorithmus](xref:Microsoft.ML.Trainers.KMeansTrainer) Daten in einen Cluster basierend auf Schwerpunkten bereit, und der [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) enthält eine Eigenschaft, die diese erlernten Schwerpunkte speichert. Um mehr zu erfahren, lesen Sie die [`Microsoft.ML.Trainers`-API-Dokumentation](xref:Microsoft.ML.Trainers), und suchen Sie nach Klassen, die `ModelParameters` in ihrem Namen enthalten.

## <a name="evaluate-model-quality"></a>Bewerten der Modellqualität

Um die Auswahl des leistungsstärksten Modells zu erleichtern, muss die Leistung anhand von Testdaten bewertet werden. Verwenden Sie die [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*)-Methode, um verschiedene Metriken für das trainierte Modell zu messen.

> [!NOTE]
> Die `Evaluate`-Methode liefert unterschiedliche Metriken, je nachdem, welche Machine Learning-Aufgabe durchgeführt wurde. Um mehr zu erfahren, lesen Sie die [`Microsoft.ML.Data`-API-Dokumentation](xref:Microsoft.ML.Data), und suchen Sie nach Klassen, die `Metrics` in ihrem Namen enthalten.

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

Im vorherigen Codebeispiel:

1. Das Testdataset wird unter Verwendung der zuvor definierten Datenaufbereitungstransformationen vorverarbeitet.
2. Das trainierte Machine Learning-Modell wird verwendet, um Vorhersagen zu den Testdaten zu treffen.
3. Bei der `Evaluate`-Methode werden die Werte in der Spalte `CurrentPrice` des Testdatasets mit der Spalte `Score` der neu ausgegebenen Vorhersagen verglichen, um die Metriken für das Regressionsmodell zu berechnen, von dem das Bestimmtheitsmaß in der `rSquared`-Variablen gespeichert wird.

> [!NOTE]
> In diesem kleinen Beispiel ist das Bestimmtheitsmaß eine Zahl, die aufgrund der begrenzten Größe der Daten nicht im Bereich von 0-1 liegt. In einem realen Szenario sollten Sie mit einem Wert zwischen 0 und 1 rechnen.
