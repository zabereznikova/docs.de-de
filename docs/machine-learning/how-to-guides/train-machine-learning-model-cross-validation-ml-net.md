---
title: Trainieren eines Machine Learning-Modells mit der Kreuzvalidierung
description: Erfahren Sie, wie Sie mit der Kreuzvalidierung stabilere Machine Learning-Modelle in ML.NET erstellen. Die Kreuzvalidierung ist eine Trainings- und Modellevaluierungstechnik, die die Daten in mehrere Partitionen unterteilt und mehrere Algorithmen auf diesen Partitionen trainiert.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 87eae789478752423f3e682d4db6cead0391aa6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976931"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a>Trainieren eines Machine Learning-Modells mit der Kreuzvalidierung

Erfahren Sie, wie Sie mit der Kreuzvalidierung stabilere Machine Learning-Modelle in ML.NET trainieren.

Die Kreuzvalidierung ist eine Trainings- und Modellevaluierungstechnik, die die Daten in mehrere Partitionen unterteilt und mehrere Algorithmen auf diesen Partitionen trainiert. Dieses Verfahren verbessert die Stabilität des Modells, indem Daten aus dem Trainingsprozess bereitgehalten werden. Abgesehen vom Verbessern der Leistung bei nicht angezeigten Beobachtungen kann es in Umgebungen mit Dateneinschränkungen ein effektives Tool sein, um Modelle mit einem kleineren Dataset zu trainieren.

## <a name="the-data-and-data-model"></a>Die Daten und das Datenmodell

Bei Daten aus einer Datei mit folgendem Format:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

Die Daten können durch eine Klasse wie `HousingData` modelliert und in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden.

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

## <a name="prepare-the-data"></a>Vorbereiten der Daten

Führen Sie eine Vorverarbeitung der Daten durch, bevor Sie damit das Machine Learning-Modell erstellen. In diesem Beispiel werden die Spalten `Size` und `HistoricalPrices` zu einem einzelnen Featurevektor kombiniert, der in einer neuen Spalte namens `Features` mithilfe der [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*)-Methode ausgegeben wird. Zusätzlich zum Abrufen der Daten in das von ML.NET-Algorithmen erwartete Format optimiert die Verkettung von Spalten nachfolgende Vorgänge in der Pipeline, indem der Vorgang einmal auf die verkettete Spalte statt auf jede separate Spalte angewendet wird.

Nachdem die Spalten in einem einzelnen Vektor kombiniert sind, wird [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) auf die abzurufende Spalte `Features` angewendet, um `Size` und `HistoricalPrices` im selben Bereich zwischen 0 und 1 abzurufen.

```csharp
// Define data prep estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Transform data
IDataView transformedData = dataPrepTransformer.Transform(data);
```

## <a name="train-model-with-cross-validation"></a>Trainieren eines Modells mit Kreuzvalidierung

Nach der Vorverarbeitung der Daten kann das Modell trainiert werden. Wählen Sie zunächst den Algorithmus aus, der der auszuführenden Machine Learning-Aufgabe am ehesten entspricht. Da der vorhergesagte Wert ein numerischer kontinuierlicher Wert ist, handelt es sich um eine Regressionsaufgabe. Einer der von ML.NET implementierten Regressionsalgorithmen ist der [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer)-Algorithmus. Um das Modell mit Kreuzvalidierung zu trainieren, verwenden Sie die [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*)-Methode.

> [!NOTE]
> Obwohl in diesem Beispiel ein lineares Regressionsmodell verwendet wird, kann CrossValidate für alle anderen Machine Learning-Aufgaben in ML.NET mit Ausnahme der Erkennung von Anomalien verwendet werden.

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) führt die folgenden Vorgänge aus:

1. Partitionieren der Daten in eine Anzahl von Partitionen, die dem im `numberOfFolds`-Parameter angegebenen Wert entspricht. Das Ergebnis der einzelnen Partitionen ist ein [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData)-Objekt.
1. Für jede der Partitionen wird mit dem angegebenen Machine Learning-Algorithmuskalkulator ein Modell mit dem Trainingsdataset trainiert.
1. Die Leistung jedes Modells wird mit der [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*)-Methode für das Testdataset ausgewertet.
1. Das Modell wird mit seinen Metriken für jedes der Modelle zurückgegeben.

Das in `cvResults` gespeicherte Ergebnis ist eine Sammlung von [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601)-Objekten. Dieses Objekt enthält das trainierte Modell sowie Metriken, und auf beides kann über die [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model)- bzw. [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics)-Eigenschaft zugegriffen werden. In diesem Beispiel ist die `Model`-Eigenschaft vom Typ [`ITransformer`](xref:Microsoft.ML.ITransformer) und die `Metrics`-Eigenschaft vom Typ [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).

## <a name="evaluate-the-model"></a>Evaluieren des Modells

Auf Metriken für die verschiedenen trainierten Modelle kann über die `Metrics`-Eigenschaft des einzelnen [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601)-Objekts zugegriffen werden. In diesem Fall wird auf die [Determinationskoeffizientenmetrik](https://en.wikipedia.org/wiki/Coefficient_of_determination) zugegriffen, und sie wird in der Variablen `rSquared` gespeichert.

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

Wenn Sie den Inhalt der `rSquared`-Variablen untersuchen, sollte die Ausgabe fünf Werte im Bereich von 0-1 umfassen, wobei der Wert besser ist, je näher er an 1 liegt. Wählen Sie mit Metriken wie der Determinationskoeffizientenmetrik die Modelle aus, von dem mit der besten bis zu dem mit der schlechtesten Leistung. Wählen Sie dann das oberste Modell aus, um Vorhersagen zu treffen oder zusätzliche Vorgänge damit auszuführen.

```csharp
// Select all models
ITransformer[] models =
    cvResults
        .OrderByDescending(fold => fold.Metrics.RSquared)
        .Select(fold => fold.Model)
        .ToArray();

// Get Top Model
ITransformer topModel = models[0];
```
