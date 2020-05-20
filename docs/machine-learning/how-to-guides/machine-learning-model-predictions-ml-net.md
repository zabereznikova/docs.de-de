---
title: Treffen von Vorhersagen mit einem trainierten Modell
description: Erfahren Sie, wie Sie mit einem trainierten Modell Vorhersagen treffen
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977043"
---
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="e1750-103">Treffen von Vorhersagen mit einem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="e1750-103">Make predictions with a trained model</span></span>

<span data-ttu-id="e1750-104">Erfahren Sie, wie Sie ein trainiertes Modell verwenden, um Vorhersagen zu treffen</span><span class="sxs-lookup"><span data-stu-id="e1750-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="e1750-105">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="e1750-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="e1750-106">Eingabedaten</span><span class="sxs-lookup"><span data-stu-id="e1750-106">Input data</span></span>

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

### <a name="output-data"></a><span data-ttu-id="e1750-107">Ausgabedaten</span><span class="sxs-lookup"><span data-stu-id="e1750-107">Output data</span></span>

<span data-ttu-id="e1750-108">Für die vorhergesagten Wertspalten, die von einem Modell erstellt werden, hat ML.NET Standardnamen wie die Eingabespaltenamen `Features` und `Label`.</span><span class="sxs-lookup"><span data-stu-id="e1750-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="e1750-109">Abhängig von der Aufgabe kann der Name abweichen.</span><span class="sxs-lookup"><span data-stu-id="e1750-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="e1750-110">Da der in diesem Beispiel verwendete Algorithmus ein linearer Regressionsalgorithmus ist, lautet der Standardname der Ausgabespalte `Score` und wird durch das [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut für die `PredictedPrice`-Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="e1750-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="e1750-111">Einrichten einer Vorhersagepipeline</span><span class="sxs-lookup"><span data-stu-id="e1750-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="e1750-112">Die Vorhersagepipeline muss sowohl bei einer einzelnen als auch Batchvorhersage in die Anwendung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e1750-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="e1750-113">Diese Pipeline enthält sowohl die Vorverarbeitungs-Datentransformationen als auch das trainierte Modell.</span><span class="sxs-lookup"><span data-stu-id="e1750-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="e1750-114">Der folgende Codeausschnitt lädt die Vorhersagepipeline aus einer Datei namens `model.zip`.</span><span class="sxs-lookup"><span data-stu-id="e1750-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="e1750-115">Einzelne Vorhersage</span><span class="sxs-lookup"><span data-stu-id="e1750-115">Single prediction</span></span>

<span data-ttu-id="e1750-116">Um eine einzelne Vorhersage zu machen, erstellen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) mithilfe der geladenen Vorhersagepipeline.</span><span class="sxs-lookup"><span data-stu-id="e1750-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="e1750-117">Verwenden Sie dann die [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*)-Methode, und übergeben Sie Ihre Eingabedaten als Parameter.</span><span class="sxs-lookup"><span data-stu-id="e1750-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="e1750-118">Beachten Sie, dass die Verwendung der [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*)-Methode nicht voraussetzt, dass die Eingabe eine [`IDataView`](xref:Microsoft.ML.IDataView) ist.</span><span class="sxs-lookup"><span data-stu-id="e1750-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="e1750-119">Der Grund ist, dass sie die Bearbeitung des Eingabedatentyps einfach internalisiert, sodass Sie ein Objekt des Eingabedatentyps übergeben können.</span><span class="sxs-lookup"><span data-stu-id="e1750-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="e1750-120">Da darüber hinaus `CurrentPrice` das Ziel oder Label ist, das Sie mit den neuen Daten vorhersagen möchten, wird vorausgesetzt, dass zurzeit kein Wert dafür vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e1750-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

<span data-ttu-id="e1750-121">Wenn Sie auf die `Score`-Eigenschaft des `prediction`-Objekts zugreifen, sollten Sie einen Wert ähnlich wie `150079` erhalten.</span><span class="sxs-lookup"><span data-stu-id="e1750-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="e1750-122">Mehrere Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="e1750-122">Multiple predictions</span></span>

<span data-ttu-id="e1750-123">Laden Sie die folgenden Daten in eine [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="e1750-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="e1750-124">In diesem Fall ist `inputData` der Name von [`IDataView`](xref:Microsoft.ML.IDataView).</span><span class="sxs-lookup"><span data-stu-id="e1750-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="e1750-125">Da `CurrentPrice` das Ziel oder Label ist, das Sie mit den neuen Daten vorhersagen möchten, wird vorausgesetzt, dass zurzeit kein Wert dafür vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e1750-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f, 175000f, 210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

<span data-ttu-id="e1750-126">Verwenden Sie dann die [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode zum Anwenden der Datentransformationen und Generieren von Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="e1750-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="e1750-127">Überprüfen Sie die vorhergesagten Werte mit der [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="e1750-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="e1750-128">Die vorhergesagten Werte in der Bewertungsspalte sollten wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="e1750-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="e1750-129">Beobachtung</span><span class="sxs-lookup"><span data-stu-id="e1750-129">Observation</span></span> | <span data-ttu-id="e1750-130">Vorhersage</span><span class="sxs-lookup"><span data-stu-id="e1750-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="e1750-131">1</span><span class="sxs-lookup"><span data-stu-id="e1750-131">1</span></span> | <span data-ttu-id="e1750-132">144638.2</span><span class="sxs-lookup"><span data-stu-id="e1750-132">144638.2</span></span> |
| <span data-ttu-id="e1750-133">2</span><span class="sxs-lookup"><span data-stu-id="e1750-133">2</span></span> | <span data-ttu-id="e1750-134">150079.4</span><span class="sxs-lookup"><span data-stu-id="e1750-134">150079.4</span></span> |
| <span data-ttu-id="e1750-135">3</span><span class="sxs-lookup"><span data-stu-id="e1750-135">3</span></span> | <span data-ttu-id="e1750-136">107789.8</span><span class="sxs-lookup"><span data-stu-id="e1750-136">107789.8</span></span> |
