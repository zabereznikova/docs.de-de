---
title: Verwenden von ML.NET in einem Szenario zur Multiklassenklassifizierung von GitHub-Issues
description: Erfahren Sie hier, wie Sie mit ML.NET in einem Szenario zur Multiklassenklassifizierung GitHub-Issues klassifizieren, um sie einem bestimmten Bereich zuzuweisen.
ms.date: 03/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e25f044247064db26e4e1e74590d6f4970fe4477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318779"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="efe06-103">Tutorial: Verwenden von ML.NET zur Klassifizierung von GitHub-Issues in einem Szenario mit Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="efe06-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="efe06-104">In diesem Beispieltutorial wird veranschaulicht, wie Sie ML.NET zum Erstellen eines Klassifizierers für GitHub-Issues über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017 verwenden können.</span><span class="sxs-lookup"><span data-stu-id="efe06-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="efe06-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="efe06-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="efe06-106">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="efe06-106">Understand the problem</span></span>
> * <span data-ttu-id="efe06-107">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="efe06-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="efe06-108">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-108">Prepare your data</span></span>
> * <span data-ttu-id="efe06-109">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-109">Transform the data</span></span>
> * <span data-ttu-id="efe06-110">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-110">Train the model</span></span>
> * <span data-ttu-id="efe06-111">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-111">Evaluate the model</span></span>
> * <span data-ttu-id="efe06-112">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="efe06-112">Predict with the trained model</span></span>
> * <span data-ttu-id="efe06-113">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="efe06-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="efe06-114">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="efe06-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="efe06-115">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="efe06-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="efe06-116">Dieses Tutorial und das zugehörige Beispiel verwenden zurzeit **ML.NET Version 0.11**.</span><span class="sxs-lookup"><span data-stu-id="efe06-116">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="efe06-117">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="efe06-117">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="efe06-118">Beispielübersicht für ein GitHub-Issue</span><span class="sxs-lookup"><span data-stu-id="efe06-118">GitHub issue sample overview</span></span>

<span data-ttu-id="efe06-119">Das Beispiel ist eine Konsolen-App, die ML.NET zum Trainieren eines Modells verwendet, das für ein GitHub-Issue die Bezeichnung „Area“ (Bereich) klassifiziert und vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="efe06-119">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="efe06-120">Sie wertet das Modell auch mit einem zweiten Dataset für die Qualitätsanalyse aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-120">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="efe06-121">Die Datasets des Issues stammen aus dem GitHub-Repository „dotnet/coreFX“.</span><span class="sxs-lookup"><span data-stu-id="efe06-121">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="efe06-122">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="efe06-122">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="efe06-123">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="efe06-123">Prerequisites</span></span>

* <span data-ttu-id="efe06-124">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="efe06-124">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="efe06-125">Die [durch Tabstopp getrennte Datei mit Github-Issues (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="efe06-125">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="efe06-126">Die [durch Tabstopp getrennte Testdatei für Github-Issues (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="efe06-126">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="efe06-127">Machine Learning-Workflow</span><span class="sxs-lookup"><span data-stu-id="efe06-127">Machine learning workflow</span></span>

<span data-ttu-id="efe06-128">Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="efe06-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="efe06-129">Die Workflowphasen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="efe06-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="efe06-130">**Verstehen des Problems**</span><span class="sxs-lookup"><span data-stu-id="efe06-130">**Understand the problem**</span></span>
2. <span data-ttu-id="efe06-131">**Vorbereiten Ihrer Daten**</span><span class="sxs-lookup"><span data-stu-id="efe06-131">**Prepare your data**</span></span>
   * <span data-ttu-id="efe06-132">**Laden der Daten**</span><span class="sxs-lookup"><span data-stu-id="efe06-132">**Load the data**</span></span>
   * <span data-ttu-id="efe06-133">**Extrahieren von Funktionen (Transformieren von Daten)**</span><span class="sxs-lookup"><span data-stu-id="efe06-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="efe06-134">**Erstellen und trainieren**</span><span class="sxs-lookup"><span data-stu-id="efe06-134">**Build and train**</span></span> 
   * <span data-ttu-id="efe06-135">**Trainieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="efe06-135">**Train the model**</span></span>
   * <span data-ttu-id="efe06-136">**Evaluieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="efe06-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="efe06-137">**Bereitstellen des Modells**</span><span class="sxs-lookup"><span data-stu-id="efe06-137">**Deploy Model**</span></span>
   * <span data-ttu-id="efe06-138">**Vorhersagen treffen mit dem Modell**</span><span class="sxs-lookup"><span data-stu-id="efe06-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="efe06-139">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="efe06-139">Understand the problem</span></span>

<span data-ttu-id="efe06-140">Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern.</span><span class="sxs-lookup"><span data-stu-id="efe06-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="efe06-141">Durch Aufschlüsseln des Problems können Sie die Ergebnisse vorhersagen und auswerten.</span><span class="sxs-lookup"><span data-stu-id="efe06-141">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="efe06-142">In diesem Tutorial wird behandelt, wie Sie erkennen können, zu welchem Bereich ein eingehendes GitHub-Issue gehört, um es anschließend für die Priorisierung und Planung korrekt zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="efe06-142">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="efe06-143">Sie können das Problem in die folgenden Einzelteile aufschlüsseln:</span><span class="sxs-lookup"><span data-stu-id="efe06-143">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="efe06-144">Titeltext des Issues</span><span class="sxs-lookup"><span data-stu-id="efe06-144">the issue title text</span></span>
* <span data-ttu-id="efe06-145">Beschreibungstext des Issues</span><span class="sxs-lookup"><span data-stu-id="efe06-145">the issue description text</span></span>
* <span data-ttu-id="efe06-146">Wert für den Bereich der Modelltrainingsdaten</span><span class="sxs-lookup"><span data-stu-id="efe06-146">an area value for the model training data</span></span>
* <span data-ttu-id="efe06-147">vorhergesagter Wert für den Bereich zur Auswertung und anschließenden praktischen Verwendung</span><span class="sxs-lookup"><span data-stu-id="efe06-147">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="efe06-148">Anschließend müssen Sie den Bereich **bestimmen**. Dadurch wird die Auswahl der Machine Learning-Aufgabe erleichtert.</span><span class="sxs-lookup"><span data-stu-id="efe06-148">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="efe06-149">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="efe06-149">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="efe06-150">Von diesem Problem kennen Sie die folgenden Fakten:</span><span class="sxs-lookup"><span data-stu-id="efe06-150">With this problem, you know the following facts:</span></span>

<span data-ttu-id="efe06-151">Trainingsdaten:</span><span class="sxs-lookup"><span data-stu-id="efe06-151">Training data:</span></span>

<span data-ttu-id="efe06-152">GitHub-Issues können, wie in den folgenden Beispielen veranschaulicht wird, in verschiedenen Bereichen (**Area**) bezeichnet werden:</span><span class="sxs-lookup"><span data-stu-id="efe06-152">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="efe06-153">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="efe06-153">area-System.Numerics</span></span>
* <span data-ttu-id="efe06-154">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="efe06-154">area-System.Xml</span></span>
* <span data-ttu-id="efe06-155">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="efe06-155">area-Infrastructure</span></span>
* <span data-ttu-id="efe06-156">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="efe06-156">area-System.Linq</span></span>
* <span data-ttu-id="efe06-157">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="efe06-157">area-System.IO</span></span>

<span data-ttu-id="efe06-158">Sagen Sie den **Bereich** eines neuen GitHub-Issues wie in den folgenden Beispielen veranschaulicht vorher:</span><span class="sxs-lookup"><span data-stu-id="efe06-158">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="efe06-159">Contract.Assert im Vergleich zu Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="efe06-159">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="efe06-160">Festlegen von Feldern in System.Xml als schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="efe06-160">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="efe06-161">Der Machine Learning-Algorithmus für die Klassifizierung ist für dieses Szenario am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="efe06-161">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="efe06-162">Informationen zum Lernalgorithmus für die Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="efe06-162">About the classification learning algorithm</span></span>

<span data-ttu-id="efe06-163">Die Klassifizierung ist ein Machine Learning-Algorithmus, der Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="efe06-163">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="efe06-164">Beispielsweise können Sie mit der Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="efe06-164">For example, you can use classification to:</span></span>

* <span data-ttu-id="efe06-165">Einen Standpunkt als positiv oder negativ identifizieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-165">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="efe06-166">E-Mails als Spam, Junk oder gut klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-166">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="efe06-167">Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.</span><span class="sxs-lookup"><span data-stu-id="efe06-167">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="efe06-168">Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-168">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="efe06-169">Die Anwendungsfälle des Lernalgorithmus für die Klassifizierung weisen meist einen der folgenden Typen auf:</span><span class="sxs-lookup"><span data-stu-id="efe06-169">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="efe06-170">Binär: entweder A oder B.</span><span class="sxs-lookup"><span data-stu-id="efe06-170">Binary: either A or B.</span></span>
* <span data-ttu-id="efe06-171">Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.</span><span class="sxs-lookup"><span data-stu-id="efe06-171">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="efe06-172">Verwenden Sie für diese Art von Problemen einen Lernalgorithmus für die Klassifizierung, da es wahrscheinlicher ist, dass Ihre Vorhersage einer Problemkategorie einer von vielen Kategorien (Multiklasse) als einer von zwei (Binär) entspricht.</span><span class="sxs-lookup"><span data-stu-id="efe06-172">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="efe06-173">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="efe06-173">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="efe06-174">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="efe06-174">Create a project</span></span>

1. <span data-ttu-id="efe06-175">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="efe06-175">Open Visual Studio 2017.</span></span> <span data-ttu-id="efe06-176">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-176">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="efe06-177">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-177">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="efe06-178">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="efe06-178">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="efe06-179">Geben Sie „GitHubIssueClassification“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-179">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="efe06-180">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="efe06-180">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="efe06-181">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-181">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="efe06-182">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="efe06-182">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="efe06-183">Erstellen Sie ein Verzeichnis mit dem Namen *Models* in Ihrem Projekt, um Ihr Modell zu speichern:</span><span class="sxs-lookup"><span data-stu-id="efe06-183">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="efe06-184">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-184">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="efe06-185">Geben Sie „Models“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="efe06-185">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="efe06-186">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="efe06-186">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="efe06-187">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-187">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="efe06-188">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-188">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="efe06-189">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="efe06-189">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="efe06-190">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-190">Prepare your data</span></span>

1. <span data-ttu-id="efe06-191">Laden Sie die Datasets [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) und [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Daten*.</span><span class="sxs-lookup"><span data-stu-id="efe06-191">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="efe06-192">Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="efe06-192">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="efe06-193">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-193">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="efe06-194">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="efe06-194">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="efe06-195">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="efe06-195">Create classes and define paths</span></span>

<span data-ttu-id="efe06-196">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-196">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="efe06-197">Erstellen Sie drei globale Felder, die die Pfade zu den zuletzt heruntergeladenen Dateien sowie globale Variablen für `MLContext`, `DataView`, `PredictionEngine` und `TextLoader` enthalten:</span><span class="sxs-lookup"><span data-stu-id="efe06-197">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="efe06-198">`_trainDataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efe06-198">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="efe06-199">`_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efe06-199">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="efe06-200">`_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="efe06-200">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="efe06-201">`_mlContext` ist die <xref:Microsoft.ML.MLContext>-Klasse, die den Verarbeitungskontext enthält.</span><span class="sxs-lookup"><span data-stu-id="efe06-201">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="efe06-202">`_trainingDataView` ist die zum Verarbeiten des Trainingsdatasets verwendete <xref:Microsoft.Data.DataView.IDataView>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="efe06-202">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="efe06-203">`_predEngine` ist die für einzelne Vorhersagen verwendete <xref:Microsoft.ML.PredictionEngine%602>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="efe06-203">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="efe06-204">`_reader` ist der zum Laden und Transformieren der Datasets verwendete <xref:Microsoft.ML.Data.TextLoader>.</span><span class="sxs-lookup"><span data-stu-id="efe06-204">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="efe06-205">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="efe06-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="efe06-206">Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="efe06-206">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="efe06-207">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="efe06-208">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="efe06-209">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="efe06-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="efe06-210">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="efe06-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="efe06-211">Die Datei *GitHubIssueData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="efe06-211">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="efe06-212">Fügen Sie am Anfang der Datei *GitHubIssueData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-212">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="efe06-213">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *GitHubIssueData.cs* den folgenden Code mit den beiden Klassen `GitHubIssue` und `IssuePrediction` hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-213">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="efe06-214">`GitHubIssue` ist die Klasse des Eingabedatasets mit den folgenden <xref:System.String>-Feldern:</span><span class="sxs-lookup"><span data-stu-id="efe06-214">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="efe06-215">`ID` enthält einen Wert für die ID des GitHub-Issues.</span><span class="sxs-lookup"><span data-stu-id="efe06-215">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="efe06-216">`Area` enthält einen Wert für die `Area`-Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="efe06-216">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="efe06-217">`Title` enthält den Titel des GitHub-Issues.</span><span class="sxs-lookup"><span data-stu-id="efe06-217">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="efe06-218">`Description` enthält die Beschreibung des GitHub-Issues.</span><span class="sxs-lookup"><span data-stu-id="efe06-218">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="efe06-219">Die `IssuePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="efe06-219">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="efe06-220">Sie verfügt über ein einzelnes `string`- (`Area`) und ein `PredictedLabel` `ColumnName`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="efe06-220">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="efe06-221">Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-221">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="efe06-222">Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="efe06-222">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="efe06-223">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="efe06-223">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="efe06-224">Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst eine <xref:Microsoft.ML.MLContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="efe06-224">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="efe06-225">`MLContext` ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="efe06-225">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="efe06-226">Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="efe06-226">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="efe06-227">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="efe06-227">Initialize variables in Main</span></span>

<span data-ttu-id="efe06-228">Initialisieren Sie die globale Variable `_mlContext` mit einer neuen Instanz von `MLContext` mit einem zufälligen Ausgangswert (`seed: 0`), um in mehreren Trainings wiederholbare/deterministische Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="efe06-228">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="efe06-229">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="efe06-229">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="efe06-230">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-230">Load the data</span></span>

<span data-ttu-id="efe06-231">Initialisieren Sie anschließend die globale <xref:Microsoft.Data.DataView.IDataView>-Variable `_trainingDataView`, und laden Sie die Daten mit dem `_trainDataPath`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="efe06-231">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="efe06-232">Als Ein- und Ausgabe von [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer) ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="efe06-232">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="efe06-233">In ML.NET ähneln die Daten einer `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="efe06-233">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="efe06-234">Sie werden verzögert ausgewertet, sind schematisiert und heterogen.</span><span class="sxs-lookup"><span data-stu-id="efe06-234">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="efe06-235">Das Objekt ist der erste Teil der Pipeline und lädt die Daten.</span><span class="sxs-lookup"><span data-stu-id="efe06-235">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="efe06-236">In diesem Tutorial wird ein Dataset mit dem Titel und der Beschreibung des Issues und der entsprechenden GitHub-Bezeichnung des Bereichs geladen.</span><span class="sxs-lookup"><span data-stu-id="efe06-236">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="efe06-237">Mit `DataView` wird das Modell erstellt und trainiert.</span><span class="sxs-lookup"><span data-stu-id="efe06-237">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="efe06-238">Da der zuvor von Ihnen erstellte `GitHubIssue`-Datenmodelltyp dem Schema des Datasets entspricht, können Sie das Initialisieren, Zuordnen und Laden des Datasets in einer Codezeile zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="efe06-238">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="efe06-239">Laden Sie die Daten mithilfe des `MLContext.Data.LoadFromTextFile`-Wrappers für die [LoadFromTextFile-Methode](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span><span class="sxs-lookup"><span data-stu-id="efe06-239">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="efe06-240">Es wird eine <xref:Microsoft.Data.DataView.IDataView> zurückgegeben, die das Datasetschema aus dem `GitHubIssue`-Datenmodelltyp ableitet und den Datasetheader verwendet.</span><span class="sxs-lookup"><span data-stu-id="efe06-240">It returns a <xref:Microsoft.Data.DataView.IDataView> which infers the dataset schema from the `GitHubIssue` data model type and uses the dataset header.</span></span> 

<span data-ttu-id="efe06-241">Das Datenschema wurde bereits beim Erstellen der `GitHubIssue`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="efe06-241">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="efe06-242">Für Ihr Schema gilt:</span><span class="sxs-lookup"><span data-stu-id="efe06-242">For your schema:</span></span>

* <span data-ttu-id="efe06-243">Die erste Spalte: `ID` (ID des GitHub-Issues)</span><span class="sxs-lookup"><span data-stu-id="efe06-243">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="efe06-244">Die zweite Spalte: `Area` (Vorhersage für das Training)</span><span class="sxs-lookup"><span data-stu-id="efe06-244">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="efe06-245">Die dritte Spalte `Title` (Titel des GitHub-Issues) ist das erste [Feature](../resources/glossary.md##feature) zur Vorhersage von `Area`.</span><span class="sxs-lookup"><span data-stu-id="efe06-245">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="efe06-246">Die vierte Spalte `Description` ist das zweite Feature für die Vorhersage von `Area`.</span><span class="sxs-lookup"><span data-stu-id="efe06-246">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="efe06-247">Fügen Sie nach der Initialisierung von `mlContext` den folgenden Code hinzu, um die globale Variable `_trainingDataView` zur Verwendung für die Pipeline zu initialisieren und zu laden:</span><span class="sxs-lookup"><span data-stu-id="efe06-247">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

<span data-ttu-id="efe06-248">Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="efe06-248">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="efe06-249">Die `ProcessData`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="efe06-249">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="efe06-250">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="efe06-250">Extracts and transforms the data.</span></span>
* <span data-ttu-id="efe06-251">Zurückgeben der Verarbeitungspipeline</span><span class="sxs-lookup"><span data-stu-id="efe06-251">Returns the processing pipeline.</span></span>

<span data-ttu-id="efe06-252">Erstellen Sie die `ProcessData`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="efe06-252">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="efe06-253">Extrahieren von Features und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-253">Extract Features and transform the data</span></span>

<span data-ttu-id="efe06-254">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efe06-254">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="efe06-255">Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="efe06-255">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="efe06-256">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="efe06-256">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="efe06-257">Mit den Transformationspipelines von ML.NET können Sie benutzerdefinierte `transforms`-Klassen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="efe06-257">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="efe06-258">Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="efe06-258">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="efe06-259">Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen.</span><span class="sxs-lookup"><span data-stu-id="efe06-259">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="efe06-260">Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="efe06-260">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="efe06-261">In den nächsten Schritten werden die Spalten mit den zuvor in der `GitHubIssue`-Klasse definierten Namen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="efe06-261">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="efe06-262">Wenn das Modell trainiert und ausgewertet wurde, gelten die Werte in der Spalte **Label** standardmäßig als richtige Werte, die vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="efe06-262">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="efe06-263">Da die GitHub-Bezeichnung des Bereichs für ein `GitHubIssue` vorhergesagt werden soll, kopieren Sie die Spalte `Area` in die Spalte **Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="efe06-263">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="efe06-264">Verwenden Sie hierfür `MLContext.Transforms.Conversion.MapValueToKey` (einen Wrapper für die Transformationsklasse <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>).</span><span class="sxs-lookup"><span data-stu-id="efe06-264">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="efe06-265">`MapValueToKey` gibt <xref:Microsoft.ML.Data.EstimatorChain%601> zurück, das eine Pipeline ist.</span><span class="sxs-lookup"><span data-stu-id="efe06-265">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="efe06-266">Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen.</span><span class="sxs-lookup"><span data-stu-id="efe06-266">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="efe06-267">Fügen Sie die nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-267">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="efe06-268">Dadurch werden verschiedene numerische Schlüsselwerte den verschiedenen Werten in jeder Spalte zugeordnet und vom Machine Learning-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="efe06-268">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="efe06-269">Rufen Sie als Nächstes `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalten (`Title` und `Description`) jeweils in einen numerischen Vektor namens `TitleFeaturized` und `DescriptionFeaturized` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="efe06-269">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="efe06-270">Fügen Sie an die Pipeline die Featurebereitstellung für beide Spalten mit dem folgenden Code an:</span><span class="sxs-lookup"><span data-stu-id="efe06-270">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="efe06-271">Die ML.NET-Version 0.10 hat die Reihenfolge der Transformationsparameter geändert.</span><span class="sxs-lookup"><span data-stu-id="efe06-271">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="efe06-272">Erst beim Erstellen des Projekts wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="efe06-272">This will not error out until you build.</span></span> <span data-ttu-id="efe06-273">Verwenden Sie für Transformationen die Parameternamen, wie Sie im vorherigen Codeausschnitt dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="efe06-273">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="efe06-274">Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse `Concatenate` in die Spalte **Features** kombiniert.</span><span class="sxs-lookup"><span data-stu-id="efe06-274">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="efe06-275">Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**.</span><span class="sxs-lookup"><span data-stu-id="efe06-275">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="efe06-276">Fügen Sie an die Pipeline diese Transformation mit dem folgenden Code an:</span><span class="sxs-lookup"><span data-stu-id="efe06-276">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="efe06-277">Fügen Sie anschließend wie im folgenden Code veranschaulicht eine <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A>-Methode zum Zwischenspeichern von DataView an. Dadurch erhalten Sie beim mehrmaligen Durchlaufen der Daten mit dem Cache möglicherweise eine bessere Leistung:</span><span class="sxs-lookup"><span data-stu-id="efe06-277">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="efe06-278">Verwenden Sie AppendCacheCheckpoint für kleine/mittlere Datasets, um die Zeit für das Training zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-278">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="efe06-279">Verwenden Sie dies NICHT bei der Verarbeitung sehr großer Datasets (entfernen Sie .AppendCacheCheckpoint()).</span><span class="sxs-lookup"><span data-stu-id="efe06-279">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="efe06-280">Geben Sie die Pipeline am Ende der `ProcessData`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="efe06-280">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="efe06-281">In diesem Schritt wird die Vorverarbeitung/Featurebereitstellung behandelt.</span><span class="sxs-lookup"><span data-stu-id="efe06-281">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="efe06-282">Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="efe06-282">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="efe06-283">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-283">Build and train the model</span></span>

<span data-ttu-id="efe06-284">Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-284">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="efe06-285">Die `BuildAndTrainModel`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="efe06-285">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="efe06-286">Erstellen der Algorithmusklasse für das Training</span><span class="sxs-lookup"><span data-stu-id="efe06-286">Creates the training algorithm class.</span></span>
* <span data-ttu-id="efe06-287">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="efe06-287">Trains the model.</span></span>
* <span data-ttu-id="efe06-288">Vorhersagen des Bereichs basierend auf den Trainingsdaten</span><span class="sxs-lookup"><span data-stu-id="efe06-288">Predicts area based on training data.</span></span>
* <span data-ttu-id="efe06-289">Speichern des Modells in einer `.zip`-Datei</span><span class="sxs-lookup"><span data-stu-id="efe06-289">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="efe06-290">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="efe06-290">Returns the model.</span></span>

<span data-ttu-id="efe06-291">Erstellen Sie die `BuildAndTrainModel`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="efe06-291">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

<span data-ttu-id="efe06-292">Beachten Sie, dass der BuildAndTrainModel-Methode zwei Parameter übergeben werden: `IDataView` für das Trainingsdataset (`trainingDataView`) und <xref:Microsoft.ML.Data.EstimatorChain%601> für die in ProcessData erstellte Verarbeitungspipeline (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="efe06-292">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="efe06-293">Fügen Sie den folgenden Code am Ende der ersten Zeile der `BuildAndTrainModel`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="efe06-293">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="efe06-294">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="efe06-294">Choose a learning algorithm</span></span>

<span data-ttu-id="efe06-295">Rufen Sie zum Hinzufügen des Lernalgorithmus die Wrappermethode `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` auf, die ein <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="efe06-295">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="efe06-296">`SdcaMultiClassTrainer` wird an die `pipeline` angefügt und akzeptiert die mit Features ausgestatteten `Title`- und `Description`-Parameter (`Features`) sowie die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="efe06-296">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="efe06-297">Ordnen Sie außerdem die Bezeichnung dem Wert zu, um den ursprünglichen lesbaren Zustand wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="efe06-297">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="efe06-298">Führen Sie diese beiden Aktionen mithilfe des folgenden Codes aus:</span><span class="sxs-lookup"><span data-stu-id="efe06-298">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="efe06-299">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-299">Train the model</span></span>

<span data-ttu-id="efe06-300">Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="efe06-300">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="efe06-301">Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> und stellen die bereits geladenen Trainingsdaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="efe06-301">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="efe06-302">Diese Methode gibt ein Modell zurück, das für Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="efe06-302">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="efe06-303">`trainingPipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück.</span><span class="sxs-lookup"><span data-stu-id="efe06-303">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="efe06-304">Das Experiment wird erst ausgeführt, wenn die `.Fit()`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="efe06-304">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="efe06-305">Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-305">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="efe06-306">Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, doch die Notwendigkeit, Vorhersagen für einzelne Beispiele zu treffen, ist ein sehr gängiges Produktionsszenario.</span><span class="sxs-lookup"><span data-stu-id="efe06-306">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="efe06-307"><xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="efe06-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="efe06-308">Fügen Sie den folgenden Code hinzu, um `PredictionEngine` als nächste Zeile in der `BuildAndTrainModel`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="efe06-308">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="efe06-309">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="efe06-309">Predict with the trained model</span></span>

<span data-ttu-id="efe06-310">Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="efe06-310">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="efe06-311">Damit können Sie die `Area`-Bezeichnung einer einzelnen Instanz der Daten des Issues vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="efe06-311">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="efe06-312">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="efe06-312">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="efe06-313">Die Eingabedaten sind eine Zeichenfolge, und das Modell enthält die Featurebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="efe06-313">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="efe06-314">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="efe06-314">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="efe06-315">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="efe06-315">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="efe06-316">Verwenden des Modells: Vorhersageergebnisse</span><span class="sxs-lookup"><span data-stu-id="efe06-316">Using the model: prediction results</span></span>

<span data-ttu-id="efe06-317">Zeigen Sie `GitHubIssue` und die entsprechende Vorhersage der `Area`-Bezeichnung an, um die Ergebnisse freizugeben und entsprechenden Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="efe06-317">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="efe06-318">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="efe06-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="efe06-319">Zurückgeben des für die Evaluierung trainierten Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-319">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="efe06-320">Geben Sie das Modell am Ende der `BuildAndTrainModel`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="efe06-320">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="efe06-321">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-321">Evaluate the model</span></span>

<span data-ttu-id="efe06-322">Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-322">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="efe06-323">In der `Evaluate`-Methode wird das in `BuildAndTrainModel` erstellte Modell zur Evaluierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="efe06-323">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="efe06-324">Erstellen Sie die `Evaluate`-Methode direkt nach `BuildAndTrainModel` wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="efe06-324">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="efe06-325">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="efe06-325">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="efe06-326">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="efe06-326">Loads the test dataset.</span></span>
* <span data-ttu-id="efe06-327">Erstellen des Multiklassenauswerters</span><span class="sxs-lookup"><span data-stu-id="efe06-327">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="efe06-328">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="efe06-328">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="efe06-329">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="efe06-329">Displays the metrics.</span></span>

<span data-ttu-id="efe06-330">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `BuildAndTrainModel`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-330">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="efe06-331">Sie können die Initialisierung, Zuordnung und das Laden des Testdatasets wie beim Trainingsdataset in einer Codezeile zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="efe06-331">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="efe06-332">Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren.</span><span class="sxs-lookup"><span data-stu-id="efe06-332">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="efe06-333">Fügen Sie der `Evaluate`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-333">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="efe06-334">`MulticlassClassificationContext.Evaluate` ist ein Wrapper für die <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A>-Methode, die die Qualitätsmetriken für das Modell mit dem angegebenen Dataset berechnet.</span><span class="sxs-lookup"><span data-stu-id="efe06-334">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="efe06-335">Das zurückgegebene <xref:Microsoft.ML.Data.MultiClassClassifierMetrics>-Objekt enthält alle von Auswertern der Multiklassenklassifizierung berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="efe06-335">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="efe06-336">Um diese Metriken zum Ermitteln der Modellqualität anzuzeigen, müssen Sie sie zunächst abrufen.</span><span class="sxs-lookup"><span data-stu-id="efe06-336">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="efe06-337">Beachten Sie die Verwendung der `Transform`-Methode der globalen Machine Learning-Variable `_trainedModel` (ein Transformator), um die Funktionen einzugeben und die Vorhersagen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="efe06-337">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="efe06-338">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-338">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="efe06-339">Für die Multiklassenklassifizierung werden die folgenden Metriken ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="efe06-339">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="efe06-340">Mikrogenauigkeit: Jedes Beispiel/Klasse-Paar trägt zu gleichen Teilen zur Genauigkeitsmetrik bei.</span><span class="sxs-lookup"><span data-stu-id="efe06-340">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="efe06-341">Die Mikrogenauigkeit sollte so nahe wie möglich bei 1 liegen.</span><span class="sxs-lookup"><span data-stu-id="efe06-341">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="efe06-342">Makrogenauigkeit: Jede Klasse trägt zu gleichen Teilen zur Genauigkeitsmetrik bei.</span><span class="sxs-lookup"><span data-stu-id="efe06-342">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="efe06-343">Minderheitsklassen werden gleich wie größere Klassen gewichtet.</span><span class="sxs-lookup"><span data-stu-id="efe06-343">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="efe06-344">Die Makrogenauigkeit sollte so nahe wie möglich bei 1 liegen.</span><span class="sxs-lookup"><span data-stu-id="efe06-344">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="efe06-345">Protokollverlust: Siehe [Protokollverlust](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="efe06-345">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="efe06-346">Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="efe06-346">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="efe06-347">Verringerung des Protokollverlusts: Liegt zwischen [-inf, 100], wobei „100“ perfekte Vorhersagen und „0“ durchschnittliche Vorhersagen bedeutet.</span><span class="sxs-lookup"><span data-stu-id="efe06-347">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="efe06-348">Die Verringerung des Protokollverlusts sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="efe06-348">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="efe06-349">Anzeigen der Metriken zur Modellvalidierung</span><span class="sxs-lookup"><span data-stu-id="efe06-349">Displaying the metrics for model validation</span></span>

<span data-ttu-id="efe06-350">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="efe06-350">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="efe06-351">Speichern des trainierten und ausgewerteten Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-351">Save the trained and evaluated model</span></span>

<span data-ttu-id="efe06-352">An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="efe06-352">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="efe06-353">Fügen Sie zum Speichern Ihres trainierten Modells in einer ZIP-Datei den folgenden Code als nächste Zeile in `BuildAndTrainModel` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="efe06-353">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="efe06-354">Speichern des Modells als ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="efe06-354">Save the model as a .zip file</span></span>

<span data-ttu-id="efe06-355">Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="efe06-355">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="efe06-356">Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="efe06-356">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="efe06-357">Speichern Sie das Modells als ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="efe06-357">Saves the model as a .zip file.</span></span>

<span data-ttu-id="efe06-358">Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="efe06-358">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="efe06-359">Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="efe06-359">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="efe06-360">Erstellen Sie `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode, um das Modell als ZIP-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="efe06-360">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="efe06-361">Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-361">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="efe06-362">Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:</span><span class="sxs-lookup"><span data-stu-id="efe06-362">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="efe06-363">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="efe06-363">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="efe06-364">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-364">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="efe06-365">Erstellen Sie die `PredictIssue`-Methode unmittelbar nach der `Evaluate`-Methode (und direkt vor der `SaveModelAsFile`-Methode) mithilfe des folgenden Codes:</span><span class="sxs-lookup"><span data-stu-id="efe06-365">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="efe06-366">Die `PredictIssue`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="efe06-366">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="efe06-367">Erstellen eines einzelnen Issues aus Testdaten</span><span class="sxs-lookup"><span data-stu-id="efe06-367">Creates a single issue of test data.</span></span>
* <span data-ttu-id="efe06-368">Vorhersagen des Bereichs basierend auf Testdaten</span><span class="sxs-lookup"><span data-stu-id="efe06-368">Predicts Area based on test data.</span></span>
* <span data-ttu-id="efe06-369">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="efe06-369">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="efe06-370">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="efe06-370">Displays the predicted results.</span></span>

<span data-ttu-id="efe06-371">Laden Sie zunächst mit dem folgenden Code das Modell, das Sie zuvor gespeichert haben:</span><span class="sxs-lookup"><span data-stu-id="efe06-371">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="efe06-372">Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="efe06-372">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="efe06-373">Mit diesem Modell können Sie nun die GitHub-Bezeichnung des Bereichs einer einzelnen Instanz der Daten des GitHub-Issues vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="efe06-373">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="efe06-374">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="efe06-374">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="efe06-375">Die Eingabedaten sind eine Zeichenfolge, und das Modell enthält die Featurebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="efe06-375">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="efe06-376">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="efe06-376">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="efe06-377">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="efe06-377">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="efe06-378">Fügen Sie für die Vorhersage den folgenden Code zur `PredictIssue`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="efe06-378">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="efe06-379">Verwenden des geladenen Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="efe06-379">Using the loaded model for prediction</span></span>

<span data-ttu-id="efe06-380">Zeigen Sie `Area` an, um das Issue zu kategorisieren und eine entsprechende Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="efe06-380">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="efe06-381">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="efe06-381">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="efe06-382">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="efe06-382">Results</span></span>

<span data-ttu-id="efe06-383">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="efe06-383">Your results should be similar to the following.</span></span> <span data-ttu-id="efe06-384">Während der Pipelineverarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="efe06-384">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="efe06-385">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="efe06-385">You may see warnings, or processing messages.</span></span> <span data-ttu-id="efe06-386">Diese Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="efe06-386">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="efe06-387">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="efe06-387">Congratulations!</span></span> <span data-ttu-id="efe06-388">Sie haben jetzt erfolgreich ein Machine Learning-Modell zur Klassifizierung und Vorhersage der Bereichsbezeichnung für ein GitHub-Issue erstellt.</span><span class="sxs-lookup"><span data-stu-id="efe06-388">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="efe06-389">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="efe06-389">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="efe06-390">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="efe06-390">Next steps</span></span>

<span data-ttu-id="efe06-391">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="efe06-391">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="efe06-392">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="efe06-392">Understand the problem</span></span>
> * <span data-ttu-id="efe06-393">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="efe06-393">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="efe06-394">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-394">Prepare your data</span></span>
> * <span data-ttu-id="efe06-395">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="efe06-395">Transform the data</span></span>
> * <span data-ttu-id="efe06-396">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-396">Train the model</span></span>
> * <span data-ttu-id="efe06-397">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="efe06-397">Evaluate the model</span></span>
> * <span data-ttu-id="efe06-398">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="efe06-398">Predict with the trained model</span></span>
> * <span data-ttu-id="efe06-399">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="efe06-399">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="efe06-400">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="efe06-400">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="efe06-401">Vorhersage des Taxifahrtpreises</span><span class="sxs-lookup"><span data-stu-id="efe06-401">Taxi Fare Predictor</span></span>](taxi-fare.md)
