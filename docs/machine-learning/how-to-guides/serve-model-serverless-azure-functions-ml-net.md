---
title: Bereitstellen des Modells für Azure Functions
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse für die Vorhersage über das Internet mit Azure Functions
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 9e62d8826227aed07451387cc733d27094327f99
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645098"
---
# <a name="deploy-a-model-to-azure-functions"></a>Bereitstellen des Modells für Azure Functions

Erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Modell für maschinelles Lernen für Vorhersagen über HTTP in einer serverlosen Azure Functions-Umgebung bereitstellen.

> [!NOTE]
> Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“ und installierter „Azure-Entwicklung“.
- [Azure Functions-Tools](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Vorab trainiertes Modell. Verwenden Sie das [Tutorial für die ML.NET-Standpunktanalyse](../tutorials/sentiment-analysis.md), um Ihr eigenes Modell zu erstellen, oder laden Sie dieses [vorab trainierte Machine Learning-Modell für die Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.

## <a name="create-azure-functions-project"></a>Erstellen eines Azure Functions-Projekts

1. Öffnen Sie Visual Studio 2017. Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus. Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **Cloud** aus. Wählen Sie dann die **Azure Functions**-Projektvorlage aus. Geben Sie „SentimentAnalysisFunctionsApp“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.
1. Öffnen Sie im Dialogfeld **Neues Projekt** die Dropdownliste über den Projektoptionen, und wählen Sie **Azure Functions v2 (.NET Core)** aus. Wählen Sie dann das Projekt **HTTP-Trigger** und die **OK**-Schaltfläche aus.
1. Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihr Modell zu speichern:

    Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus. Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.

1. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

1. Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

## <a name="add-pre-trained-model-to-project"></a>Hinzufügen des vorab trainierten Modells zum Projekt

1. Kopieren Sie Ihr vorbereitetes Modell in den *MLModels*-Ordner.
1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr vorbereitetes Modell, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Erstellen einer Azure-Funktion zur Standpunktanalyse

Erstellen Sie eine Klasse, um den Standpunkt vorherzusagen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Azure-Funktion** aus, und ändern Sie das Feld **Name** in *AnalyzeSentiment.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

1. Wählen Sie im Dialogfeld **Neue Azure-Funktion** die Option **HTTP-Trigger** aus. Wählen Sie dann die Schaltfläche **OK** aus.

    Die Datei *AnalyzeSentiment.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *AnalyzeSentiment.cs* die folgende `using`-Anweisung hinzu:

    ```csharp
    using System;
    using System.IO;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.AspNetCore.Http;
    using Microsoft.Extensions.Logging;
    using Newtonsoft.Json;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    Standardmäßig ist die `AnalyzeSentiment`-Klasse `static`. Entfernen Sie das `static` -Schlüsselwort aus der Klassendefinition.

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a>Erstellen von Datenmodellen

Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen > Neuer Ordner** aus. Geben Sie „DataModels“ ein, und drücken Sie die EINGABETASTE.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.
3. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus. 

    Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentData.cs* hinzu:
    
    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.
5. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus. Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    `SentimentPrediction` erbt von `SentimentData`, was den Zugriff auf die Originaldaten in der `SentimentText`-Eigenschaft sowie auf die vom Modell generierte Ausgabe ermöglicht.

## <a name="register-predictionenginepool-service"></a>Registrieren des PredictionEnginePool-Diensts

Sie können [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) verwenden, um eine einzelne Vorhersage zu treffen. Um [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in Ihrer Anwendung verwenden zu können, müssen Sie sie bei Bedarf erstellen. Für diesen Fall hat sich die Abhängigkeitsinjektion bewährt.

Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion](https://en.wikipedia.org/wiki/Dependency_injection).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *Startup.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus. 

    Die Datei *Startup.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *Startup.cs* die folgende using-Anweisung hinzu:

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    Entfernen Sie den vorhandenen Code unterhalb der using-Anweisungen, und fügen Sie den folgenden Code zur Datei *Startup.cs* hinzu:

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Verwenden Sie für verbesserte Leistung und Threadsicherheit den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von `PredictionEngine`-Objekten für die Anwendungsverwendung erstellt. 

## <a name="register-startup-as-an-azure-functions-extension"></a>Registrieren von Startup als Azure Functions-Erweiterung

Um `Startup` in Ihrer Anwendung verwenden zu können, müssen Sie es als Azure Functions-Erweiterung registrieren. Erstellen Sie in Ihrem Projekt eine neue Datei namens *extensions.json*, wenn diese noch nicht vorhanden ist.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element** den Knoten **Visual C#** und anschließend den Knoten **Web** aus. Wählen Sie dann die Option **JSON-Datei**. Geben Sie „extensions.json“ im Textfeld **Name** ein, und klicken Sie auf **OK**.

    Die Datei *extensions.json* wird im Code-Editor geöffnet. Fügen Sie folgenden Inhalt in der *extensions.json* ein:
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihre Datei *extensions.json*, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

## <a name="load-the-model-into-the-function"></a>Laden des Modells in die Funktion

Fügen Sie den folgenden Code in die *AnalyzeSentiment*-Klasse ein:

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

Mit diesem Code wird die `PredictionEnginePool` durch Übergabe an den Konstruktor der Funktion zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.

## <a name="use-the-model-to-make-predictions"></a>Verwenden des Modells für Vorhersagen

Ersetzen Sie die vorhandene Implementierung der *Run*-Methode in der *AnalyzeSentiment*-Klasse durch den folgenden Code:

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);
    
    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

Wenn die Methode `Run` ausgeführt wird, werden die eingehenden Daten aus der HTTP-Anforderung deserialisiert und als Eingabe für den `PredictionEnginePool` verwendet. Die `Predict`-Methode wird dann aufgerufen, um eine Vorhersage zu generieren und das Ergebnis an den Benutzer zurückzugeben. 

## <a name="test-locally"></a>Lokales Testen

Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen:

1. Ausführen der Anwendung
1. Öffnen Sie PowerShell, und geben Sie den Code in der Eingabeaufforderung ein, wobei PORT der Port ist, auf dem Ihre Anwendung ausgeführt wird. In der Regel ist es Port 7071.

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:
    
    ```powershell
    Negative
    ```

Herzlichen Glückwunsch! Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer Azure-Funktion Vorhersagen über das Internet zu treffen.

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellung in Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)
