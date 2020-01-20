---
title: 'Tutorial: Kategorisieren von Schwertlilien (k-Means-Algorithmus)'
description: Hier erfahren Sie, wie Sie ML.NET in einem Clusteringszenario verwenden.
author: pkulikov
ms.date: 11/15/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: cc3a1ae984289eb01ad8fdee9741f3f9788196c7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716235"
---
# <a name="tutorial-categorize-iris-flowers-using-k-means-clustering-with-mlnet"></a><span data-ttu-id="cbbc8-103">Tutorial: Kategorisieren von Schwertlilien unter Verwendung eines k-Means-Algorithmus mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="cbbc8-103">Tutorial: Categorize iris flowers using k-means clustering with ML.NET</span></span>

<span data-ttu-id="cbbc8-104">Dieses Tutorial zeigt, wie Sie mit ML.NET ein [Clusteringmodell](../resources/tasks.md#clustering) für das [Iris-Dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set) erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-104">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="cbbc8-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cbbc8-106">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-106">Understand the problem</span></span>
> - <span data-ttu-id="cbbc8-107">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="cbbc8-107">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="cbbc8-108">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="cbbc8-108">Prepare the data</span></span>
> - <span data-ttu-id="cbbc8-109">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="cbbc8-109">Load and transform the data</span></span>
> - <span data-ttu-id="cbbc8-110">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="cbbc8-110">Choose a learning algorithm</span></span>
> - <span data-ttu-id="cbbc8-111">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="cbbc8-111">Train the model</span></span>
> - <span data-ttu-id="cbbc8-112">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-112">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cbbc8-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-113">Prerequisites</span></span>

- <span data-ttu-id="cbbc8-114">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-114">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="cbbc8-115">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-115">Understand the problem</span></span>

<span data-ttu-id="cbbc8-116">Bei diesem Problem geht es darum, Iris anhand ihrer Blütenmerkmale in unterschiedliche Gruppen einzuteilen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-116">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="cbbc8-117">Die entsprechenden Merkmale sind Länge und Breite des Kelchblatts sowie Länge und Breite des Kronblatts.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-117">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="cbbc8-118">Für dieses Tutorial wird angenommen, dass der Typ jeder Blume unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-118">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="cbbc8-119">Sie werden die Struktur eines Datasets basierend auf Merkmalen kennenlernen und vorhersagen können, wie eine Dateninstanz in diese Struktur passt.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-119">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="cbbc8-120">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="cbbc8-120">Select the appropriate machine learning task</span></span>

<span data-ttu-id="cbbc8-121">Da Sie nicht wissen, zu welcher Gruppe jede Blume gehört, wählen Sie die Aufgabe [Unüberwachtes maschinelles Lernen](../resources/glossary.md#unsupervised-machine-learning) aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-121">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="cbbc8-122">Um ein Dataset so in Gruppen zu unterteilen, dass Elemente in derselben Gruppe einander ähnlicher sind als in anderen Gruppen, verwenden Sie eine [Clustering](../resources/tasks.md#clustering)-Aufgabe für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-122">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="cbbc8-123">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="cbbc8-123">Create a console application</span></span>

1. <span data-ttu-id="cbbc8-124">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-124">Open Visual Studio.</span></span> <span data-ttu-id="cbbc8-125">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-125">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="cbbc8-126">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-126">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="cbbc8-127">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="cbbc8-127">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="cbbc8-128">Geben Sie im Textfeld **Name** „IrisFlowerClustering“ ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-128">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="cbbc8-129">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-129">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="cbbc8-130">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-130">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="cbbc8-131">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-131">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="cbbc8-132">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-132">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="cbbc8-133">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-133">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="cbbc8-134">Wählen Sie als Paketquelle „nuget.org“ aus. Klicken Sie dann auf die Registerkarte **Durchsuchen**, suchen Sie nach **Microsoft.ML**, und klicken Sie anschließend auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-134">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML** and select the **Install** button.</span></span> <span data-ttu-id="cbbc8-135">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="cbbc8-136">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="cbbc8-136">Prepare the data</span></span>

1. <span data-ttu-id="cbbc8-137">Laden Sie das Dataset [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) herunter und speichern Sie es im Ordner *Data*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-137">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="cbbc8-138">Weitere Informationen zum Iris-Dataset finden Sie im englischen Wikipedia-Artikel [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) und auf der Website [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris), der Quelle des Datasets.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-138">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="cbbc8-139">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *iris.data*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-139">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="cbbc8-140">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-140">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="cbbc8-141">Die Datei *iris.data* enthält fünf Spalten, die Folgendes darstellen:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-141">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="cbbc8-142">Kelchblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="cbbc8-142">sepal length in centimetres</span></span>
- <span data-ttu-id="cbbc8-143">Kelchblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="cbbc8-143">sepal width in centimetres</span></span>
- <span data-ttu-id="cbbc8-144">Kronblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="cbbc8-144">petal length in centimetres</span></span>
- <span data-ttu-id="cbbc8-145">Kronblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="cbbc8-145">petal width in centimetres</span></span>
- <span data-ttu-id="cbbc8-146">Iristyp</span><span class="sxs-lookup"><span data-stu-id="cbbc8-146">type of iris flower</span></span>

<span data-ttu-id="cbbc8-147">Für das Clusteringbeispiel wird in diesem Tutorial die letzte Spalte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-147">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="cbbc8-148">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-148">Create data classes</span></span>

<span data-ttu-id="cbbc8-149">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-149">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="cbbc8-150">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-150">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="cbbc8-151">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="cbbc8-152">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-152">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="cbbc8-153">Fügen Sie der neuen Datei die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-153">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="cbbc8-154">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *IrisData.cs* den folgenden Code hinzu, der die Klassen `IrisData` und `ClusterPrediction` definiert:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-154">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="cbbc8-155">`IrisData` ist die Eingabedatenklasse und verfügt über Definitionen für jedes Merkmal im Dataset.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-155">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="cbbc8-156">Verwenden Sie das Attribut [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute), um die Indizes der Quellspalten in der Datasetdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-156">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="cbbc8-157">Die Klasse `ClusterPrediction` repräsentiert die Ausgabe des Clusteringmodells, das auf eine `IrisData`-Instanz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-157">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="cbbc8-158">Verwenden Sie das Attribut [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute), um die Felder `PredictedClusterId` und `Distances` an die Spalten **PredictedLabel** bzw. **Score** zu binden.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-158">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="cbbc8-159">Bei der Clusteringaufgabe haben diese Spalten die folgende Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-159">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="cbbc8-160">Die Spalte **PredictedLabel** enthält die ID des vorhergesagten Clusters.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-160">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="cbbc8-161">Die Spalte **Score** enthält ein Array mit den quadratischen euklidischen Abständen zum Clusterschwerpunkt.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-161">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="cbbc8-162">Die Arraylänge ist gleich der Anzahl von Clustern.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-162">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="cbbc8-163">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-163">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="cbbc8-164">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="cbbc8-164">Define data and model paths</span></span>

<span data-ttu-id="cbbc8-165">Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie zwei Felder hinzu, die die Pfade zur Datasetdatei und zur Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-165">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="cbbc8-166">`_dataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-166">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="cbbc8-167">`_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-167">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="cbbc8-168">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-168">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="cbbc8-169">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-169">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="cbbc8-170">ML-Kontext erstellen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-170">Create ML context</span></span>

<span data-ttu-id="cbbc8-171">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-171">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="cbbc8-172">Ersetzen Sie in der `Main`-Methode die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-172">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="cbbc8-173">Die Klasse <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> stellt die Umgebung für maschinelles Lernen dar und bietet Mechanismen für die Protokollierung sowie Einstiegspunkte für das Laden von Daten, das Trainieren von Modellen, Vorhersagen und weitere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-173">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="cbbc8-174">Dies ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-174">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="set-up-data-loading"></a><span data-ttu-id="cbbc8-175">Einrichten des Ladens von Daten</span><span class="sxs-lookup"><span data-stu-id="cbbc8-175">Set up data loading</span></span>

<span data-ttu-id="cbbc8-176">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um das Verfahren zum Laden von Daten einzurichten:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-176">Add the following code to the `Main` method to set up the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

<span data-ttu-id="cbbc8-177">Die generische [`MLContext.Data.LoadFromTextFile`-Erweiterungsmethode](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) leitet das Datasetschema aus dem bereitgestellten `IrisData`-Typ ab und gibt <xref:Microsoft.ML.IDataView> zurück, was als Eingabe für Transformatoren verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-177">The generic [`MLContext.Data.LoadFromTextFile` extension method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) infers the data set schema from the provided `IrisData` type and returns <xref:Microsoft.ML.IDataView> which can be used as input for transformers.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="cbbc8-178">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="cbbc8-178">Create a learning pipeline</span></span>

<span data-ttu-id="cbbc8-179">Im Rahmen dieses Tutorials umfasst die Pipeline der Clusteraufgabe die zwei folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-179">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="cbbc8-180">Verketten geladener Spalten zu einer Spalte **Features**, die von einem Clustertrainer verwendet wird;</span><span class="sxs-lookup"><span data-stu-id="cbbc8-180">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="cbbc8-181">Verwenden eines <xref:Microsoft.ML.Trainers.KMeansTrainer>-Trainers, um das Modell mithilfe des Clusteralgorithmus k-means++ zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-181">use a <xref:Microsoft.ML.Trainers.KMeansTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="cbbc8-182">Fügen Sie der `Main`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-182">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="cbbc8-183">Der Code gibt an, dass das Dataset in drei Cluster aufgeteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-183">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="cbbc8-184">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="cbbc8-184">Train the model</span></span>

<span data-ttu-id="cbbc8-185">Die in den vorangegangenen Abschnitten hinzugefügten Schritte haben die Pipeline für das Training vorbereitet, es wurden jedoch keine ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-185">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="cbbc8-186">Fügen Sie der `Main`-Methode die folgende Zeile hinzu, um das Laden der Daten und das Trainieren des Modells auszuführen:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-186">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="cbbc8-187">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="cbbc8-187">Save the model</span></span>

<span data-ttu-id="cbbc8-188">An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-188">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="cbbc8-189">Um das Modell in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code der Methode `Main` hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-189">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="cbbc8-190">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-190">Use the model for predictions</span></span>

<span data-ttu-id="cbbc8-191">Verwenden Sie für Vorhersagen die <xref:Microsoft.ML.PredictionEngine%602>-Klasse, die Instanzen des Eingabetyps über die Transformationspipeline annimmt und Instanzen des Ausgabetyps erzeugt.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-191">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="cbbc8-192">Fügen Sie der `Main`-Methode die folgende Zeile hinzu, um eine Instanz dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-192">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="cbbc8-193">Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-193">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="cbbc8-194">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-194">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="cbbc8-195">Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-195">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="cbbc8-196">Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-196">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="cbbc8-197">Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-197">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="cbbc8-198">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-198">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="cbbc8-199">Erstellen Sie die Klasse `TestIrisData`, um Testdateninstanzen unterzubringen:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-199">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="cbbc8-200">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-200">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="cbbc8-201">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-201">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="cbbc8-202">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-202">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="cbbc8-203">Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-203">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="cbbc8-204">Dieses Tutorial führt eine Irisdateninstanz innerhalb dieser Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-204">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="cbbc8-205">Sie können weitere Szenarios zum Testen des Models hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-205">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="cbbc8-206">Fügen Sie den folgenden Code der `TestIrisData`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-206">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="cbbc8-207">Um herauszufinden, zu welchem Cluster das angegebene Element gehört, gehen Sie zurück zur Datei *Program.cs* und fügen Sie den folgenden Code in die Methode `Main` ein:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-207">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="cbbc8-208">Führen Sie das Programm aus, um festzustellen, welcher Cluster die angegebene Dateninstanz und die quadratischen Abstände von dieser Instanz zum Clusterschwerpunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-208">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="cbbc8-209">Die Ergebnisse sollten den hier dargestellten ähneln:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-209">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="cbbc8-210">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="cbbc8-210">Congratulations!</span></span> <span data-ttu-id="cbbc8-211">Sie haben erfolgreich ein Machine Learning-Modell für Iris-Clustering erstellt und für Vorhersagen verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-211">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="cbbc8-212">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering).</span><span class="sxs-lookup"><span data-stu-id="cbbc8-212">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cbbc8-213">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cbbc8-213">Next steps</span></span>

<span data-ttu-id="cbbc8-214">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="cbbc8-214">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="cbbc8-215">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-215">Understand the problem</span></span>
> - <span data-ttu-id="cbbc8-216">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="cbbc8-216">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="cbbc8-217">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="cbbc8-217">Prepare the data</span></span>
> - <span data-ttu-id="cbbc8-218">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="cbbc8-218">Load and transform the data</span></span>
> - <span data-ttu-id="cbbc8-219">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="cbbc8-219">Choose a learning algorithm</span></span>
> - <span data-ttu-id="cbbc8-220">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="cbbc8-220">Train the model</span></span>
> - <span data-ttu-id="cbbc8-221">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="cbbc8-221">Use the model for predictions</span></span>

<span data-ttu-id="cbbc8-222">In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.</span><span class="sxs-lookup"><span data-stu-id="cbbc8-222">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="cbbc8-223">dotnet/machinelearning GitHub repository</span><span class="sxs-lookup"><span data-stu-id="cbbc8-223">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
