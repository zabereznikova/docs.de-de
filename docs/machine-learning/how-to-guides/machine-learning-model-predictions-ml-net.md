---
title: Treffen von Vorhersagen mit einem trainierten Modell
description: Erfahren Sie, wie Sie mit einem trainierten Modell Vorhersagen treffen
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977043"
---
# <a name="make-predictions-with-a-trained-model"></a>Treffen von Vorhersagen mit einem trainierten Modell

Erfahren Sie, wie Sie ein trainiertes Modell verwenden, um Vorhersagen zu treffen

## <a name="create-data-models"></a>Erstellen von Datenmodellen

### <a name="input-data"></a>Eingabedaten

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

### <a name="output-data"></a>Ausgabedaten

Für die vorhergesagten Wertspalten, die von einem Modell erstellt werden, hat ML.NET Standardnamen wie die Eingabespaltenamen `Features` und `Label`. Abhängig von der Aufgabe kann der Name abweichen.

Da der in diesem Beispiel verwendete Algorithmus ein linearer Regressionsalgorithmus ist, lautet der Standardname der Ausgabespalte `Score` und wird durch das [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute)-Attribut für die `PredictedPrice`-Eigenschaft definiert.

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a>Einrichten einer Vorhersagepipeline

Die Vorhersagepipeline muss sowohl bei einer einzelnen als auch Batchvorhersage in die Anwendung geladen werden. Diese Pipeline enthält sowohl die Vorverarbeitungs-Datentransformationen als auch das trainierte Modell. Der folgende Codeausschnitt lädt die Vorhersagepipeline aus einer Datei namens `model.zip`.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a>Einzelne Vorhersage

Um eine einzelne Vorhersage zu machen, erstellen Sie eine [ `PredictionEngine` ](xref:Microsoft.ML.PredictionEngine%602) mithilfe der geladenen Vorhersagepipeline.

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

Verwenden Sie dann die [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*)-Methode, und übergeben Sie Ihre Eingabedaten als Parameter. Beachten Sie, dass die Verwendung der [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*)-Methode nicht voraussetzt, dass die Eingabe eine [`IDataView`](xref:Microsoft.ML.IDataView) ist. Der Grund ist, dass sie die Bearbeitung des Eingabedatentyps einfach internalisiert, sodass Sie ein Objekt des Eingabedatentyps übergeben können. Da darüber hinaus `CurrentPrice` das Ziel oder Label ist, das Sie mit den neuen Daten vorhersagen möchten, wird vorausgesetzt, dass zurzeit kein Wert dafür vorhanden ist.

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

Wenn Sie auf die `Score`-Eigenschaft des `prediction`-Objekts zugreifen, sollten Sie einen Wert ähnlich wie `150079` erhalten.

## <a name="multiple-predictions"></a>Mehrere Vorhersagen

Laden Sie die folgenden Daten in eine [`IDataView`](xref:Microsoft.ML.IDataView). In diesem Fall ist `inputData` der Name von [`IDataView`](xref:Microsoft.ML.IDataView). Da `CurrentPrice` das Ziel oder Label ist, das Sie mit den neuen Daten vorhersagen möchten, wird vorausgesetzt, dass zurzeit kein Wert dafür vorhanden ist.

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

Verwenden Sie dann die [`Transform`](xref:Microsoft.ML.ITransformer.Transform*)-Methode zum Anwenden der Datentransformationen und Generieren von Vorhersagen.

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

Überprüfen Sie die vorhergesagten Werte mit der [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*)-Methode.

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

Die vorhergesagten Werte in der Bewertungsspalte sollten wie folgt aussehen:

| Beobachtung | Vorhersage |
|---|---|
| 1 | 144638.2 |
| 2 | 150079.4 |
| 3 | 107789.8 |
