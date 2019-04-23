---
title: Bereitstellen eines Machine Learning-Modells in der ASP.NET Core-Web-API
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse über das Internet mithilfe der ASP.NET Core-Web-API
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: af51ccaac263202fc34d36e746722d2da46404f8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321229"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a>Vorgehensweise: Bereitstellen eines Machine Learning-Modells über die ASP.NET Core-Web-API

Hier erfahren Sie, wie Sie ein vorbereitetes ML.NET-Machine Learning-Modell mithilfe einer ASP.NET Core-Web-API im Internet bereitstellen. Auf diese Weise können Benutzer für Vorhersagen über HTTP-Standardmethoden auf die API zugreifen.

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.
- PowerShell.
- Vorab trainiertes Modell.
    - Erstellen Sie Ihr eigenes Modell mithilfe des Tutorials [Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung](../tutorials/sentiment-analysis.md).
    - Laden Sie dieses [vorab trainierte Machine Learning-Modell zur Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.

## <a name="create-aspnet-core-web-api-project"></a>Erstellen eines ASP.NET Core-Web-API-Projekts

1. Öffnen Sie Visual Studio 2017. Wählen Sie in der Menüleiste **Datei > Neues Projekt** aus. Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus. Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus. Geben Sie „SentimentAnalysisWebAPI“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.
1. Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **API** und dann die **OK**-Schaltfläche aus.
1. Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihre vorgefertigten Machine Learning-Modelldateien zu speichern:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus. Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.

1. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Hinzufügen eines Modells zum ASP.NET Core-Web-API-Projekt

1. Kopieren Sie Ihr vorbereitetes Modell in das *MLModels*-Verzeichnis.
1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die ZIP-Datei des Modells, und wählen Sie „Eigenschaften“ aus. Ändern Sie unter „Erweitert“ den Wert von „In Ausgabeverzeichnis kopieren“ in „Kopieren, wenn neuer“.

## <a name="build-data-models"></a>Erstellen von Datenmodellen

Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus. Geben Sie „DataModels“ ein, und drücken Sie die **EINGABETASTE**.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie „Hinzufügen > Neues Element“ aus.
3. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus. Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei **SentimentData.cs** hinzu:

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.
5. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*. Wählen Sie dann die Schaltfläche „Hinzufügen“ aus. Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="register-predictionengine-for-use-in-application"></a>Registrieren von PredictionEngine zur Verwendung in der Anwendung

Sie können `PredictionEngine` verwenden, um eine einzelne Vorhersage zu treffen. Wenn Sie `PredictionEngine` in Ihrer Anwendung verwenden möchten, müssen Sie sie jedes Mal erstellen, wenn sie benötigt wird. Für diesen Fall hat sich die ASP.NET Core-Abhängigkeitsinjektion bewährt.

Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Öffnen Sie die *Startup.cs*-Klasse, und fügen Sie am Anfang der Datei die folgdende using-Anweisung hinzu:

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

2. Fügen Sie die folgenden Codezeilen der *ConfigureServices*-Methode hinzu:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddScoped<MLContext>();
    services.AddScoped<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
}
```

> [!WARNING]
> `PredictionEngine` ist nicht threadsicher. Indem Sie die Lebensdauer auf *Bereichsbezogen* festlegen, können Sie die Kosten für die Objekterstellung beschränken. Objekte vom Typ *Bereichsbezogen* sind innerhalb einer Anforderung identisch, anforderungsübergreifend sind sie jedoch unterschiedlich. Klicken Sie auf den Link [Lebensdauer](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes), um weitere Informationen darüber zu erhalten.

Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.

## <a name="create-predict-controller"></a>Erstellen des Vorhersagecontrollers

Um die eingehenden HTTP-Anforderungen zu verarbeiten, müssen Sie einen Controller erstellen.

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Controllers*-Verzeichnis, und wählen Sie **Hinzufügen > Controller** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **API-Controller – Leer**  und dann **Hinzufügen** aus.
1. Ändern Sie in der Eingabeaufforderung das Feld **Controllername** in *PredictController.cs*. Wählen Sie dann die Schaltfläche „Hinzufügen“ aus. Die Datei *PredictController.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *PredictController.cs* die folgende using-Anweisung hinzu:

```csharp
using System;
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using Microsoft.ML;
```

Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictController.cs* hinzu:

```csharp
public class PredictController : ControllerBase
{
    
    private readonly PredictionEngine<SentimentData,SentimentPrediction> _predictionEngine;

    public PredictController(PredictionEngine<SentimentData, SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine; //Define prediction engine
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }

        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return Ok(isToxic);
    }
    
}
```

Damit wird die `PredictionEngine` durch Übergabe an den Konstruktor des Controllers zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten. Dann wird die `PredictionEngine` in der POST-Methode dieses Controllers verwendet, um Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.

## <a name="test-web-api-locally"></a>Lokales Testen der Web-API

Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen.

1. Führen Sie die Anwendung aus.
1. Öffnen Sie PowerShell, und geben Sie den folgenden Code ein, wobei PORT der Port ist, auf dem Ihre Anwendung lauscht.

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:

```powershell
Toxic
```

Herzlichen Glückwunsch! Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer ASP.NET Core-API Vorhersagen über das Internet zu treffen.

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellung in Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)