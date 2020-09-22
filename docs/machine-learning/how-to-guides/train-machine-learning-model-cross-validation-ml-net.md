---
title: Trainieren eines Machine Learning-Modells mit der Kreuzvalidierung
description: Erfahren Sie, wie Sie mit der Kreuzvalidierung stabilere Machine Learning-Modelle in ML.NET erstellen. Die Kreuzvalidierung ist eine Trainings- und Modellevaluierungstechnik, die die Daten in mehrere Partitionen unterteilt und mehrere Algorithmen auf diesen Partitionen trainiert.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 02cec3d22588d8f10d36216422bc19faafffe94b
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679520"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a><span data-ttu-id="9baf1-104">Trainieren eines Machine Learning-Modells mit der Kreuzvalidierung</span><span class="sxs-lookup"><span data-stu-id="9baf1-104">Train a machine learning model using cross validation</span></span>

<span data-ttu-id="9baf1-105">Erfahren Sie, wie Sie mit der Kreuzvalidierung stabilere Machine Learning-Modelle in ML.NET trainieren.</span><span class="sxs-lookup"><span data-stu-id="9baf1-105">Learn how to use cross validation to train more robust machine learning models in ML.NET.</span></span>

<span data-ttu-id="9baf1-106">Die Kreuzvalidierung ist eine Trainings- und Modellevaluierungstechnik, die die Daten in mehrere Partitionen unterteilt und mehrere Algorithmen auf diesen Partitionen trainiert.</span><span class="sxs-lookup"><span data-stu-id="9baf1-106">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="9baf1-107">Dieses Verfahren verbessert die Stabilität des Modells, indem Daten aus dem Trainingsprozess bereitgehalten werden.</span><span class="sxs-lookup"><span data-stu-id="9baf1-107">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="9baf1-108">Abgesehen vom Verbessern der Leistung bei nicht angezeigten Beobachtungen kann es in Umgebungen mit Dateneinschränkungen ein effektives Tool sein, um Modelle mit einem kleineren Dataset zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="9baf1-108">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

## <a name="the-data-and-data-model"></a><span data-ttu-id="9baf1-109">Die Daten und das Datenmodell</span><span class="sxs-lookup"><span data-stu-id="9baf1-109">The data and data model</span></span>

<span data-ttu-id="9baf1-110">Bei Daten aus einer Datei mit folgendem Format:</span><span class="sxs-lookup"><span data-stu-id="9baf1-110">Given data from a file that has the following format:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

<span data-ttu-id="9baf1-111">Die Daten können durch eine Klasse wie `HousingData` modelliert und in eine [`IDataView`](xref:Microsoft.ML.IDataView) geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf1-111">The data can be modeled by a class like `HousingData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

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

## <a name="prepare-the-data"></a><span data-ttu-id="9baf1-112">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="9baf1-112">Prepare the data</span></span>

<span data-ttu-id="9baf1-113">Führen Sie eine Vorverarbeitung der Daten durch, bevor Sie damit das Machine Learning-Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="9baf1-113">Pre-process the data before using it to build the machine learning model.</span></span> <span data-ttu-id="9baf1-114">In diesem Beispiel werden die Spalten `Size` und `HistoricalPrices` zu einem einzelnen Featurevektor kombiniert, der in einer neuen Spalte namens `Features` mithilfe der [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A)-Methode ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9baf1-114">In this sample, the `Size` and `HistoricalPrices` columns are combined into a single feature vector,  which is output to a new column called `Features` using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A) method.</span></span> <span data-ttu-id="9baf1-115">Zusätzlich zum Abrufen der Daten in das von ML.NET-Algorithmen erwartete Format optimiert die Verkettung von Spalten nachfolgende Vorgänge in der Pipeline, indem der Vorgang einmal auf die verkettete Spalte statt auf jede separate Spalte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9baf1-115">In addition to getting the data into the format expected by ML.NET algorithms, concatenating columns optimizes subsequent operations in the pipeline by applying the operation once for the concatenated column instead of each of the separate columns.</span></span>

<span data-ttu-id="9baf1-116">Nachdem die Spalten in einem einzelnen Vektor kombiniert sind, wird [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) auf die abzurufende Spalte `Features` angewendet, um `Size` und `HistoricalPrices` im selben Bereich zwischen 0 und 1 abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9baf1-116">Once the columns are combined into a single vector, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) is applied to the `Features` column to get `Size` and `HistoricalPrices` in the same range between 0-1.</span></span>

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

## <a name="train-model-with-cross-validation"></a><span data-ttu-id="9baf1-117">Trainieren eines Modells mit Kreuzvalidierung</span><span class="sxs-lookup"><span data-stu-id="9baf1-117">Train model with cross validation</span></span>

<span data-ttu-id="9baf1-118">Nach der Vorverarbeitung der Daten kann das Modell trainiert werden.</span><span class="sxs-lookup"><span data-stu-id="9baf1-118">Once the data has been pre-processed, it's time to train the model.</span></span> <span data-ttu-id="9baf1-119">Wählen Sie zunächst den Algorithmus aus, der der auszuführenden Machine Learning-Aufgabe am ehesten entspricht.</span><span class="sxs-lookup"><span data-stu-id="9baf1-119">First, select the algorithm that most closely aligns with the machine learning task to be performed.</span></span> <span data-ttu-id="9baf1-120">Da der vorhergesagte Wert ein numerischer kontinuierlicher Wert ist, handelt es sich um eine Regressionsaufgabe.</span><span class="sxs-lookup"><span data-stu-id="9baf1-120">Because the predicted value is a numerically continuous value, the task is regression.</span></span> <span data-ttu-id="9baf1-121">Einer der von ML.NET implementierten Regressionsalgorithmen ist der [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer)-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="9baf1-121">One of the regression algorithms implemented by ML.NET is the [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorithm.</span></span> <span data-ttu-id="9baf1-122">Um das Modell mit Kreuzvalidierung zu trainieren, verwenden Sie die [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A)-Methode.</span><span class="sxs-lookup"><span data-stu-id="9baf1-122">To train the model with cross-validation use the [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) method.</span></span>

> [!NOTE]
> <span data-ttu-id="9baf1-123">Obwohl in diesem Beispiel ein lineares Regressionsmodell verwendet wird, kann CrossValidate für alle anderen Machine Learning-Aufgaben in ML.NET mit Ausnahme der Erkennung von Anomalien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9baf1-123">Although this sample uses a linear regression model, CrossValidate is applicable to all other machine learning tasks in ML.NET except Anomaly Detection.</span></span>

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

<span data-ttu-id="9baf1-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) führt die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="9baf1-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate%2A) performs the following operations:</span></span>

1. <span data-ttu-id="9baf1-125">Partitionieren der Daten in eine Anzahl von Partitionen, die dem im `numberOfFolds`-Parameter angegebenen Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="9baf1-125">Partitions the data into a number of partitions equal to the value specified in the `numberOfFolds` parameter.</span></span> <span data-ttu-id="9baf1-126">Das Ergebnis der einzelnen Partitionen ist ein [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData)-Objekt.</span><span class="sxs-lookup"><span data-stu-id="9baf1-126">The result of each partition is a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object.</span></span>
1. <span data-ttu-id="9baf1-127">Für jede der Partitionen wird mit dem angegebenen Machine Learning-Algorithmuskalkulator ein Modell mit dem Trainingsdataset trainiert.</span><span class="sxs-lookup"><span data-stu-id="9baf1-127">A model is trained on each of the partitions using the specified machine learning algorithm estimator on the training data set.</span></span>
1. <span data-ttu-id="9baf1-128">Die Leistung jedes Modells wird mit der [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A)-Methode für das Testdataset ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9baf1-128">Each model's performance is evaluated using the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) method on the test data set.</span></span>
1. <span data-ttu-id="9baf1-129">Das Modell wird mit seinen Metriken für jedes der Modelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9baf1-129">The model along with its metrics are returned for each of the models.</span></span>

<span data-ttu-id="9baf1-130">Das in `cvResults` gespeicherte Ergebnis ist eine Sammlung von [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601)-Objekten.</span><span class="sxs-lookup"><span data-stu-id="9baf1-130">The result stored in `cvResults` is a collection of [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) objects.</span></span> <span data-ttu-id="9baf1-131">Dieses Objekt enthält das trainierte Modell sowie Metriken, und auf beides kann über die [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model)- bzw. [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics)-Eigenschaft zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf1-131">This object includes the trained model as well as metrics which are both accessible form the [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) and [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) properties respectively.</span></span> <span data-ttu-id="9baf1-132">In diesem Beispiel ist die `Model`-Eigenschaft vom Typ [`ITransformer`](xref:Microsoft.ML.ITransformer) und die `Metrics`-Eigenschaft vom Typ [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span><span class="sxs-lookup"><span data-stu-id="9baf1-132">In this sample, the `Model` property is of type [`ITransformer`](xref:Microsoft.ML.ITransformer) and the `Metrics` property is of type [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="9baf1-133">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="9baf1-133">Evaluate the model</span></span>

<span data-ttu-id="9baf1-134">Auf Metriken für die verschiedenen trainierten Modelle kann über die `Metrics`-Eigenschaft des einzelnen [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601)-Objekts zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9baf1-134">Metrics for the different trained models can be accessed through the `Metrics` property of the individual [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) object.</span></span> <span data-ttu-id="9baf1-135">In diesem Fall wird auf die [Determinationskoeffizientenmetrik](https://en.wikipedia.org/wiki/Coefficient_of_determination) zugegriffen, und sie wird in der Variablen `rSquared` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9baf1-135">In this case, the [R-Squared metric](https://en.wikipedia.org/wiki/Coefficient_of_determination) is accessed and stored in the variable `rSquared`.</span></span>

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

<span data-ttu-id="9baf1-136">Wenn Sie den Inhalt der `rSquared`-Variablen untersuchen, sollte die Ausgabe fünf Werte im Bereich von 0-1 umfassen, wobei der Wert besser ist, je näher er an 1 liegt.</span><span class="sxs-lookup"><span data-stu-id="9baf1-136">If you inspect the contents of the `rSquared` variable, the output should be five values ranging from 0-1 where closer to 1 means best.</span></span> <span data-ttu-id="9baf1-137">Wählen Sie mit Metriken wie der Determinationskoeffizientenmetrik die Modelle aus, von dem mit der besten bis zu dem mit der schlechtesten Leistung.</span><span class="sxs-lookup"><span data-stu-id="9baf1-137">Using metrics like R-Squared, select the models from best to worst performing.</span></span> <span data-ttu-id="9baf1-138">Wählen Sie dann das oberste Modell aus, um Vorhersagen zu treffen oder zusätzliche Vorgänge damit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9baf1-138">Then, select the top model to make predictions or perform additional operations with.</span></span>

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
