---
title: Bereitstellen des ML.NET-Modells für Azure Functions
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse für die Vorhersage über das Internet mit Azure Functions
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59330635"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="94aaf-103">Vorgehensweise: Verwenden des ML.NET-Modells in Azure Functions</span><span class="sxs-lookup"><span data-stu-id="94aaf-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="94aaf-104">In dieser Vorgehensweise wird gezeigt, wie einzelne Vorhersagen mithilfe eines vorgefertigten ML.NET-Machine Learning-Modells über das Internet in einer serverlosen Umgebung wie Azure Functions vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="94aaf-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="94aaf-105">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="94aaf-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="94aaf-106">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="94aaf-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="94aaf-107">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="94aaf-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="94aaf-108">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="94aaf-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94aaf-109">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="94aaf-109">Prerequisites</span></span>

- <span data-ttu-id="94aaf-110">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“ und installierter „Azure-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="94aaf-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="94aaf-111">Azure Functions-Tools</span><span class="sxs-lookup"><span data-stu-id="94aaf-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="94aaf-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="94aaf-112">Powershell</span></span>
- <span data-ttu-id="94aaf-113">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="94aaf-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="94aaf-114">Erstellen Sie Ihr eigenes Modell mithilfe des Tutorials [Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung](../tutorials/sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="94aaf-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="94aaf-115">Laden Sie dieses [vorab trainierte Machine Learning-Modell zur Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="94aaf-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="94aaf-116">Erstellen eines Azure Functions-Projekts</span><span class="sxs-lookup"><span data-stu-id="94aaf-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="94aaf-117">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="94aaf-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="94aaf-118">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="94aaf-119">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **Cloud** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="94aaf-120">Wählen Sie dann die **Azure Functions**-Projektvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="94aaf-121">Geben Sie „SentimentAnalysisFunctionsApp“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="94aaf-122">Öffnen Sie im Dialogfeld **Neues Projekt** die Dropdownliste über den Projektoptionen, und wählen Sie **Azure Functions v2 (.NET Core)** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="94aaf-123">Wählen Sie dann das Projekt **HTTP-Trigger** und die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="94aaf-124">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihr Modell zu speichern:</span><span class="sxs-lookup"><span data-stu-id="94aaf-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="94aaf-125">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="94aaf-126">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="94aaf-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="94aaf-127">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="94aaf-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="94aaf-128">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="94aaf-129">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="94aaf-130">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="94aaf-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="94aaf-131">Hinzufügen des vorab erstellten Modells zum Projekt</span><span class="sxs-lookup"><span data-stu-id="94aaf-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="94aaf-132">Kopieren Sie Ihr vorbereitetes Modell in den *MLModels*-Ordner.</span><span class="sxs-lookup"><span data-stu-id="94aaf-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="94aaf-133">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr vorbereitetes Modell, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="94aaf-134">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="94aaf-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="94aaf-135">Erstellen einer Funktion zur Standpunktanalyse</span><span class="sxs-lookup"><span data-stu-id="94aaf-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="94aaf-136">Erstellen Sie eine Klasse, um den Standpunkt vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="94aaf-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="94aaf-137">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="94aaf-138">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="94aaf-139">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Azure-Funktion** aus, und ändern Sie das Feld **Name** in *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="94aaf-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="94aaf-140">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="94aaf-141">Wählen Sie im Dialogfeld **Neue Azure-Funktion** die Option **HTTP-Trigger** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="94aaf-142">Wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="94aaf-143">Die Datei *AnalyzeSentiment.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="94aaf-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="94aaf-144">Fügen Sie am Anfang der Datei *GitHubIssueData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

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
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="94aaf-145">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="94aaf-145">Create Data Models</span></span>

<span data-ttu-id="94aaf-146">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="94aaf-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="94aaf-147">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="94aaf-148">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen > Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="94aaf-149">Geben Sie „DataModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="94aaf-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="94aaf-150">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="94aaf-151">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="94aaf-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="94aaf-152">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-152">Then, select the **Add** button.</span></span> <span data-ttu-id="94aaf-153">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="94aaf-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="94aaf-154">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="94aaf-155">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei „SentimentData.cs“ hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="94aaf-156">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="94aaf-157">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="94aaf-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="94aaf-158">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="94aaf-158">Then, select the **Add** button.</span></span> <span data-ttu-id="94aaf-159">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="94aaf-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="94aaf-160">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="94aaf-161">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="94aaf-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="94aaf-162">Hinzufügen von Vorhersagelogik</span><span class="sxs-lookup"><span data-stu-id="94aaf-162">Add Prediction Logic</span></span>

<span data-ttu-id="94aaf-163">Ersetzen Sie die vorhandene Implementierung der *Run*-Methode in der *AnalyzeSentiment*-Klasse durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="94aaf-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="94aaf-164">Lokales Testen</span><span class="sxs-lookup"><span data-stu-id="94aaf-164">Test Locally</span></span>

<span data-ttu-id="94aaf-165">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen:</span><span class="sxs-lookup"><span data-stu-id="94aaf-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="94aaf-166">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="94aaf-166">Run the application</span></span>
1. <span data-ttu-id="94aaf-167">Öffnen Sie PowerShell, und geben Sie den Code in der Eingabeaufforderung ein, wobei PORT der Port ist, auf dem Ihre Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="94aaf-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="94aaf-168">In der Regel ist es Port 7071.</span><span class="sxs-lookup"><span data-stu-id="94aaf-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="94aaf-169">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="94aaf-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="94aaf-170">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="94aaf-170">Congratulations!</span></span> <span data-ttu-id="94aaf-171">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer Azure-Funktion Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="94aaf-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94aaf-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="94aaf-172">Next Steps</span></span>

- [<span data-ttu-id="94aaf-173">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="94aaf-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)