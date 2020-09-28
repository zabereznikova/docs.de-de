---
title: Erneutes Trainieren eines Modells
description: Erfahren Sie, wie Sie ein Modell in ML.NET erneut trainieren.
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 50f35e3511acc344339b1e150b47d7ce6de94254
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679559"
---
# <a name="re-train-a-model"></a><span data-ttu-id="bf81c-103">Erneutes Trainieren eines Modells</span><span class="sxs-lookup"><span data-stu-id="bf81c-103">Re-train a model</span></span>

<span data-ttu-id="bf81c-104">Erfahren Sie, wie ein Machine Learning-Modell in ML.NET erneut trainieren.</span><span class="sxs-lookup"><span data-stu-id="bf81c-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="bf81c-105">Die Welt und die Daten um sie herum verändern sich in einem konstanten Tempo.</span><span class="sxs-lookup"><span data-stu-id="bf81c-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="bf81c-106">Daher müssen auch Modelle geändert und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="bf81c-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="bf81c-107">ML.NET bietet Funktionen für das erneute Trainieren von Modellen unter Verwendung erlernter Modellparameter als Ausgangspunkt, um kontinuierlich auf früheren Erfahrungen aufzubauen, anstatt jedes Mal bei Null anzufangen.</span><span class="sxs-lookup"><span data-stu-id="bf81c-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>

<span data-ttu-id="bf81c-108">Die folgenden Algorithmen sind in ML.NET erneut trainierbar:</span><span class="sxs-lookup"><span data-stu-id="bf81c-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="bf81c-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="bf81c-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="bf81c-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="bf81c-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="bf81c-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="bf81c-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="bf81c-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="bf81c-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="bf81c-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="bf81c-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="bf81c-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="bf81c-119">Laden eines vorab trainierten Modells</span><span class="sxs-lookup"><span data-stu-id="bf81c-119">Load pre-trained model</span></span>

<span data-ttu-id="bf81c-120">Laden Sie zunächst das vorab trainierte Modell in Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bf81c-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="bf81c-121">Weitere Informationen über das Laden von Trainingspipelines und -modellen finden Sie unter [Speichern und Laden eines trainierten Modells](save-load-machine-learning-models-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="bf81c-121">To learn more about loading training pipelines and models, see [Save and load a trained model](save-load-machine-learning-models-ml-net.md).</span></span>

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

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="bf81c-122">Extrahieren von vorab trainierten Modellparametern</span><span class="sxs-lookup"><span data-stu-id="bf81c-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="bf81c-123">Sobald das Modell geladen ist, extrahieren Sie die erlernten Modellparameter, indem Sie auf die [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase%601.Model%2A)-Eigenschaft des vorab trainierten Modells zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bf81c-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase%601.Model%2A) property of the pre-trained model.</span></span> <span data-ttu-id="bf81c-124">Das vorab trainierte Modell wurde mit dem linearen Regressionsmodell [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) trainiert, das eine [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601)-Klasse erstellt, die eine [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters)-Klasse ausgibt.</span><span class="sxs-lookup"><span data-stu-id="bf81c-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="bf81c-125">Diese Parameter des linearen Regressionsmodells enthalten den erlernten Trend und die Gewichtung oder die Koeffizienten des Modells.</span><span class="sxs-lookup"><span data-stu-id="bf81c-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="bf81c-126">Diese Werte werden als Ausgangspunkt für das neue, erneut trainierte Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf81c-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters =
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="bf81c-127">Erneutes Trainieren eines Modells</span><span class="sxs-lookup"><span data-stu-id="bf81c-127">Re-train model</span></span>

<span data-ttu-id="bf81c-128">Der Prozess des erneuten Trainierens eines Modells unterscheidet sich nicht von dem des Trainierens eines Modells.</span><span class="sxs-lookup"><span data-stu-id="bf81c-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="bf81c-129">Der einzige Unterschied besteht darin, dass die [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer%602.Fit%2A)-Methode zusätzlich zu den Daten auch die ursprünglich erlernten Modellparameter als Eingabe übernimmt und sie als Ausgangspunkt für das erneute Training verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf81c-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer%602.Fit%2A) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>

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

## <a name="compare-model-parameters"></a><span data-ttu-id="bf81c-130">Vergleichen von Modellparametern</span><span class="sxs-lookup"><span data-stu-id="bf81c-130">Compare model parameters</span></span>

<span data-ttu-id="bf81c-131">Woher wissen Sie, ob das Modell wirklich erneut trainiert wurde?</span><span class="sxs-lookup"><span data-stu-id="bf81c-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="bf81c-132">Eine Möglichkeit wäre, zu vergleichen, ob sich die Parameter des erneut trainierten Modells von denen des Originalmodells unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bf81c-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="bf81c-133">Das folgende Codebeispiel vergleicht das Original mit den Gewichtungen des erneut trainierten Modells und gibt sie an die Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="bf81c-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

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

<span data-ttu-id="bf81c-134">In der folgenden Tabelle sehen Sie, wie eine Ausgabe aussehen könnte.</span><span class="sxs-lookup"><span data-stu-id="bf81c-134">The table below shows what the output might look like.</span></span>

|<span data-ttu-id="bf81c-135">Ursprünglich</span><span class="sxs-lookup"><span data-stu-id="bf81c-135">Original</span></span> | <span data-ttu-id="bf81c-136">Erneut trainiert</span><span class="sxs-lookup"><span data-stu-id="bf81c-136">Retrained</span></span> | <span data-ttu-id="bf81c-137">Unterschied</span><span class="sxs-lookup"><span data-stu-id="bf81c-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="bf81c-138">33039,86</span><span class="sxs-lookup"><span data-stu-id="bf81c-138">33039.86</span></span> | <span data-ttu-id="bf81c-139">56293,76</span><span class="sxs-lookup"><span data-stu-id="bf81c-139">56293.76</span></span> | <span data-ttu-id="bf81c-140">-23253,9</span><span class="sxs-lookup"><span data-stu-id="bf81c-140">-23253.9</span></span> |
| <span data-ttu-id="bf81c-141">29099,14</span><span class="sxs-lookup"><span data-stu-id="bf81c-141">29099.14</span></span> | <span data-ttu-id="bf81c-142">49586,03</span><span class="sxs-lookup"><span data-stu-id="bf81c-142">49586.03</span></span> | <span data-ttu-id="bf81c-143">-20486,89</span><span class="sxs-lookup"><span data-stu-id="bf81c-143">-20486.89</span></span> |
| <span data-ttu-id="bf81c-144">28938,38</span><span class="sxs-lookup"><span data-stu-id="bf81c-144">28938.38</span></span> | <span data-ttu-id="bf81c-145">48609,23</span><span class="sxs-lookup"><span data-stu-id="bf81c-145">48609.23</span></span> | <span data-ttu-id="bf81c-146">-19670,85</span><span class="sxs-lookup"><span data-stu-id="bf81c-146">-19670.85</span></span> |
| <span data-ttu-id="bf81c-147">30484,02</span><span class="sxs-lookup"><span data-stu-id="bf81c-147">30484.02</span></span> | <span data-ttu-id="bf81c-148">53745,43</span><span class="sxs-lookup"><span data-stu-id="bf81c-148">53745.43</span></span> | <span data-ttu-id="bf81c-149">-23261,41</span><span class="sxs-lookup"><span data-stu-id="bf81c-149">-23261.41</span></span> |
