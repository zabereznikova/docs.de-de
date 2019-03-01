---
title: Verwenden von ML.NET in einem Szenario zur Multiklassenklassifizierung von GitHub-Issues
description: Erfahren Sie hier, wie Sie mit ML.NET in einem Szenario zur Multiklassenklassifizierung GitHub-Issues klassifizieren, um sie einem bestimmten Bereich zuzuweisen.
ms.date: 02/20/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: fdb6621078854d80f0af484ae1b92526f0f9cbb8
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584290"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="f204a-103">Tutorial: Verwenden von ML.NET zur Klassifizierung von GitHub-Issues in einem Szenario mit Multiklassenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="f204a-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="f204a-104">In diesem Beispieltutorial wird veranschaulicht, wie Sie ML.NET zum Erstellen eines Klassifizierers für GitHub-Issues über eine .NET Core-Konsolenanwendung mithilfe von C# in Visual Studio 2017 verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f204a-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="f204a-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f204a-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f204a-106">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="f204a-106">Understand the problem</span></span>
> * <span data-ttu-id="f204a-107">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="f204a-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="f204a-108">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-108">Prepare your data</span></span>
> * <span data-ttu-id="f204a-109">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-109">Transform the data</span></span>
> * <span data-ttu-id="f204a-110">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-110">Train the model</span></span>
> * <span data-ttu-id="f204a-111">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-111">Evaluate the model</span></span>
> * <span data-ttu-id="f204a-112">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="f204a-112">Predict with the trained model</span></span>
> * <span data-ttu-id="f204a-113">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="f204a-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="f204a-114">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f204a-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f204a-115">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f204a-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="f204a-116">Beispielübersicht für ein GitHub-Issue</span><span class="sxs-lookup"><span data-stu-id="f204a-116">GitHub issue sample overview</span></span>

<span data-ttu-id="f204a-117">Das Beispiel ist eine Konsolen-App, die ML.NET zum Trainieren eines Modells verwendet, das für ein GitHub-Issue die Bezeichnung „Area“ (Bereich) klassifiziert und vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="f204a-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="f204a-118">Sie wertet das Modell auch mit einem zweiten Dataset für die Qualitätsanalyse aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="f204a-119">Die Datasets des Issues stammen aus dem GitHub-Repository „dotnet/coreFX“.</span><span class="sxs-lookup"><span data-stu-id="f204a-119">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="f204a-120">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="f204a-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f204a-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="f204a-121">Prerequisites</span></span>

* <span data-ttu-id="f204a-122">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="f204a-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="f204a-123">Die [durch Tabstopp getrennte Datei mit Github-Issues (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span><span class="sxs-lookup"><span data-stu-id="f204a-123">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="f204a-124">Die [durch Tabstopp getrennte Testdatei für Github-Issues (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span><span class="sxs-lookup"><span data-stu-id="f204a-124">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="f204a-125">Machine Learning-Workflow</span><span class="sxs-lookup"><span data-stu-id="f204a-125">Machine learning workflow</span></span>

<span data-ttu-id="f204a-126">Dieses Tutorial folgt einem Machine Learning-Workflow, der den geordneten Ablauf des Prozesses ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f204a-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="f204a-127">Die Workflowphasen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f204a-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="f204a-128">**Verstehen des Problems**</span><span class="sxs-lookup"><span data-stu-id="f204a-128">**Understand the problem**</span></span>
2. <span data-ttu-id="f204a-129">**Vorbereiten Ihrer Daten**</span><span class="sxs-lookup"><span data-stu-id="f204a-129">**Prepare your data**</span></span>
   * <span data-ttu-id="f204a-130">**Laden der Daten**</span><span class="sxs-lookup"><span data-stu-id="f204a-130">**Load the data**</span></span>
   * <span data-ttu-id="f204a-131">**Extrahieren von Funktionen (Transformieren von Daten)**</span><span class="sxs-lookup"><span data-stu-id="f204a-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="f204a-132">**Erstellen und trainieren**</span><span class="sxs-lookup"><span data-stu-id="f204a-132">**Build and train**</span></span> 
   * <span data-ttu-id="f204a-133">**Trainieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="f204a-133">**Train the model**</span></span>
   * <span data-ttu-id="f204a-134">**Evaluieren des Modells**</span><span class="sxs-lookup"><span data-stu-id="f204a-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="f204a-135">**Bereitstellen des Modells**</span><span class="sxs-lookup"><span data-stu-id="f204a-135">**Deploy Model**</span></span>
   * <span data-ttu-id="f204a-136">**Vorhersagen treffen mit dem Modell**</span><span class="sxs-lookup"><span data-stu-id="f204a-136">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="f204a-137">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="f204a-137">Understand the problem</span></span>

<span data-ttu-id="f204a-138">Sie müssen das Problem zuerst verstehen, damit Sie es in Teile aufschlüsseln können, die das Erstellen und Trainieren des Modells erleichtern.</span><span class="sxs-lookup"><span data-stu-id="f204a-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="f204a-139">Durch Aufschlüsseln des Problems können Sie die Ergebnisse vorhersagen und auswerten.</span><span class="sxs-lookup"><span data-stu-id="f204a-139">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="f204a-140">In diesem Tutorial wird behandelt, wie Sie erkennen können, zu welchem Bereich ein eingehendes GitHub-Issue gehört, um es anschließend für die Priorisierung und Planung korrekt zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="f204a-140">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="f204a-141">Sie können das Problem in die folgenden Einzelteile aufschlüsseln:</span><span class="sxs-lookup"><span data-stu-id="f204a-141">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="f204a-142">Titeltext des Issues</span><span class="sxs-lookup"><span data-stu-id="f204a-142">the issue title text</span></span>
* <span data-ttu-id="f204a-143">Beschreibungstext des Issues</span><span class="sxs-lookup"><span data-stu-id="f204a-143">the issue description text</span></span>
* <span data-ttu-id="f204a-144">Wert für den Bereich der Modelltrainingsdaten</span><span class="sxs-lookup"><span data-stu-id="f204a-144">an area value for the model training data</span></span>
* <span data-ttu-id="f204a-145">vorhergesagter Wert für den Bereich zur Auswertung und anschließenden praktischen Verwendung</span><span class="sxs-lookup"><span data-stu-id="f204a-145">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="f204a-146">Anschließend müssen Sie den Bereich **bestimmen**. Dadurch wird die Auswahl der Machine Learning-Aufgabe erleichtert.</span><span class="sxs-lookup"><span data-stu-id="f204a-146">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="f204a-147">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="f204a-147">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="f204a-148">Von diesem Problem kennen Sie die folgenden Fakten:</span><span class="sxs-lookup"><span data-stu-id="f204a-148">With this problem, you know the following facts:</span></span>

<span data-ttu-id="f204a-149">Trainingsdaten:</span><span class="sxs-lookup"><span data-stu-id="f204a-149">Training data:</span></span>

<span data-ttu-id="f204a-150">GitHub-Issues können, wie in den folgenden Beispielen veranschaulicht wird, in verschiedenen Bereichen (**Area**) bezeichnet werden:</span><span class="sxs-lookup"><span data-stu-id="f204a-150">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="f204a-151">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="f204a-151">area-System.Numerics</span></span>
* <span data-ttu-id="f204a-152">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="f204a-152">area-System.Xml</span></span>
* <span data-ttu-id="f204a-153">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="f204a-153">area-Infrastructure</span></span>
* <span data-ttu-id="f204a-154">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="f204a-154">area-System.Linq</span></span>
* <span data-ttu-id="f204a-155">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="f204a-155">area-System.IO</span></span>

<span data-ttu-id="f204a-156">Sagen Sie den **Bereich** eines neuen GitHub-Issues wie in den folgenden Beispielen veranschaulicht vorher:</span><span class="sxs-lookup"><span data-stu-id="f204a-156">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="f204a-157">Contract.Assert im Vergleich zu Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="f204a-157">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="f204a-158">Festlegen von Feldern in System.Xml als schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f204a-158">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="f204a-159">Der Machine Learning-Algorithmus für die Klassifizierung ist für dieses Szenario am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="f204a-159">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="f204a-160">Informationen zum Lernalgorithmus für die Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f204a-160">About the classification learning algorithm</span></span>

<span data-ttu-id="f204a-161">Die Klassifizierung ist ein Machine Learning-Algorithmus, der Daten zum **Bestimmen** von Kategorie, Typ oder Klasse eines Elements oder einer Datenzeile verwendet.</span><span class="sxs-lookup"><span data-stu-id="f204a-161">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="f204a-162">Beispielsweise können Sie mit der Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="f204a-162">For example, you can use classification to:</span></span>

* <span data-ttu-id="f204a-163">Einen Standpunkt als positiv oder negativ identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-163">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="f204a-164">E-Mails als Spam, Junk oder gut klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-164">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="f204a-165">Bestimmen, ob die Gewebeprobe eines Patienten Krebszellen enthält.</span><span class="sxs-lookup"><span data-stu-id="f204a-165">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="f204a-166">Kunden nach ihrer Neigung kategorisieren, auf eine Werbekampagne zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-166">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="f204a-167">Die Anwendungsfälle des Lernalgorithmus für die Klassifizierung weisen meist einen der folgenden Typen auf:</span><span class="sxs-lookup"><span data-stu-id="f204a-167">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="f204a-168">Binär: entweder A oder B.</span><span class="sxs-lookup"><span data-stu-id="f204a-168">Binary: either A or B.</span></span>
* <span data-ttu-id="f204a-169">Multiklasse: mehrere Kategorien, die mit einem einzelnen Modell vorhergesagt werden können.</span><span class="sxs-lookup"><span data-stu-id="f204a-169">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="f204a-170">Verwenden Sie für diese Art von Problemen einen Lernalgorithmus für die Klassifizierung, da es wahrscheinlicher ist, dass Ihre Vorhersage einer Problemkategorie einer von vielen Kategorien (Multiklasse) als einer von zwei (Binär) entspricht.</span><span class="sxs-lookup"><span data-stu-id="f204a-170">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f204a-171">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="f204a-171">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="f204a-172">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="f204a-172">Create a project</span></span>

1. <span data-ttu-id="f204a-173">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f204a-173">Open Visual Studio 2017.</span></span> <span data-ttu-id="f204a-174">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-174">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="f204a-175">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-175">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="f204a-176">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="f204a-176">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f204a-177">Geben Sie „GitHubIssueClassification“ im Textfeld **Name** ein, und wählen Sie die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-177">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="f204a-178">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="f204a-178">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="f204a-179">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-179">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f204a-180">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f204a-180">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="f204a-181">Erstellen Sie ein Verzeichnis mit dem Namen *Models* in Ihrem Projekt, um Ihr Modell zu speichern:</span><span class="sxs-lookup"><span data-stu-id="f204a-181">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="f204a-182">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-182">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="f204a-183">Geben Sie „Models“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f204a-183">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="f204a-184">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="f204a-184">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f204a-185">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-185">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f204a-186">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte „Durchsuchen“ aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste sowie anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-186">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f204a-187">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="f204a-187">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="f204a-188">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-188">Prepare your data</span></span>

1. <span data-ttu-id="f204a-189">Laden Sie die Datasets [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) und [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) herunter, und speichern Sie sie im zuvor erstellten Ordner *Daten*.</span><span class="sxs-lookup"><span data-stu-id="f204a-189">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="f204a-190">Das erste Dataset trainiert das Machine Learning-Modell, und das zweite kann verwendet werden, um zu evaluieren, wie genau das Modell ist.</span><span class="sxs-lookup"><span data-stu-id="f204a-190">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="f204a-191">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.tsv-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-191">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="f204a-192">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="f204a-192">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="f204a-193">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="f204a-193">Create classes and define paths</span></span>

<span data-ttu-id="f204a-194">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-194">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="f204a-195">Erstellen Sie drei globale Felder, die die Pfade zu den zuletzt heruntergeladenen Dateien sowie globale Variablen für `MLContext`, `DataView`, `PredictionEngine` und `TextLoader` enthalten:</span><span class="sxs-lookup"><span data-stu-id="f204a-195">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="f204a-196">`_trainDataPath` enthält den Pfad zu dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f204a-196">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="f204a-197">`_testDataPath` enthält den Pfad zu dem Dataset, das zum Evaluieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f204a-197">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="f204a-198">`_modelPath` enthält den Pfad zu dem Speicherort, in dem das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f204a-198">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="f204a-199">`_mlContext` ist die <xref:Microsoft.ML.MLContext>-Klasse, die den Verarbeitungskontext enthält.</span><span class="sxs-lookup"><span data-stu-id="f204a-199">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="f204a-200">`_trainingDataView` ist die zum Verarbeiten des Trainingsdatasets verwendete <xref:Microsoft.Data.DataView.IDataView>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f204a-200">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="f204a-201">`_predEngine` ist die für einzelne Vorhersagen verwendete <xref:Microsoft.ML.PredictionEngine%602>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f204a-201">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="f204a-202">`_reader` ist der zum Laden und Transformieren der Datasets verwendete <xref:Microsoft.ML.Data.TextLoader>.</span><span class="sxs-lookup"><span data-stu-id="f204a-202">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="f204a-203">Fügen Sie den folgenden Code der Zeile direkt über der `Main`-Methode hinzu, um diese Pfade und die anderen Variablen anzugeben:</span><span class="sxs-lookup"><span data-stu-id="f204a-203">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="f204a-204">Erstellen Sie einige Klassen für Ihre Eingabedaten und Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="f204a-204">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="f204a-205">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-205">Add a new class to your project:</span></span>

1. <span data-ttu-id="f204a-206">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-206">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="f204a-207">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *GitHubIssueData.cs*.</span><span class="sxs-lookup"><span data-stu-id="f204a-207">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="f204a-208">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f204a-208">Then, select the **Add** button.</span></span>

    <span data-ttu-id="f204a-209">Die Datei *GitHubIssueData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f204a-209">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="f204a-210">Fügen Sie am Anfang der Datei *GitHubIssueData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-210">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="f204a-211">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *GitHubIssueData.cs* den folgenden Code mit den beiden Klassen `GitHubIssue` und `IssuePrediction` hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-211">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="f204a-212">`GitHubIssue` ist die Klasse des Eingabedatasets mit den folgenden <xref:System.String>-Feldern:</span><span class="sxs-lookup"><span data-stu-id="f204a-212">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="f204a-213">`ID` enthält einen Wert für die ID des GitHub-Issues.</span><span class="sxs-lookup"><span data-stu-id="f204a-213">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="f204a-214">`Area` enthält einen Wert für die `Area`-Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="f204a-214">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="f204a-215">`Title` enthält den Titel des GitHub-Issues.</span><span class="sxs-lookup"><span data-stu-id="f204a-215">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="f204a-216">`Description` enthält die Beschreibung des GitHub-Issues.</span><span class="sxs-lookup"><span data-stu-id="f204a-216">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="f204a-217">Die `IssuePrediction`-Klasse wird für die Vorhersage verwendet, nachdem das Modell trainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f204a-217">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="f204a-218">Sie verfügt über ein einzelnes `string`- (`Area`) und ein `PredictedLabel` `ColumnName`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="f204a-218">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="f204a-219">Das `Label` dient zum Erstellen und Trainieren des Modells, und es wird auch mit einem zweiten Dataset verwendet, um das Modell zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-219">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="f204a-220">Das `PredictedLabel` wird während der Vorhersage und Evaluierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f204a-220">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="f204a-221">Für die Evaluierung werden eine Eingabe mit Trainingsdaten, die vorhergesagten Werte und das Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="f204a-221">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="f204a-222">Beim Erstellen eines Modells mit ML.NET erstellen Sie zunächst eine <xref:Microsoft.ML.MLContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f204a-222">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="f204a-223">`MLContext` ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="f204a-223">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="f204a-224">Die Umgebung bietet einen Kontext für Ihren ML-Job, der für die Verfolgung und Protokollierung von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f204a-224">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="f204a-225">Initialisieren von Variablen in Main</span><span class="sxs-lookup"><span data-stu-id="f204a-225">Initialize variables in Main</span></span>

<span data-ttu-id="f204a-226">Initialisieren Sie die globale Variable `_mlContext` mit einer neuen Instanz von `MLContext` mit einem zufälligen Ausgangswert (`seed: 0`), um in mehreren Trainings wiederholbare/deterministische Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f204a-226">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="f204a-227">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` mit dem folgenden Code in der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="f204a-227">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="f204a-228">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-228">Load the data</span></span>

<span data-ttu-id="f204a-229">Initialisieren Sie anschließend die globale <xref:Microsoft.Data.DataView.IDataView>-Variable `_trainingDataView`, und laden Sie die Daten mit dem `_trainDataPath`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="f204a-229">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="f204a-230">Als Ein- und Ausgabe von [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer) ist ein `DataView` der grundlegende Datenpipelinetyp, vergleichbar mit `IEnumerable` für `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="f204a-230">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="f204a-231">In ML.NET ähneln die Daten einer `SQL view`.</span><span class="sxs-lookup"><span data-stu-id="f204a-231">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="f204a-232">Sie werden verzögert ausgewertet, sind schematisiert und heterogen.</span><span class="sxs-lookup"><span data-stu-id="f204a-232">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="f204a-233">Das Objekt ist der erste Teil der Pipeline und lädt die Daten.</span><span class="sxs-lookup"><span data-stu-id="f204a-233">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="f204a-234">In diesem Tutorial wird ein Dataset mit dem Titel und der Beschreibung des Issues und der entsprechenden GitHub-Bezeichnung des Bereichs geladen.</span><span class="sxs-lookup"><span data-stu-id="f204a-234">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="f204a-235">Mit `DataView` wird das Modell erstellt und trainiert.</span><span class="sxs-lookup"><span data-stu-id="f204a-235">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="f204a-236">Da der zuvor von Ihnen erstellte `GitHubIssue`-Datenmodelltyp dem Schema des Datasets entspricht, können Sie das Initialisieren, Zuordnen und Laden des Datasets in einer Codezeile zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="f204a-236">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="f204a-237">Der erste Teil der Zeile (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) erstellt eine <xref:Microsoft.ML.Data.TextLoader>-Klasse, indem Rückschlüsse vom `GitHubIssue`-Datenmodelltyp auf das Schema des Datasets gezogen werden und der Header des Datasets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f204a-237">The first part of the line (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="f204a-238">Das Datenschema wurde bereits beim Erstellen der `GitHubIssue`-Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="f204a-238">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="f204a-239">Für Ihr Schema gilt:</span><span class="sxs-lookup"><span data-stu-id="f204a-239">For your schema:</span></span>

* <span data-ttu-id="f204a-240">Die erste Spalte: `ID` (ID des GitHub-Issues)</span><span class="sxs-lookup"><span data-stu-id="f204a-240">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="f204a-241">Die zweite Spalte: `Area` (Vorhersage für das Training)</span><span class="sxs-lookup"><span data-stu-id="f204a-241">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="f204a-242">Die dritte Spalte `Title` (Titel des GitHub-Issues) ist das erste [Feature](../resources/glossary.md##feature) zur Vorhersage von `Area`.</span><span class="sxs-lookup"><span data-stu-id="f204a-242">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="f204a-243">Die vierte Spalte `Description` ist das zweite Feature für die Vorhersage von `Area`.</span><span class="sxs-lookup"><span data-stu-id="f204a-243">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="f204a-244">Der zweite Teil der Zeile (`.Read(_trainDataPath)`) verwendet die <xref:Microsoft.ML.Data.TextLoader.Read%2A>-Methode, um die Trainingstextdatei mithilfe von `_trainDataPath` in die globale `IDataView`-Variable `_trainingDataView` zu laden.</span><span class="sxs-lookup"><span data-stu-id="f204a-244">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="f204a-245">Fügen Sie nach der Initialisierung von `mlContext` den folgenden Code hinzu, um die globale Variable `_trainingDataView` zur Verwendung für die Pipeline zu initialisieren und zu laden:</span><span class="sxs-lookup"><span data-stu-id="f204a-245">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="f204a-246">Fügen Sie den folgenden Text als nächste Codezeile in die `Main`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="f204a-246">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="f204a-247">Die `ProcessData`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f204a-247">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="f204a-248">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="f204a-248">Extracts and transforms the data.</span></span>
* <span data-ttu-id="f204a-249">Zurückgeben der Verarbeitungspipeline</span><span class="sxs-lookup"><span data-stu-id="f204a-249">Returns the processing pipeline.</span></span>

<span data-ttu-id="f204a-250">Erstellen Sie die `ProcessData`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="f204a-250">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="f204a-251">Extrahieren von Features und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-251">Extract Features and transform the data</span></span>

<span data-ttu-id="f204a-252">Vorverarbeitung und Bereinigung von Daten sind wichtige Aufgaben, die durchgeführt werden, bevor ein Dataset effektiv für Machine Learning verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f204a-252">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="f204a-253">Rohdaten sind häufig verunreinigt und unzuverlässig, und es können darin Werte fehlen.</span><span class="sxs-lookup"><span data-stu-id="f204a-253">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="f204a-254">Die Verwendung von Daten ohne diese Modellierungsaufgaben kann irreführende Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="f204a-254">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="f204a-255">Mit den Transformationspipelines von ML.NET können Sie benutzerdefinierte `transforms`-Klassen erstellen, die vor dem Trainieren oder Testen auf Ihre Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f204a-255">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="f204a-256">Die Transformationen dienen in erster Linie der [Datenfeaturebereitstellung](../resources/glossary.md#feature-engineering).</span><span class="sxs-lookup"><span data-stu-id="f204a-256">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="f204a-257">Machine Learning-Algorithmen verstehen die mit [Features ausgestatteten](../resources/glossary.md#feature) Daten, sodass der nächste Schritt darin besteht, unsere Textdaten in ein Format zu transformieren, das unsere ML-Algorithmen erkennen.</span><span class="sxs-lookup"><span data-stu-id="f204a-257">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="f204a-258">Dieses Format ist ein [numerischer Vektor](../resources/glossary.md#numerical-feature-vector).</span><span class="sxs-lookup"><span data-stu-id="f204a-258">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="f204a-259">In den nächsten Schritten werden die Spalten mit den zuvor in der `GitHubIssue`-Klasse definierten Namen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f204a-259">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="f204a-260">Wenn das Modell trainiert und ausgewertet wurde, gelten die Werte in der Spalte **Label** standardmäßig als richtige Werte, die vorhergesagt werden.</span><span class="sxs-lookup"><span data-stu-id="f204a-260">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="f204a-261">Da die GitHub-Bezeichnung des Bereichs für ein `GitHubIssue` vorhergesagt werden soll, kopieren Sie die Spalte `Area` in die Spalte **Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="f204a-261">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="f204a-262">Verwenden Sie hierfür `MLContext.Transforms.Conversion.MapValueToKey` (einen Wrapper für die Transformationsklasse <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A>).</span><span class="sxs-lookup"><span data-stu-id="f204a-262">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="f204a-263">`MapValueToKey` gibt <xref:Microsoft.ML.Data.EstimatorChain%601> zurück, das eine Pipeline ist.</span><span class="sxs-lookup"><span data-stu-id="f204a-263">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="f204a-264">Geben Sie den Namen `pipeline` ein, da Sie den Trainer an die `EstimatorChain` anfügen.</span><span class="sxs-lookup"><span data-stu-id="f204a-264">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="f204a-265">Fügen Sie die nächste Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-265">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="f204a-266">Dadurch werden verschiedene numerische Schlüsselwerte den verschiedenen Werten in jeder Spalte zugeordnet und vom Machine Learning-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="f204a-266">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="f204a-267">Rufen Sie als Nächstes `mlContext.Transforms.Text.FeaturizeText` auf, wodurch die Textspalten (`Title` und `Description`) jeweils in einen numerischen Vektor namens `TitleFeaturized` und `DescriptionFeaturized` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="f204a-267">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="f204a-268">Fügen Sie an die Pipeline die Featurebereitstellung für beide Spalten mit dem folgenden Code an:</span><span class="sxs-lookup"><span data-stu-id="f204a-268">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="f204a-269">Die ML.NET-Version 0.10 hat die Reihenfolge der Transformationsparameter geändert.</span><span class="sxs-lookup"><span data-stu-id="f204a-269">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="f204a-270">Erst beim Erstellen des Projekts wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f204a-270">This will not error out until you build.</span></span> <span data-ttu-id="f204a-271">Verwenden Sie für Transformationen die Parameternamen, wie Sie im vorherigen Codeausschnitt dargestellt sind.</span><span class="sxs-lookup"><span data-stu-id="f204a-271">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="f204a-272">Im letzten Schritt der Vorbereitung der Daten werden alle Feature-Spalten mithilfe der Transformationsklasse `Concatenate` in die Spalte **Features** kombiniert.</span><span class="sxs-lookup"><span data-stu-id="f204a-272">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="f204a-273">Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**.</span><span class="sxs-lookup"><span data-stu-id="f204a-273">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="f204a-274">Fügen Sie an die Pipeline diese Transformation mit dem folgenden Code an:</span><span class="sxs-lookup"><span data-stu-id="f204a-274">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="f204a-275">Fügen Sie anschließend wie im folgenden Code veranschaulicht eine <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A>-Methode zum Zwischenspeichern von DataView an. Dadurch erhalten Sie beim mehrmaligen Durchlaufen der Daten mit dem Cache möglicherweise eine bessere Leistung:</span><span class="sxs-lookup"><span data-stu-id="f204a-275">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="f204a-276">Verwenden Sie AppendCacheCheckpoint für kleine/mittlere Datasets, um die Zeit für das Training zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-276">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="f204a-277">Verwenden Sie dies NICHT bei der Verarbeitung sehr großer Datasets (entfernen Sie .AppendCacheCheckpoint()).</span><span class="sxs-lookup"><span data-stu-id="f204a-277">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="f204a-278">Geben Sie die Pipeline am Ende der `ProcessData`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="f204a-278">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="f204a-279">In diesem Schritt wird die Vorverarbeitung/Featurebereitstellung behandelt.</span><span class="sxs-lookup"><span data-stu-id="f204a-279">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="f204a-280">Die Verwendung zusätzlicher in ML.NET verfügbarer Komponenten kann bessere Ergebnisse mit dem Modell ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f204a-280">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="f204a-281">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-281">Build and train the model</span></span>

<span data-ttu-id="f204a-282">Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-282">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="f204a-283">Die `BuildAndTrainModel`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f204a-283">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="f204a-284">Erstellen der Algorithmusklasse für das Training</span><span class="sxs-lookup"><span data-stu-id="f204a-284">Creates the training algorithm class.</span></span>
* <span data-ttu-id="f204a-285">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="f204a-285">Trains the model.</span></span>
* <span data-ttu-id="f204a-286">Vorhersagen des Bereichs basierend auf den Trainingsdaten</span><span class="sxs-lookup"><span data-stu-id="f204a-286">Predicts area based on training data.</span></span>
* <span data-ttu-id="f204a-287">Speichern des Modells in einer `.zip`-Datei</span><span class="sxs-lookup"><span data-stu-id="f204a-287">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="f204a-288">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="f204a-288">Returns the model.</span></span>

<span data-ttu-id="f204a-289">Erstellen Sie die `BuildAndTrainModel`-Methode mit dem folgenden Code direkt nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="f204a-289">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="f204a-290">Beachten Sie, dass der BuildAndTrainModel-Methode zwei Parameter übergeben werden: `IDataView` für das Trainingsdataset (`trainingDataView`) und <xref:Microsoft.ML.Data.EstimatorChain%601> für die in ProcessData erstellte Verarbeitungspipeline (`pipeline`).</span><span class="sxs-lookup"><span data-stu-id="f204a-290">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="f204a-291">Fügen Sie den folgenden Code am Ende der ersten Zeile der `BuildAndTrainModel`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="f204a-291">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="f204a-292">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="f204a-292">Choose a learning algorithm</span></span>

<span data-ttu-id="f204a-293">Rufen Sie zum Hinzufügen des Lernalgorithmus die Wrappermethode `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` auf, die ein <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f204a-293">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="f204a-294">`SdcaMultiClassTrainer` wird an die `pipeline` angefügt und akzeptiert die mit Features ausgestatteten `Title`- und `Description`-Parameter (`Features`) sowie die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="f204a-294">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="f204a-295">Ordnen Sie außerdem die Bezeichnung dem Wert zu, um den ursprünglichen lesbaren Zustand wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f204a-295">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="f204a-296">Führen Sie diese beiden Aktionen mithilfe des folgenden Codes aus:</span><span class="sxs-lookup"><span data-stu-id="f204a-296">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="f204a-297">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-297">Train the model</span></span>

<span data-ttu-id="f204a-298">Sie trainieren das Modell <xref:Microsoft.ML.Data.TransformerChain%601> basierend auf dem Dataset, das geladen und transformiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="f204a-298">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="f204a-299">Sobald die Schätzung definiert ist, trainieren Sie Ihr Modell mit <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> und stellen die bereits geladenen Trainingsdaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f204a-299">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="f204a-300">Diese Methode gibt ein Modell zurück, das für Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f204a-300">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="f204a-301">`trainingPipeline.Fit()` trainiert die Pipeline und gibt einen `Transformer` basierend auf der eingegebenen `DataView` zurück.</span><span class="sxs-lookup"><span data-stu-id="f204a-301">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="f204a-302">Das Experiment wird erst ausgeführt, wenn die `.Fit()`-Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f204a-302">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="f204a-303">Fügen Sie der `BuildAndTrainModel`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-303">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="f204a-304">Das `model` ist ein `transformer`, der auf vielen Datenzeilen arbeitet, doch die Notwendigkeit, Vorhersagen für einzelne Beispiele zu treffen, ist ein sehr gängiges Produktionsszenario.</span><span class="sxs-lookup"><span data-stu-id="f204a-304">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="f204a-305"><xref:Microsoft.ML.PredictionEngine%602> ist ein Wrapper, der von der `CreatePredictionEngine`-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f204a-305">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="f204a-306">Fügen Sie den folgenden Code hinzu, um `PredictionEngine` als nächste Zeile in der `BuildAndTrainModel`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f204a-306">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="f204a-307">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="f204a-307">Predict with the trained model</span></span>

<span data-ttu-id="f204a-308">Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="f204a-308">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="f204a-309">Damit können Sie die `Area`-Bezeichnung einer einzelnen Instanz der Daten des Issues vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="f204a-309">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="f204a-310">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="f204a-310">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="f204a-311">Die Eingabedaten sind eine Zeichenfolge, und das Modell enthält die Featurebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f204a-311">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="f204a-312">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f204a-312">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="f204a-313">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="f204a-313">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="f204a-314">Verwenden des Modells: Vorhersageergebnisse</span><span class="sxs-lookup"><span data-stu-id="f204a-314">Using the model: prediction results</span></span>

<span data-ttu-id="f204a-315">Zeigen Sie `GitHubIssue` und die entsprechende Vorhersage der `Area`-Bezeichnung an, um die Ergebnisse freizugeben und entsprechenden Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f204a-315">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="f204a-316">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="f204a-316">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="f204a-317">Zurückgeben des für die Evaluierung trainierten Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-317">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="f204a-318">Geben Sie das Modell am Ende der `BuildAndTrainModel`-Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="f204a-318">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="f204a-319">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-319">Evaluate the model</span></span>

<span data-ttu-id="f204a-320">Da Sie nun das Modell erstellt und trainiert haben, müssen Sie es zur Qualitätssicherung und Validierung mit einem anderen Dataset evaluieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-320">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="f204a-321">In der `Evaluate`-Methode wird das in `BuildAndTrainModel` erstellte Modell zur Evaluierung übergeben.</span><span class="sxs-lookup"><span data-stu-id="f204a-321">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="f204a-322">Erstellen Sie die `Evaluate`-Methode direkt nach `BuildAndTrainModel` wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f204a-322">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="f204a-323">Die `Evaluate`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f204a-323">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="f204a-324">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="f204a-324">Loads the test dataset.</span></span>
* <span data-ttu-id="f204a-325">Erstellen des Multiklassenauswerters</span><span class="sxs-lookup"><span data-stu-id="f204a-325">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="f204a-326">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="f204a-326">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="f204a-327">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="f204a-327">Displays the metrics.</span></span>

<span data-ttu-id="f204a-328">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `BuildAndTrainModel`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-328">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="f204a-329">Sie können die Initialisierung, Zuordnung und das Laden des Testdatasets wie beim Trainingsdataset in einer Codezeile zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="f204a-329">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="f204a-330">Sie können das Modell unter Verwendung dieses Datasets in Form einer Qualitätsüberprüfung evaluieren.</span><span class="sxs-lookup"><span data-stu-id="f204a-330">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="f204a-331">Fügen Sie der `Evaluate`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-331">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="f204a-332">`MulticlassClassificationContext.Evaluate` ist ein Wrapper für die <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A>-Methode, die die Qualitätsmetriken für das Modell mit dem angegebenen Dataset berechnet.</span><span class="sxs-lookup"><span data-stu-id="f204a-332">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="f204a-333">Das zurückgegebene <xref:Microsoft.ML.Data.MultiClassClassifierMetrics>-Objekt enthält alle von Auswertern der Multiklassenklassifizierung berechneten Metriken.</span><span class="sxs-lookup"><span data-stu-id="f204a-333">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="f204a-334">Um diese Metriken zum Ermitteln der Modellqualität anzuzeigen, müssen Sie sie zunächst abrufen.</span><span class="sxs-lookup"><span data-stu-id="f204a-334">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="f204a-335">Beachten Sie die Verwendung der `Transform`-Methode der globalen Machine Learning-Variable `_trainedModel` (ein Transformator), um die Funktionen einzugeben und die Vorhersagen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f204a-335">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="f204a-336">Fügen Sie der `Evaluate`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-336">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="f204a-337">Für die Multiklassenklassifizierung werden die folgenden Metriken ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="f204a-337">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="f204a-338">Mikrogenauigkeit: Jedes Beispiel/Klasse-Paar trägt zu gleichen Teilen zur Genauigkeitsmetrik bei.</span><span class="sxs-lookup"><span data-stu-id="f204a-338">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="f204a-339">Die Mikrogenauigkeit sollte so nahe wie möglich bei 1 liegen.</span><span class="sxs-lookup"><span data-stu-id="f204a-339">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="f204a-340">Makrogenauigkeit: Jede Klasse trägt zu gleichen Teilen zur Genauigkeitsmetrik bei.</span><span class="sxs-lookup"><span data-stu-id="f204a-340">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="f204a-341">Minderheitsklassen werden gleich wie größere Klassen gewichtet.</span><span class="sxs-lookup"><span data-stu-id="f204a-341">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="f204a-342">Die Makrogenauigkeit sollte so nahe wie möglich bei 1 liegen.</span><span class="sxs-lookup"><span data-stu-id="f204a-342">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="f204a-343">Protokollverlust: Siehe [Protokollverlust](../resources/glossary.md#log-loss).</span><span class="sxs-lookup"><span data-stu-id="f204a-343">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="f204a-344">Der Protokollverlust sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="f204a-344">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="f204a-345">Verringerung des Protokollverlusts: Liegt zwischen [-inf, 100], wobei „100“ perfekte Vorhersagen und „0“ durchschnittliche Vorhersagen bedeutet.</span><span class="sxs-lookup"><span data-stu-id="f204a-345">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="f204a-346">Die Verringerung des Protokollverlusts sollte so nahe wie möglich bei 0 liegen.</span><span class="sxs-lookup"><span data-stu-id="f204a-346">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="f204a-347">Anzeigen der Metriken zur Modellvalidierung</span><span class="sxs-lookup"><span data-stu-id="f204a-347">Displaying the metrics for model validation</span></span>

<span data-ttu-id="f204a-348">Verwenden Sie den folgenden Code, um die Metriken anzuzeigen, die Ergebnisse freizugeben und dann mit ihnen zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="f204a-348">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="f204a-349">Speichern des trainierten und ausgewerteten Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-349">Save the trained and evaluated model</span></span>

<span data-ttu-id="f204a-350">An diesem Punkt haben Sie ein Modell vom Typ <xref:Microsoft.ML.Data.TransformerChain%601>, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f204a-350">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="f204a-351">Fügen Sie zum Speichern Ihres trainierten Modells in einer ZIP-Datei den folgenden Code als nächste Zeile in `BuildAndTrainModel` hinzu, um die `SaveModelAsFile`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="f204a-351">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="f204a-352">Speichern des Modells als ZIP-Datei</span><span class="sxs-lookup"><span data-stu-id="f204a-352">Save the model as a .zip file</span></span>

<span data-ttu-id="f204a-353">Erstellen Sie die `SaveModelAsFile`-Methode mit dem folgenden Code direkt nach der `Evaluate`-Methode:</span><span class="sxs-lookup"><span data-stu-id="f204a-353">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="f204a-354">Die `SaveModelAsFile`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f204a-354">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="f204a-355">Speichern Sie das Modells als ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="f204a-355">Saves the model as a .zip file.</span></span>

<span data-ttu-id="f204a-356">Erstellen Sie anschließend eine Methode zum Speichern des Modells, damit es wiederverwendet und in anderen Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f204a-356">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="f204a-357">Der `ITransformer` enthält eine <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)>-Methode mit dem globalen Feld `_modelPath` und einem <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="f204a-357">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="f204a-358">Erstellen Sie `FileStream` unmittelbar vor dem Aufruf der `SaveTo`-Methode, um das Modell als ZIP-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f204a-358">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="f204a-359">Fügen Sie der `SaveModelAsFile`-Methode folgenden Code als nächste Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-359">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="f204a-360">Sie können auch anzeigen, wo die Datei geschrieben wurde, indem Sie mit dem folgenden Code eine Konsolenmeldung mit dem `_modelPath` schreiben:</span><span class="sxs-lookup"><span data-stu-id="f204a-360">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="f204a-361">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="f204a-361">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="f204a-362">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `Evaluate`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-362">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="f204a-363">Erstellen Sie die `PredictIssue`-Methode unmittelbar nach der `Evaluate`-Methode (und direkt vor der `SaveModelAsFile`-Methode) mithilfe des folgenden Codes:</span><span class="sxs-lookup"><span data-stu-id="f204a-363">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="f204a-364">Die `PredictIssue`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f204a-364">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="f204a-365">Erstellen eines einzelnen Issues aus Testdaten</span><span class="sxs-lookup"><span data-stu-id="f204a-365">Creates a single issue of test data.</span></span>
* <span data-ttu-id="f204a-366">Vorhersagen des Bereichs basierend auf Testdaten</span><span class="sxs-lookup"><span data-stu-id="f204a-366">Predicts Area based on test data.</span></span>
* <span data-ttu-id="f204a-367">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="f204a-367">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="f204a-368">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f204a-368">Displays the predicted results.</span></span>

<span data-ttu-id="f204a-369">Laden Sie zunächst mit dem folgenden Code das Modell, das Sie zuvor gespeichert haben:</span><span class="sxs-lookup"><span data-stu-id="f204a-369">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="f204a-370">Fügen Sie ein GitHub-Issue hinzu, um die Vorhersage des trainierten Modells in der `Predict`-Methode zu testen, indem Sie eine `GitHubIssue`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="f204a-370">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="f204a-371">Mit diesem Modell können Sie nun die GitHub-Bezeichnung des Bereichs einer einzelnen Instanz der Daten des GitHub-Issues vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="f204a-371">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="f204a-372">Verwenden Sie zum Abrufen einer Vorhersage <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> für die Daten.</span><span class="sxs-lookup"><span data-stu-id="f204a-372">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="f204a-373">Die Eingabedaten sind eine Zeichenfolge, und das Modell enthält die Featurebereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f204a-373">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="f204a-374">Die Pipeline ist während Training und Vorhersage synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f204a-374">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="f204a-375">Sie mussten keinen Vorverarbeitungs-/Featurebereitstellungscode speziell für Vorhersagen schreiben, und die gleiche API wird sowohl für Batch- als auch einmalige Vorhersagen eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="f204a-375">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="f204a-376">Fügen Sie für die Vorhersage den folgenden Code zur `PredictIssue`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="f204a-376">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="f204a-377">Verwenden des geladenen Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="f204a-377">Using the loaded model for prediction</span></span>

<span data-ttu-id="f204a-378">Zeigen Sie `Area` an, um das Issue zu kategorisieren und eine entsprechende Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f204a-378">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="f204a-379">Erstellen Sie mit dem folgenden <xref:System.Console.WriteLine?displayProperty=nameWithType>-Code eine Anzeige für die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="f204a-379">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="f204a-380">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="f204a-380">Results</span></span>

<span data-ttu-id="f204a-381">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="f204a-381">Your results should be similar to the following.</span></span> <span data-ttu-id="f204a-382">Während der Pipelineverarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f204a-382">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="f204a-383">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="f204a-383">You may see warnings, or processing messages.</span></span> <span data-ttu-id="f204a-384">Diese Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="f204a-384">These messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="f204a-385">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="f204a-385">Congratulations!</span></span> <span data-ttu-id="f204a-386">Sie haben jetzt erfolgreich ein Machine Learning-Modell zur Klassifizierung und Vorhersage der Bereichsbezeichnung für ein GitHub-Issue erstellt.</span><span class="sxs-lookup"><span data-stu-id="f204a-386">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="f204a-387">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).</span><span class="sxs-lookup"><span data-stu-id="f204a-387">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f204a-388">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f204a-388">Next steps</span></span>

<span data-ttu-id="f204a-389">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f204a-389">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f204a-390">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="f204a-390">Understand the problem</span></span>
> * <span data-ttu-id="f204a-391">Auswählen des entsprechenden Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="f204a-391">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="f204a-392">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-392">Prepare your data</span></span>
> * <span data-ttu-id="f204a-393">Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="f204a-393">Transform the data</span></span>
> * <span data-ttu-id="f204a-394">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-394">Train the model</span></span>
> * <span data-ttu-id="f204a-395">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="f204a-395">Evaluate the model</span></span>
> * <span data-ttu-id="f204a-396">Vorhersagen treffen mit dem trainierten Modell</span><span class="sxs-lookup"><span data-stu-id="f204a-396">Predict with the trained model</span></span>
> * <span data-ttu-id="f204a-397">Bereitstellen eines geladenen Modells und Vorhersagen mit diesem treffen</span><span class="sxs-lookup"><span data-stu-id="f204a-397">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="f204a-398">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="f204a-398">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f204a-399">Vorhersage des Taxifahrtpreises</span><span class="sxs-lookup"><span data-stu-id="f204a-399">Taxi Fare Predictor</span></span>](taxi-fare.md)
