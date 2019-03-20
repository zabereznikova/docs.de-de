---
title: Bereitstellen eines Machine Learning-Modells in der ASP.NET Core-Web-API
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse über das Internet mithilfe der ASP.NET Core-Web-API
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856702"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="75eb5-103">Vorgehensweise: Bereitstellen eines Machine Learning-Modells über die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="75eb5-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="75eb5-104">Hier erfahren Sie, wie Sie ein vorbereitetes ML.NET-Machine Learning-Modell mithilfe einer ASP.NET Core-Web-API im Internet bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="75eb5-105">Auf diese Weise können Benutzer für Vorhersagen über HTTP-Standardmethoden auf die API zugreifen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="75eb5-106">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="75eb5-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="75eb5-107">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="75eb5-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="75eb5-108">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="75eb5-109">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="75eb5-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75eb5-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="75eb5-110">Prerequisites</span></span>

- <span data-ttu-id="75eb5-111">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="75eb5-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="75eb5-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75eb5-112">Powershell.</span></span>
- <span data-ttu-id="75eb5-113">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="75eb5-113">Pre-trained model.</span></span>
    - <span data-ttu-id="75eb5-114">Erstellen Sie Ihr eigenes Modell mithilfe des Tutorials [Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung](../tutorials/sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="75eb5-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="75eb5-115">Laden Sie dieses [vorab trainierte Machine Learning-Modell zur Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="75eb5-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="75eb5-116">Erstellen eines ASP.NET Core-Web-API-Projekts</span><span class="sxs-lookup"><span data-stu-id="75eb5-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="75eb5-117">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="75eb5-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="75eb5-118">Wählen Sie in der Menüleiste **Datei > Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="75eb5-119">Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="75eb5-120">Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="75eb5-121">Geben Sie „SentimentAnalysisWebAPI“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="75eb5-122">Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **API** und dann die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="75eb5-123">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihre vorgefertigten Machine Learning-Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="75eb5-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="75eb5-124">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="75eb5-125">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="75eb5-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="75eb5-126">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="75eb5-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="75eb5-127">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="75eb5-128">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="75eb5-129">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="75eb5-130">Hinzufügen eines Modells zum ASP.NET Core-Web-API-Projekt</span><span class="sxs-lookup"><span data-stu-id="75eb5-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="75eb5-131">Kopieren Sie Ihr vorbereitetes Modell in das *MLModels*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="75eb5-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="75eb5-132">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die ZIP-Datei des Modells, und wählen Sie „Eigenschaften“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="75eb5-133">Ändern Sie unter „Erweitert“ den Wert von „In Ausgabeverzeichnis kopieren“ in „Kopieren, wenn neuer“.</span><span class="sxs-lookup"><span data-stu-id="75eb5-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="75eb5-134">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="75eb5-134">Build Data Models</span></span>

<span data-ttu-id="75eb5-135">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="75eb5-136">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="75eb5-137">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern:</span><span class="sxs-lookup"><span data-stu-id="75eb5-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="75eb5-138">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="75eb5-139">Geben Sie „DataModels“ ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="75eb5-140">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie „Hinzufügen > Neues Element“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="75eb5-141">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="75eb5-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="75eb5-142">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-142">Then, select the **Add** button.</span></span> <span data-ttu-id="75eb5-143">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="75eb5-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="75eb5-144">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="75eb5-145">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei **SentimentData.cs** hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="75eb5-146">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="75eb5-147">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="75eb5-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="75eb5-148">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-148">Then, select the Add button.</span></span> <span data-ttu-id="75eb5-149">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="75eb5-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="75eb5-150">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="75eb5-151">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="create-prediction-service"></a><span data-ttu-id="75eb5-152">Erstellen eines Vorhersagediensts</span><span class="sxs-lookup"><span data-stu-id="75eb5-152">Create Prediction Service</span></span>

<span data-ttu-id="75eb5-153">Um die Vorhersagelogik in der gesamten Anwendung zu organisieren und erneut zu verwenden, erstellen Sie einen Vorhersagedienst.</span><span class="sxs-lookup"><span data-stu-id="75eb5-153">To organize and re-use the prediction logic throughout the entire application, create a prediction service.</span></span>

1. <span data-ttu-id="75eb5-154">Erstellen Sie ein Verzeichnis mit dem Namen *Services* in Ihrem Projekt für die Dienste, die von der Anwendung verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="75eb5-154">Create a directory named *Services* in your project to hold services to be used by the application:</span></span>

    <span data-ttu-id="75eb5-155">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen > Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-155">In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="75eb5-156">Geben Sie „Services“ ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="75eb5-156">Type "Services" and hit **Enter**.</span></span>

1. <span data-ttu-id="75eb5-157">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Services*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-157">In Solution Explorer, right-click the *Services* directory, and then select **Add > New Item**.</span></span>
1. <span data-ttu-id="75eb5-158">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *PredictionService.cs*.</span><span class="sxs-lookup"><span data-stu-id="75eb5-158">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *PredictionService.cs*.</span></span> <span data-ttu-id="75eb5-159">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-159">Then, select the **Add** button.</span></span> <span data-ttu-id="75eb5-160">Die Datei *PredictionService.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="75eb5-160">The *PredictionService.cs* file opens in the code editor.</span></span> <span data-ttu-id="75eb5-161">Fügen Sie am Anfang der Datei *PredictionService.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-161">Add the following using statement to the top of *PredictionService.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

<span data-ttu-id="75eb5-162">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictionService.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-162">Remove the existing class definition and add the following code to the *PredictionService.cs* file:</span></span>

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a><span data-ttu-id="75eb5-163">Registrieren des Vorhersagediensts für die Verwendung in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="75eb5-163">Register Predictions Service for Use in Application</span></span>

<span data-ttu-id="75eb5-164">Um den Vorhersagedienst in Ihrer Anwendung zu verwenden, müssen Sie ihn jedes Mal erstellen, wenn er benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="75eb5-164">To use the prediction service in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="75eb5-165">Für diesen Fall hat sich die ASP.NET Core-Abhängigkeitsinjektion bewährt.</span><span class="sxs-lookup"><span data-stu-id="75eb5-165">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="75eb5-166">Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="75eb5-166">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="75eb5-167">Öffnen Sie die *Startup.cs*-Klasse, und fügen Sie am Anfang der Datei die folgdende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-167">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

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
using SentimentAnalysisWebAPI.Services;
```

1. <span data-ttu-id="75eb5-168">Fügen Sie die folgenden Codezeilen der *ConfigureServices*-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-168">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
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
    services.AddSingleton<PredictionService>();
}
```

<span data-ttu-id="75eb5-169">Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="75eb5-169">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="75eb5-170">Erstellen des Vorhersagecontrollers</span><span class="sxs-lookup"><span data-stu-id="75eb5-170">Create Predict Controller</span></span>

<span data-ttu-id="75eb5-171">Um die eingehenden HTTP-Anforderungen zu verarbeiten, müssen Sie einen Controller erstellen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-171">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="75eb5-172">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Controllers*-Verzeichnis, und wählen Sie **Hinzufügen > Controller** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-172">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="75eb5-173">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **API-Controller – Leer**  und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-173">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="75eb5-174">Ändern Sie in der Eingabeaufforderung das Feld **Controllername** in *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="75eb5-174">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="75eb5-175">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-175">Then, select the Add button.</span></span> <span data-ttu-id="75eb5-176">Die Datei *PredictController.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="75eb5-176">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="75eb5-177">Fügen Sie am Anfang der Datei *PredictController.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-177">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

<span data-ttu-id="75eb5-178">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictController.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="75eb5-178">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

<span data-ttu-id="75eb5-179">Damit wird der Vorhersagedienst durch Übergabe an den Konstruktor des Controllers zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.</span><span class="sxs-lookup"><span data-stu-id="75eb5-179">This is assigning the Prediction service by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="75eb5-180">Dann wird der Vorhersagedienst in der POST-Methode dieses Controllers verwendet, um Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="75eb5-180">Then, in the POST method of this controller the Prediction service is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="75eb5-181">Lokales Testen der Web-API</span><span class="sxs-lookup"><span data-stu-id="75eb5-181">Test Web API Locally</span></span>

<span data-ttu-id="75eb5-182">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-182">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="75eb5-183">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="75eb5-183">Run the application.</span></span>
1. <span data-ttu-id="75eb5-184">Öffnen Sie PowerShell, und geben Sie den folgenden Code ein, wobei PORT der Port ist, auf dem Ihre Anwendung lauscht.</span><span class="sxs-lookup"><span data-stu-id="75eb5-184">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="75eb5-185">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="75eb5-185">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="75eb5-186">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="75eb5-186">Congratulations!</span></span> <span data-ttu-id="75eb5-187">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer ASP.NET Core-API Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="75eb5-187">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="75eb5-188">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="75eb5-188">Next Steps</span></span>

- [<span data-ttu-id="75eb5-189">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="75eb5-189">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)