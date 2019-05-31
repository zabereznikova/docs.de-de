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
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="1700d-103">Bereitstellen des Modells für Azure Functions</span><span class="sxs-lookup"><span data-stu-id="1700d-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="1700d-104">Erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Modell für maschinelles Lernen für Vorhersagen über HTTP in einer serverlosen Azure Functions-Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1700d-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="1700d-105">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1700d-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1700d-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="1700d-106">Prerequisites</span></span>

- <span data-ttu-id="1700d-107">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“ und installierter „Azure-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="1700d-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- [<span data-ttu-id="1700d-108">Azure Functions-Tools</span><span class="sxs-lookup"><span data-stu-id="1700d-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="1700d-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1700d-109">Powershell</span></span>
- <span data-ttu-id="1700d-110">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="1700d-110">Pre-trained model.</span></span> <span data-ttu-id="1700d-111">Verwenden Sie das [Tutorial für die ML.NET-Standpunktanalyse](../tutorials/sentiment-analysis.md), um Ihr eigenes Modell zu erstellen, oder laden Sie dieses [vorab trainierte Machine Learning-Modell für die Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="1700d-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="1700d-112">Erstellen eines Azure Functions-Projekts</span><span class="sxs-lookup"><span data-stu-id="1700d-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="1700d-113">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="1700d-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="1700d-114">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="1700d-115">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **Cloud** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="1700d-116">Wählen Sie dann die **Azure Functions**-Projektvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="1700d-117">Geben Sie „SentimentAnalysisFunctionsApp“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="1700d-118">Öffnen Sie im Dialogfeld **Neues Projekt** die Dropdownliste über den Projektoptionen, und wählen Sie **Azure Functions v2 (.NET Core)** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="1700d-119">Wählen Sie dann das Projekt **HTTP-Trigger** und die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="1700d-120">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihr Modell zu speichern:</span><span class="sxs-lookup"><span data-stu-id="1700d-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="1700d-121">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="1700d-122">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1700d-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="1700d-123">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="1700d-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="1700d-124">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="1700d-125">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="1700d-126">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="1700d-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="1700d-127">Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="1700d-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="1700d-128">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="1700d-129">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="1700d-130">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="1700d-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="1700d-131">Hinzufügen des vorab trainierten Modells zum Projekt</span><span class="sxs-lookup"><span data-stu-id="1700d-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="1700d-132">Kopieren Sie Ihr vorbereitetes Modell in den *MLModels*-Ordner.</span><span class="sxs-lookup"><span data-stu-id="1700d-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="1700d-133">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr vorbereitetes Modell, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="1700d-134">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="1700d-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="1700d-135">Erstellen einer Azure-Funktion zur Standpunktanalyse</span><span class="sxs-lookup"><span data-stu-id="1700d-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="1700d-136">Erstellen Sie eine Klasse, um den Standpunkt vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="1700d-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="1700d-137">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="1700d-138">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="1700d-139">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Azure-Funktion** aus, und ändern Sie das Feld **Name** in *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="1700d-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="1700d-140">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="1700d-141">Wählen Sie im Dialogfeld **Neue Azure-Funktion** die Option **HTTP-Trigger** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="1700d-142">Wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="1700d-143">Die Datei *AnalyzeSentiment.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1700d-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="1700d-144">Fügen Sie am Anfang der Datei *AnalyzeSentiment.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="1700d-145">Standardmäßig ist die `AnalyzeSentiment`-Klasse `static`.</span><span class="sxs-lookup"><span data-stu-id="1700d-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="1700d-146">Entfernen Sie das `static` -Schlüsselwort aus der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="1700d-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="1700d-147">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="1700d-147">Create data models</span></span>

<span data-ttu-id="1700d-148">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="1700d-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="1700d-149">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="1700d-150">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen > Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="1700d-151">Geben Sie „DataModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1700d-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="1700d-152">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="1700d-153">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="1700d-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="1700d-154">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="1700d-155">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1700d-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="1700d-156">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="1700d-157">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="1700d-158">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="1700d-159">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="1700d-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="1700d-160">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-160">Then, select the **Add** button.</span></span> <span data-ttu-id="1700d-161">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1700d-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="1700d-162">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="1700d-163">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="1700d-164">`SentimentPrediction` erbt von `SentimentData`, was den Zugriff auf die Originaldaten in der `SentimentText`-Eigenschaft sowie auf die vom Modell generierte Ausgabe ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1700d-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="1700d-165">Registrieren des PredictionEnginePool-Diensts</span><span class="sxs-lookup"><span data-stu-id="1700d-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="1700d-166">Sie können [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) verwenden, um eine einzelne Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="1700d-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="1700d-167">Um [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in Ihrer Anwendung verwenden zu können, müssen Sie sie bei Bedarf erstellen.</span><span class="sxs-lookup"><span data-stu-id="1700d-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="1700d-168">Für diesen Fall hat sich die Abhängigkeitsinjektion bewährt.</span><span class="sxs-lookup"><span data-stu-id="1700d-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="1700d-169">Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="1700d-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="1700d-170">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="1700d-171">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="1700d-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="1700d-172">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="1700d-173">Die Datei *Startup.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1700d-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="1700d-174">Fügen Sie am Anfang der Datei *Startup.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="1700d-175">Entfernen Sie den vorhandenen Code unterhalb der using-Anweisungen, und fügen Sie den folgenden Code zur Datei *Startup.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="1700d-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

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

<span data-ttu-id="1700d-176">Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="1700d-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="1700d-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="1700d-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="1700d-178">Verwenden Sie für verbesserte Leistung und Threadsicherheit den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von `PredictionEngine`-Objekten für die Anwendungsverwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="1700d-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="1700d-179">Registrieren von Startup als Azure Functions-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="1700d-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="1700d-180">Um `Startup` in Ihrer Anwendung verwenden zu können, müssen Sie es als Azure Functions-Erweiterung registrieren.</span><span class="sxs-lookup"><span data-stu-id="1700d-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="1700d-181">Erstellen Sie in Ihrem Projekt eine neue Datei namens *extensions.json*, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1700d-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="1700d-182">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="1700d-183">Wählen Sie im Dialogfeld **Neues Element** den Knoten **Visual C#** und anschließend den Knoten **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="1700d-184">Wählen Sie dann die Option **JSON-Datei**.</span><span class="sxs-lookup"><span data-stu-id="1700d-184">Then select the **Json File** option.</span></span> <span data-ttu-id="1700d-185">Geben Sie „extensions.json“ im Textfeld **Name** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1700d-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="1700d-186">Die Datei *extensions.json* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1700d-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="1700d-187">Fügen Sie folgenden Inhalt in der *extensions.json* ein:</span><span class="sxs-lookup"><span data-stu-id="1700d-187">Add the following content to *extensions.json*:</span></span>
    
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

1. <span data-ttu-id="1700d-188">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihre Datei *extensions.json*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="1700d-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="1700d-189">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="1700d-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="1700d-190">Laden des Modells in die Funktion</span><span class="sxs-lookup"><span data-stu-id="1700d-190">Load the model into the function</span></span>

<span data-ttu-id="1700d-191">Fügen Sie den folgenden Code in die *AnalyzeSentiment*-Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="1700d-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="1700d-192">Mit diesem Code wird die `PredictionEnginePool` durch Übergabe an den Konstruktor der Funktion zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.</span><span class="sxs-lookup"><span data-stu-id="1700d-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="1700d-193">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="1700d-193">Use the model to make predictions</span></span>

<span data-ttu-id="1700d-194">Ersetzen Sie die vorhandene Implementierung der *Run*-Methode in der *AnalyzeSentiment*-Klasse durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="1700d-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="1700d-195">Wenn die Methode `Run` ausgeführt wird, werden die eingehenden Daten aus der HTTP-Anforderung deserialisiert und als Eingabe für den `PredictionEnginePool` verwendet.</span><span class="sxs-lookup"><span data-stu-id="1700d-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="1700d-196">Die `Predict`-Methode wird dann aufgerufen, um eine Vorhersage zu generieren und das Ergebnis an den Benutzer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1700d-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="1700d-197">Lokales Testen</span><span class="sxs-lookup"><span data-stu-id="1700d-197">Test locally</span></span>

<span data-ttu-id="1700d-198">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen:</span><span class="sxs-lookup"><span data-stu-id="1700d-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="1700d-199">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="1700d-199">Run the application</span></span>
1. <span data-ttu-id="1700d-200">Öffnen Sie PowerShell, und geben Sie den Code in der Eingabeaufforderung ein, wobei PORT der Port ist, auf dem Ihre Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1700d-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="1700d-201">In der Regel ist es Port 7071.</span><span class="sxs-lookup"><span data-stu-id="1700d-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="1700d-202">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="1700d-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="1700d-203">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="1700d-203">Congratulations!</span></span> <span data-ttu-id="1700d-204">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer Azure-Funktion Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="1700d-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1700d-205">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1700d-205">Next Steps</span></span>

- [<span data-ttu-id="1700d-206">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="1700d-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
