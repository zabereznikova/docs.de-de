---
title: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung
description: Erfahren Sie, wie Sie ML.NET in einem Szenario mit binärer Klassifizierung verwenden, um zu erfahren, wie Sie die Standpunktvorhersage verwenden, um die geeignete Aktion auszuführen.
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 57ade448f5773bee3474cb46bec8ad33e3afbee3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391058"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="5ee13-103">Tutorial: Verwenden von ML.NET in einem Standpunktanalyse-Szenario mit binärer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="5ee13-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="5ee13-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5ee13-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="5ee13-105">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="5ee13-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="5ee13-106">Dieses Beispieltutorial veranschaulicht das Verwenden von ML.NET zum Erstellen eines Standpunktklassifizierers über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5ee13-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="5ee13-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="5ee13-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5ee13-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="5ee13-108">Understand the problem</span></span>
> * <span data-ttu-id="5ee13-109">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5ee13-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="5ee13-110">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="5ee13-110">Prepare your data</span></span>
> * <span data-ttu-id="5ee13-111">Erstellen der Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="5ee13-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="5ee13-112">Laden eines Klassifizierers</span><span class="sxs-lookup"><span data-stu-id="5ee13-112">Load a classifier</span></span>
> * <span data-ttu-id="5ee13-113">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="5ee13-113">Train the model</span></span>
> * <span data-ttu-id="5ee13-114">Auswerten des Modells mit einem anderen Dataset</span><span class="sxs-lookup"><span data-stu-id="5ee13-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="5ee13-115">Vorhersagen der Testdatenergebnisse mit dem Modell</span><span class="sxs-lookup"><span data-stu-id="5ee13-115">Predict the test data outcomes with the model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="5ee13-116">Übersicht über das Standpunktanalyse-Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ee13-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="5ee13-117">Das Beispiel ist eine Konsolen-App, die ML.NET verwendet, um ein Modell zu trainieren, das den Standpunkt als positiv oder negativ klassifiziert und vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="5ee13-118">Sie wertet das Modell auch mit einem zweiten Dataset für die Qualitätsanalyse aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="5ee13-119">Die Standpunktdatasets stammen aus dem Projekt WikiDetox.</span><span class="sxs-lookup"><span data-stu-id="5ee13-119">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ee13-120">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="5ee13-120">Prerequisites</span></span>

* <span data-ttu-id="5ee13-121">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="5ee13-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="5ee13-122">Die [tabstoppgetrennte Wikipedia-Detox-Zeilendatendatei (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span><span class="sxs-lookup"><span data-stu-id="5ee13-122">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="5ee13-123">Die [tabstoppgetrennte Wikipedia-Detox-Zeilentestdatei (wikiPedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span><span class="sxs-lookup"><span data-stu-id="5ee13-123">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="5ee13-124">Machine Learning-Workflow</span><span class="sxs-lookup"><span data-stu-id="5ee13-124">Machine learning workflow</span></span>

<span data-ttu-id="5ee13-125">Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5ee13-125">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="5ee13-126">Die Workflowphasen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5ee13-126">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="5ee13-127">**Verstehen des Problems**</span><span class="sxs-lookup"><span data-stu-id="5ee13-127">**Understand the problem**</span></span>
2. <span data-ttu-id="5ee13-128">**Erfassen der Daten**</span><span class="sxs-lookup"><span data-stu-id="5ee13-128">**Ingest the data**</span></span>
3. <span data-ttu-id="5ee13-129">**Vorverarbeitung der Daten und Feature Engineering**</span><span class="sxs-lookup"><span data-stu-id="5ee13-129">**Data preprocess and feature engineering**</span></span>
4. <span data-ttu-id="5ee13-130">**Trainieren und Vorhersagen des Modells**</span><span class="sxs-lookup"><span data-stu-id="5ee13-130">**Train and predict the model**</span></span>
5. <span data-ttu-id="5ee13-131">**Evaluieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="5ee13-131">**Evaluate the model**</span></span>
6. <span data-ttu-id="5ee13-132">**Operationalisierung des Modells**</span><span class="sxs-lookup"><span data-stu-id="5ee13-132">**Model operationalization**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="5ee13-133">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="5ee13-133">Understand the problem</span></span>

<span data-ttu-id="5ee13-134">Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern.</span><span class="sxs-lookup"><span data-stu-id="5ee13-134">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="5ee13-135">Schlüsseln Sie das Problem auf, um die Ergebnisse vorherzusagen und auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-135">Breaking the problem down you to predict and evaluate the results.</span></span>

<span data-ttu-id="5ee13-136">Das Problem besteht bei diesem Tutorial darin, aus den auf der Website eingehenden Kommentaren den Standpunkt zu ermitteln, um die geeignete Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-136">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="5ee13-137">Sie können das Problem nach dem Standpunkttext und dem Standpunktwert für die Daten aufschlüsseln, mit denen Sie das Modell trainieren möchten, und einem vorhergesagten Standpunktwert, den Sie auswerten und dann praktisch verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5ee13-137">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="5ee13-138">Sie müssen dann den Standpunkt **bestimmen**, was Ihnen die Auswahl der Machine Learning-Aufgabe erleichtert.</span><span class="sxs-lookup"><span data-stu-id="5ee13-138">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="5ee13-139">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5ee13-139">Select the appropriate machine learning task</span></span>

<span data-ttu-id="5ee13-140">Von diesem Problem kennen Sie die folgenden Fakten:</span><span class="sxs-lookup"><span data-stu-id="5ee13-140">With this problem, you know the following facts:</span></span>

<span data-ttu-id="5ee13-141">Trainingsdaten: Websitekommentare können positiv oder negativ sein (**Standpunkt**).</span><span class="sxs-lookup"><span data-stu-id="5ee13-141">Training data: website comments can be positive or negative (**sentiment**).</span></span>
<span data-ttu-id="5ee13-142">Sagen Sie den **Standpunkt** eines neuen Websitekommentars voraus, positiv oder negativ, wie in den folgenden Beispielen:</span><span class="sxs-lookup"><span data-stu-id="5ee13-142">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="5ee13-143">Bitte schreiben Sie keinen Unsinn in Wikipedia.</span><span class="sxs-lookup"><span data-stu-id="5ee13-143">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="5ee13-144">Er ist der beste, und das müsste der Artikel hervorheben.</span><span class="sxs-lookup"><span data-stu-id="5ee13-144">He is the best, and the article should say that.</span></span>

<span data-ttu-id="5ee13-145">Die Machine Learning-Aufgabe zum Klassifizieren eignet sich optimal für dieses Szenario.</span><span class="sxs-lookup"><span data-stu-id="5ee13-145">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="5ee13-146">Informationen zur Klassifizierungsaufgabe</span><span class="sxs-lookup"><span data-stu-id="5ee13-146">About the classification task</span></span>

<span data-ttu-id="5ee13-147">Die Klassifizierung ist eine Machine Learning-Aufgabe, die Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ee13-147">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="5ee13-148">Beispielsweise können Sie mit der Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="5ee13-148">For example, you can use classification to:</span></span>

* <span data-ttu-id="5ee13-149">Einen Standpunkt als positiv oder negativ identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-149">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="5ee13-150">E-Mails als Spam, Junk oder gut klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-150">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="5ee13-151">Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.</span><span class="sxs-lookup"><span data-stu-id="5ee13-151">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="5ee13-152">Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-152">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="5ee13-153">Klassifizierungsaufgaben zählen häufig zu einem der folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="5ee13-153">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="5ee13-154">Binär: entweder A oder B.</span><span class="sxs-lookup"><span data-stu-id="5ee13-154">Binary: either A or B.</span></span>
* <span data-ttu-id="5ee13-155">Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.</span><span class="sxs-lookup"><span data-stu-id="5ee13-155">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="5ee13-156">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5ee13-156">Create a console application</span></span>

1. <span data-ttu-id="5ee13-157">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="5ee13-157">Open Visual Studio 2017.</span></span> <span data-ttu-id="5ee13-158">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-158">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="5ee13-159">Klicken Sie im Dialogfeld *Neues Projekt*\* auf den Knoten **Visual C#** und anschließend auf den Knoten **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="5ee13-159">In the *New Project*\* dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="5ee13-160">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="5ee13-160">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="5ee13-161">Geben Sie „SentimentAnalysis“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-161">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="5ee13-162">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="5ee13-162">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="5ee13-163">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-163">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="5ee13-164">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5ee13-164">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="5ee13-165">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="5ee13-165">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5ee13-166">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-166">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5ee13-167">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-167">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5ee13-168">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-168">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="5ee13-169">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="5ee13-169">Prepare your data</span></span>

1. <span data-ttu-id="5ee13-170">Laden Sie die Datasets [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) und [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Data*.</span><span class="sxs-lookup"><span data-stu-id="5ee13-170">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="5ee13-171">Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="5ee13-171">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="5ee13-172">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-172">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="5ee13-173">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="5ee13-173">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="5ee13-174">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="5ee13-174">Create classes and define paths</span></span>

<span data-ttu-id="5ee13-175">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="5ee13-176">Sie müssen drei globale Felder erstellen, die den Pfad zu den zuletzt heruntergeladenen Dateien enthalten:</span><span class="sxs-lookup"><span data-stu-id="5ee13-176">You need to create three global fields to hold the paths to the recently downloaded files:</span></span>

* <span data-ttu-id="5ee13-177">`_dataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ee13-177">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="5ee13-178">`_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ee13-178">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="5ee13-179">`_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="5ee13-179">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="5ee13-180">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="5ee13-180">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

<span data-ttu-id="5ee13-181">Sie müssen einige Klassen für die Eingabedaten und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-181">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="5ee13-182">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-182">Add a new class to your project:</span></span>

1. <span data-ttu-id="5ee13-183">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-183">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="5ee13-184">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="5ee13-184">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="5ee13-185">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-185">Then, select the **Add** button.</span></span>

    <span data-ttu-id="5ee13-186">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5ee13-186">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5ee13-187">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-187">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="5ee13-188">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-188">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="5ee13-189">`SentimentData` ist die Klasse des Eingabedatasets und verfügt über eine `float`-Variable (`Sentiment`), die einen entweder positiven oder negativen Wert für den Standpunkt enthält, und eine String-Variable für den Kommentar (`SentimentText`).</span><span class="sxs-lookup"><span data-stu-id="5ee13-189">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="5ee13-190">Beiden Feldern sind `Column`-Attribute angefügt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-190">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="5ee13-191">Dieses Attribut beschreibt die Reihenfolge der Felder in der Datendatei, und welches das `Label`-Feld ist.</span><span class="sxs-lookup"><span data-stu-id="5ee13-191">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="5ee13-192">Die `SentimentPrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5ee13-192">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="5ee13-193">Er verfügt über einen einzelnen booleschen Wert (`Sentiment`) und ein `PredictedLabel` `ColumnName`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="5ee13-193">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="5ee13-194">Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-194">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="5ee13-195">Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ee13-195">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="5ee13-196">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ee13-196">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="5ee13-197">Ändern Sie in der Datei *Program.cs* die Signatur der `Main`-Methode durch Ersetzen von `void` mit `async Task`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5ee13-197">In the *Program.cs* file, change the `Main` method signature by replacing `void` with `async Task`, as in the following example:</span></span>

```csharp
static async Task Main(string[] args) 
{

}
```

<span data-ttu-id="5ee13-198">Fügen Sie `async` zu `Main` mit einem <xref:System.Threading.Tasks.Task>-Rückgabetyp hinzu, da Sie das Modell später in einer ZIP-Datei speichern, und das Programm warten muss, bis diese externe Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5ee13-198">You add `async` to `Main` with a <xref:System.Threading.Tasks.Task> return type because you're saving the model to a zip file later, and the program needs to wait until that external task completes.</span></span>

> [!NOTE]
> <span data-ttu-id="5ee13-199">Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ee13-199">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="5ee13-200">Weitere Informationen finden Sie im C#-Programmierhandbuch im Thema [Main() und Befehlszeilenargumente (C#-Programmierhandbuch)](../../../docs/csharp/programming-guide/main-and-command-args/index.md) .</span><span class="sxs-lookup"><span data-stu-id="5ee13-200">For more information, see the [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) topic in the C# programming guide.</span></span>

<span data-ttu-id="5ee13-201">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="5ee13-201">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

<span data-ttu-id="5ee13-202">Die `Train`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5ee13-202">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="5ee13-203">Laden oder Erfassen der Daten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-203">Loads or ingests the data.</span></span>
* <span data-ttu-id="5ee13-204">Vorverarbeitung und Featurebereitstellung der Daten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-204">Preprocesses and featurizes the data.</span></span>
* <span data-ttu-id="5ee13-205">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="5ee13-205">Trains the model.</span></span>
* <span data-ttu-id="5ee13-206">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-206">Predicts sentiment based on test data.</span></span>

<span data-ttu-id="5ee13-207">Erstellen Sie die `Train`-Methode direkt nach der `Main`-Methode mit dem folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5ee13-207">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a><span data-ttu-id="5ee13-208">Erfassen der Daten</span><span class="sxs-lookup"><span data-stu-id="5ee13-208">Ingest the data</span></span>

<span data-ttu-id="5ee13-209">Initialisieren Sie eine neue Instanz der <xref:Microsoft.ML.LearningPipeline>, die das Laden von Daten, Datenverarbeitung/-featurebereitstellung und Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="5ee13-209">Initialize a new instance of <xref:Microsoft.ML.LearningPipeline> that will include the data loading, data processing/featurization, and model.</span></span> <span data-ttu-id="5ee13-210">Fügen Sie den folgenden Code am Ende der ersten Zeile der `Train`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="5ee13-210">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<span data-ttu-id="5ee13-211">Das <xref:Microsoft.ML.Data.TextLoader>-Objekt ist der erste Teil der Pipeline und lädt die Trainingsdateidaten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-211">The <xref:Microsoft.ML.Data.TextLoader> object is the first part of the pipeline, and loads the training file data.</span></span>

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a><span data-ttu-id="5ee13-212">Vorverarbeitung der Daten und Feature Engineering</span><span class="sxs-lookup"><span data-stu-id="5ee13-212">Data preprocess and feature engineering</span></span>

<span data-ttu-id="5ee13-213">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ee13-213">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="5ee13-214">Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-214">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="5ee13-215">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-215">Using data without these modeling tasks can produce misleading results.</span></span> <span data-ttu-id="5ee13-216">Mit den Transformationspipelines von ML.NET können Sie einen benutzerdefinierten Satz von Transformationen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ee13-216">ML.NET's transform pipelines allow you to compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="5ee13-217">Die Transformationen dienen in erster Linie der Datenfeaturebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5ee13-217">The transforms' primary purpose is for data featurization.</span></span> <span data-ttu-id="5ee13-218">Der Vorteil einer Transformationspipeline besteht darin, dass Sie sie nach der Transformationspipeline-Definition speichern können, um sie auf Testdaten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="5ee13-218">A transform pipeline's advantage is that after transform pipeline definition, save the pipeline to apply it to test data.</span></span>

<span data-ttu-id="5ee13-219">Wenden Sie einen <xref:Microsoft.ML.Transforms.TextFeaturizer> an, um die `SentimentText`-Spalte in einen [numerischen Vektor](../resources/glossary.md#numerical-feature-vector) namens `Features` zu konvertieren, den der Machine Learning-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ee13-219">Apply a <xref:Microsoft.ML.Transforms.TextFeaturizer> to convert the `SentimentText` column into a [numeric vector](../resources/glossary.md#numerical-feature-vector) called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="5ee13-220">Dies ist der Vorverarbeitungs-/Featurebereitstellungsschritt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-220">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="5ee13-221">Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-221">Using additional components available in ML.NET can enable better results with your model.</span></span> <span data-ttu-id="5ee13-222">Fügen Sie der Pipeline `TextFeaturizer` als nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-222">Add `TextFeaturizer` to the pipeline as the next line of code:</span></span>

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="5ee13-223">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="5ee13-223">Choose a learning algorithm</span></span>

<span data-ttu-id="5ee13-224">Das <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier>-Objekt ist ein Entscheidungsstruktur-Lernmodul, das Sie in dieser Pipeline verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ee13-224">The <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> object is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="5ee13-225">Ähnlich wie der Featurebereitstellungsschritt führt das Ausprobieren verschiedener in ML.NET verfügbarer Lernmodule und Ändern ihrer Parameter zu unterschiedlichen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-225">Similar to the featurization step, trying out different learners available in ML.NET and changing their parameters leads to different results.</span></span> <span data-ttu-id="5ee13-226">Bei der Optimierung können Sie [Hyperparameter](../resources/glossary.md#hyperparameter) wie <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> und <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs> festlegen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-226">For tuning, you can set [hyperparameters](../resources/glossary.md#hyperparameter) like <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves>, and <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span></span> <span data-ttu-id="5ee13-227">Diese Hyperparameter werden vor jeglichen Auswirkungen auf das Modell festgelegt und sind modellspezifisch.</span><span class="sxs-lookup"><span data-stu-id="5ee13-227">These hyperparameters are set before anything affects the model and are model-specific.</span></span> <span data-ttu-id="5ee13-228">Sie werden zur Optimierung der Entscheidungsstrukturleistung verwendet, sodass größere Werte sich negativ auf die Leistung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="5ee13-228">They're used to tune the decision tree for performance, so larger values can negatively impact performance.</span></span>

<span data-ttu-id="5ee13-229">Fügen Sie der `Train`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-229">Add the following code to the `Train` method:</span></span>

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a><span data-ttu-id="5ee13-230">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="5ee13-230">Train the model</span></span>

<span data-ttu-id="5ee13-231">Sie trainieren das Modell <xref:Microsoft.ML.PredictionModel%602> basierend auf dem Dataset, das geladen und transformiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="5ee13-231">You train the model, <xref:Microsoft.ML.PredictionModel%602>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="5ee13-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trainiert die Pipeline (lädt die Daten, trainiert den Featurebereitsteller und das Lernmodul).</span><span class="sxs-lookup"><span data-stu-id="5ee13-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trains the pipeline (loads the data, trains the featurizer and learner).</span></span> <span data-ttu-id="5ee13-233">Das Experiment wird erst ausgeführt, wenn dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="5ee13-233">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="5ee13-234">Fügen Sie der `Train`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-234">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="5ee13-235">Speichern und Zurückgeben des trainierten Modells zur Verwendung für die Evaluierung</span><span class="sxs-lookup"><span data-stu-id="5ee13-235">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="5ee13-236">An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ee13-236">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="5ee13-237">Fügen Sie den folgenden Code der nächsten Zeile in `Train` hinzu, um das Modell vor der Rückgabe in einer ZIP-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="5ee13-237">To save your model to a .zip file before returning, add the following code to the next line in `Train`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

<span data-ttu-id="5ee13-238">Geben Sie das Modell am Ende der `Train`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="5ee13-238">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="5ee13-239">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="5ee13-239">Evaluate the model</span></span>

<span data-ttu-id="5ee13-240">Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-240">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="5ee13-241">In der `Evaluate`-Methode wird das in `Train` erstellte Modell zur Evaluierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="5ee13-241">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="5ee13-242">Erstellen Sie die `Evaluate`-Methode direkt nach `Train` wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5ee13-242">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="5ee13-243">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5ee13-243">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="5ee13-244">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="5ee13-244">Loads the test dataset.</span></span>
* <span data-ttu-id="5ee13-245">Erstellen des binären Auswerters.</span><span class="sxs-lookup"><span data-stu-id="5ee13-245">Creates the binary evaluator.</span></span>
* <span data-ttu-id="5ee13-246">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="5ee13-246">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="5ee13-247">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="5ee13-247">Displays the metrics.</span></span>

<span data-ttu-id="5ee13-248">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Train`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-248">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<span data-ttu-id="5ee13-249">Die <xref:Microsoft.ML.Data.TextLoader>-Klasse lädt das neue Testdataset mit dem gleichen Schema.</span><span class="sxs-lookup"><span data-stu-id="5ee13-249">The <xref:Microsoft.ML.Data.TextLoader> class loads the new test dataset with the same schema.</span></span> <span data-ttu-id="5ee13-250">Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-250">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="5ee13-251">Fügen Sie der `Evaluate`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-251">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<span data-ttu-id="5ee13-252">Das <xref:Microsoft.ML.Models.BinaryClassificationEvaluator>-Objekt berechnet die Qualitätsmetriken für das `PredictionModel` mit dem angegebenen Dataset.</span><span class="sxs-lookup"><span data-stu-id="5ee13-252">The <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> object computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="5ee13-253">Fügen Sie zur Anzeige dieser Metriken den Auswerter als nächste Zeile mit folgendem Code der `Evaluate`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-253">To see those metrics, add the evaluator as the next line in the `Evaluate` method, with the following code:</span></span>

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<span data-ttu-id="5ee13-254">Die <xref:Microsoft.ML.Models.BinaryClassificationMetrics> enthält alle von Auswertern der binären Klassifizierung berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="5ee13-254">The <xref:Microsoft.ML.Models.BinaryClassificationMetrics> contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="5ee13-255">Um diese zur Bestimmung der Qualität des Modells anzuzeigen, müssen Sie die Metriken zuerst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-255">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="5ee13-256">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-256">Add the following code:</span></span>

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="5ee13-257">Anzeigen der Metriken zur Modellvalidierung</span><span class="sxs-lookup"><span data-stu-id="5ee13-257">Displaying the metrics for model validation</span></span>

<span data-ttu-id="5ee13-258">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="5ee13-258">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a><span data-ttu-id="5ee13-259">Vorhersagen der Testdatenergebnisse mit dem Modell</span><span class="sxs-lookup"><span data-stu-id="5ee13-259">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="5ee13-260">Erstellen Sie die `Predict`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="5ee13-260">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="5ee13-261">Die `Predict`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5ee13-261">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="5ee13-262">Erstellen von Testdaten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-262">Creates test data.</span></span>
* <span data-ttu-id="5ee13-263">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-263">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="5ee13-264">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="5ee13-264">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="5ee13-265">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="5ee13-265">Displays the predicted results.</span></span>

<span data-ttu-id="5ee13-266">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-266">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

<span data-ttu-id="5ee13-267">Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `Predict`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-267">Add some comments to test the trained model's predictions in the `Predict` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

<span data-ttu-id="5ee13-268">Nun besitzen Sie ein Modell, mit dem Sie den positiven oder negative Standpunkt der Kommentardaten unter Verwendung der <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType>-Methode vorhersagen können.</span><span class="sxs-lookup"><span data-stu-id="5ee13-268">Now that you have a model, you can use that to predict the positive or negative sentiment of the comment data using the <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5ee13-269">Verwenden Sie zum Abrufen einer Vorhersage `Predict` mit neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="5ee13-269">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="5ee13-270">Beachten Sie, dass die Eingabedaten eine Zeichenfolge sind und das Modell die Featurebereitstellungsschritt umfasst.</span><span class="sxs-lookup"><span data-stu-id="5ee13-270">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="5ee13-271">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="5ee13-271">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="5ee13-272">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-272">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="5ee13-273">Operationalisierung des Modells: Vorhersage</span><span class="sxs-lookup"><span data-stu-id="5ee13-273">Model operationalization: prediction</span></span>

<span data-ttu-id="5ee13-274">Anzeigen von `SentimentText` und entsprechender Standpunktvorhersage, um die Ergebnisse freizugeben und entsprechend mit ihnen zu agieren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-274">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="5ee13-275">Dies wird als Operationalisierung bezeichnet, wobei die zurückgegebenen Daten als Teil der Betriebsrichtlinien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ee13-275">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="5ee13-276">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Kopfzeile für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="5ee13-276">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

<span data-ttu-id="5ee13-277">Kombinieren Sie vor der Anzeige der vorhergesagten Ergebnisse Standpunkt und Vorhersage, um den ursprünglichen Kommentar mit dem vorhergesagten Standpunkt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-277">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="5ee13-278">Der folgende Code verwendet hierzu die <xref:System.Linq.Enumerable.Zip%2A>-Methode, darum fügen Sie diesen Code als Nächstes hinzu:</span><span class="sxs-lookup"><span data-stu-id="5ee13-278">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="5ee13-279">Da Sie nun `SentimentText` und `Sentiment` in einer Klasse kombiniert haben, können Sie die Ergebnisse mithilfe der <xref:System.Console.WriteLine?displayProperty=nameWithType>-Methode anzeigen:</span><span class="sxs-lookup"><span data-stu-id="5ee13-279">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

<span data-ttu-id="5ee13-280">Da abgeleitete Tupelelementnamen ein neues Feature in C# 7.1 sind und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.</span><span class="sxs-lookup"><span data-stu-id="5ee13-280">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="5ee13-281">Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-281">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="5ee13-282">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="5ee13-282">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="5ee13-283">Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus.</span><span class="sxs-lookup"><span data-stu-id="5ee13-283">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="5ee13-284">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ee13-284">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="5ee13-285">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="5ee13-285">Results</span></span>

<span data-ttu-id="5ee13-286">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="5ee13-286">Your results should be similar to the following.</span></span> <span data-ttu-id="5ee13-287">Während der Pipelineverarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-287">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="5ee13-288">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="5ee13-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="5ee13-289">Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-289">These have been removed from the following results for clarity.</span></span>

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

<span data-ttu-id="5ee13-290">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="5ee13-290">Congratulations!</span></span> <span data-ttu-id="5ee13-291">Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ee13-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="5ee13-292">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="5ee13-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ee13-293">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5ee13-293">Next steps</span></span>

<span data-ttu-id="5ee13-294">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="5ee13-294">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5ee13-295">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="5ee13-295">Understand the problem</span></span>
> * <span data-ttu-id="5ee13-296">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="5ee13-296">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="5ee13-297">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="5ee13-297">Prepare your data</span></span>
> * <span data-ttu-id="5ee13-298">Erstellen der Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="5ee13-298">Create the learning pipeline</span></span>
> * <span data-ttu-id="5ee13-299">Laden eines Klassifizierers</span><span class="sxs-lookup"><span data-stu-id="5ee13-299">Load a classifier</span></span>
> * <span data-ttu-id="5ee13-300">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="5ee13-300">Train the model</span></span>
> * <span data-ttu-id="5ee13-301">Auswerten des Modells mit einem anderen Dataset</span><span class="sxs-lookup"><span data-stu-id="5ee13-301">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="5ee13-302">Vorhersagen der Testdatenergebnisse mit dem Modell</span><span class="sxs-lookup"><span data-stu-id="5ee13-302">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="5ee13-303">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="5ee13-303">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="5ee13-304">Vorhersage des Taxifahrtpreises</span><span class="sxs-lookup"><span data-stu-id="5ee13-304">Taxi Fare Predictor</span></span>](taxi-fare.md)
