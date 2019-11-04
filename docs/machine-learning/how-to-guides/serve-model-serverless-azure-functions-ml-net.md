---
title: Bereitstellen des Modells für Azure Functions
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse für die Vorhersage über das Internet mit Azure Functions
ms.date: 09/12/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 4f805c638df9e60160c27fa08995ce393e59d007
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774526"
---
# <a name="deploy-a-model-to-azure-functions"></a>Bereitstellen des Modells für Azure Functions

Erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Modell für maschinelles Lernen für Vorhersagen über HTTP in einer serverlosen Azure Functions-Umgebung bereitstellen.

> [!NOTE]
> Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“ und installierter „Azure-Entwicklung“.
- NuGet-Paketversion 1.0.28+ von „Microsoft.NET.Sdk.Functions“
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

1. Installieren Sie das **NuGet-Paket „Microsoft.Azure.Functions.Extensions“** :

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.Azure.Functions.Extensions**. Wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

1. Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

1. Aktualisieren Sie das **NuGet-Paket Microsoft.NET.Sdk.Functions** auf Version 1.0.28 oder höher:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Installiert“ aus, und suchen Sie nach **Microsoft.NET.Sdk.Functions**. Wählen Sie das Paket in der Liste und dann 1.0.28 aus, und klicken Sie anschließend auf die Schaltfläche **Aktualisieren**. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

## <a name="add-pre-trained-model-to-project"></a>Hinzufügen des vorab trainierten Modells zum Projekt

1. Kopieren Sie Ihr vorbereitetes Modell in den *MLModels*-Ordner.
1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr vorbereitetes Modell, und wählen Sie **Eigenschaften** aus. Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Erstellen einer Azure-Funktion zur Standpunktanalyse

Erstellen Sie eine Klasse, um den Standpunkt vorherzusagen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.

1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Azure-Funktion** aus, und ändern Sie das Feld **Name** in *AnalyzeSentiment.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

1. Wählen Sie im Dialogfeld **Neue Azure-Funktion** die Option **HTTP-Trigger** aus. Wählen Sie dann die Schaltfläche **OK** aus.

    Die Datei *AnalyzeSentiment.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *AnalyzeSentiment.cs* die folgende `using`-Anweisung hinzu:

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

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

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentData.cs* hinzu:

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.
5. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus. Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    `SentimentPrediction` erbt von `SentimentData`, was den Zugriff auf die Originaldaten in der `SentimentText`-Eigenschaft sowie auf die vom Modell generierte Ausgabe ermöglicht.

## <a name="register-predictionenginepool-service"></a>Registrieren des PredictionEnginePool-Diensts

Um eine einzelne Vorhersage zu treffen, müssen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) erstellen. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Außerdem müssen Sie eine Instanz davon überall dort erstellen, wo diese in Ihrer Anwendung erforderlich ist. Wenn die Anwendung wächst, kann dieser Prozess ggf. nicht mehr verwaltet werden. Für verbesserte Leistung und Threadsicherheit verwenden Sie eine Kombination aus Abhängigkeitsinjektion (Dependency Injection, DI) und dem `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.

Unter dem folgenden Link finden Sie weitere Informationen zur [Abhängigkeitsinjektion](https://en.wikipedia.org/wiki/Dependency_injection).

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *Startup.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus.

    Die Datei *Startup.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *Startup.cs* die folgende using-Anweisung hinzu:

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    Entfernen Sie den vorhandenen Code unterhalb der using-Anweisungen, und fügen Sie den folgenden Code zur Datei *Startup.cs* hinzu:

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
            }
        }
    }
    ```

Auf hoher Ebene initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch für eine spätere Verwendung, sodass dies nicht manuell durchgeführt werden muss.

Machine Learning-Modelle sind nicht statisch. Wenn neue Trainingsdaten verfügbar werden, wird das Modell erneut trainiert und erneut bereitgestellt. Eine Möglichkeit, die neueste Version des Modells in Ihre Anwendung zu integrieren, besteht darin, die gesamte Anwendung erneut bereitzustellen. Dies führt jedoch zu Ausfallzeiten der Anwendung. Der `PredictionEnginePool`-Dienst bietet einen Mechanismus zum erneuten Laden eines aktualisierten Modells, ohne dass die Anwendung ausfällt.

Legen Sie den `watchForChanges`-Parameter auf `true` fest. Der `PredictionEnginePool` startet dann einen [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher), der auf Änderungsbenachrichtigungen des Dateisystems lauscht und Ereignisse auslöst, wenn die Datei geändert wird. Dadurch wird der `PredictionEnginePool` aufgefordert, das Modell automatisch erneut zu laden.

Das Modell wird durch den Parameter `modelName` identifiziert, sodass bei der Änderung mehrere Modelle pro Anwendung erneut geladen werden können.

> [!TIP]
> Alternativ können Sie beim Arbeiten mit Modellen, die remote gespeichert sind, die `FromUri`-Methode verwenden. Anstatt auf Dateiänderungsereignisse zu warten, fragt `FromUri` den Remotespeicherort nach Änderungen ab. Das Abruf Intervall beträgt standardmäßig 5 Minuten. Sie können das Abrufintervall basierend auf den Anforderungen Ihrer Anwendung vergrößern oder verkleinern. Im folgenden Codebeispiel fragt der `PredictionEnginePool` das am angegebenen URI gespeicherte Modell jede Minute ab.
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a>Laden des Modells in die Funktion

Fügen Sie den folgenden Code in die *AnalyzeSentiment*-Klasse ein:

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

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
    SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

Wenn die Methode `Run` ausgeführt wird, werden die eingehenden Daten aus der HTTP-Anforderung deserialisiert und als Eingabe für den `PredictionEnginePool` verwendet. Anschließend wird die `Predict`-Methode aufgerufen, um mithilfe des in der `Startup`-Klasse registrierten `SentimentAnalysisModel` Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.

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
