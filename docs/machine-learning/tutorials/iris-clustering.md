---
title: 'Tutorial: Kategorisieren von Schwertlilien (k-Means-Algorithmus)'
description: Hier erfahren Sie, wie Sie ML.NET in einem Clusteringszenario verwenden.
author: pkulikov
ms.date: 05/16/2019
ms.topic: tutorial
ms.custom: mvc, seodec18, title-hack-0516
ms.openlocfilehash: e2aaeb8abc6981b420329f194aa7b82c90cae00a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929101"
---
# <a name="tutorial-categorize-iris-flowers-using-k-means-clustering-with-mlnet"></a><span data-ttu-id="3efe4-103">Tutorial: Kategorisieren von Schwertlilien unter Verwendung eines k-Means-Algorithmus mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="3efe4-103">Tutorial: Categorize iris flowers using k-means clustering with ML.NET</span></span>

<span data-ttu-id="3efe4-104">Dieses Tutorial zeigt, wie Sie mit ML.NET ein [Clusteringmodell](../resources/tasks.md#clustering) für das [Iris-Dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set) erstellen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-104">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="3efe4-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="3efe4-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3efe4-106">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="3efe4-106">Understand the problem</span></span>
> - <span data-ttu-id="3efe4-107">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="3efe4-107">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="3efe4-108">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="3efe4-108">Prepare the data</span></span>
> - <span data-ttu-id="3efe4-109">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="3efe4-109">Load and transform the data</span></span>
> - <span data-ttu-id="3efe4-110">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="3efe4-110">Choose a learning algorithm</span></span>
> - <span data-ttu-id="3efe4-111">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="3efe4-111">Train the model</span></span>
> - <span data-ttu-id="3efe4-112">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="3efe4-112">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3efe4-113">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="3efe4-113">Prerequisites</span></span>

- <span data-ttu-id="3efe4-114">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="3efe4-114">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="3efe4-115">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="3efe4-115">Understand the problem</span></span>

<span data-ttu-id="3efe4-116">Bei diesem Problem geht es darum, Iris anhand ihrer Blütenmerkmale in unterschiedliche Gruppen einzuteilen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-116">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="3efe4-117">Die entsprechenden Merkmale sind Länge und Breite des Kelchblatts sowie Länge und Breite des Kronblatts.</span><span class="sxs-lookup"><span data-stu-id="3efe4-117">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="3efe4-118">Für dieses Tutorial wird angenommen, dass der Typ jeder Blume unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="3efe4-118">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="3efe4-119">Sie werden die Struktur eines Datasets basierend auf Merkmalen kennenlernen und vorhersagen können, wie eine Dateninstanz in diese Struktur passt.</span><span class="sxs-lookup"><span data-stu-id="3efe4-119">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="3efe4-120">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="3efe4-120">Select the appropriate machine learning task</span></span>

<span data-ttu-id="3efe4-121">Da Sie nicht wissen, zu welcher Gruppe jede Blume gehört, wählen Sie die Aufgabe [Unüberwachtes maschinelles Lernen](../resources/glossary.md#unsupervised-machine-learning) aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-121">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="3efe4-122">Um ein Dataset so in Gruppen zu unterteilen, dass Elemente in derselben Gruppe einander ähnlicher sind als in anderen Gruppen, verwenden Sie eine [Clustering](../resources/tasks.md#clustering)-Aufgabe für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-122">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="3efe4-123">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="3efe4-123">Create a console application</span></span>

1. <span data-ttu-id="3efe4-124">Öffnen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3efe4-124">Open Visual Studio.</span></span> <span data-ttu-id="3efe4-125">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-125">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="3efe4-126">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-126">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="3efe4-127">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="3efe4-127">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="3efe4-128">Geben Sie im Textfeld **Name** „IrisFlowerClustering“ ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-128">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="3efe4-129">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="3efe4-129">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="3efe4-130">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-130">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="3efe4-131">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="3efe4-131">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="3efe4-132">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="3efe4-132">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="3efe4-133">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-133">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3efe4-134">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das **v1.0.0**-Paket in der Liste und anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-134">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="3efe4-135">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="3efe4-136">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="3efe4-136">Prepare the data</span></span>

1. <span data-ttu-id="3efe4-137">Laden Sie das Dataset [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) herunter und speichern Sie es im Ordner *Data*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3efe4-137">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="3efe4-138">Weitere Informationen zum Iris-Dataset finden Sie im englischen Wikipedia-Artikel [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) und auf der Website [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris), der Quelle des Datasets.</span><span class="sxs-lookup"><span data-stu-id="3efe4-138">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="3efe4-139">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *iris.data*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-139">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="3efe4-140">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="3efe4-140">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="3efe4-141">Die Datei *iris.data* enthält fünf Spalten, die Folgendes darstellen:</span><span class="sxs-lookup"><span data-stu-id="3efe4-141">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="3efe4-142">Kelchblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="3efe4-142">sepal length in centimetres</span></span>
- <span data-ttu-id="3efe4-143">Kelchblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="3efe4-143">sepal width in centimetres</span></span>
- <span data-ttu-id="3efe4-144">Kronblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="3efe4-144">petal length in centimetres</span></span>
- <span data-ttu-id="3efe4-145">Kronblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="3efe4-145">petal width in centimetres</span></span>
- <span data-ttu-id="3efe4-146">Iristyp</span><span class="sxs-lookup"><span data-stu-id="3efe4-146">type of iris flower</span></span>

<span data-ttu-id="3efe4-147">Für das Clusteringbeispiel wird in diesem Tutorial die letzte Spalte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3efe4-147">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="3efe4-148">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="3efe4-148">Create data classes</span></span>

<span data-ttu-id="3efe4-149">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="3efe4-149">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="3efe4-150">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-150">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="3efe4-151">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="3efe4-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="3efe4-152">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-152">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="3efe4-153">Fügen Sie der neuen Datei die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="3efe4-153">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="3efe4-154">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *IrisData.cs* den folgenden Code hinzu, der die Klassen `IrisData` und `ClusterPrediction` definiert:</span><span class="sxs-lookup"><span data-stu-id="3efe4-154">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="3efe4-155">`IrisData` ist die Eingabedatenklasse und verfügt über Definitionen für jedes Merkmal im Dataset.</span><span class="sxs-lookup"><span data-stu-id="3efe4-155">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="3efe4-156">Verwenden Sie das Attribut [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute), um die Indizes der Quellspalten in der Datasetdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-156">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="3efe4-157">Die Klasse `ClusterPrediction` repräsentiert die Ausgabe des Clusteringmodells, das auf eine `IrisData`-Instanz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3efe4-157">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="3efe4-158">Verwenden Sie das Attribut [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute), um die Felder `PredictedClusterId` und `Distances` an die Spalten **PredictedLabel** bzw. **Score** zu binden.</span><span class="sxs-lookup"><span data-stu-id="3efe4-158">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="3efe4-159">Bei der Clusteringaufgabe haben diese Spalten die folgende Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="3efe4-159">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="3efe4-160">Die Spalte **PredictedLabel** enthält die ID des vorhergesagten Clusters.</span><span class="sxs-lookup"><span data-stu-id="3efe4-160">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="3efe4-161">Die Spalte **Score** enthält ein Array mit den quadratischen euklidischen Abständen zum Clusterschwerpunkt.</span><span class="sxs-lookup"><span data-stu-id="3efe4-161">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="3efe4-162">Die Arraylänge ist gleich der Anzahl von Clustern.</span><span class="sxs-lookup"><span data-stu-id="3efe4-162">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="3efe4-163">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-163">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="3efe4-164">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="3efe4-164">Define data and model paths</span></span>

<span data-ttu-id="3efe4-165">Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie zwei Felder hinzu, die die Pfade zur Datasetdatei und zur Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="3efe4-165">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="3efe4-166">`_dataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3efe4-166">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="3efe4-167">`_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="3efe4-167">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="3efe4-168">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="3efe4-168">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="3efe4-169">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="3efe4-169">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="3efe4-170">ML-Kontext erstellen</span><span class="sxs-lookup"><span data-stu-id="3efe4-170">Create ML context</span></span>

<span data-ttu-id="3efe4-171">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="3efe4-171">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="3efe4-172">Ersetzen Sie in der `Main`-Methode die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3efe4-172">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="3efe4-173">Die Klasse <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> stellt die Umgebung für maschinelles Lernen dar und bietet Mechanismen für die Protokollierung sowie Einstiegspunkte für das Laden von Daten, das Trainieren von Modellen, Vorhersagen und weitere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="3efe4-173">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="3efe4-174">Dies ist im Prinzip vergleichbar mit der Verwendung von `DbContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3efe4-174">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="3efe4-175">Einrichten des Ladens von Daten</span><span class="sxs-lookup"><span data-stu-id="3efe4-175">Setup data loading</span></span>

<span data-ttu-id="3efe4-176">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um das Verfahren zum Laden von Daten einzurichten:</span><span class="sxs-lookup"><span data-stu-id="3efe4-176">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

<span data-ttu-id="3efe4-177">Die generische [`MLContext.Data.LoadFromTextFile`-Erweiterungsmethode](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) leitet das Datasetschema aus dem bereitgestellten `IrisData`-Typ ab und gibt <xref:Microsoft.ML.IDataView> zurück, was als Eingabe für Transformatoren verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3efe4-177">The generic [`MLContext.Data.LoadFromTextFile` extension method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) infers the data set schema from the provided `IrisData` type and returns <xref:Microsoft.ML.IDataView> which can be used as input for transformers.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="3efe4-178">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="3efe4-178">Create a learning pipeline</span></span>

<span data-ttu-id="3efe4-179">Im Rahmen dieses Tutorials umfasst die Pipeline der Clusteraufgabe die zwei folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="3efe4-179">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="3efe4-180">Verketten geladener Spalten zu einer Spalte **Features**, die von einem Clustertrainer verwendet wird;</span><span class="sxs-lookup"><span data-stu-id="3efe4-180">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="3efe4-181">Verwenden eines <xref:Microsoft.ML.Trainers.KMeansTrainer>-Trainers, um das Modell mithilfe des Clusteralgorithmus k-means++ zu trainieren.</span><span class="sxs-lookup"><span data-stu-id="3efe4-181">use a <xref:Microsoft.ML.Trainers.KMeansTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="3efe4-182">Fügen Sie der `Main`-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="3efe4-182">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="3efe4-183">Der Code gibt an, dass das Dataset in drei Cluster aufgeteilt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3efe4-183">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="3efe4-184">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="3efe4-184">Train the model</span></span>

<span data-ttu-id="3efe4-185">Die in den vorangegangenen Abschnitten hinzugefügten Schritte haben die Pipeline für das Training vorbereitet, es wurden jedoch keine ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3efe4-185">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="3efe4-186">Fügen Sie der `Main`-Methode die folgende Zeile hinzu, um das Laden der Daten und das Trainieren des Modells auszuführen:</span><span class="sxs-lookup"><span data-stu-id="3efe4-186">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="3efe4-187">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="3efe4-187">Save the model</span></span>

<span data-ttu-id="3efe4-188">An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3efe4-188">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="3efe4-189">Um das Modell in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code der Methode `Main` hinzu:</span><span class="sxs-lookup"><span data-stu-id="3efe4-189">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="3efe4-190">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="3efe4-190">Use the model for predictions</span></span>

<span data-ttu-id="3efe4-191">Verwenden Sie für Vorhersagen die <xref:Microsoft.ML.PredictionEngine%602>-Klasse, die Instanzen des Eingabetyps über die Transformationspipeline annimmt und Instanzen des Ausgabetyps erzeugt.</span><span class="sxs-lookup"><span data-stu-id="3efe4-191">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="3efe4-192">Fügen Sie der `Main`-Methode die folgende Zeile hinzu, um eine Instanz dieser Klasse zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3efe4-192">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="3efe4-193">Erstellen Sie die Klasse `TestIrisData`, um Testdateninstanzen unterzubringen:</span><span class="sxs-lookup"><span data-stu-id="3efe4-193">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="3efe4-194">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-194">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="3efe4-195">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="3efe4-195">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="3efe4-196">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="3efe4-196">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="3efe4-197">Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:</span><span class="sxs-lookup"><span data-stu-id="3efe4-197">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="3efe4-198">Dieses Tutorial führt eine Irisdateninstanz innerhalb dieser Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="3efe4-198">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="3efe4-199">Sie können weitere Szenarios zum Testen des Models hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3efe4-199">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="3efe4-200">Fügen Sie den folgenden Code der `TestIrisData`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="3efe4-200">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="3efe4-201">Um herauszufinden, zu welchem Cluster das angegebene Element gehört, gehen Sie zurück zur Datei *Program.cs* und fügen Sie den folgenden Code in die Methode `Main` ein:</span><span class="sxs-lookup"><span data-stu-id="3efe4-201">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="3efe4-202">Führen Sie das Programm aus, um festzustellen, welcher Cluster die angegebene Dateninstanz und die quadratischen Abstände von dieser Instanz zum Clusterschwerpunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="3efe4-202">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="3efe4-203">Die Ergebnisse sollten den hier dargestellten ähneln:</span><span class="sxs-lookup"><span data-stu-id="3efe4-203">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="3efe4-204">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="3efe4-204">Congratulations!</span></span> <span data-ttu-id="3efe4-205">Sie haben erfolgreich ein Machine Learning-Modell für Iris-Clustering erstellt und für Vorhersagen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3efe4-205">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="3efe4-206">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering).</span><span class="sxs-lookup"><span data-stu-id="3efe4-206">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3efe4-207">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3efe4-207">Next steps</span></span>

<span data-ttu-id="3efe4-208">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="3efe4-208">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="3efe4-209">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="3efe4-209">Understand the problem</span></span>
> - <span data-ttu-id="3efe4-210">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="3efe4-210">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="3efe4-211">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="3efe4-211">Prepare the data</span></span>
> - <span data-ttu-id="3efe4-212">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="3efe4-212">Load and transform the data</span></span>
> - <span data-ttu-id="3efe4-213">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="3efe4-213">Choose a learning algorithm</span></span>
> - <span data-ttu-id="3efe4-214">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="3efe4-214">Train the model</span></span>
> - <span data-ttu-id="3efe4-215">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="3efe4-215">Use the model for predictions</span></span>

<span data-ttu-id="3efe4-216">In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.</span><span class="sxs-lookup"><span data-stu-id="3efe4-216">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3efe4-217">dotnet/machinelearning GitHub repository</span><span class="sxs-lookup"><span data-stu-id="3efe4-217">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
