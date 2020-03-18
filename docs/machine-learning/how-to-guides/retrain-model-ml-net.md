---
title: Erneutes Trainieren eines Modells
description: Erfahren Sie, wie Sie ein Modell in ML.NET erneut trainieren.
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 735782a4a0877a917b6e1885f009aa49d834170f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976968"
---
# <a name="re-train-a-model"></a>Erneutes Trainieren eines Modells

Erfahren Sie, wie ein Machine Learning-Modell in ML.NET erneut trainieren.

Die Welt und die Daten um sie herum verändern sich in einem konstanten Tempo. Daher müssen auch Modelle geändert und aktualisiert werden. ML.NET bietet Funktionen für das erneute Trainieren von Modellen unter Verwendung erlernter Modellparameter als Ausgangspunkt, um kontinuierlich auf früheren Erfahrungen aufzubauen, anstatt jedes Mal bei Null anzufangen.

Die folgenden Algorithmen sind in ML.NET erneut trainierbar:

- [AveragedPerceptronTrainer](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [FieldAwareFactorizationMachineTrainer](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [LbfgsLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [LbfgsMaximumEntropyMulticlassTrainer](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [LbfgsPoissonRegressionTrainer](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [LinearSvmTrainer](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [OnlineGradientDescentTrainer](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [SgdCalibratedTrainer](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [SgdNonCalibratedTrainer](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [SymbolicSgdLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a>Laden eines vorab trainierten Modells

Laden Sie zunächst das vorab trainierte Modell in Ihrer Anwendung. Weitere Informationen über das Laden von Trainingspipelines und -modellen finden Sie unter [Speichern und Laden eines trainierten Modells](save-load-machine-learning-models-ml-net.md).

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a>Extrahieren von vorab trainierten Modellparametern

Sobald das Modell geladen ist, extrahieren Sie die erlernten Modellparameter, indem Sie auf die [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*)-Eigenschaft des vorab trainierten Modells zugreifen. Das vorab trainierte Modell wurde mit dem linearen Regressionsmodell [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) trainiert, das einen [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) erstellt, der [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) ausgibt. Diese Parameter des linearen Regressionsmodells enthalten den erlernten Trend und die Gewichtung oder die Koeffizienten des Modells. Diese Werte werden als Ausgangspunkt für das neue, erneut trainierte Modell verwendet.

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters =
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a>Erneutes Trainieren eines Modells

Der Prozess des erneuten Trainierens eines Modells unterscheidet sich nicht von dem des Trainierens eines Modells. Der einzige Unterschied besteht darin, dass die [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*)-Methode zusätzlich zu den Daten auch die ursprünglich erlernten Modellparameter als Eingabe übernimmt und sie als Ausgangspunkt für das erneute Training verwendet.

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
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

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel =
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a>Vergleichen von Modellparametern

Woher wissen Sie, ob das Modell wirklich erneut trainiert wurde? Eine Möglichkeit wäre, zu vergleichen, ob sich die Parameter des erneut trainierten Modells von denen des Originalmodells unterscheiden. Das folgende Codebeispiel vergleicht das Original mit den Gewichtungen des erneut trainierten Modells und gibt sie an die Konsole aus.

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs =
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

In der folgenden Tabelle sehen Sie, wie eine Ausgabe aussehen könnte.

|Ursprünglich | Erneut trainiert | Unterschied |
|---|---|---|
| 33039,86 | 56293,76 | -23253,9 |
| 29099,14 | 49586,03 | -20486,89 |
| 28938,38 | 48609,23 | -19670,85 |
| 30484,02 | 53745,43 | -23261,41 |
