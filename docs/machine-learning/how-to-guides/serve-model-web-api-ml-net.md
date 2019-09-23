---
title: Bereitstellen eines Modells in einer ASP.NET Core-Web-API
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse über das Internet mithilfe der ASP.NET Core-Web-API
ms.date: 08/20/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: 8d21ae5ae3aa4701ddd7d042d5069351c22864bb
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182554"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="53158-103">Bereitstellen eines Modells in einer ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="53158-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="53158-104">Hier erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Machine Learning-Modell mithilfe einer ASP.NET Core-Web-API im Internet bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="53158-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="53158-105">Das Bereitstellen eines Modells über eine Web-API ermöglicht Vorhersagen über HTTP-Standardmethoden.</span><span class="sxs-lookup"><span data-stu-id="53158-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="53158-106">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53158-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="53158-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="53158-107">Prerequisites</span></span>

- <span data-ttu-id="53158-108">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="53158-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="53158-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53158-109">Powershell.</span></span>
- <span data-ttu-id="53158-110">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="53158-110">Pre-trained model.</span></span> <span data-ttu-id="53158-111">Verwenden Sie das [Tutorial für die ML.NET-Standpunktanalyse](../tutorials/sentiment-analysis.md), um Ihr eigenes Modell zu erstellen, oder laden Sie dieses [vorab trainierte Machine Learning-Modell für die Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="53158-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="53158-112">Erstellen eines ASP.NET Core-Web-API-Projekts</span><span class="sxs-lookup"><span data-stu-id="53158-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="53158-113">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="53158-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="53158-114">Wählen Sie in der Menüleiste **Datei > Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="53158-115">Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="53158-116">Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="53158-117">Geben Sie „SentimentAnalysisWebAPI“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="53158-118">Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **API** und dann die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="53158-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="53158-119">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihre vorgefertigten Machine Learning-Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="53158-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="53158-120">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="53158-121">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="53158-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="53158-122">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="53158-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="53158-123">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="53158-124">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="53158-125">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="53158-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="53158-126">Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="53158-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="53158-127">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="53158-128">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="53158-129">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="53158-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="53158-130">Hinzufügen eines Modells zum ASP.NET Core-Web-API-Projekt</span><span class="sxs-lookup"><span data-stu-id="53158-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="53158-131">Kopieren Sie Ihr vorbereitetes Modell in das *MLModels*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="53158-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="53158-132">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die ZIP-Datei des Modells, und wählen Sie „Eigenschaften“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="53158-133">Ändern Sie unter „Erweitert“ den Wert von „In Ausgabeverzeichnis kopieren“ in „Kopieren, wenn neuer“.</span><span class="sxs-lookup"><span data-stu-id="53158-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="53158-134">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="53158-134">Create data models</span></span>

<span data-ttu-id="53158-135">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="53158-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="53158-136">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="53158-137">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern:</span><span class="sxs-lookup"><span data-stu-id="53158-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="53158-138">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="53158-139">Geben Sie „DataModels“ ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="53158-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="53158-140">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie „Hinzufügen > Neues Element“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="53158-141">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="53158-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="53158-142">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-142">Then, select the **Add** button.</span></span> <span data-ttu-id="53158-143">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="53158-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="53158-144">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="53158-145">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei **SentimentData.cs** hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="53158-146">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="53158-147">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="53158-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="53158-148">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-148">Then, select the Add button.</span></span> <span data-ttu-id="53158-149">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="53158-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="53158-150">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="53158-151">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="53158-152">`SentimentPrediction` erbt von `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="53158-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="53158-153">Dadurch wird es einfacher, die Originaldaten in der `SentimentText`-Eigenschaft zusammen mit der vom Modell generierten Ausgabe zu sehen.</span><span class="sxs-lookup"><span data-stu-id="53158-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="53158-154">Registrieren von PredictionEnginePool zur Verwendung in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="53158-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="53158-155">Sie können [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) verwenden, um eine einzelne Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="53158-155">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="53158-156">Um [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in Ihrer Anwendung verwenden zu können, müssen Sie sie bei Bedarf erstellen.</span><span class="sxs-lookup"><span data-stu-id="53158-156">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="53158-157">Für diesen Fall hat sich die Abhängigkeitsinjektion bewährt.</span><span class="sxs-lookup"><span data-stu-id="53158-157">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="53158-158">Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion in ASP.NET Core](/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="53158-158">The following link provides more information if you want to learn about [dependency injection in ASP.NET Core](/aspnet/core/fundamentals/dependency-injection).</span></span>

1. <span data-ttu-id="53158-159">Öffnen Sie die *Startup.cs*-Klasse, und fügen Sie am Anfang der Datei die folgdende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-159">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="53158-160">Fügen Sie den folgenden Code der *ConfigureServices*-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-160">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

<span data-ttu-id="53158-161">Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="53158-161">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="53158-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="53158-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="53158-163">Verwenden Sie für verbesserte Leistung und Threadsicherheit den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von `PredictionEngine`-Objekten für die Anwendungsverwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="53158-163">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="53158-164">Lesen Sie den folgenden Blogbeitrag, um mehr über das Erstellen und [Verwenden von `PredictionEngine`-Objektpools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/) zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="53158-164">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>  

## <a name="create-predict-controller"></a><span data-ttu-id="53158-165">Erstellen des Vorhersagecontrollers</span><span class="sxs-lookup"><span data-stu-id="53158-165">Create Predict controller</span></span>

<span data-ttu-id="53158-166">Um die eingehenden HTTP-Anforderungen zu verarbeiten, erstellen Sie einen Controller.</span><span class="sxs-lookup"><span data-stu-id="53158-166">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="53158-167">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Controllers*-Verzeichnis, und wählen Sie **Hinzufügen > Controller** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-167">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="53158-168">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **API-Controller – Leer**  und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="53158-168">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="53158-169">Ändern Sie in der Eingabeaufforderung das Feld **Controllername** in *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="53158-169">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="53158-170">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="53158-170">Then, select the Add button.</span></span> <span data-ttu-id="53158-171">Die Datei *PredictController.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="53158-171">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="53158-172">Fügen Sie am Anfang der Datei *PredictController.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-172">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="53158-173">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictController.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="53158-173">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
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

<span data-ttu-id="53158-174">Mit diesem Code wird die `PredictionEnginePool` durch Übergabe an den Konstruktor des Controllers zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.</span><span class="sxs-lookup"><span data-stu-id="53158-174">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="53158-175">Dann verwendet die `Post`-Methode des `Predict`-Controllers den `PredictionEnginePool`, um Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="53158-175">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="53158-176">Lokales Testen der Web-API</span><span class="sxs-lookup"><span data-stu-id="53158-176">Test web API locally</span></span>

<span data-ttu-id="53158-177">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen.</span><span class="sxs-lookup"><span data-stu-id="53158-177">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="53158-178">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="53158-178">Run the application.</span></span>
1. <span data-ttu-id="53158-179">Öffnen Sie PowerShell, und geben Sie den folgenden Code ein, wobei PORT der Port ist, auf dem Ihre Anwendung lauscht.</span><span class="sxs-lookup"><span data-stu-id="53158-179">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="53158-180">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="53158-180">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="53158-181">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="53158-181">Congratulations!</span></span> <span data-ttu-id="53158-182">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer ASP.NET Core-Web-API Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="53158-182">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="53158-183">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="53158-183">Next Steps</span></span>

- [<span data-ttu-id="53158-184">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="53158-184">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
