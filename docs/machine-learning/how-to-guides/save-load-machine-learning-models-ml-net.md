---
title: Speichern und Laden trainierter Modelle
description: Erfahren Sie, wie Sie trainierte Modelle speichern und laden
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: e3cebe979b5c279ce8cb90db5510f8758c24c2b4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977008"
---
# <a name="save-and-load-trained-models"></a><span data-ttu-id="24041-103">Speichern und Laden trainierter Modelle</span><span class="sxs-lookup"><span data-stu-id="24041-103">Save and load trained models</span></span>

<span data-ttu-id="24041-104">Erfahren Sie, wie Sie trainierte Modelle in Ihre Anwendung laden und dort speichern.</span><span class="sxs-lookup"><span data-stu-id="24041-104">Learn how to save and load trained models in your application.</span></span>

<span data-ttu-id="24041-105">Im gesamten Modellerstellungsprozess liegt ein Modell im Arbeitsspeicher vor, auf das während des gesamten Lebenszyklus der Anwendung zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="24041-105">Throughout the model building process, a model lives in memory and is accessible throughout the application's lifecycle.</span></span> <span data-ttu-id="24041-106">Doch sobald die Ausführung der Anwendung beendet wird, kann auf das Modell nicht mehr zugegriffen werden, wenn es nicht lokal oder remote gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="24041-106">However, once the application stops running, if the model is not saved somewhere locally or remotely, it's no longer accessible.</span></span> <span data-ttu-id="24041-107">Modelle werden in der Regel ab einem bestimmten Punkt nach dem Training entweder für Rückschlüsse oder erneutes Training in anderen Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="24041-107">Typically models are used at some point after training in other applications either for inference or re-training.</span></span> <span data-ttu-id="24041-108">Aus diesem Grund ist es wichtig, das Modell zu speichern.</span><span class="sxs-lookup"><span data-stu-id="24041-108">Therefore, it's important to store the model.</span></span> <span data-ttu-id="24041-109">Speichern und laden Sie Modelle mithilfe der in den nachfolgenden Abschnitten dieses Dokuments beschriebenen Schritte, wenn Sie Datenvorbereitungs- und Modelltrainingpipelines wie die nachfolgend beschriebenen verwenden.</span><span class="sxs-lookup"><span data-stu-id="24041-109">Save and load models using the steps described in subsequent sections of this document when using data preparation and model training pipelines like the one detailed below.</span></span> <span data-ttu-id="24041-110">Obwohl in diesem Beispiel ein lineares Regressionsmodell verwendet wird, gilt der gleiche Prozess für andere ML.NET-Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="24041-110">Although this sample uses a linear regression model, the same process applies to other ML.NET algorithms.</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f, 125000f, 122000f },
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
    }
};

// Create MLContext
MLContext mlContext = new MLContext();

// Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Define data preparation estimator
EstimatorChain<RegressionPredictionTransformer<LinearRegressionModelParameters>> pipelineEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .Append(mlContext.Regression.Trainers.Sdca());

// Train model
ITransformer trainedModel = pipelineEstimator.Fit(data);

// Save model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

<span data-ttu-id="24041-111">Da die meisten Modelle und Datenvorbereitungspipelines von demselben Klassensatz erben, sind die Speicher- und Lademethodensignaturen für diese Komponenten identisch.</span><span class="sxs-lookup"><span data-stu-id="24041-111">Because most models and data preparation pipelines inherit from the same set of classes, the save and load method signatures for these components is the same.</span></span> <span data-ttu-id="24041-112">Abhängig von Ihrem Anwendungsfall können Sie entweder Datenvorbereitungspipeline und Modell in einer einzelnen [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) kombinieren, sodass ein einzelner [`ITransformer`](xref:Microsoft.ML.ITransformer) ausgeben würde, oder sie trennen und für beide jeweils einen separaten [`ITransformer`](xref:Microsoft.ML.ITransformer) erstellen.</span><span class="sxs-lookup"><span data-stu-id="24041-112">Depending on your use case, you can either combine the data preparation pipeline and model into a single [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) which would output a single [`ITransformer`](xref:Microsoft.ML.ITransformer) or separate them thus creating a separate [`ITransformer`](xref:Microsoft.ML.ITransformer) for each.</span></span>

## <a name="save-a-model-locally"></a><span data-ttu-id="24041-113">Lokales Speichern eines Modells</span><span class="sxs-lookup"><span data-stu-id="24041-113">Save a model locally</span></span>

<span data-ttu-id="24041-114">Beim Speichern eines Modells benötigen Sie zwei Dinge:</span><span class="sxs-lookup"><span data-stu-id="24041-114">When saving a model you need two things:</span></span>

1. <span data-ttu-id="24041-115">Den [`ITransformer`](xref:Microsoft.ML.ITransformer) des Modells.</span><span class="sxs-lookup"><span data-stu-id="24041-115">The [`ITransformer`](xref:Microsoft.ML.ITransformer) of the model.</span></span>
2. <span data-ttu-id="24041-116">Das [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) der erwarteten Eingabe des [`ITransformer`](xref:Microsoft.ML.ITransformer).</span><span class="sxs-lookup"><span data-stu-id="24041-116">The [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) of the [`ITransformer`](xref:Microsoft.ML.ITransformer)'s expected input.</span></span>

<span data-ttu-id="24041-117">Speichern Sie nach dem Training des Modells das trainierte Modell mit der [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*)-Methode in einer Datei namens `model.zip` unter Verwendung des `DataViewSchema` der Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="24041-117">After training the model, use the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to save the trained model to a file called `model.zip` using the `DataViewSchema` of the input data.</span></span>

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a><span data-ttu-id="24041-118">Laden eines lokal gespeicherten Modells</span><span class="sxs-lookup"><span data-stu-id="24041-118">Load a model stored locally</span></span>

<span data-ttu-id="24041-119">Lokal gespeicherte Modelle können in anderen Prozessen oder Anwendungen wie `ASP.NET Core` und `Serverless Web Applications` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24041-119">Models stored locally can be used in other processes or applications like `ASP.NET Core` and `Serverless Web Applications`.</span></span> <span data-ttu-id="24041-120">Unter [Vorgehensweise: Bereitstellen eines Machine Learning-Modells über die ASP.NET Core-Web-API](./serve-model-web-api-ml-net.md) und [Vorgehensweise: Verwenden des ML.NET-Modells in Azure Functions](./serve-model-serverless-azure-functions-ml-net.md) finden Sie nähere Anleitungen.</span><span class="sxs-lookup"><span data-stu-id="24041-120">See [Use ML.NET in Web API](./serve-model-web-api-ml-net.md) and [Deploy ML.NET Serverless Web App](./serve-model-serverless-azure-functions-ml-net.md) how-to articles to learn more.</span></span>

<span data-ttu-id="24041-121">Verwenden Sie in separaten Anwendungen oder Prozessen die [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*)-Methode zusammen mit den Dateipfad, um das trainierte Modell in Ihre Anwendung zu laden.</span><span class="sxs-lookup"><span data-stu-id="24041-121">In a separate application or process, use the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method along with the file path to get the trained model into your application.</span></span>

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a><span data-ttu-id="24041-122">Laden eines remote gespeicherten Modells</span><span class="sxs-lookup"><span data-stu-id="24041-122">Load a model stored remotely</span></span>

<span data-ttu-id="24041-123">Um Datenvorbereitungspipelines und an einem Remotespeicherort gespeicherte Modelle in Ihre Anwendung zu laden, verwenden Sie einen [`Stream`](xref:System.IO.Stream) anstatt eines Dateipfads in der [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*)-Methode.</span><span class="sxs-lookup"><span data-stu-id="24041-123">To load data preparation pipelines and models stored in a remote location into your application, use a [`Stream`](xref:System.IO.Stream) instead of a file path in the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema and ITransformers
DataViewSchema modelSchema;
ITransformer trainedModel;

// Load data prep pipeline and trained model
using (HttpClient client = new HttpClient())
{
    Stream modelFile = await client.GetStreamAsync("<YOUR-REMOTE-FILE-LOCATION>");

    trainedModel = mlContext.Model.Load(modelFile, out modelSchema);
}
```

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a><span data-ttu-id="24041-124">Arbeiten mit separaten Datenvorbereitungs- und Modellpipelines</span><span class="sxs-lookup"><span data-stu-id="24041-124">Working with separate data preparation and model pipelines</span></span>

> [!NOTE]
> <span data-ttu-id="24041-125">Arbeiten mit separaten Datenvorbereitungs- und Modelltrainingspipelines ist optional.</span><span class="sxs-lookup"><span data-stu-id="24041-125">Working with separate data preparation and model training pipelines is optional.</span></span> <span data-ttu-id="24041-126">Die Trennung von Pipelines erleichtert die Überprüfung der gelernten Modellparameter.</span><span class="sxs-lookup"><span data-stu-id="24041-126">Separation of pipelines makes it easier to inspect the learned model parameters.</span></span> <span data-ttu-id="24041-127">Für Vorhersagen ist es einfacher, eine einzelne Pipeline zu speichern und zu laden, die die Datenvorbereitungs- und Modelltrainingsvorgänge enthält.</span><span class="sxs-lookup"><span data-stu-id="24041-127">For predictions, it's easier to save and load a single pipeline that includes the data preparation and model training operations.</span></span>

<span data-ttu-id="24041-128">Bei der Arbeit mit separaten Datenvorbereitungspipelines und Modellen wird derselbe Prozess wie bei einzelnen Pipelines durchgeführt, mit dem Unterschied, dass nun beide Pipelines gleichzeitig gespeichert und geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="24041-128">When working with separate data preparation pipelines and models, the same process as single pipelines applies; except now both pipelines need to be saved and loaded simultaneously.</span></span>

<span data-ttu-id="24041-129">Bei separaten Datenvorbereitungs- und Modelltrainingspipelines:</span><span class="sxs-lookup"><span data-stu-id="24041-129">Given separate data preparation and model training pipelines:</span></span>

```csharp
// Define data preparation estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data preparation transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Pre-process data using data prep operations
IDataView transformedData = dataPrepTransformer.Transform(data);

// Train regression model
RegressionPredictionTransformer<LinearRegressionModelParameters> trainedModel = sdcaEstimator.Fit(transformedData);
```

### <a name="save-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="24041-130">Speichern von Datenvorbereitungspipeline und trainiertem Modell</span><span class="sxs-lookup"><span data-stu-id="24041-130">Save data preparation pipeline and trained model</span></span>

<span data-ttu-id="24041-131">Um Datenvorbereitungspipeline und trainiertes Modell zu speichern, verwenden Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="24041-131">To save both the data preparation pipeline and trained model, use the following commands:</span></span>

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="24041-132">Laden von Datenvorbereitungspipeline und trainiertem Modell</span><span class="sxs-lookup"><span data-stu-id="24041-132">Load data preparation pipeline and trained model</span></span>

<span data-ttu-id="24041-133">Laden Sie in einem separaten Prozess oder einer separaten Anwendung die Datenvorbereitungspipeline und das trainierte Modell gleichzeitig wie folgt:</span><span class="sxs-lookup"><span data-stu-id="24041-133">In a separate process or application, load the data preparation pipeline and trained model simultaneously as follows:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
