---
title: Bereitstellen eines Machine Learning-Modells in der ASP.NET Core-Web-API
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse über das Internet mithilfe der ASP.NET Core-Web-API
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0cc13ec22b3a8805ec4aa17bf10560b2564ccd63
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307914"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="a26f4-103">Vorgehensweise: Bereitstellen eines Machine Learning-Modells über die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="a26f4-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="a26f4-104">Hier erfahren Sie, wie Sie ein vorbereitetes ML.NET-Machine Learning-Modell mithilfe einer ASP.NET Core-Web-API im Internet bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="a26f4-105">Auf diese Weise können Benutzer für Vorhersagen über HTTP-Standardmethoden auf die API zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="a26f4-106">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a26f4-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="a26f4-107">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a26f4-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="a26f4-108">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="a26f4-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="a26f4-109">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="a26f4-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a26f4-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a26f4-110">Prerequisites</span></span>

- <span data-ttu-id="a26f4-111">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="a26f4-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="a26f4-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a26f4-112">Powershell.</span></span>
- <span data-ttu-id="a26f4-113">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="a26f4-113">Pre-trained model.</span></span>
    - <span data-ttu-id="a26f4-114">Erstellen Sie Ihr eigenes Modell mithilfe des Tutorials [Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung](../tutorials/sentiment-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="a26f4-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="a26f4-115">Laden Sie dieses [vorab trainierte Machine Learning-Modell zur Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="a26f4-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="a26f4-116">Erstellen eines ASP.NET Core-Web-API-Projekts</span><span class="sxs-lookup"><span data-stu-id="a26f4-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="a26f4-117">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a26f4-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="a26f4-118">Wählen Sie in der Menüleiste **Datei > Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="a26f4-119">Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="a26f4-120">Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="a26f4-121">Geben Sie „SentimentAnalysisWebAPI“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="a26f4-122">Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **API** und dann die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="a26f4-123">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihre vorgefertigten Machine Learning-Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="a26f4-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="a26f4-124">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="a26f4-125">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="a26f4-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="a26f4-126">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="a26f4-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a26f4-127">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a26f4-128">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="a26f4-129">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="a26f4-130">Hinzufügen eines Modells zum ASP.NET Core-Web-API-Projekt</span><span class="sxs-lookup"><span data-stu-id="a26f4-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="a26f4-131">Kopieren Sie Ihr vorbereitetes Modell in das *MLModels*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a26f4-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="a26f4-132">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die ZIP-Datei des Modells, und wählen Sie „Eigenschaften“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="a26f4-133">Ändern Sie unter „Erweitert“ den Wert von „In Ausgabeverzeichnis kopieren“ in „Kopieren, wenn neuer“.</span><span class="sxs-lookup"><span data-stu-id="a26f4-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="a26f4-134">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="a26f4-134">Build Data Models</span></span>

<span data-ttu-id="a26f4-135">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a26f4-136">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="a26f4-137">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern:</span><span class="sxs-lookup"><span data-stu-id="a26f4-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="a26f4-138">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="a26f4-139">Geben Sie „DataModels“ ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="a26f4-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="a26f4-140">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie „Hinzufügen > Neues Element“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="a26f4-141">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="a26f4-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a26f4-142">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-142">Then, select the **Add** button.</span></span> <span data-ttu-id="a26f4-143">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a26f4-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a26f4-144">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="a26f4-145">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei **SentimentData.cs** hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="a26f4-146">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="a26f4-147">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="a26f4-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="a26f4-148">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-148">Then, select the Add button.</span></span> <span data-ttu-id="a26f4-149">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a26f4-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a26f4-150">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="a26f4-151">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="register-predictionengine-for-use-in-application"></a><span data-ttu-id="a26f4-152">Registrieren von PredictionEngine zur Verwendung in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="a26f4-152">Register PredictionEngine for Use in Application</span></span>

<span data-ttu-id="a26f4-153">Sie können `PredictionEngine` verwenden, um eine einzelne Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-153">To make a single prediction, you can use `PredictionEngine`.</span></span> <span data-ttu-id="a26f4-154">Wenn Sie `PredictionEngine` in Ihrer Anwendung verwenden möchten, müssen Sie sie jedes Mal erstellen, wenn sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a26f4-154">In order to use `PredictionEngine` in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="a26f4-155">Für diesen Fall hat sich die ASP.NET Core-Abhängigkeitsinjektion bewährt.</span><span class="sxs-lookup"><span data-stu-id="a26f4-155">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="a26f4-156">Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="a26f4-156">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="a26f4-157">Öffnen Sie die *Startup.cs*-Klasse, und fügen Sie am Anfang der Datei die folgdende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-157">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

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

2. <span data-ttu-id="a26f4-158">Fügen Sie die folgenden Codezeilen der *ConfigureServices*-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-158">Add the following lines of code to the *ConfigureServices* method:</span></span>

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
> <span data-ttu-id="a26f4-159">`PredictionEngine` ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="a26f4-159">`PredictionEngine` is not thread-safe.</span></span> <span data-ttu-id="a26f4-160">Indem Sie die Lebensdauer auf *Bereichsbezogen* festlegen, können Sie die Kosten für die Objekterstellung beschränken.</span><span class="sxs-lookup"><span data-stu-id="a26f4-160">A way that you can limit the cost of creating the object is by making its service lifetime *Scoped*.</span></span> <span data-ttu-id="a26f4-161">Objekte vom Typ *Bereichsbezogen* sind innerhalb einer Anforderung identisch, anforderungsübergreifend sind sie jedoch unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="a26f4-161">*Scoped* objects are the same within a request but different across requests.</span></span> <span data-ttu-id="a26f4-162">Klicken Sie auf den Link [Lebensdauer](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes), um weitere Informationen darüber zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a26f4-162">Visit the following link to learn more about [service lifetimes](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).</span></span>

<span data-ttu-id="a26f4-163">Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a26f4-163">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="a26f4-164">Erstellen des Vorhersagecontrollers</span><span class="sxs-lookup"><span data-stu-id="a26f4-164">Create Predict Controller</span></span>

<span data-ttu-id="a26f4-165">Um die eingehenden HTTP-Anforderungen zu verarbeiten, müssen Sie einen Controller erstellen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-165">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="a26f4-166">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Controllers*-Verzeichnis, und wählen Sie **Hinzufügen > Controller** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-166">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="a26f4-167">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **API-Controller – Leer**  und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-167">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="a26f4-168">Ändern Sie in der Eingabeaufforderung das Feld **Controllername** in *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="a26f4-168">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="a26f4-169">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-169">Then, select the Add button.</span></span> <span data-ttu-id="a26f4-170">Die Datei *PredictController.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a26f4-170">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="a26f4-171">Fügen Sie am Anfang der Datei *PredictController.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-171">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using System;
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using Microsoft.ML;
```

<span data-ttu-id="a26f4-172">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictController.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="a26f4-172">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

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

<span data-ttu-id="a26f4-173">Damit wird die `PredictionEngine` durch Übergabe an den Konstruktor des Controllers zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.</span><span class="sxs-lookup"><span data-stu-id="a26f4-173">This is assigning the `PredictionEngine` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="a26f4-174">Dann wird die `PredictionEngine` in der POST-Methode dieses Controllers verwendet, um Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a26f4-174">Then, in the POST method of this controller the `PredictionEngine` is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="a26f4-175">Lokales Testen der Web-API</span><span class="sxs-lookup"><span data-stu-id="a26f4-175">Test Web API Locally</span></span>

<span data-ttu-id="a26f4-176">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-176">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="a26f4-177">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="a26f4-177">Run the application.</span></span>
1. <span data-ttu-id="a26f4-178">Öffnen Sie PowerShell, und geben Sie den folgenden Code ein, wobei PORT der Port ist, auf dem Ihre Anwendung lauscht.</span><span class="sxs-lookup"><span data-stu-id="a26f4-178">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="a26f4-179">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="a26f4-179">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="a26f4-180">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="a26f4-180">Congratulations!</span></span> <span data-ttu-id="a26f4-181">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer ASP.NET Core-API Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="a26f4-181">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a26f4-182">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a26f4-182">Next Steps</span></span>

- [<span data-ttu-id="a26f4-183">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="a26f4-183">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)