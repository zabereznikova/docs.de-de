---
title: Bereitstellen des Modells für Azure Functions
description: Bereitstellen eines Machine Learning-Modells zur ML.NET-Standpunktanalyse für die Vorhersage über das Internet mit Azure Functions
ms.date: 08/20/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 96b62017994da5b7b209c441b3e7fb760cad5201
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666669"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="13cba-103">Bereitstellen des Modells für Azure Functions</span><span class="sxs-lookup"><span data-stu-id="13cba-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="13cba-104">Erfahren Sie, wie Sie ein vorab trainiertes ML.NET-Modell für maschinelles Lernen für Vorhersagen über HTTP in einer serverlosen Azure Functions-Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="13cba-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="13cba-105">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="13cba-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13cba-106">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="13cba-106">Prerequisites</span></span>

- <span data-ttu-id="13cba-107">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“ und installierter „Azure-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="13cba-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="13cba-108">NuGet-Paketversion 1.0.28+ von „Microsoft.NET.Sdk.Functions“</span><span class="sxs-lookup"><span data-stu-id="13cba-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- [<span data-ttu-id="13cba-109">Azure Functions-Tools</span><span class="sxs-lookup"><span data-stu-id="13cba-109">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="13cba-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="13cba-110">Powershell</span></span>
- <span data-ttu-id="13cba-111">Vorab trainiertes Modell.</span><span class="sxs-lookup"><span data-stu-id="13cba-111">Pre-trained model.</span></span> <span data-ttu-id="13cba-112">Verwenden Sie das [Tutorial für die ML.NET-Standpunktanalyse](../tutorials/sentiment-analysis.md), um Ihr eigenes Modell zu erstellen, oder laden Sie dieses [vorab trainierte Machine Learning-Modell für die Standpunktanalyse](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="13cba-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="13cba-113">Erstellen eines Azure Functions-Projekts</span><span class="sxs-lookup"><span data-stu-id="13cba-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="13cba-114">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="13cba-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="13cba-115">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="13cba-116">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **Cloud** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="13cba-117">Wählen Sie dann die **Azure Functions**-Projektvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="13cba-118">Geben Sie „SentimentAnalysisFunctionsApp“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="13cba-119">Öffnen Sie im Dialogfeld **Neues Projekt** die Dropdownliste über den Projektoptionen, und wählen Sie **Azure Functions v2 (.NET Core)** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="13cba-120">Wählen Sie dann das Projekt **HTTP-Trigger** und die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="13cba-121">Erstellen Sie ein Verzeichnis mit dem Namen *MLModels* in Ihrem Projekt, um Ihr Modell zu speichern:</span><span class="sxs-lookup"><span data-stu-id="13cba-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="13cba-122">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="13cba-123">Geben Sie „MLModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="13cba-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="13cba-124">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="13cba-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="13cba-125">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="13cba-126">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="13cba-127">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="13cba-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="13cba-128">Installieren Sie das **NuGet-Paket „Microsoft.Azure.Functions.Extensions“** :</span><span class="sxs-lookup"><span data-stu-id="13cba-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="13cba-129">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="13cba-130">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, und suchen Sie nach **Microsoft.Azure.Functions.Extensions**. Wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="13cba-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="13cba-131">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="13cba-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="13cba-132">Installieren Sie das NuGet-Paket **Microsoft.Extensions.ML**:</span><span class="sxs-lookup"><span data-stu-id="13cba-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="13cba-133">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="13cba-134">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach „Microsoft.Extensions.ML“, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="13cba-135">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="13cba-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="13cba-136">Aktualisieren Sie das **NuGet-Paket Microsoft.NET.Sdk.Functions** auf Version 1.0.28 oder höher:</span><span class="sxs-lookup"><span data-stu-id="13cba-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28+:</span></span>

    <span data-ttu-id="13cba-137">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="13cba-138">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Installiert“ aus, und suchen Sie nach **Microsoft.NET.Sdk.Functions**. Wählen Sie das Paket in der Liste und dann 1.0.28 aus, und klicken Sie anschließend auf die Schaltfläche **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="13cba-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="13cba-139">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="13cba-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="13cba-140">Hinzufügen des vorab trainierten Modells zum Projekt</span><span class="sxs-lookup"><span data-stu-id="13cba-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="13cba-141">Kopieren Sie Ihr vorbereitetes Modell in den *MLModels*-Ordner.</span><span class="sxs-lookup"><span data-stu-id="13cba-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="13cba-142">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr vorbereitetes Modell, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="13cba-143">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="13cba-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="13cba-144">Erstellen einer Azure-Funktion zur Standpunktanalyse</span><span class="sxs-lookup"><span data-stu-id="13cba-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="13cba-145">Erstellen Sie eine Klasse, um den Standpunkt vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="13cba-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="13cba-146">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="13cba-147">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="13cba-148">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Azure-Funktion** aus, und ändern Sie das Feld **Name** in *AnalyzeSentiment.cs*.</span><span class="sxs-lookup"><span data-stu-id="13cba-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="13cba-149">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="13cba-150">Wählen Sie im Dialogfeld **Neue Azure-Funktion** die Option **HTTP-Trigger** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="13cba-151">Wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="13cba-152">Die Datei *AnalyzeSentiment.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="13cba-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="13cba-153">Fügen Sie am Anfang der Datei *AnalyzeSentiment.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="13cba-154">Standardmäßig ist die `AnalyzeSentiment`-Klasse `static`.</span><span class="sxs-lookup"><span data-stu-id="13cba-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="13cba-155">Entfernen Sie das `static` -Schlüsselwort aus der Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="13cba-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="13cba-156">Erstellen von Datenmodellen</span><span class="sxs-lookup"><span data-stu-id="13cba-156">Create data models</span></span>

<span data-ttu-id="13cba-157">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="13cba-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="13cba-158">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="13cba-159">Erstellen Sie ein Verzeichnis mit dem Namen *DataModels* in Ihrem Projekt, um Ihre Datenmodelle zu speichern: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen > Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="13cba-160">Geben Sie „DataModels“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="13cba-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="13cba-161">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="13cba-162">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="13cba-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="13cba-163">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-163">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="13cba-164">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="13cba-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="13cba-165">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="13cba-166">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="13cba-167">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das *DataModels*-Verzeichnis, und wählen Sie **Hinzufügen > Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="13cba-168">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentPrediction.cs*.</span><span class="sxs-lookup"><span data-stu-id="13cba-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="13cba-169">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-169">Then, select the **Add** button.</span></span> <span data-ttu-id="13cba-170">Die Datei *SentimentPrediction.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="13cba-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="13cba-171">Fügen Sie am Anfang der Datei *SentimentPrediction.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="13cba-172">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code der Datei *SentimentPrediction.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="13cba-173">`SentimentPrediction` erbt von `SentimentData`, was den Zugriff auf die Originaldaten in der `SentimentText`-Eigenschaft sowie auf die vom Modell generierte Ausgabe ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="13cba-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="13cba-174">Registrieren des PredictionEnginePool-Diensts</span><span class="sxs-lookup"><span data-stu-id="13cba-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="13cba-175">Sie können [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) verwenden, um eine einzelne Vorhersage zu treffen.</span><span class="sxs-lookup"><span data-stu-id="13cba-175">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="13cba-176">Um [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in Ihrer Anwendung verwenden zu können, müssen Sie sie bei Bedarf erstellen.</span><span class="sxs-lookup"><span data-stu-id="13cba-176">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="13cba-177">Für diesen Fall hat sich die Abhängigkeitsinjektion bewährt.</span><span class="sxs-lookup"><span data-stu-id="13cba-177">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="13cba-178">Unter dem folgenden Link finden Sie weitere Informationen über die [Abhängigkeitsinjektion](https://en.wikipedia.org/wiki/Dependency_injection).</span><span class="sxs-lookup"><span data-stu-id="13cba-178">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="13cba-179">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-179">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="13cba-180">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="13cba-180">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="13cba-181">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="13cba-181">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="13cba-182">Die Datei *Startup.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="13cba-182">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="13cba-183">Fügen Sie am Anfang der Datei *Startup.cs* die folgende using-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-183">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="13cba-184">Entfernen Sie den vorhandenen Code unterhalb der using-Anweisungen, und fügen Sie den folgenden Code zur Datei *Startup.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="13cba-184">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="13cba-185">Auf der höchsten Stufe initialisiert dieser Code die Objekte und Dienste bei Anforderung automatisch, sodass dies nicht manuell durchgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="13cba-185">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="13cba-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="13cba-186">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="13cba-187">Verwenden Sie für verbesserte Leistung und Threadsicherheit den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) von `PredictionEngine`-Objekten für die Anwendungsverwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="13cba-187">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="13cba-188">Laden des Modells in die Funktion</span><span class="sxs-lookup"><span data-stu-id="13cba-188">Load the model into the function</span></span>

<span data-ttu-id="13cba-189">Fügen Sie den folgenden Code in die *AnalyzeSentiment*-Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="13cba-189">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="13cba-190">Mit diesem Code wird die `PredictionEnginePool` durch Übergabe an den Konstruktor der Funktion zugewiesen, den Sie über die Abhängigkeitsinjektion erhalten.</span><span class="sxs-lookup"><span data-stu-id="13cba-190">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="13cba-191">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="13cba-191">Use the model to make predictions</span></span>

<span data-ttu-id="13cba-192">Ersetzen Sie die vorhandene Implementierung der *Run*-Methode in der *AnalyzeSentiment*-Klasse durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="13cba-192">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="13cba-193">Wenn die Methode `Run` ausgeführt wird, werden die eingehenden Daten aus der HTTP-Anforderung deserialisiert und als Eingabe für den `PredictionEnginePool` verwendet.</span><span class="sxs-lookup"><span data-stu-id="13cba-193">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="13cba-194">Die `Predict`-Methode wird dann aufgerufen, um eine Vorhersage zu generieren und das Ergebnis an den Benutzer zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="13cba-194">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="13cba-195">Lokales Testen</span><span class="sxs-lookup"><span data-stu-id="13cba-195">Test locally</span></span>

<span data-ttu-id="13cba-196">Nachdem alles eingerichtet ist, ist es Zeit, die Anwendung zu testen:</span><span class="sxs-lookup"><span data-stu-id="13cba-196">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="13cba-197">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="13cba-197">Run the application</span></span>
1. <span data-ttu-id="13cba-198">Öffnen Sie PowerShell, und geben Sie den Code in der Eingabeaufforderung ein, wobei PORT der Port ist, auf dem Ihre Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="13cba-198">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="13cba-199">In der Regel ist es Port 7071.</span><span class="sxs-lookup"><span data-stu-id="13cba-199">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="13cba-200">Bei erfolgreicher Ausführung sollte die Ausgabe dem folgenden Text ähneln:</span><span class="sxs-lookup"><span data-stu-id="13cba-200">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="13cba-201">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="13cba-201">Congratulations!</span></span> <span data-ttu-id="13cba-202">Sie haben Ihr Modell erfolgreich bereitgestellt, um mit einer Azure-Funktion Vorhersagen über das Internet zu treffen.</span><span class="sxs-lookup"><span data-stu-id="13cba-202">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13cba-203">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="13cba-203">Next Steps</span></span>

- [<span data-ttu-id="13cba-204">Bereitstellung in Azure</span><span class="sxs-lookup"><span data-stu-id="13cba-204">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
