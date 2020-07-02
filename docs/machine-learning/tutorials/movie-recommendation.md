---
title: 'Tutorial: Erstellen eines Programms zur Filmempfehlung (Matrixfaktorisierung)'
description: Dieses Tutorial zeigt Ihnen, wie Sie mithilfe von ML.NET in einer .NET Core-Konsolenanwendung ein Filmempfehlungssystem erstellen. Für die Schritte verwenden Sie C# und Visual Studio 2019.
author: briacht
ms.date: 06/30/2020
ms.custom: mvc, title-hack-0516
ms.topic: tutorial
ms.openlocfilehash: 5445a255d32f824b1e451c828f1d46b3e1c16001
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803377"
---
# <a name="tutorial-build-a-movie-recommender-using-matrix-factorization-with-mlnet"></a><span data-ttu-id="7c451-104">Tutorial: Erstellen eines Programms zur Filmempfehlung mithilfe der Matrixfaktorisierung mit ML.NET</span><span class="sxs-lookup"><span data-stu-id="7c451-104">Tutorial: Build a movie recommender using matrix factorization with ML.NET</span></span>

<span data-ttu-id="7c451-105">Dieses Tutorial zeigt Ihnen, wie Sie mithilfe von ML.NET in einer .NET Core-Konsolenanwendung ein Filmempfehlungssystem erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c451-105">This tutorial shows you how to build a movie recommender with ML.NET in a .NET Core console application.</span></span> <span data-ttu-id="7c451-106">Für die Schritte verwenden Sie C# und Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="7c451-106">The steps use C# and Visual Studio 2019.</span></span>

<span data-ttu-id="7c451-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7c451-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="7c451-108">Auswählen eines Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="7c451-108">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="7c451-109">Vorbereiten und Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="7c451-109">Prepare and load your data</span></span>
> * <span data-ttu-id="7c451-110">Erstellen und Trainieren eines Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-110">Build and train a model</span></span>
> * <span data-ttu-id="7c451-111">Auswerten eines Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-111">Evaluate a model</span></span>
> * <span data-ttu-id="7c451-112">Bereitstellen und Nutzen eines Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-112">Deploy and consume a model</span></span>

<span data-ttu-id="7c451-113">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="7c451-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="7c451-114">Machine Learning-Workflow</span><span class="sxs-lookup"><span data-stu-id="7c451-114">Machine learning workflow</span></span>

<span data-ttu-id="7c451-115">Die folgenden Schritten eignen sich für diese und alle anderen ML.NET-Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="7c451-115">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="7c451-116">Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="7c451-116">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="7c451-117">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-117">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="7c451-118">Auswerten des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-118">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="7c451-119">Verwenden des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-119">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="7c451-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7c451-120">Prerequisites</span></span>

* <span data-ttu-id="7c451-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher oder Visual Studio 2017 Version 15.6 oder höher mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="7c451-121">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="7c451-122">Auswählen der entsprechenden Machine Learning-Aufgabe</span><span class="sxs-lookup"><span data-stu-id="7c451-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="7c451-123">Es gibt mehrere Möglichkeiten, ein Empfehlungssystem umzusetzen. Beispielsweise könnten Sie eine Liste mit empfohlenen Filmen oder mit ähnlichen Produkten erstellen. In diesem Szenario sagt Ihr Modell jedoch vorher, wie ein Benutzer einen bestimmten Film auf einer Skala von eins bis fünf bewertet. Falls dieser Wert höher als ein festgelegter Schwellenwert ist, wird der Film empfohlen. Dabei entsprechen höhere Bewertungen auch einer höheren Wahrscheinlichkeit dafür, dass ein Benutzer einen bestimmten Film mag.</span><span class="sxs-lookup"><span data-stu-id="7c451-123">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="7c451-124">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="7c451-124">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="7c451-125">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="7c451-125">Create a project</span></span>

1. <span data-ttu-id="7c451-126">Öffnen Sie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7c451-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="7c451-127">Wählen Sie **Datei** > **Neu** > **Projekt** aus der Menüleiste aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="7c451-128">Wählen Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C#** und anschließend den Knoten **.NET Core** aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="7c451-129">Klicken Sie dann auf die Projektvorlage **Konsolen-App (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="7c451-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="7c451-130">Geben Sie im Textfeld **Name** „MovieRecommender“ ein, und klicken Sie anschließend auf die Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c451-130">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="7c451-131">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um das Dataset zu speichern:</span><span class="sxs-lookup"><span data-stu-id="7c451-131">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="7c451-132">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** > **Neuer Ordner** aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="7c451-133">Geben Sie „Data“ ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="7c451-133">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="7c451-134">Installieren Sie die NuGet-Pakete **Microsoft.ML** und **Microsoft.ML.Recommender**:</span><span class="sxs-lookup"><span data-stu-id="7c451-134">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="7c451-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="7c451-136">Wählen Sie als Paketquelle „nuget.org“ aus. Wählen Sie anschließend die Registerkarte **Durchsuchen** aus, suchen Sie nach **Microsoft.ML**, und wählen Sie das Paket in der Liste und anschließend die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="7c451-137">Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.</span><span class="sxs-lookup"><span data-stu-id="7c451-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="7c451-138">Wiederholen Sie diese Schritte für **Microsoft.ML.Recommender**.</span><span class="sxs-lookup"><span data-stu-id="7c451-138">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

4. <span data-ttu-id="7c451-139">Fügen Sie am Anfang der Datei *Program.cs* die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="7c451-139">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[UsingStatements](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="7c451-140">Herunterladen der Daten</span><span class="sxs-lookup"><span data-stu-id="7c451-140">Download your data</span></span>

1. <span data-ttu-id="7c451-141">Laden Sie die beiden Datasets herunter, und speichern Sie sie im Ordner *Data*, den Sie vorher erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="7c451-141">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="7c451-142">Klicken Sie mit der rechten Maustaste auf [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) und anschließend auf „Save Link As...“ (Link speichern unter...) oder „Save Target As...“ (Ziel speichern unter...).</span><span class="sxs-lookup"><span data-stu-id="7c451-142">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
   * <span data-ttu-id="7c451-143">Klicken Sie mit der rechten Maustaste auf [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) und anschließend auf „Save Link As“ (Link speichern unter) oder „Save Target As“ (Ziel speichern unter).</span><span class="sxs-lookup"><span data-stu-id="7c451-143">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="7c451-144">Achten Sie darauf, \* die CSV-Dateien entweder im Ordner *Data* zu speichern oder sie in den Ordner *Data* zu verschieben, nachdem Sie \* die Dateien an anderer Stelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="7c451-144">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="7c451-145">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die \*.csv-Dateien, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="7c451-146">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="7c451-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![GIF der Auswahl der Option „Kopieren, wenn neuer“](./media/movie-recommendation/copy-to-output-if-newer.gif)

## <a name="load-your-data"></a><span data-ttu-id="7c451-148">Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="7c451-148">Load your data</span></span>

<span data-ttu-id="7c451-149">Der erste Schritt im ML.NET-Prozess besteht darin, die Modelltrainings- und Testdaten vorzubereiten und zu laden.</span><span class="sxs-lookup"><span data-stu-id="7c451-149">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="7c451-150">Die Empfehlungsbewertungsdaten werden in die Datasets `Train` und `Test` unterteilt.</span><span class="sxs-lookup"><span data-stu-id="7c451-150">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="7c451-151">Die `Train`-Daten werden verwendet, um das Modell anzupassen.</span><span class="sxs-lookup"><span data-stu-id="7c451-151">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="7c451-152">Die `Test`-Daten werden verwendet, um mit dem trainierten Modell Vorhersagen zu treffen und die Modellleistung auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="7c451-152">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="7c451-153">`Train`- und `Test`-Daten werden üblicherweise im Verhältnis 80 zu 20 aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="7c451-153">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="7c451-154">Unten sehen Sie eine Vorschau der Daten aus den CSV-Dateien:</span><span class="sxs-lookup"><span data-stu-id="7c451-154">Below is a preview of the data from your \*.csv files:</span></span>

![Screenshot: Vorschau des CVS-Datasets](./media/movie-recommendation/csv-file-dataset-preview.png)

<span data-ttu-id="7c451-156">In den CSV-Dateien befinden sich vier Spalten:</span><span class="sxs-lookup"><span data-stu-id="7c451-156">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="7c451-157">Im Machine Learning-Kontext heißen Spalten, mit denen eine Vorhersage getroffen wird, [Features](../resources/glossary.md#feature). Die Spalte mit der zurückgegebenen Vorhersage wird als [Label](../resources/glossary.md#label) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7c451-157">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="7c451-158">Da Sie Filmbewertungen vorhersagen möchten, ist `Label` die Bewertungsspalte.</span><span class="sxs-lookup"><span data-stu-id="7c451-158">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="7c451-159">Die anderen drei Spalten `userId`, `movieId` und `timestamp` sind alle `Features`, mit denen das `Label` vorhergesagt wird.</span><span class="sxs-lookup"><span data-stu-id="7c451-159">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="7c451-160">Features</span><span class="sxs-lookup"><span data-stu-id="7c451-160">Features</span></span>      | <span data-ttu-id="7c451-161">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="7c451-161">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="7c451-162">Sie müssen selbst entscheiden, welche `Features` Sie verwenden möchten, um das `Label` vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="7c451-162">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="7c451-163">Sie können auch Methoden wie [Permutation Feature Importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) verwenden, um die Auswahl der besten `Features` zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7c451-163">You can also use methods like [permutation feature importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="7c451-164">In diesem Tutorial sollten Sie die `timestamp`-Spalte nicht als `Feature` festlegen, da der Zeitstempel nicht beeinflusst, wie ein Benutzer einen Film bewertet, und daher nicht zu einer genaueren Vorhersage beitragen würde.</span><span class="sxs-lookup"><span data-stu-id="7c451-164">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="7c451-165">Features</span><span class="sxs-lookup"><span data-stu-id="7c451-165">Features</span></span>      | <span data-ttu-id="7c451-166">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="7c451-166">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="7c451-167">Als Nächstes müssen Sie die Datenstruktur für die Eingabeklasse definieren.</span><span class="sxs-lookup"><span data-stu-id="7c451-167">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="7c451-168">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="7c451-168">Add a new class to your project:</span></span>

1. <span data-ttu-id="7c451-169">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und klicken Sie auf **Hinzufügen > Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="7c451-169">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="7c451-170">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *MovieRatingData.cs*.</span><span class="sxs-lookup"><span data-stu-id="7c451-170">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="7c451-171">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-171">Then, select the **Add** button.</span></span>

<span data-ttu-id="7c451-172">Die Datei *MovieRatingData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7c451-172">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="7c451-173">Fügen Sie am Anfang der Datei *MovieRatingData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="7c451-173">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="7c451-174">Erstellen Sie eine Klasse mit dem Namen `MovieRating`, indem Sie die vorhandene Klassendefinition entfernen und *MovieRatingData.cs* den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7c451-174">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](~/samples/snippets/machine-learning/MovieRecommendation/csharp/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="7c451-175">`MovieRating` ist eine Klasse für Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="7c451-175">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="7c451-176">Das [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribut legt fest, welche Spalten (durch Angabe des Spaltenindex) im Dataset geladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7c451-176">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="7c451-177">Die Spalten `userId` und `movieId` sind `Features`, also die Eingaben, die dem Modell übergeben werden, um das `Label` vorherzusagen. Die Bewertungsspalte ist das vorhergesagte `Label`, also die Ausgabe des Modells.</span><span class="sxs-lookup"><span data-stu-id="7c451-177">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="7c451-178">Erstellen Sie eine weitere Klasse mit dem Namen `MovieRatingPrediction`, um die vorhergesagten Ergebnisse darzustellen, indem Sie nach der Klasse `MovieRating` den folgenden Code in *MovieRatingData.cs* hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7c451-178">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](~/samples/snippets/machine-learning/MovieRecommendation/csharp/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="7c451-179">Ersetzen Sie in *Program.cs* innerhalb von `Main()` die Zeile `Console.WriteLine("Hello World!")` durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="7c451-179">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="7c451-180">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Startpunkt für alle ML.NET-Vorgänge. Durch das Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für mehrere Objekte des Modellerstellungsworkflows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c451-180">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="7c451-181">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="7c451-181">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="7c451-182">Erstellen Sie nach `Main()` die Methode `LoadData()`:</span><span class="sxs-lookup"><span data-stu-id="7c451-182">After `Main()`, create a method called `LoadData()`:</span></span>

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> <span data-ttu-id="7c451-183">Diese Methode löst zunächst eine Fehlermeldung aus. Dies ändert sich erst, wenn Sie in den folgenden Schritten eine Rückgabeanweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c451-183">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="7c451-184">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in `LoadData()` ein, um die Datenpfadvariablen zu initialisieren, die Daten aus den CSV-Dateien zu laden und die `Train`- und`Test` -Daten als `IDataView`-Objekte zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-184">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="7c451-185">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7c451-185">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="7c451-186">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7c451-186">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="7c451-187">Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7c451-187">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="7c451-188">Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="7c451-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="7c451-189">Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="7c451-189">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="7c451-190">In diesem Tutorial geben Sie den Pfad für die `Test`- und `Train`-Dateien, den Textdateiheader (zur korrekten Verwendung der Spaltennamen) und das Komma als Zeichendatentrennzeichen an (das Standardtrennzeichen ist ein Tabstopp).</span><span class="sxs-lookup"><span data-stu-id="7c451-190">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="7c451-191">Fügen Sie den folgenden Code zur Methode `Main()` hinzu, um die Methode `LoadData()` aufzurufen und die Daten `Train` und `Test` zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-191">Add the following code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a><span data-ttu-id="7c451-192">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-192">Build and train your model</span></span>

<span data-ttu-id="7c451-193">In ML.NET werden die folgenden drei Hauptkonzepte genutzt: [Daten](../resources/glossary.md#data), [Transformatoren](../resources/glossary.md#transformer) (Transformers) und [Schätzer](../resources/glossary.md#estimator) (Estimators).</span><span class="sxs-lookup"><span data-stu-id="7c451-193">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

<span data-ttu-id="7c451-194">Für Machine Learning-Trainingsalgorithmen sind Daten in einem bestimmten Format erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7c451-194">Machine learning training algorithms require data in a certain format.</span></span> <span data-ttu-id="7c451-195">`Transformers` werden verwendet, um Tabellendaten in ein kompatibles Format zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="7c451-195">`Transformers` are used to transform tabular data to a compatible format.</span></span>

![Diagramm des Transformationsdatenflusses](./media/movie-recommendation/data-transformer-transformed.png)

<span data-ttu-id="7c451-197">`Transformers` werden in ML.NET mithilfe von `Estimators` erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c451-197">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> <span data-ttu-id="7c451-198">`Estimators` akzeptieren Daten und geben `Transformers` zurück.</span><span class="sxs-lookup"><span data-stu-id="7c451-198">`Estimators` take in data and return `Transformers`.</span></span>

![Diagramm des Schätzungsdatenflusses](./media/movie-recommendation/data-estimator-transformer.png)

<span data-ttu-id="7c451-200">Der Trainingsalgorithmus für Empfehlungen, den Sie für das Training des Modells einsetzen, ist ein Beispiel für einen `Estimator`.</span><span class="sxs-lookup"><span data-stu-id="7c451-200">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="7c451-201">Erstellen Sie mit den folgenden Schritten einen `Estimator`:</span><span class="sxs-lookup"><span data-stu-id="7c451-201">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="7c451-202">Erstellen Sie die `BuildAndTrainModel()`-Methode mit dem folgenden Code direkt nach der `LoadData()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7c451-202">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> <span data-ttu-id="7c451-203">Diese Methode löst zunächst eine Fehlermeldung aus. Dies ändert sich erst, wenn Sie in den folgenden Schritten eine Rückgabeanweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c451-203">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="7c451-204">Fügen Sie `BuildAndTrainModel()` folgenden Code hinzu, um die Datentransformationen zu definieren:</span><span class="sxs-lookup"><span data-stu-id="7c451-204">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>

[!code-csharp[DataTransformations](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="7c451-205">Da `userId` und `movieId` keine reellen Zahlen, sondern Benutzer und Filmtitel darstellen, verwenden Sie die [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A)-Methode, um jede `userId` und `movieId` in eine `Feature`-Spalte mit einem numerischen Schlüsseltyp (also in ein Format, das von Empfehlungsalgorithmen akzeptiert wird) zu transformieren. Anschließend fügen Sie die Werte als neue Datasetspalten ein:</span><span class="sxs-lookup"><span data-stu-id="7c451-205">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="7c451-206">userId</span><span class="sxs-lookup"><span data-stu-id="7c451-206">userId</span></span> | <span data-ttu-id="7c451-207">movieId</span><span class="sxs-lookup"><span data-stu-id="7c451-207">movieId</span></span> | <span data-ttu-id="7c451-208">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="7c451-208">Label</span></span> | <span data-ttu-id="7c451-209">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="7c451-209">userIdEncoded</span></span> | <span data-ttu-id="7c451-210">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="7c451-210">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="7c451-211">1</span><span class="sxs-lookup"><span data-stu-id="7c451-211">1</span></span> | <span data-ttu-id="7c451-212">1</span><span class="sxs-lookup"><span data-stu-id="7c451-212">1</span></span> | <span data-ttu-id="7c451-213">4</span><span class="sxs-lookup"><span data-stu-id="7c451-213">4</span></span> | <span data-ttu-id="7c451-214">userKey1</span><span class="sxs-lookup"><span data-stu-id="7c451-214">userKey1</span></span> | <span data-ttu-id="7c451-215">movieKey1</span><span class="sxs-lookup"><span data-stu-id="7c451-215">movieKey1</span></span> |
| <span data-ttu-id="7c451-216">1</span><span class="sxs-lookup"><span data-stu-id="7c451-216">1</span></span> | <span data-ttu-id="7c451-217">3</span><span class="sxs-lookup"><span data-stu-id="7c451-217">3</span></span> | <span data-ttu-id="7c451-218">4</span><span class="sxs-lookup"><span data-stu-id="7c451-218">4</span></span> | <span data-ttu-id="7c451-219">userKey1</span><span class="sxs-lookup"><span data-stu-id="7c451-219">userKey1</span></span> | <span data-ttu-id="7c451-220">movieKey2</span><span class="sxs-lookup"><span data-stu-id="7c451-220">movieKey2</span></span> |
| <span data-ttu-id="7c451-221">1</span><span class="sxs-lookup"><span data-stu-id="7c451-221">1</span></span> | <span data-ttu-id="7c451-222">6</span><span class="sxs-lookup"><span data-stu-id="7c451-222">6</span></span> | <span data-ttu-id="7c451-223">4</span><span class="sxs-lookup"><span data-stu-id="7c451-223">4</span></span> | <span data-ttu-id="7c451-224">userKey1</span><span class="sxs-lookup"><span data-stu-id="7c451-224">userKey1</span></span> | <span data-ttu-id="7c451-225">movieKey3</span><span class="sxs-lookup"><span data-stu-id="7c451-225">movieKey3</span></span> |

<span data-ttu-id="7c451-226">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in `BuildAndTrainModel()` ein, um den Machine Learning-Algorithmus festzulegen und ihn an die Datentransformationsdefinitionen anzufügen:</span><span class="sxs-lookup"><span data-stu-id="7c451-226">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="7c451-227">Als Trainingsalgorithmus für Empfehlungen wird der [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c451-227">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="7c451-228">Die [Matrixfaktorisierung](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) wird häufig für Empfehlungen eingesetzt, wenn Daten dazu vorliegen, wie Benutzer Produkte in der Vergangenheit bewertet haben. Dies trifft auf die Datasets dieses Tutorials zu.</span><span class="sxs-lookup"><span data-stu-id="7c451-228">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="7c451-229">Falls andere Daten verfügbar sind, können noch mehr Empfehlungsalgorithmen eingesetzt werden. Weitere Informationen dazu finden Sie im Abschnitt [Weitere Empfehlungsalgorithmen](#other-recommendation-algorithms) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="7c451-229">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span>

<span data-ttu-id="7c451-230">In diesem Tutorial verwendet der `Matrix Factorization`-Algorithmus kollaborative Filter. Dabei wird Folgendes angenommen: Wenn Benutzer 1 zu einem bestimmten Thema die gleiche Meinung wie Benutzer 2 hat, vertritt Benutzer 1 zu einem anderen Thema mit höherer Wahrscheinlichkeit die gleiche Meinung wie Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="7c451-230">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="7c451-231">Wenn beispielsweise Benutzer 1 und Benutzer 2 Filme ähnlich bewerten, gefällt Benutzer 2 mit höherer Wahrscheinlichkeit ein Film, den Benutzer 1 angesehen und hoch bewertet hat:</span><span class="sxs-lookup"><span data-stu-id="7c451-231">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="7c451-232">Benutzer 1</span><span class="sxs-lookup"><span data-stu-id="7c451-232">User 1</span></span> | <span data-ttu-id="7c451-233">Hat den Film gesehen und ihn gemocht</span><span class="sxs-lookup"><span data-stu-id="7c451-233">Watched and liked movie</span></span> | <span data-ttu-id="7c451-234">Hat den Film gesehen und ihn gemocht</span><span class="sxs-lookup"><span data-stu-id="7c451-234">Watched and liked movie</span></span> | <span data-ttu-id="7c451-235">Hat den Film gesehen und ihn gemocht</span><span class="sxs-lookup"><span data-stu-id="7c451-235">Watched and liked movie</span></span> |
| <span data-ttu-id="7c451-236">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="7c451-236">User 2</span></span> | <span data-ttu-id="7c451-237">Hat den Film gesehen und ihn gemocht</span><span class="sxs-lookup"><span data-stu-id="7c451-237">Watched and liked movie</span></span> | <span data-ttu-id="7c451-238">Hat den Film gesehen und ihn gemocht</span><span class="sxs-lookup"><span data-stu-id="7c451-238">Watched and liked movie</span></span> | <span data-ttu-id="7c451-239">Hat den Film nicht gesehen; Film wird empfohlen</span><span class="sxs-lookup"><span data-stu-id="7c451-239">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="7c451-240">Der `Matrix Factorization`-Trainer kann durch mehrere [Optionen](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options) angepasst werden. Weitere Informationen zu diesen finden Sie im Abschnitt [Hyperparameter für Algorithmen](#algorithm-hyperparameters) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="7c451-240">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="7c451-241">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `BuildAndTrainModel()`-Methode ein, um das Modell an die `Train`-Daten anzupassen und das trainierte Modell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-241">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="7c451-242">Die [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29)-Methode trainiert das Modell mit dem bereitgestellten Trainingsdataset.</span><span class="sxs-lookup"><span data-stu-id="7c451-242">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="7c451-243">Sie führt die `Estimator`-Definitionen aus, indem sie die Daten transformiert und das Training durchführt. Anschließend gibt sie das trainierte Modell als `Transformer` zurück.</span><span class="sxs-lookup"><span data-stu-id="7c451-243">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="7c451-244">Fügen Sie den unten aufgeführten Code als nächste Codezeile in der Methode `Main()` hinzu, um die `BuildAndTrainModel()`-Methode aufzurufen und das trainierte Modell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-244">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="7c451-245">Auswerten des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-245">Evaluate your model</span></span>

<span data-ttu-id="7c451-246">Nachdem Sie Ihr Modell trainiert haben, werten Sie mit den Testdaten die Modellleistung aus.</span><span class="sxs-lookup"><span data-stu-id="7c451-246">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span>

<span data-ttu-id="7c451-247">Erstellen Sie die `EvaluateModel()`-Methode mit dem folgenden Code direkt nach der `BuildAndTrainModel()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7c451-247">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

<span data-ttu-id="7c451-248">Fügen Sie `EvaluateModel()` den folgenden Code hinzu, um die `Test`-Daten zu transformieren:</span><span class="sxs-lookup"><span data-stu-id="7c451-248">Transform the `Test` data by adding the following code to `EvaluateModel()`:</span></span>

[!code-csharp[Transform](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#Transform "Transform the test data")]

<span data-ttu-id="7c451-249">Die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="7c451-249">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="7c451-250">Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `EvaluateModel()`-Methode ein, um das Modell auszuwerten:</span><span class="sxs-lookup"><span data-stu-id="7c451-250">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="7c451-251">Nach der Vorhersagekonfiguration wertet die [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A)-Methode das Modell aus. Dabei werden die Vorhersagewerte mit den tatsächlichen `Labels` im Testdataset verglichen und die Leistungsmetriken für das Modell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c451-251">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="7c451-252">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `EvaluateModel()`-Methode ein, um die Auswertungsmetriken auf der Konsole auszugeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-252">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="7c451-253">Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Main()`-Methode ein, um die `EvaluateModel()`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="7c451-253">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="7c451-254">Bis hierhin sollte die Ausgabe in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7c451-254">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="7c451-255">Diese Ausgabe enthält 20 Iterationen.</span><span class="sxs-lookup"><span data-stu-id="7c451-255">In this output, there are 20 iterations.</span></span> <span data-ttu-id="7c451-256">Bei jeder Iteration verringert sich der Fehlermesswert und nähert sich immer mehr 0 an.</span><span class="sxs-lookup"><span data-stu-id="7c451-256">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="7c451-257">Die Wurzel der mittleren Fehlerquadratsumme (`root of mean squared error`; auch als RMS oder RMSE bezeichnet) wird verwendet, um die Unterschiede zwischen den vom Modell vorhergesagten Werten und den Beobachtungswerten des Testdatasets zu messen.</span><span class="sxs-lookup"><span data-stu-id="7c451-257">The `root of mean squared error` (RMS or RMSE) is used to measure the differences between the model predicted values and the test dataset observed values.</span></span> <span data-ttu-id="7c451-258">Es handelt sich dabei um die Quadratwurzel der durchschnittlichen Fehlerquadrate.</span><span class="sxs-lookup"><span data-stu-id="7c451-258">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="7c451-259">Je niedriger sie ausfällt, desto besser ist das Modell.</span><span class="sxs-lookup"><span data-stu-id="7c451-259">The lower it is, the better the model is.</span></span>

<span data-ttu-id="7c451-260">`R Squared` gibt an, wie gut Daten zu einem Modell passen.</span><span class="sxs-lookup"><span data-stu-id="7c451-260">`R Squared` indicates how well data fits a model.</span></span> <span data-ttu-id="7c451-261">Die Werte liegen zwischen 0 und 1.</span><span class="sxs-lookup"><span data-stu-id="7c451-261">Ranges from 0 to 1.</span></span> <span data-ttu-id="7c451-262">Der Wert 0 bedeutet, dass die Daten zufällig sind oder nicht an das Modell angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="7c451-262">A value of 0 means that the data is random or otherwise can't be fit to the model.</span></span> <span data-ttu-id="7c451-263">Ein Wert von 1 bedeutet, dass das Modell exakt mit den Daten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="7c451-263">A value of 1 means that the model exactly matches the data.</span></span> <span data-ttu-id="7c451-264">Der Wert von `R Squared` sollte möglichst nahe bei 1 liegen.</span><span class="sxs-lookup"><span data-stu-id="7c451-264">You want your `R Squared` score to be as close to 1 as possible.</span></span>

<span data-ttu-id="7c451-265">Erfolgreiche Modelle zu erstellen ist ein iterativer Prozess.</span><span class="sxs-lookup"><span data-stu-id="7c451-265">Building successful models is an iterative process.</span></span> <span data-ttu-id="7c451-266">Dieses Modell hat erst geringere Qualität, da das Tutorial kleine Datasets verwendet, um schnelles Modelltraining zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7c451-266">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="7c451-267">Wenn Sie nicht mit der Modellqualität zufrieden sind, können Sie versuchen, sie durch die Bereitstellung größerer Trainingsdatasets oder die Auswahl anderer Trainingsalgorithmen mit anderen Hyperparametern für jeden Algorithmus zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7c451-267">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span> <span data-ttu-id="7c451-268">Weitere Informationen finden Sie im Abschnitt [Verbessern des Modells](#improve-your-model) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="7c451-268">For more information, check out the [Improve your model](#improve-your-model) section below.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="7c451-269">Verwenden Ihres Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-269">Use your model</span></span>

<span data-ttu-id="7c451-270">Nun können Sie mit dem trainierten Modell Vorhersagen für neue Daten treffen.</span><span class="sxs-lookup"><span data-stu-id="7c451-270">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="7c451-271">Erstellen Sie die `UseModelForSinglePrediction()`-Methode mit dem folgenden Code direkt nach der `EvaluateModel()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7c451-271">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="7c451-272">Fügen Sie `UseModelForSinglePrediction()` den folgenden Code hinzu, um mit `PredictionEngine` die Bewertung vorherzusagen:</span><span class="sxs-lookup"><span data-stu-id="7c451-272">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="7c451-273">Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können.</span><span class="sxs-lookup"><span data-stu-id="7c451-273">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="7c451-274">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="7c451-274">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="7c451-275">Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="7c451-275">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="7c451-276">Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c451-276">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="7c451-277">Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.</span><span class="sxs-lookup"><span data-stu-id="7c451-277">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

> [!NOTE]
> <span data-ttu-id="7c451-278">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7c451-278">`PredictionEnginePool` service extension is currently in preview.</span></span>

<span data-ttu-id="7c451-279">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `UseModelForSinglePrediction()`-Methode ein, um eine Instanz von `MovieRating` mit dem Namen `testInput` zu erstellen und diese der PredictionEngine-Klasse zu übergeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-279">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="7c451-280">Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenspalte.</span><span class="sxs-lookup"><span data-stu-id="7c451-280">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="7c451-281">Anschließend können Sie mit dem `Score` (der vorhergesagten Bewertung) bestimmen, ob der Film mit der movieId 10 Benutzer 6 empfohlen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c451-281">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="7c451-282">Je höher der `Score`, desto höher ist die Wahrscheinlichkeit, dass einem Benutzer ein bestimmter Film gefällt.</span><span class="sxs-lookup"><span data-stu-id="7c451-282">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="7c451-283">In diesem Tutorial wird festgelegt, dass Filme mit einer höheren Bewertung als 3,5 empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="7c451-283">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="7c451-284">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `UseModelForSinglePrediction()`-Methode ein, um die Ergebnisse auszugeben:</span><span class="sxs-lookup"><span data-stu-id="7c451-284">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="7c451-285">Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Main()`-Methode ein, um die `UseModelForSinglePrediction()`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="7c451-285">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="7c451-286">Die Ausgabe dieser Methode sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7c451-286">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="7c451-287">Speichern des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-287">Save your model</span></span>

<span data-ttu-id="7c451-288">Sie müssen das Modell zuerst speichern, um damit Vorhersagen in Endbenutzeranwendungen treffen zu können.</span><span class="sxs-lookup"><span data-stu-id="7c451-288">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="7c451-289">Erstellen Sie die `SaveModel()`-Methode mit dem folgenden Code direkt nach der `UseModelForSinglePrediction()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="7c451-289">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>

```csharp
public static void SaveModel(MLContext mlContext, DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

<span data-ttu-id="7c451-290">Fügen Sie der `SaveModel()`-Methode folgenden Code hinzu, um das trainierte Modell zu speichern:</span><span class="sxs-lookup"><span data-stu-id="7c451-290">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="7c451-291">Diese Methode speichert das trainierte Modell in einer ZIP-Datei (im Ordner „Data“), die anschließend in anderen .NET-Anwendungen für Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7c451-291">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="7c451-292">Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Main()`-Methode ein, um die `SaveModel()`-Methode aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="7c451-292">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](~/samples/snippets/machine-learning/MovieRecommendation/csharp/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="7c451-293">Verwenden des gespeicherten Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-293">Use your saved model</span></span>

<span data-ttu-id="7c451-294">Nachdem Sie Ihr trainiertes Modell gespeichert haben, können Sie das Modell in verschiedenen Umgebungen nutzen.</span><span class="sxs-lookup"><span data-stu-id="7c451-294">Once you have saved your trained model, you can consume the model in different environments.</span></span> <span data-ttu-id="7c451-295">Weitere Informationen zum Nutzbarmachen eines trainierten Machine Learning-Modells in Apps finden Sie unter [Speichern und Laden trainierter Modelle](../how-to-guides/save-load-machine-learning-models-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="7c451-295">See [Save and load trained models](../how-to-guides/save-load-machine-learning-models-ml-net.md) to learn how to operationalize a trained machine learning model in apps.</span></span>

## <a name="results"></a><span data-ttu-id="7c451-296">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="7c451-296">Results</span></span>

<span data-ttu-id="7c451-297">Nachdem Sie die obigen Schritte durchgeführt haben, können Sie nun die Konsolen-App ausführen (STRG+F5).</span><span class="sxs-lookup"><span data-stu-id="7c451-297">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="7c451-298">Die Ergebnisse der obigen Vorhersage sollten in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="7c451-298">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="7c451-299">Möglicherweise werden Warnungen oder Verarbeitungsnachrichten angezeigt. Diese wurden jedoch aus Gründen der Übersichtlichkeit aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="7c451-299">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="7c451-300">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="7c451-300">Congratulations!</span></span> <span data-ttu-id="7c451-301">Sie haben ein Machine Learning-Modell zur Empfehlung von Filmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c451-301">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="7c451-302">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).</span><span class="sxs-lookup"><span data-stu-id="7c451-302">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="7c451-303">Verbessern des Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-303">Improve your model</span></span>

<span data-ttu-id="7c451-304">Es gibt mehrere Möglichkeiten, die Leistung des Modells zu verbessern, um so genauere Vorhersagen treffen zu können.</span><span class="sxs-lookup"><span data-stu-id="7c451-304">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="7c451-305">Daten</span><span class="sxs-lookup"><span data-stu-id="7c451-305">Data</span></span>

<span data-ttu-id="7c451-306">Wenn Sie mehr Trainingsdaten mit ausreichend Beispielen für jeden Benutzer und für jede movieId hinzufügen, kann die Qualität des Empfehlungsmodells gesteigert werden.</span><span class="sxs-lookup"><span data-stu-id="7c451-306">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="7c451-307">Die [Kreuzvalidierung](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) ist eine Methode zur Auswertung von Modellen, bei der nicht –wie in diesem Tutorial – Testdaten aus dem Dataset extrahiert, sondern stattdessen nach dem Zufallsprinzip Daten in Teilmengen aufgeteilt werden. Anschließend werden einige Gruppen als Trainingsdaten und einige als Testdaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c451-307">[Cross validation](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="7c451-308">Diese Methode führt im Vergleich zur Aufteilung von Daten in Trainings- und Testdatasets zu einer höheren Modellqualität.</span><span class="sxs-lookup"><span data-stu-id="7c451-308">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="7c451-309">Features</span><span class="sxs-lookup"><span data-stu-id="7c451-309">Features</span></span>

<span data-ttu-id="7c451-310">In diesem Tutorial verwenden Sie nur die drei `Features` (`user id`, `movie id` und `rating`), die vom Dataset bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7c451-310">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span>

<span data-ttu-id="7c451-311">Dies ist für den Anfang ausreichend. In einem echten Szenario sollten Sie jedoch weitere Attribute oder `Features` (beispielsweise Alter, Geschlecht, Standort usw.) hinzufügen, falls diese im Dataset enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7c451-311">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="7c451-312">Durch das Hinzufügen relevanter `Features` können Sie die Leistung des Empfehlungsmodells verbessern.</span><span class="sxs-lookup"><span data-stu-id="7c451-312">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span>

<span data-ttu-id="7c451-313">Wenn Sie nicht genau wissen, welche `Features` für Ihre Machine Learning-Aufgabe am relevantesten sind, können Sie auch die Methoden Feature Contribution Calculation (FCC) und [Permutation Feature Importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) verwenden, die ML.NET zur Ermittlung der wichtigsten `Features` bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7c451-313">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [permutation feature importance](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="7c451-314">Hyperparameter für Algorithmen</span><span class="sxs-lookup"><span data-stu-id="7c451-314">Algorithm hyperparameters</span></span>

<span data-ttu-id="7c451-315">ML.NET stellt viele effiziente Trainingsalgorithmen bereit. Sie können die Leistung allerdings noch weiter optimieren, indem Sie die [Hyperparameter](../resources/glossary.md#hyperparameter) des Algorithmus anpassen.</span><span class="sxs-lookup"><span data-stu-id="7c451-315">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="7c451-316">Bei `Matrix Factorization` können Sie mit Hyperparametern wie [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) und [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) experimentieren, um möglicherweise bessere Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="7c451-316">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="7c451-317">In diesem Tutorial werden beispielsweise folgende Algorithmusoptionen verwendet:</span><span class="sxs-lookup"><span data-stu-id="7c451-317">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="7c451-318">Weitere Empfehlungsalgorithmen</span><span class="sxs-lookup"><span data-stu-id="7c451-318">Other Recommendation Algorithms</span></span>

<span data-ttu-id="7c451-319">Der Algorithmus zur Matrixfaktorisierung mit kollaborativen Filtern ist nur eine Möglichkeit für Filmempfehlungen.</span><span class="sxs-lookup"><span data-stu-id="7c451-319">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="7c451-320">In vielen Fällen verfügen Sie möglicherweise nicht über die Bewertungsdaten, sondern nur über den Filmverlauf der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7c451-320">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="7c451-321">In anderen Fällen sind eventuell zusätzlich zu den Bewertungsdaten der Benutzer noch weitere Daten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7c451-321">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="7c451-322">Algorithmus</span><span class="sxs-lookup"><span data-stu-id="7c451-322">Algorithm</span></span>       | <span data-ttu-id="7c451-323">Szenario</span><span class="sxs-lookup"><span data-stu-id="7c451-323">Scenario</span></span>           | <span data-ttu-id="7c451-324">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c451-324">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="7c451-325">One Class Matrix Factorization (Matrixfaktorisierung mit einer Klasse)</span><span class="sxs-lookup"><span data-stu-id="7c451-325">One Class Matrix Factorization</span></span> | <span data-ttu-id="7c451-326">Verwenden Sie diesen Algorithmus, wenn nur userId und movieId zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7c451-326">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="7c451-327">Diese Empfehlungsstrategie wird für Szenarios eingesetzt, in denen Produkte oft zusammen gekauft werden. Kunden werden auf diese Weise empfohlene Produkte auf Grundlage des eigenen Bestellverlaufs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7c451-327">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="7c451-328">> Ausprobieren</span><span class="sxs-lookup"><span data-stu-id="7c451-328">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="7c451-329">Field Aware Factorization Machines (Faktorisierungsverfahren mit Berücksichtigung von Feldern)</span><span class="sxs-lookup"><span data-stu-id="7c451-329">Field Aware Factorization Machines</span></span> | <span data-ttu-id="7c451-330">Verwenden Sie diesen Algorithmus für Empfehlungen, wenn zusätzlich zur userId, productId und Bewertung noch weitere Features wie eine Produktbeschreibung oder ein Produktpreis vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7c451-330">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="7c451-331">Auch bei dieser Methode kommen kollaborative Filter zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="7c451-331">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="7c451-332">> Ausprobieren</span><span class="sxs-lookup"><span data-stu-id="7c451-332">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="7c451-333">Szenario mit neuen Benutzern</span><span class="sxs-lookup"><span data-stu-id="7c451-333">New user scenario</span></span>

<span data-ttu-id="7c451-334">Bei kollaborativen Filtern tritt häufig das sogenannte Kaltstartproblem auf. Hierbei müssen für neue Benutzer Rückschlüsse gezogen werden, obwohl noch keine Datengrundlage vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7c451-334">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="7c451-335">Das Problem wird oft dadurch gelöst, dass neue Benutzer aufgefordert werden, ein Profil zu erstellen und z. B. bereits gesehene Filme zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="7c451-335">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="7c451-336">Diese Methode stellt zwar für Benutzer einen gewissen Aufwand dar, liefert jedoch zumindest einige Startdaten für neue Benutzer ohne Bewertungsverlauf.</span><span class="sxs-lookup"><span data-stu-id="7c451-336">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="7c451-337">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7c451-337">Resources</span></span>

<span data-ttu-id="7c451-338">Die Daten aus diesem Tutorial stammen aus dem [MovieLens-Dataset](http://files.grouplens.org/datasets/movielens/).</span><span class="sxs-lookup"><span data-stu-id="7c451-338">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7c451-339">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7c451-339">Next steps</span></span>

<span data-ttu-id="7c451-340">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7c451-340">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="7c451-341">Auswählen eines Machine Learning-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="7c451-341">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="7c451-342">Vorbereiten und Laden von Daten</span><span class="sxs-lookup"><span data-stu-id="7c451-342">Prepare and load your data</span></span>
> * <span data-ttu-id="7c451-343">Erstellen und Trainieren eines Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-343">Build and train a model</span></span>
> * <span data-ttu-id="7c451-344">Auswerten eines Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-344">Evaluate a model</span></span>
> * <span data-ttu-id="7c451-345">Bereitstellen und Nutzen eines Modells</span><span class="sxs-lookup"><span data-stu-id="7c451-345">Deploy and consume a model</span></span>

<span data-ttu-id="7c451-346">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="7c451-346">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="7c451-347">Standpunktanalyse</span><span class="sxs-lookup"><span data-stu-id="7c451-347">Sentiment Analysis</span></span>](sentiment-analysis.md)
