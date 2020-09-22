---
title: Speichern und Laden trainierter Modelle
description: Erfahren Sie, wie Sie trainierte Modelle speichern und laden
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 681a35956a8959e2f1cbb5a7023e0ef29b67097e
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679533"
---
# <a name="save-and-load-trained-models"></a>Speichern und Laden trainierter Modelle

Erfahren Sie, wie Sie trainierte Modelle in Ihre Anwendung laden und dort speichern.

Im gesamten Modellerstellungsprozess liegt ein Modell im Arbeitsspeicher vor, auf das während des gesamten Lebenszyklus der Anwendung zugegriffen werden kann. Doch sobald die Ausführung der Anwendung beendet wird, kann auf das Modell nicht mehr zugegriffen werden, wenn es nicht lokal oder remote gespeichert wird. Modelle werden in der Regel ab einem bestimmten Punkt nach dem Training entweder für Rückschlüsse oder erneutes Training in anderen Anwendungen verwendet. Aus diesem Grund ist es wichtig, das Modell zu speichern. Speichern und laden Sie Modelle mithilfe der in den nachfolgenden Abschnitten dieses Dokuments beschriebenen Schritte, wenn Sie Datenvorbereitungs- und Modelltrainingpipelines wie die nachfolgend beschriebenen verwenden. Obwohl in diesem Beispiel ein lineares Regressionsmodell verwendet wird, gilt der gleiche Prozess für andere ML.NET-Algorithmen.

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

Da die meisten Modelle und Datenvorbereitungspipelines von demselben Klassensatz erben, sind die Speicher- und Lademethodensignaturen für diese Komponenten identisch. Abhängig von Ihrem Anwendungsfall können Sie entweder Datenvorbereitungspipeline und Modell in einer einzelnen [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) kombinieren, sodass ein einzelner [`ITransformer`](xref:Microsoft.ML.ITransformer) ausgeben würde, oder sie trennen und für beide jeweils einen separaten [`ITransformer`](xref:Microsoft.ML.ITransformer) erstellen.

## <a name="save-a-model-locally"></a>Lokales Speichern eines Modells

Beim Speichern eines Modells benötigen Sie zwei Dinge:

1. Den [`ITransformer`](xref:Microsoft.ML.ITransformer) des Modells.
2. Das [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) der erwarteten Eingabe des [`ITransformer`](xref:Microsoft.ML.ITransformer).

Speichern Sie nach dem Training des Modells das trainierte Modell mit der [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save%2A)-Methode in einer Datei namens `model.zip` unter Verwendung des `DataViewSchema` der Eingabedaten.

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a>Laden eines lokal gespeicherten Modells

Lokal gespeicherte Modelle können in anderen Prozessen oder Anwendungen wie `ASP.NET Core` und `Serverless Web Applications` verwendet werden. Unter [Vorgehensweise: Bereitstellen eines Machine Learning-Modells über die ASP.NET Core-Web-API](./serve-model-web-api-ml-net.md) und [Vorgehensweise: Verwenden des ML.NET-Modells in Azure Functions](./serve-model-serverless-azure-functions-ml-net.md) finden Sie nähere Anleitungen.

Verwenden Sie in separaten Anwendungen oder Prozessen die [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A)-Methode zusammen mit den Dateipfad, um das trainierte Modell in Ihre Anwendung zu laden.

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a>Laden eines remote gespeicherten Modells

Um Datenvorbereitungspipelines und an einem Remotespeicherort gespeicherte Modelle in Ihre Anwendung zu laden, verwenden Sie einen [`Stream`](xref:System.IO.Stream) anstatt eines Dateipfads in der [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load%2A)-Methode.

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

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a>Arbeiten mit separaten Datenvorbereitungs- und Modellpipelines

> [!NOTE]
> Arbeiten mit separaten Datenvorbereitungs- und Modelltrainingspipelines ist optional. Die Trennung von Pipelines erleichtert die Überprüfung der gelernten Modellparameter. Für Vorhersagen ist es einfacher, eine einzelne Pipeline zu speichern und zu laden, die die Datenvorbereitungs- und Modelltrainingsvorgänge enthält.

Bei der Arbeit mit separaten Datenvorbereitungspipelines und Modellen wird derselbe Prozess wie bei einzelnen Pipelines durchgeführt, mit dem Unterschied, dass nun beide Pipelines gleichzeitig gespeichert und geladen werden müssen.

Bei separaten Datenvorbereitungs- und Modelltrainingspipelines:

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

### <a name="save-data-preparation-pipeline-and-trained-model"></a>Speichern von Datenvorbereitungspipeline und trainiertem Modell

Um Datenvorbereitungspipeline und trainiertes Modell zu speichern, verwenden Sie die folgenden Befehle:

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a>Laden von Datenvorbereitungspipeline und trainiertem Modell

Laden Sie in einem separaten Prozess oder einer separaten Anwendung die Datenvorbereitungspipeline und das trainierte Modell gleichzeitig wie folgt:

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
