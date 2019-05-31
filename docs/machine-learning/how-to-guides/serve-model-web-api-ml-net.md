---
title: Bereitstellen eines Modells in einer ASP.NET Core-Web-API
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse über das Internet mithilfe der ASP.NET Core-Web-API
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f8b8f74f752aeb243d4a2987929bd28ddc5f7d5a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641081"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a>Bereitstellen eines Modells in einer ASP.NET Core-Web-API

Hier erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Machine Learning-Modell mithilfe einer ASP.NET Core-Web-API im Internet bereitstellen. Das Bereitstellen eines Modells über eine Web-API ermöglicht Vorhersagen über HTTP-Standardmethoden.

> [!NOTE]
> Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.

## <a name="prerequisites"></a>Erforderliche Komponenten

- [Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.
- PowerShell.
- Vorab trainiertes Modell. Verwenden Sie das [Tutorial für die ML.NET-Standpunktanalyse](../tutorials/sentiment-analysis.md), um Ihr eigenes Modell zu erstellen, oder laden Sie dieses [vorab trainierte Machine Learning-Modell für die Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.

## <a name="create-aspnet-core-web-api-project"></a>Erstellen eines ASP.NET Core-Web-API-Projekts

1. Öffnen Sie Visual Studio 2017. Wählen Sie in der Menüleiste **Datei > Neues Projekt** aus. Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus. Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus. Geben Sie „SentimentAnalysisWebAPI“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.

1. Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **API** und dann die **OK**-Schaltfläche aus.

1. Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihre vorgefertigten Machine Learning-Modelldateien zu speichern:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus. Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.

1. Installieren des **Microsoft.ML NuGet-Pakets**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

1. Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Hinzufügen eines Modells zum ASP.NET Core-Web-API-Projekt

1. Kopieren Sie Ihr vorbereitetes Modell in das *MLModels*-Verzeichnis.
1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die ZIP-Datei des Modells, und wählen Sie „Eigenschaften“ aus. Ändern Sie unter „Erweitert“ den Wert von „In Ausgabeverzeichnis kopieren“ in „Kopieren, wenn neuer“.

## <a name="create-data-models"></a>Erstellen von Datenmodellen

Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen. Fügen Sie dem Projekt eine neue Klasse hinzu:

1. Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern:

    Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus. Geben Sie „DataModels“ ein, und drücken Sie die **EINGABETASTE**.

2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie „Hinzufügen > Neues Element“ aus.
3. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*. Wählen Sie dann die Schaltfläche **Hinzufügen** aus. Die Datei *SentimentData.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei **SentimentData.cs** hinzu:
    
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
5. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*. Wählen Sie dann die Schaltfläche „Hinzufügen“ aus. Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:

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

    `SentimentPrediction` erbt von `SentimentData`. Dadurch wird es einfacher, die Originaldaten in der `SentimentText`-Eigenschaft zusammen mit der vom Modell generierten Ausgabe zu sehen. 

## <a name="register-predictionenginepool-for-use-in-the-application"></a>Registrieren von PredictionEnginePool zur Verwendung in der Anwendung

Sie können [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) verwenden, um eine einzelne Vorhersage zu treffen. Um [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in Ihrer Anwendung verwenden zu können, müssen Sie sie bei Bedarf erstellen. Für diesen Fall hat sich die Abhängigkeitsinjektion bewährt.

Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Öffnen Sie die *Startup.cs*-Klasse, und fügen Sie am Anfang der Datei die folgdende using-Anweisung hinzu:

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. Fügen Sie den folgenden Code der *ConfigureServices*-Methode hinzu:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher. Verwenden Sie für verbesserte Leistung und Threadsicherheit den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von `PredictionEngine`-Objekten für die Anwendungsverwendung erstellt. Lesen Sie den folgenden Blogbeitrag, um mehr über das Erstellen und [Verwenden von `PredictionEngine`-Objektpools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/) zu erfahren.  

## <a name="create-predict-controller"></a>Erstellen des Vorhersagecontrollers

Um die eingehenden HTTP-Anforderungen zu verarbeiten, erstellen Sie einen Controller.

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Controllers*-Verzeichnis, und wählen Sie **Hinzufügen > Controller** aus.
1. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **API-Controller – Leer**  und dann **Hinzufügen** aus.
1. Ändern Sie in der Eingabeaufforderung das Feld **Controllername** in *PredictController.cs*. Wählen Sie dann die Schaltfläche „Hinzufügen“ aus. Die Datei *PredictController.cs* wird im Code-Editor geöffnet. Fügen Sie am Anfang der Datei *PredictController.cs* die folgende using-Anweisung hinzu:

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictController.cs* hinzu:
    
    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

Mit diesem Code wird die `PredictionEnginePool` durch Übergabe an den Konstruktor des Controllers zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten. Dann verwendet die `Post`-Methode des `Predict`-Controllers den `PredictionEnginePool`, um Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.

## <a name="test-web-api-locally"></a>Lokales Testen der Web-API

Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen.

1. Führen Sie die Anwendung aus.
1. Öffnen Sie PowerShell, und geben Sie den folgenden Code ein, wobei PORT der Port ist, auf dem Ihre Anwendung lauscht.

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:
    
    ```powershell
    Negative
    ```

Herzlichen Glückwunsch! Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer ASP.NET Core-Web-API Vorhersagen über das Internet zu treffen.

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellung in Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
