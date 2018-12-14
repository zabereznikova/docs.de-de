---
title: Iris-Clustering mithilfe eines Clusteringlernmoduls – ML.NET
description: Hier erfahren Sie, wie Sie ML.NET in einem Clusteringszenario verwenden.
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 5bd73c774f60466daaf52215c34e7e17b5f5cc9c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145626"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="e3f4a-103">Tutorial: Iris-Clustering mithilfe eines Clusteringlernmoduls – ML.NET</span><span class="sxs-lookup"><span data-stu-id="e3f4a-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="e3f4a-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="e3f4a-105">Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e3f4a-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="e3f4a-106">Dieses Tutorial zeigt, wie Sie mit ML.NET ein [Clusteringmodell](../resources/tasks.md#clustering) für das [Iris-Dataset](https://en.wikipedia.org/wiki/Iris_flower_data_set) erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="e3f4a-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="e3f4a-108">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-108">Understand the problem</span></span>
> - <span data-ttu-id="e3f4a-109">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e3f4a-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="e3f4a-110">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-110">Prepare the data</span></span>
> - <span data-ttu-id="e3f4a-111">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-111">Load and transform the data</span></span>
> - <span data-ttu-id="e3f4a-112">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="e3f4a-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="e3f4a-113">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="e3f4a-113">Train the model</span></span>
> - <span data-ttu-id="e3f4a-114">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3f4a-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-115">Prerequisites</span></span>

- <span data-ttu-id="e3f4a-116">[Visual Studio 2017 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="e3f4a-117">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-117">Understand the problem</span></span>

<span data-ttu-id="e3f4a-118">Bei diesem Problem geht es darum, Iris anhand ihrer Blütenmerkmale in unterschiedliche Gruppen einzuteilen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="e3f4a-119">Die entsprechenden Merkmale sind Länge und Breite des Kelchblatts sowie Länge und Breite des Kronblatts.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="e3f4a-120">Für dieses Tutorial wird angenommen, dass der Typ jeder Blume unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="e3f4a-121">Sie werden die Struktur eines Datasets basierend auf Merkmalen kennenlernen und vorhersagen können, wie eine Dateninstanz in diese Struktur passt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="e3f4a-122">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e3f4a-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="e3f4a-123">Da Sie nicht wissen, zu welcher Gruppe jede Blume gehört, wählen Sie die Aufgabe [Unüberwachtes maschinelles Lernen](../resources/glossary.md#unsupervised-machine-learning) aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="e3f4a-124">Um ein Dataset so in Gruppen zu unterteilen, dass Elemente in derselben Gruppe einander ähnlicher sind als in anderen Gruppen, verwenden Sie eine [Clustering](../resources/tasks.md#clustering)-Aufgabe für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="e3f4a-125">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="e3f4a-125">Create a console application</span></span>

1. <span data-ttu-id="e3f4a-126">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="e3f4a-127">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="e3f4a-128">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="e3f4a-129">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="e3f4a-130">Geben Sie im Textfeld **Name** „IrisClustering“ ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-130">In the **Name** text box, type "IrisClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="e3f4a-131">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset und die Modelldateien zu speichern:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="e3f4a-132">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="e3f4a-133">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="e3f4a-134">Installieren Sie das NuGet-Paket **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="e3f4a-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e3f4a-136">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, wählen Sie das Paket in der Liste aus, und klicken Sie anschließend auf die Schaltfläche **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="e3f4a-137">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="e3f4a-138">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-138">Prepare the data</span></span>

1. <span data-ttu-id="e3f4a-139">Laden Sie das Dataset [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) herunter und speichern Sie es im Ordner *Data*, den Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="e3f4a-140">Weitere Informationen zum Iris-Dataset finden Sie im englischen Wikipedia-Artikel [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) und auf der Website [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris), der Quelle des Datasets.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="e3f4a-141">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *iris.data*, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="e3f4a-142">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="e3f4a-143">Die Datei *iris.data* enthält fünf Spalten, die Folgendes darstellen:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="e3f4a-144">Kelchblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="e3f4a-144">sepal length in centimetres</span></span>
- <span data-ttu-id="e3f4a-145">Kelchblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="e3f4a-145">sepal width in centimetres</span></span>
- <span data-ttu-id="e3f4a-146">Kronblattlänge in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="e3f4a-146">petal length in centimetres</span></span>
- <span data-ttu-id="e3f4a-147">Kronblattbreite in Zentimetern</span><span class="sxs-lookup"><span data-stu-id="e3f4a-147">petal width in centimetres</span></span>
- <span data-ttu-id="e3f4a-148">Iristyp</span><span class="sxs-lookup"><span data-stu-id="e3f4a-148">type of iris flower</span></span>

<span data-ttu-id="e3f4a-149">Für das Clusteringbeispiel wird in diesem Tutorial die letzte Spalte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="e3f4a-150">Erstellen von Datenklassen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-150">Create data classes</span></span>

<span data-ttu-id="e3f4a-151">Erstellen Sie Klassen für die Eingabedaten und die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="e3f4a-152">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="e3f4a-153">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *IrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="e3f4a-154">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="e3f4a-155">Fügen Sie der neuen Datei die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

<span data-ttu-id="e3f4a-156">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie der Datei *IrisData.cs* den folgenden Code hinzu, der die Klassen `IrisData` und `ClusterPrediction` definiert:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

<span data-ttu-id="e3f4a-157">`IrisData` ist die Eingabedatenklasse und verfügt über Definitionen für jedes Merkmal im Dataset.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="e3f4a-158">Verwenden Sie das Attribut [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute), um die Indizes der Quellspalten in der Datasetdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-158">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="e3f4a-159">Die Klasse `ClusterPrediction` repräsentiert die Ausgabe des Clusteringmodells, das auf eine `IrisData`-Instanz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="e3f4a-160">Verwenden Sie das Attribut [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute), um die Felder `PredictedClusterId` und `Distances` an die Spalten **PredictedLabel** bzw. **Score** zu binden.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-160">Use the [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="e3f4a-161">Bei der Clusteringaufgabe haben diese Spalten die folgende Bedeutung:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="e3f4a-162">Die Spalte **PredictedLabel** enthält die ID des vorhergesagten Clusters.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="e3f4a-163">Die Spalte **Score** enthält ein Array mit den quadratischen euklidischen Abständen zum Clusterschwerpunkt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="e3f4a-164">Die Arraylänge ist gleich der Anzahl von Clustern.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="e3f4a-165">Verwenden Sie den Typ `float`, um Gleitkommawerte in den Eingabe- und Vorhersagedatenklassen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="e3f4a-166">Definieren von Daten und Modellpfaden</span><span class="sxs-lookup"><span data-stu-id="e3f4a-166">Define data and model paths</span></span>

<span data-ttu-id="e3f4a-167">Wechseln Sie zurück zur Datei *Program.cs*, und fügen Sie zwei Felder hinzu, die die Pfade zur Datasetdatei und zur Datei zum Speichern des Modells enthalten:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="e3f4a-168">`_dataPath` enthält den Pfad zur Datei mit dem Dataset, das zum Trainieren des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="e3f4a-169">`_modelPath` enthält den Pfad zur Datei, in der das trainierte Modell gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="e3f4a-170">Fügen Sie den folgenden Code direkt über der `Main`-Methode hinzu, um diese Pfade anzugeben:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

<span data-ttu-id="e3f4a-171">Fügen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzu, um den obenstehenden Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="e3f4a-172">Erstellen einer Lernpipeline</span><span class="sxs-lookup"><span data-stu-id="e3f4a-172">Create a learning pipeline</span></span>

<span data-ttu-id="e3f4a-173">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

<span data-ttu-id="e3f4a-174">Ersetzen Sie in der `Main`-Methode `Console.WriteLine("Hello World!")` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-174">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

<span data-ttu-id="e3f4a-175">Die `Train`-Methode trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-175">The `Train` method trains the model.</span></span> <span data-ttu-id="e3f4a-176">Erstellen Sie die Methode direkt unter der Methode `Main` mit dem folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-176">Create that method just below the `Main` method, using the following code:</span></span>

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

<span data-ttu-id="e3f4a-177">Die Lernpipeline lädt alle Daten und Algorithmen, die zum Trainieren des Modells erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-177">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="e3f4a-178">Fügen Sie den folgenden Code der `Train`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-178">Add the following code into the `Train` method:</span></span>

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a><span data-ttu-id="e3f4a-179">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-179">Load and transform data</span></span>

<span data-ttu-id="e3f4a-180">Laden Sie zuerst das Trainingsdataset.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-180">The first step to perform is to load the training data set.</span></span> <span data-ttu-id="e3f4a-181">In diesem Fall wird das Trainingsdataset in der Textdatei mit einem Pfad gespeichert, der vom Feld `_dataPath` definiert wird.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-181">In our case, the training data set is stored in the text file with a path defined by the `_dataPath` field.</span></span> <span data-ttu-id="e3f4a-182">Die Spalten in der Datei werden durch Kommas („,“) getrennt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-182">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="e3f4a-183">Fügen Sie den folgenden Code der `Train`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-183">Add the following code into the `Train` method:</span></span>

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

<span data-ttu-id="e3f4a-184">Im nächsten Schritt werden alle Spalten mit Merkmalen mithilfe der Transformationsklasse <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> in der Spalte **Features** zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-184">The next step is to combine all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="e3f4a-185">Standardmäßig verarbeitet ein Lernalgorithmus nur Merkmale aus der Spalte **Features**.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-185">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="e3f4a-186">Fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-186">Add the following code:</span></span>

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="e3f4a-187">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="e3f4a-187">Choose a learning algorithm</span></span>

<span data-ttu-id="e3f4a-188">Nach dem Hinzufügen von Daten zur Pipeline und dem Transformieren in das richtige Eingabeformat wählen Sie einen Lernalgorithmus (**Lernmodul**) aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-188">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="e3f4a-189">Das Lernmodul trainiert das Modell.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-189">The learner trains the model.</span></span> <span data-ttu-id="e3f4a-190">ML.NET bietet ein Lernmodul <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer>, das den [k-Means-Algorithmus](https://en.wikipedia.org/wiki/K-means_clustering) mit einer verbesserten Methode zur Auswahl der anfänglichen Clusterschwerpunkte implementiert.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-190">ML.NET provides a <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> learner that implements [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) with an improved method for choosing the initial cluster centroids.</span></span>

<span data-ttu-id="e3f4a-191">Fügen Sie den folgenden Code nach dem im vorherigen Schritt hinzugefügten Datenverarbeitungscode in die `Train`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-191">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

<span data-ttu-id="e3f4a-192">Verwenden Sie die Eigenschaft <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType>, um die Anzahl von Clustern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-192">Use the <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> property to specify number of clusters.</span></span> <span data-ttu-id="e3f4a-193">Der obige Code gibt an, dass das Dataset in drei Cluster aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-193">The code above specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="e3f4a-194">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="e3f4a-194">Train the model</span></span>

<span data-ttu-id="e3f4a-195">Die in den vorangegangenen Abschnitten hinzugefügten Schritte haben die Pipeline für das Training vorbereitet, es wurden jedoch keine ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-195">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="e3f4a-196">Die Methode `pipeline.Train<TInput, TOutput>` erzeugt das Modell, das eine Instanz vom Typ `TInput` annimmt und eine Instanz vom Typ `TOutput` ausgibt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-196">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="e3f4a-197">Fügen Sie den folgenden Code der `Train`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-197">Add the following code into the `Train` method:</span></span>

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a><span data-ttu-id="e3f4a-198">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="e3f4a-198">Save the model</span></span>

<span data-ttu-id="e3f4a-199">An diesem Punkt haben Sie ein Modell, das in eine der vorhandenen oder neuen .NET-Anwendungen integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-199">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="e3f4a-200">Um das Modell in einer ZIP-Datei zu speichern, fügen Sie den folgenden Code der Methode `Main` unter dem Aufruf der Methode `Train` hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-200">To save your model to a .zip file, add the following code to the `Main` method below the call to the `Train` method:</span></span>

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

<span data-ttu-id="e3f4a-201">Wenn Sie `await` in der Methode `Main` verwenden, bedeutet dies, dass die `Main`-Methode den Modifizierer `async` erfordert und eine Aufgabe `Task` zurückgeben muss:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-201">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

<span data-ttu-id="e3f4a-202">Außerdem müssen Sie die folgende `using`-Anweisung am Anfang der Datei *Program.cs* hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-202">You also need to add the following `using` directive at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

<span data-ttu-id="e3f4a-203">Da die `async Main`-Methode ein neues Feature in C# 7.1 und die Standardsprachversion des Projekts C# 7.0 ist, müssen Sie die Sprachversion auf C# 7.1 oder höher ändern.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-203">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="e3f4a-204">Klicken Sie hierzu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-204">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="e3f4a-205">Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-205">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="e3f4a-206">Wählen Sie in der Dropdownliste **C# 7.1** (oder eine höhere Version) aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-206">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="e3f4a-207">Klicken Sie auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-207">Select the **OK** button.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="e3f4a-208">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-208">Use the model for predictions</span></span>

<span data-ttu-id="e3f4a-209">Erstellen Sie die Klasse `TestIrisData`, um Testdateninstanzen unterzubringen:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-209">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="e3f4a-210">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-210">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="e3f4a-211">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *TestIrisData.cs*.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-211">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="e3f4a-212">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-212">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="e3f4a-213">Ändern Sie die Klasse wie im folgenden Beispiel in „statisch“:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-213">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

<span data-ttu-id="e3f4a-214">Dieses Tutorial führt eine Irisdateninstanz innerhalb dieser Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-214">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="e3f4a-215">Sie können weitere Szenarios zum Testen des Models hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-215">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="e3f4a-216">Fügen Sie den folgenden Code der `TestIrisData`-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-216">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

<span data-ttu-id="e3f4a-217">Um herauszufinden, zu welchem Cluster das angegebene Element gehört, gehen Sie zurück zur Datei *Program.cs* und fügen Sie den folgenden Code in die Methode `Main` ein:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-217">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

<span data-ttu-id="e3f4a-218">Führen Sie das Programm aus, um festzustellen, welcher Cluster die angegebene Dateninstanz und die quadratischen Abstände von dieser Instanz zum Clusterschwerpunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-218">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="e3f4a-219">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-219">Your results should be similar to the following.</span></span> <span data-ttu-id="e3f4a-220">Während die Pipeline verarbeitet wird, werden möglicherweise Warnungen oder Meldungen zur Verarbeitung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-220">As the pipeline processes, it might display warnings or processing messages.</span></span> <span data-ttu-id="e3f4a-221">Diese wurden der Übersichtlichkeit halber aus der folgenden Ausgabe entfernt.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-221">These have been removed from the following output for clarity.</span></span>

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

<span data-ttu-id="e3f4a-222">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="e3f4a-222">Congratulations!</span></span> <span data-ttu-id="e3f4a-223">Sie haben erfolgreich ein Machine Learning-Modell für Iris-Clustering erstellt und für Vorhersagen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-223">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="e3f4a-224">Sie finden den Quellcode für dieses Tutorial im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering).</span><span class="sxs-lookup"><span data-stu-id="e3f4a-224">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3f4a-225">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e3f4a-225">Next steps</span></span>

<span data-ttu-id="e3f4a-226">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e3f4a-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="e3f4a-227">Das Problem verstehen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-227">Understand the problem</span></span>
> - <span data-ttu-id="e3f4a-228">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="e3f4a-228">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="e3f4a-229">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-229">Prepare the data</span></span>
> - <span data-ttu-id="e3f4a-230">Laden und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="e3f4a-230">Load and transform the data</span></span>
> - <span data-ttu-id="e3f4a-231">Auswählen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="e3f4a-231">Choose a learning algorithm</span></span>
> - <span data-ttu-id="e3f4a-232">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="e3f4a-232">Train the model</span></span>
> - <span data-ttu-id="e3f4a-233">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="e3f4a-233">Use the model for predictions</span></span>

<span data-ttu-id="e3f4a-234">In unserem GitHub-Repository können Sie mit dem Lernen fortfahren und weitere Beispiele finden.</span><span class="sxs-lookup"><span data-stu-id="e3f4a-234">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e3f4a-235">dotnet/machinelearning GitHub repository</span><span class="sxs-lookup"><span data-stu-id="e3f4a-235">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
