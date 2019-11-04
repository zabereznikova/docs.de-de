---
title: Bereitstellen eines Modells in einer ASP.NET Core-Web-API
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse über das Internet mithilfe der ASP.NET Core-Web-API
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: b85d77900c5d9227ecc6fe81b8a8d68171dd9ef5
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774510"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="43b4a-103">Bereitstellen eines Modells in einer ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="43b4a-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="43b4a-104">Hier erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Machine Learning-Modell mithilfe einer ASP.NET Core-Web-API im Internet bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="43b4a-105">Das Bereitstellen eines Modells über eine Web-API ermöglicht Vorhersagen über HTTP-Standardmethoden.</span><span class="sxs-lookup"><span data-stu-id="43b4a-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="43b4a-106">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43b4a-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43b4a-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="43b4a-107">Prerequisites</span></span>

- <span data-ttu-id="43b4a-108">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="43b4a-108">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="43b4a-109">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43b4a-109">Powershell.</span></span>
- <span data-ttu-id="43b4a-110">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="43b4a-110">Pre-trained model.</span></span> <span data-ttu-id="43b4a-111">Verwenden Sie das [Tutorial für die ML.NET-Standpunktanalyse](../tutorials/sentiment-analysis.md), um Ihr eigenes Modell zu erstellen, oder laden Sie dieses [vorab trainierte Machine Learning-Modell für die Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="43b4a-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="43b4a-112">Erstellen eines ASP.NET Core-Web-API-Projekts</span><span class="sxs-lookup"><span data-stu-id="43b4a-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="43b4a-113">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="43b4a-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="43b4a-114">Wählen Sie in der Menüleiste **Datei > Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="43b4a-115">Wählen Sie im Dialogfeld „Neues Projekt“ den Knoten **Visual C#** und anschließend den Knoten **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="43b4a-116">Wählen Sie dann die Projektvorlage **ASP.NET Core-Webanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="43b4a-117">Geben Sie „SentimentAnalysisWebAPI“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="43b4a-118">Wählen Sie im Fenster, das die verschiedenen Typen von ASP.NET Core-Projekten anzeigt, **API** und dann die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="43b4a-119">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihre vorgefertigten Machine Learning-Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="43b4a-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="43b4a-120">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="43b4a-121">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="43b4a-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="43b4a-122">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="43b4a-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="43b4a-123">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="43b4a-124">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="43b4a-125">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="43b4a-126">Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="43b4a-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="43b4a-127">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="43b4a-128">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche „Installieren“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="43b4a-129">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld „Zustimmung zur Lizenz“ aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="43b4a-130">Hinzufügen eines Modells zum ASP.NET Core-Web-API-Projekt</span><span class="sxs-lookup"><span data-stu-id="43b4a-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="43b4a-131">Kopieren Sie Ihr vorbereitetes Modell in das *MLModels*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="43b4a-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="43b4a-132">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die ZIP-Datei des Modells, und wählen Sie „Eigenschaften“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="43b4a-133">Ändern Sie unter „Erweitert“ den Wert von „In Ausgabeverzeichnis kopieren“ in „Kopieren, wenn neuer“.</span><span class="sxs-lookup"><span data-stu-id="43b4a-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="43b4a-134">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="43b4a-134">Create data models</span></span>

<span data-ttu-id="43b4a-135">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="43b4a-136">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="43b4a-137">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern:</span><span class="sxs-lookup"><span data-stu-id="43b4a-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="43b4a-138">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie „Hinzufügen > Neuer Ordner“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="43b4a-139">Geben Sie „DataModels“ ein, und drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="43b4a-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="43b4a-140">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie „Hinzufügen > Neues Element“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="43b4a-141">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="43b4a-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="43b4a-142">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-142">Then, select the **Add** button.</span></span> <span data-ttu-id="43b4a-143">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="43b4a-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="43b4a-144">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="43b4a-145">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei **SentimentData.cs** hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

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

4. <span data-ttu-id="43b4a-146">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="43b4a-147">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="43b4a-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="43b4a-148">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-148">Then, select the Add button.</span></span> <span data-ttu-id="43b4a-149">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="43b4a-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="43b4a-150">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="43b4a-151">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="43b4a-152">`SentimentPrediction` erbt von `SentimentData`.</span><span class="sxs-lookup"><span data-stu-id="43b4a-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="43b4a-153">Dadurch wird es einfacher, die Originaldaten in der `SentimentText`-Eigenschaft zusammen mit der vom Modell generierten Ausgabe zu sehen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="43b4a-154">Registrieren von PredictionEnginePool zur Verwendung in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="43b4a-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="43b4a-155">Um eine einzelne Vorhersage zu treffen, müssen Sie eine [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) erstellen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-155">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="43b4a-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="43b4a-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="43b4a-157">Außerdem müssen Sie eine Instanz davon überall dort erstellen, wo diese in Ihrer Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="43b4a-157">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="43b4a-158">Wenn die Anwendung wächst, kann dieser Prozess ggf. nicht mehr verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="43b4a-158">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="43b4a-159">Für verbesserte Leistung und Threadsicherheit verwenden Sie eine Kombination aus Abhängigkeitsinjektion (Dependency Injection, DI) und dem `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="43b4a-159">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="43b4a-160">Unter dem folgenden Link finden Sie weitere Informationen zur [Abhängigkeitsinjektion in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span><span class="sxs-lookup"><span data-stu-id="43b4a-160">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="43b4a-161">Öffnen Sie die *Startup.cs*-Klasse, und fügen Sie am Anfang der Datei die folgdende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-161">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="43b4a-162">Fügen Sie den folgenden Code der *ConfigureServices*-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-162">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    }
    ```

<span data-ttu-id="43b4a-163">Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch für eine spätere Verwendung, sodass dies nicht manuell durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="43b4a-163">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="43b4a-164">Machine Learning-Modelle sind nicht statisch.</span><span class="sxs-lookup"><span data-stu-id="43b4a-164">Machine learning models are not static.</span></span> <span data-ttu-id="43b4a-165">Wenn neue Trainingsdaten verfügbar werden, wird das Modell erneut trainiert und erneut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="43b4a-165">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="43b4a-166">Eine Möglichkeit, die neueste Version des Modells in Ihre Anwendung zu integrieren, besteht darin, die gesamte Anwendung erneut bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-166">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="43b4a-167">Dies führt jedoch zu Ausfallzeiten der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="43b4a-167">However, this introduces application downtime.</span></span> <span data-ttu-id="43b4a-168">Der `PredictionEnginePool`-Dienst bietet einen Mechanismus zum erneuten Laden eines aktualisierten Modells, ohne dass die Anwendung ausfällt.</span><span class="sxs-lookup"><span data-stu-id="43b4a-168">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="43b4a-169">Legen Sie den `watchForChanges`-Parameter auf `true` fest. Der `PredictionEnginePool` startet dann einen [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher), der auf Änderungsbenachrichtigungen des Dateisystems lauscht und Ereignisse auslöst, wenn die Datei geändert wird.</span><span class="sxs-lookup"><span data-stu-id="43b4a-169">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="43b4a-170">Dadurch wird der `PredictionEnginePool` aufgefordert, das Modell automatisch erneut zu laden.</span><span class="sxs-lookup"><span data-stu-id="43b4a-170">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="43b4a-171">Das Modell wird durch den Parameter `modelName` identifiziert, sodass bei der Änderung mehrere Modelle pro Anwendung erneut geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="43b4a-171">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="43b4a-172">Alternativ können Sie beim Arbeiten mit Modellen, die remote gespeichert sind, die `FromUri`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="43b4a-172">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="43b4a-173">Anstatt auf Dateiänderungsereignisse zu warten, fragt `FromUri` den Remotespeicherort nach Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="43b4a-173">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="43b4a-174">Das Abruf Intervall beträgt standardmäßig 5 Minuten.</span><span class="sxs-lookup"><span data-stu-id="43b4a-174">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="43b4a-175">Sie können das Abrufintervall basierend auf den Anforderungen Ihrer Anwendung vergrößern oder verkleinern.</span><span class="sxs-lookup"><span data-stu-id="43b4a-175">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="43b4a-176">Im folgenden Codebeispiel fragt der `PredictionEnginePool` das am angegebenen URI gespeicherte Modell jede Minute ab.</span><span class="sxs-lookup"><span data-stu-id="43b4a-176">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="43b4a-177">Erstellen des Vorhersagecontrollers</span><span class="sxs-lookup"><span data-stu-id="43b4a-177">Create Predict controller</span></span>

<span data-ttu-id="43b4a-178">Um die eingehenden HTTP-Anforderungen zu verarbeiten, erstellen Sie einen Controller.</span><span class="sxs-lookup"><span data-stu-id="43b4a-178">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="43b4a-179">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *Controllers*-Verzeichnis, und wählen Sie **Hinzufügen > Controller** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-179">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="43b4a-180">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **API-Controller – Leer**  und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-180">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="43b4a-181">Ändern Sie in der Eingabeaufforderung das Feld **Controllername** in *PredictController.cs*.</span><span class="sxs-lookup"><span data-stu-id="43b4a-181">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="43b4a-182">Wählen Sie dann die Schaltfläche „Hinzufügen“ aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-182">Then, select the Add button.</span></span> <span data-ttu-id="43b4a-183">Die Datei *PredictController.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="43b4a-183">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="43b4a-184">Fügen Sie am Anfang der Datei *PredictController.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-184">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="43b4a-185">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *PredictController.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="43b4a-185">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

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

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="43b4a-186">Mit diesem Code wird die `PredictionEnginePool` durch Übergabe an den Konstruktor des Controllers zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.</span><span class="sxs-lookup"><span data-stu-id="43b4a-186">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="43b4a-187">Dann verwendet die `Post`-Methode des `Predict`-Controllers den `PredictionEnginePool`, um mithilfe des in der `Startup`-Klasse registrierten `SentimentAnalysisModel` Vorhersagen zu treffen und bei Erfolg die Ergebnisse an den Benutzer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="43b4a-187">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="43b4a-188">Lokales Testen der Web-API</span><span class="sxs-lookup"><span data-stu-id="43b4a-188">Test web API locally</span></span>

<span data-ttu-id="43b4a-189">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-189">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="43b4a-190">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="43b4a-190">Run the application.</span></span>
1. <span data-ttu-id="43b4a-191">Öffnen Sie PowerShell, und geben Sie den folgenden Code ein, wobei PORT der Port ist, auf dem Ihre Anwendung lauscht.</span><span class="sxs-lookup"><span data-stu-id="43b4a-191">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="43b4a-192">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="43b4a-192">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="43b4a-193">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="43b4a-193">Congratulations!</span></span> <span data-ttu-id="43b4a-194">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer ASP.NET Core-Web-API Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="43b4a-194">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="43b4a-195">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="43b4a-195">Next Steps</span></span>

- [<span data-ttu-id="43b4a-196">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="43b4a-196">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
