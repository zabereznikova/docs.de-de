---
title: Iris-Clustering mithilfe eines Clusteringlernmoduls – ML.NET
description: Hier erfahren Sie, wie Sie ML.NET in einem Clusteringszenario verwenden.
author: pkulikov
ms.author: johalex
ms.date: 01/11/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: ab888a2cd9469d5ce0131ba2b17f7c134cf2855c
ms.sourcegitcommit: 81bd16c7435a8c9183d2a7e878a2a5eff7d04584
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2019
ms.locfileid: "54249072"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="d8789-103">Tutorial: Iris-Clustering mithilfe eines Clusteringlernmoduls – ML.NET</span><span class="sxs-lookup"><span data-stu-id="d8789-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="d8789-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d8789-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="d8789-105">Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d8789-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="d8789-106">Dieses Tutorial zeigt, wie Sie mit ML.NET ein [Clusteringmodell](../resources/tasks.md#clustering) für das [Iris-Dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set) erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8789-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="d8789-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d8789-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d8789-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="d8789-108">Understand the problem</span></span>
> - <span data-ttu-id="d8789-109">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="d8789-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="d8789-110">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="d8789-110">Prepare the data</span></span>
> - <span data-ttu-id="d8789-111">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="d8789-111">Load and transform the data</span></span>
> - <span data-ttu-id="d8789-112">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="d8789-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="d8789-113">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="d8789-113">Train the model</span></span>
> - <span data-ttu-id="d8789-114">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="d8789-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8789-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="d8789-115">Prerequisites</span></span>

- <span data-ttu-id="d8789-116">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="d8789-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="d8789-117">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="d8789-117">Understand the problem</span></span>

<span data-ttu-id="d8789-118">Bei diesem Problem geht es darum, Iris anhand ihrer Blütenmerkmale in unterschiedliche Gruppen einzuteilen.</span><span class="sxs-lookup"><span data-stu-id="d8789-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="d8789-119">Die entsprechenden Merkmale sind Länge und Breite des Kelchblatts sowie Länge und Breite des Kronblatts.</span><span class="sxs-lookup"><span data-stu-id="d8789-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="d8789-120">Für dieses Tutorial wird angenommen, dass der Typ jeder Blume unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="d8789-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="d8789-121">Sie werden die Struktur eines Datasets basierend auf Merkmalen kennenlernen und vorhersagen können, wie eine Dateninstanz in diese Struktur passt.</span><span class="sxs-lookup"><span data-stu-id="d8789-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="d8789-122">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="d8789-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="d8789-123">Da Sie nicht wissen, zu welcher Gruppe jede Blume gehört, wählen Sie die Aufgabe [Unüberwachtes maschinelles Lernen](../resources/glossary.md#unsupervised-machine-learning) aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="d8789-124">Um ein Dataset so in Gruppen zu unterteilen, dass Elemente in derselben Gruppe einander ähnlicher sind als in anderen Gruppen, verwenden Sie eine [Clustering](../resources/tasks.md#clustering)-Aufgabe für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="d8789-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="d8789-125">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="d8789-125">Create a console application</span></span>

1. <span data-ttu-id="d8789-126">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d8789-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="d8789-127">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="d8789-128">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="d8789-129">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="d8789-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="d8789-130">Geben Sie im Textfeld **Name** „IrisFlowerClustering“ ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-130">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="d8789-131">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="d8789-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="d8789-132">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="d8789-133">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="d8789-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="d8789-134">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="d8789-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="d8789-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d8789-136">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="d8789-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d8789-137">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="d8789-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="d8789-138">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="d8789-138">Prepare the data</span></span>

1. <span data-ttu-id="d8789-139">Laden Sie das Dataset [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) herunter und speichern Sie es im Ordner *Data*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d8789-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="d8789-140">Weitere Informationen zum Iris-Dataset finden Sie im englischen Wikipedia-Artikel [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) und auf der Website [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris), der Quelle des Datasets.</span><span class="sxs-lookup"><span data-stu-id="d8789-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="d8789-141">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *iris.data*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="d8789-142">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="d8789-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="d8789-143">Die Datei *iris.data* enthält fünf Spalten, die Folgendes darstellen:</span><span class="sxs-lookup"><span data-stu-id="d8789-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="d8789-144">Kelchblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="d8789-144">sepal length in centimetres</span></span>
- <span data-ttu-id="d8789-145">Kelchblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="d8789-145">sepal width in centimetres</span></span>
- <span data-ttu-id="d8789-146">Kronblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="d8789-146">petal length in centimetres</span></span>
- <span data-ttu-id="d8789-147">Kronblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="d8789-147">petal width in centimetres</span></span>
- <span data-ttu-id="d8789-148">Iristyp</span><span class="sxs-lookup"><span data-stu-id="d8789-148">type of iris flower</span></span>

<span data-ttu-id="d8789-149">Für das Clusteringbeispiel wird in diesem Tutorial die letzte Spalte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d8789-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="d8789-150">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="d8789-150">Create data classes</span></span>

<span data-ttu-id="d8789-151">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="d8789-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="d8789-152">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d8789-153">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="d8789-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="d8789-154">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="d8789-155">Fügen Sie der neuen Datei die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8789-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="d8789-156">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *IrisData.cs* den folgenden Code hinzu, der die Klassen `IrisData` und `ClusterPrediction` definiert:</span><span class="sxs-lookup"><span data-stu-id="d8789-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="d8789-157">`IrisData` ist die Eingabedatenklasse und verfügt über Definitionen für jedes Merkmal im Dataset.</span><span class="sxs-lookup"><span data-stu-id="d8789-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="d8789-158">Verwenden Sie das Attribut [Column](xref:Microsoft.ML.Data.ColumnAttribute), um die Indizes der Quellspalten in der Datasetdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d8789-158">Use the [Column](xref:Microsoft.ML.Data.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="d8789-159">Die Klasse `ClusterPrediction` repräsentiert die Ausgabe des Clusteringmodells, das auf eine `IrisData`-Instanz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8789-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="d8789-160">Verwenden Sie das Attribut [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute), um die Felder `PredictedClusterId` und `Distances` an die Spalten **PredictedLabel** bzw. **Score** zu binden.</span><span class="sxs-lookup"><span data-stu-id="d8789-160">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="d8789-161">Bei der Clusteringaufgabe haben diese Spalten die folgende Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="d8789-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="d8789-162">Die Spalte **PredictedLabel** enthält die ID des vorhergesagten Clusters.</span><span class="sxs-lookup"><span data-stu-id="d8789-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="d8789-163">Die Spalte **Score** enthält ein Array mit den quadratischen euklidischen Abständen zum Clusterschwerpunkt.</span><span class="sxs-lookup"><span data-stu-id="d8789-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="d8789-164">Die Arraylänge ist gleich der Anzahl von Clustern.</span><span class="sxs-lookup"><span data-stu-id="d8789-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="d8789-165">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="d8789-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="d8789-166">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="d8789-166">Define data and model paths</span></span>

<span data-ttu-id="d8789-167">Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie zwei Felder hinzu, die die Pfade zur Datasetdatei und zur Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="d8789-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="d8789-168">`_dataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d8789-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="d8789-169">`_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d8789-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="d8789-170">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d8789-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="d8789-171">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="d8789-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="d8789-172">ML-Kontext erstellen</span><span class="sxs-lookup"><span data-stu-id="d8789-172">Create ML context</span></span>

<span data-ttu-id="d8789-173">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8789-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="d8789-174">Ersetzen Sie in der `Main`-Methode die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="d8789-174">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="d8789-175">Die Klasse <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> stellt die Umgebung für maschinelles Lernen dar und bietet Mechanismen für die Protokollierung sowie Einstiegspunkte für das Laden von Daten, das Trainieren von Modellen, Vorhersagen und weitere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="d8789-175">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="d8789-176">Dies ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d8789-176">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="d8789-177">Einrichten des Ladens von Daten</span><span class="sxs-lookup"><span data-stu-id="d8789-177">Setup data loading</span></span>

<span data-ttu-id="d8789-178">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um das Verfahren zum Laden von Daten einzurichten:</span><span class="sxs-lookup"><span data-stu-id="d8789-178">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="d8789-179">Beachten Sie, dass die Spaltennamen und Indizes mit dem durch die Klasse `IrisData` definierten Schema übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d8789-179">Note that the column names and indices match the schema defined by the `IrisData` class.</span></span> <span data-ttu-id="d8789-180">Der <xref:Microsoft.ML.Data.DataKind.R4?displayProperty=nameWithType>-Wert gibt den `float`-Typ an.</span><span class="sxs-lookup"><span data-stu-id="d8789-180">The <xref:Microsoft.ML.Data.DataKind.R4?displayProperty=nameWithType> value specifies the `float` type.</span></span>

<span data-ttu-id="d8789-181">Verwenden Sie eine instanziierte Instanz von <xref:Microsoft.ML.Data.TextLoader>, um eine <xref:Microsoft.ML.Data.IDataView>-Instanz zu erstellen, die die Datenquelle für das Trainingsdataset bildet:</span><span class="sxs-lookup"><span data-stu-id="d8789-181">Use instantiated <xref:Microsoft.ML.Data.TextLoader> instance to create an <xref:Microsoft.ML.Data.IDataView> instance, which represents the data source for the training data set:</span></span>

[!code-csharp[Create IDataView](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="d8789-182">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="d8789-182">Create a learning pipeline</span></span>

<span data-ttu-id="d8789-183">Im Rahmen dieses Tutorials umfasst die Pipeline der Clusteraufgabe die zwei folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="d8789-183">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="d8789-184">Verketten geladener Spalten zu einer Spalte **Features**, die von einem Clustertrainer verwendet wird;</span><span class="sxs-lookup"><span data-stu-id="d8789-184">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="d8789-185">Verwenden eines <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer>-Trainers, um das Modell mithilfe des Clusteralgorithmus k-means++ zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="d8789-185">use a <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="d8789-186">Fügen Sie der `Main`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8789-186">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="d8789-187">Der Code gibt an, dass das Dataset in drei Cluster aufgeteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8789-187">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="d8789-188">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="d8789-188">Train the model</span></span>

<span data-ttu-id="d8789-189">Die in den vorangegangenen Abschnitten hinzugefügten Schritte haben die Pipeline für das Training vorbereitet, es wurden jedoch keine ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8789-189">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="d8789-190">Fügen Sie der `Main`-Methode die folgende Zeile hinzu, um das Laden der Daten und das Trainieren des Modells auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d8789-190">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="d8789-191">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="d8789-191">Save the model</span></span>

<span data-ttu-id="d8789-192">An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8789-192">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="d8789-193">Um das Modell in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code der Methode `Main` hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8789-193">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="d8789-194">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="d8789-194">Use the model for predictions</span></span>

<span data-ttu-id="d8789-195">Verwenden Sie für Vorhersagen die <xref:Microsoft.ML.PredictionEngine%602>-Klasse, die Instanzen des Eingabetyps über die Transformationspipeline annimmt und Instanzen des Ausgabetyps erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d8789-195">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="d8789-196">Fügen Sie der `Main`-Methode die folgende Zeile hinzu, um eine Instanz dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d8789-196">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="d8789-197">Erstellen Sie die Klasse `TestIrisData`, um Testdateninstanzen unterzubringen:</span><span class="sxs-lookup"><span data-stu-id="d8789-197">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="d8789-198">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-198">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d8789-199">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="d8789-199">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="d8789-200">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d8789-200">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="d8789-201">Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:</span><span class="sxs-lookup"><span data-stu-id="d8789-201">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="d8789-202">Dieses Tutorial führt eine Irisdateninstanz innerhalb dieser Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="d8789-202">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="d8789-203">Sie können weitere Szenarios zum Testen des Models hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d8789-203">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="d8789-204">Fügen Sie den folgenden Code der `TestIrisData`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="d8789-204">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="d8789-205">Um herauszufinden, zu welchem Cluster das angegebene Element gehört, gehen Sie zurück zur Datei *Program.cs* und fügen Sie den folgenden Code in die Methode `Main` ein:</span><span class="sxs-lookup"><span data-stu-id="d8789-205">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="d8789-206">Führen Sie das Programm aus, um festzustellen, welcher Cluster die angegebene Dateninstanz und die quadratischen Abstände von dieser Instanz zum Clusterschwerpunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="d8789-206">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="d8789-207">Die Ergebnisse sollten den hier dargestellten ähneln:</span><span class="sxs-lookup"><span data-stu-id="d8789-207">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="d8789-208">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="d8789-208">Congratulations!</span></span> <span data-ttu-id="d8789-209">Sie haben erfolgreich ein Machine Learning-Modell für Iris-Clustering erstellt und für Vorhersagen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8789-209">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="d8789-210">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering).</span><span class="sxs-lookup"><span data-stu-id="d8789-210">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8789-211">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d8789-211">Next steps</span></span>

<span data-ttu-id="d8789-212">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="d8789-212">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d8789-213">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="d8789-213">Understand the problem</span></span>
> - <span data-ttu-id="d8789-214">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="d8789-214">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="d8789-215">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="d8789-215">Prepare the data</span></span>
> - <span data-ttu-id="d8789-216">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="d8789-216">Load and transform the data</span></span>
> - <span data-ttu-id="d8789-217">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="d8789-217">Choose a learning algorithm</span></span>
> - <span data-ttu-id="d8789-218">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="d8789-218">Train the model</span></span>
> - <span data-ttu-id="d8789-219">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="d8789-219">Use the model for predictions</span></span>

<span data-ttu-id="d8789-220">In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.</span><span class="sxs-lookup"><span data-stu-id="d8789-220">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d8789-221">dotnet/machinelearning GitHub repository</span><span class="sxs-lookup"><span data-stu-id="d8789-221">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
