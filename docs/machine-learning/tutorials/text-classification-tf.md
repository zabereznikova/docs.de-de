---
title: 'Tutorial: Analysieren der Überprüfungsstimmung mithilfe eines TensorFlow-Modells'
description: In diesem Tutorial wird gezeigt, wie Sie ein vortrainiertes TensorFlow-Modell verwenden, um die Stimmung in Websitekommentaren zu klassifizieren. Der binäre Stimmungsklassifizierer ist eine C#-Konsolenanwendung, die mit Visual Studio entwickelt wurde.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9c1e45f183bd5edc488e4f37bea648566d124c65
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803260"
---
# <a name="tutorial-analyze-sentiment-of-movie-reviews-using-a-pre-trained-tensorflow-model-in-mlnet"></a><span data-ttu-id="71a74-104">Tutorial: Analysieren der Stimmung von Filmkritiken mithilfe eines vortrainierten TensorFlow-Modells in ML.NET</span><span class="sxs-lookup"><span data-stu-id="71a74-104">Tutorial: Analyze sentiment of movie reviews using a pre-trained TensorFlow model in ML.NET</span></span>

<span data-ttu-id="71a74-105">In diesem Tutorial wird gezeigt, wie Sie ein vortrainiertes TensorFlow-Modell verwenden, um die Stimmung in Websitekommentaren zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="71a74-105">This tutorial shows you how to use a pre-trained TensorFlow model to classify sentiment in website comments.</span></span> <span data-ttu-id="71a74-106">Der binäre Stimmungsklassifizierer ist eine C#-Konsolenanwendung, die mit Visual Studio entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="71a74-106">The binary sentiment classifier is a C# console application developed using Visual Studio.</span></span>

<span data-ttu-id="71a74-107">Das in diesem Tutorial verwendete TensorFlow-Modell wurde mithilfe der Filmkritiken aus der IMDB-Datenbank trainiert.</span><span class="sxs-lookup"><span data-stu-id="71a74-107">The TensorFlow model used in this tutorial was trained using movie reviews from the IMDB database.</span></span> <span data-ttu-id="71a74-108">Sobald Sie die Entwicklung der Anwendung abgeschlossen haben, können Sie Filmkritiktext bereitstellen. Die Anwendung informiert Sie dann, ob die Rezension eine positive oder negative Stimmung hat.</span><span class="sxs-lookup"><span data-stu-id="71a74-108">Once you have finished developing the application, you will be able to supply movie review text and the application will tell you whether the review has positive or negative sentiment.</span></span>

<span data-ttu-id="71a74-109">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="71a74-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="71a74-110">Laden eines vortrainierten TensorFlow-Modells</span><span class="sxs-lookup"><span data-stu-id="71a74-110">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="71a74-111">Umwandeln von Websitekommentartext in für das Modell geeignete Merkmale</span><span class="sxs-lookup"><span data-stu-id="71a74-111">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="71a74-112">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="71a74-112">Use the model to make a prediction</span></span>

<span data-ttu-id="71a74-113">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="71a74-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71a74-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="71a74-114">Prerequisites</span></span>

* <span data-ttu-id="71a74-115">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“.</span><span class="sxs-lookup"><span data-stu-id="71a74-115">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="setup"></a><span data-ttu-id="71a74-116">Setup</span><span class="sxs-lookup"><span data-stu-id="71a74-116">Setup</span></span>

### <a name="create-the-application"></a><span data-ttu-id="71a74-117">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="71a74-117">Create the application</span></span>

1. <span data-ttu-id="71a74-118">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „TextClassificationTF“.</span><span class="sxs-lookup"><span data-stu-id="71a74-118">Create a **.NET Core Console Application** called "TextClassificationTF".</span></span>

2. <span data-ttu-id="71a74-119">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="71a74-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="71a74-120">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="71a74-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    <span data-ttu-id="71a74-121">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="71a74-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="71a74-122">Wählen Sie „nuget.org“ als Paketquelle aus und anschließend die Registerkarte **Durchsuchen**. Suchen Sie nach **Microsoft.ML**, wählen Sie das gewünschte Paket aus, und wählen Sie dann die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="71a74-122">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="71a74-123">Fahren Sie mit der Installation fort, indem Sie den Lizenzbedingungen für das von Ihnen gewählte Paket zustimmen.</span><span class="sxs-lookup"><span data-stu-id="71a74-123">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="71a74-124">Wiederholen Sie diese Schritte für **Microsoft.ML.TensorFlow**, **Microsoft.ML.SampleUtils** und **SciSharp.TensorFlow.Redist**.</span><span class="sxs-lookup"><span data-stu-id="71a74-124">Repeat these steps for **Microsoft.ML.TensorFlow**, **Microsoft.ML.SampleUtils** and **SciSharp.TensorFlow.Redist**.</span></span>

### <a name="add-the-tensorflow-model-to-the-project"></a><span data-ttu-id="71a74-125">Hinzufügen des TensorFlow-Modells zum Projekt</span><span class="sxs-lookup"><span data-stu-id="71a74-125">Add the TensorFlow model to the project</span></span>

> [!NOTE]
> <span data-ttu-id="71a74-126">Das Modell für dieses Tutorial stammt aus dem GitHub-Repository [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model).</span><span class="sxs-lookup"><span data-stu-id="71a74-126">The model for this tutorial is from the [dotnet/machinelearning-testdata](https://github.com/dotnet/machinelearning-testdata/tree/master/Microsoft.ML.TensorFlow.TestModels/sentiment_model) GitHub repo.</span></span> <span data-ttu-id="71a74-127">Das Modell weist das SavedModel-Format von TensorFlow auf.</span><span class="sxs-lookup"><span data-stu-id="71a74-127">The model is in TensorFlow SavedModel format.</span></span>

1. <span data-ttu-id="71a74-128">Laden Sie die ZIP-Datei [sentiment_model](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true) herunter, und entpacken Sie sie.</span><span class="sxs-lookup"><span data-stu-id="71a74-128">Download the [sentiment_model zip file](https://github.com/dotnet/samples/blob/master/machine-learning/models/textclassificationtf/sentiment_model.zip?raw=true), and unzip.</span></span>

    <span data-ttu-id="71a74-129">Die ZIP-Datei enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="71a74-129">The zip file contains:</span></span>

    * <span data-ttu-id="71a74-130">`saved_model.pb`: Das TensorFlow-Modell selbst.</span><span class="sxs-lookup"><span data-stu-id="71a74-130">`saved_model.pb`: the TensorFlow model itself.</span></span> <span data-ttu-id="71a74-131">Das Modell nimmt ein Integerarray mit einer festen Länge (Größe 600) von Merkmalen an, die den Text in einer IMDB-Kritikzeichenfolge darstellen, und gibt zwei Wahrscheinlichkeiten aus, die die Summe 1 bilden: die Wahrscheinlichkeit, dass die Eingabekritik eine positive Stimmung aufweist, und die Wahrscheinlichkeit, dass die Eingabekritik eine negative Stimmung hat.</span><span class="sxs-lookup"><span data-stu-id="71a74-131">The model takes a fixed length (size 600) integer array of features representing the text in an IMDB review string, and outputs two probabilities which sum to 1: the probability that the input review has positive sentiment, and the probability that the input review has negative sentiment.</span></span>
    * <span data-ttu-id="71a74-132">`imdb_word_index.csv`: Eine Zuordnung von einzelnen Wörtern zu einem ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="71a74-132">`imdb_word_index.csv`: a mapping from individual words to an integer value.</span></span> <span data-ttu-id="71a74-133">Die Zuordnung wird verwendet, um die Eingabemerkmale für das TensorFlow-Modell zu generieren.</span><span class="sxs-lookup"><span data-stu-id="71a74-133">The mapping is used to generate the input features for the TensorFlow model.</span></span>

2. <span data-ttu-id="71a74-134">Kopieren Sie den Inhalt des innersten `sentiment_model`-Verzeichnisses in Ihr *TextClassificationTF*-Projektverzeichnis `sentiment_model`.</span><span class="sxs-lookup"><span data-stu-id="71a74-134">Copy the contents of the innermost `sentiment_model` directory into your *TextClassificationTF* project `sentiment_model` directory.</span></span> <span data-ttu-id="71a74-135">Dieses Verzeichnis enthält das Modell und die zusätzlich für dieses Tutorial erforderlichen Unterstützungsdateien wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="71a74-135">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inhalt des Verzeichnisses „sentiment_model“](./media/text-classification-tf/sentiment-model-files.png)

3. <span data-ttu-id="71a74-137">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf jede Datei im Verzeichnis `sentiment_model`und im Unterverzeichnis, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="71a74-137">In Solution Explorer, right-click each of the files in the `sentiment_model` directory and subdirectory and select **Properties**.</span></span> <span data-ttu-id="71a74-138">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="71a74-138">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="add-using-statements-and-global-variables"></a><span data-ttu-id="71a74-139">Hinzufügen von using-Anweisungen und globalen Variablen</span><span class="sxs-lookup"><span data-stu-id="71a74-139">Add using statements and global variables</span></span>

1. <span data-ttu-id="71a74-140">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="71a74-140">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

   [!code-csharp[AddUsings](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="71a74-141">Erstellen Sie zwei globale Variablen direkt über der `Main`-Methode, um den gespeicherten Pfad der Modelldatei sowie die Länge des Merkmalsvektors aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="71a74-141">Create two global variables right above the `Main` method to hold the saved model file path, and the feature vector length.</span></span>

   [!code-csharp[DeclareGlobalVariables](../../../samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

    * <span data-ttu-id="71a74-142">`_modelPath` ist der Dateipfad des trainierten Modells.</span><span class="sxs-lookup"><span data-stu-id="71a74-142">`_modelPath` is the file path of the trained model.</span></span>
    * <span data-ttu-id="71a74-143">`FeatureLength` ist die Länge des ganzzahligen Merkmalsarrays, das vom Modell erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="71a74-143">`FeatureLength` is the length of the integer feature array that the model is expecting.</span></span>

### <a name="model-the-data"></a><span data-ttu-id="71a74-144">Modellieren der Daten</span><span class="sxs-lookup"><span data-stu-id="71a74-144">Model the data</span></span>

<span data-ttu-id="71a74-145">Filmkritiken sind Freiformtext.</span><span class="sxs-lookup"><span data-stu-id="71a74-145">Movie reviews are free form text.</span></span> <span data-ttu-id="71a74-146">Ihre Anwendung konvertiert den Text in das vom Modell erwartete Eingabeformat in einer Reihe diskreter Schritte.</span><span class="sxs-lookup"><span data-stu-id="71a74-146">Your application converts the text into the input format expected by the model in a number of discrete stages.</span></span>

<span data-ttu-id="71a74-147">Der erste besteht darin, den Text in separate Wörter aufzuteilen und die bereitgestellte Zuordnungsdatei zu verwenden, um jedes Wort einer ganzzahligen Codierung zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="71a74-147">The first is to split the text into separate words and use the provided mapping file to map each word onto an integer encoding.</span></span> <span data-ttu-id="71a74-148">Das Ergebnis dieser Transformation ist ein Intergerarray variabler Länge mit einer Länge, die der Anzahl der Wörter im Satz entspricht.</span><span class="sxs-lookup"><span data-stu-id="71a74-148">The result of this transformation is a variable length integer array with a length corresponding to the number of words in the sentence.</span></span>

|<span data-ttu-id="71a74-149">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="71a74-149">Property</span></span>| <span data-ttu-id="71a74-150">Wert</span><span class="sxs-lookup"><span data-stu-id="71a74-150">Value</span></span>|<span data-ttu-id="71a74-151">Typ</span><span class="sxs-lookup"><span data-stu-id="71a74-151">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="71a74-152">ReviewText</span><span class="sxs-lookup"><span data-stu-id="71a74-152">ReviewText</span></span>|<span data-ttu-id="71a74-153">this film is really good</span><span class="sxs-lookup"><span data-stu-id="71a74-153">this film is really good</span></span>|<span data-ttu-id="71a74-154">string</span><span class="sxs-lookup"><span data-stu-id="71a74-154">string</span></span>|
|<span data-ttu-id="71a74-155">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="71a74-155">VariableLengthFeatures</span></span>|<span data-ttu-id="71a74-156">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="71a74-156">14,22,9,66,78,...</span></span> |<span data-ttu-id="71a74-157">int[]</span><span class="sxs-lookup"><span data-stu-id="71a74-157">int[]</span></span>|

<span data-ttu-id="71a74-158">Die Größe des Merkmalsarrays variabler Länge wird dann in eine feste Länge von 600 geändert.</span><span class="sxs-lookup"><span data-stu-id="71a74-158">The variable length feature array is then resized to a fixed length of 600.</span></span> <span data-ttu-id="71a74-159">Dies ist die Länge, die das TensorFlow-Modell erwartet.</span><span class="sxs-lookup"><span data-stu-id="71a74-159">This is the length that the TensorFlow model expects.</span></span>

|<span data-ttu-id="71a74-160">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="71a74-160">Property</span></span>| <span data-ttu-id="71a74-161">Wert</span><span class="sxs-lookup"><span data-stu-id="71a74-161">Value</span></span>|<span data-ttu-id="71a74-162">Typ</span><span class="sxs-lookup"><span data-stu-id="71a74-162">Type</span></span>|
|-------------|-----------------------|------|
|<span data-ttu-id="71a74-163">ReviewText</span><span class="sxs-lookup"><span data-stu-id="71a74-163">ReviewText</span></span>|<span data-ttu-id="71a74-164">this film is really good</span><span class="sxs-lookup"><span data-stu-id="71a74-164">this film is really good</span></span>|<span data-ttu-id="71a74-165">string</span><span class="sxs-lookup"><span data-stu-id="71a74-165">string</span></span>|
|<span data-ttu-id="71a74-166">VariableLengthFeatures</span><span class="sxs-lookup"><span data-stu-id="71a74-166">VariableLengthFeatures</span></span>|<span data-ttu-id="71a74-167">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="71a74-167">14,22,9,66,78,...</span></span> |<span data-ttu-id="71a74-168">int[]</span><span class="sxs-lookup"><span data-stu-id="71a74-168">int[]</span></span>|
|<span data-ttu-id="71a74-169">Features</span><span class="sxs-lookup"><span data-stu-id="71a74-169">Features</span></span>|<span data-ttu-id="71a74-170">14,22,9,66,78,...</span><span class="sxs-lookup"><span data-stu-id="71a74-170">14,22,9,66,78,...</span></span> |<span data-ttu-id="71a74-171">int[600]</span><span class="sxs-lookup"><span data-stu-id="71a74-171">int[600]</span></span>|

1. <span data-ttu-id="71a74-172">Erstellen Sie eine Klasse für Ihre Eingabedaten nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="71a74-172">Create a class for your input data, after the `Main` method:</span></span>

    [!code-csharp[MovieReviewClass](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MovieReviewClass "Declare movie review type")]

    <span data-ttu-id="71a74-173">Die Eingabedatenklasse (`MovieReview`) verfügt über ein `string`-Element für Benutzerkommentare (`ReviewText`).</span><span class="sxs-lookup"><span data-stu-id="71a74-173">The input data class, `MovieReview`, has a `string` for user comments (`ReviewText`).</span></span>

1. <span data-ttu-id="71a74-174">Erstellen Sie nach der `Main`-Methode eine Klasse für die Merkmale mit variabler Länge:</span><span class="sxs-lookup"><span data-stu-id="71a74-174">Create a class for the variable length features, after the `Main` method:</span></span>

    [!code-csharp[VariableLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#VariableLengthFeatures "Declare variable length features type")]

    <span data-ttu-id="71a74-175">Die `VariableLengthFeatures`-Eigenschaft verfügt über ein Attribut [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A), um sie als Vektor festzulegen.</span><span class="sxs-lookup"><span data-stu-id="71a74-175">The `VariableLengthFeatures` property has a [VectorType](xref:Microsoft.ML.Data.VectorTypeAttribute.%23ctor%2A) attribute to designate it as a vector.</span></span>  <span data-ttu-id="71a74-176">Alle Vektorelemente müssen denselben Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="71a74-176">All of the vector elements must be the same type.</span></span> <span data-ttu-id="71a74-177">In Datasets mit einer großen Anzahl von Spalten verringert das Laden mehrerer Spalten als einzelner Vektor die Anzahl der Datenübergabevorgänge, wenn Sie Datentransformationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="71a74-177">In data sets with a large number of columns, loading multiple columns as a single vector reduces the number of data passes when you apply data transformations.</span></span>

    <span data-ttu-id="71a74-178">Diese Klasse wird in der `ResizeFeatures`-Aktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="71a74-178">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="71a74-179">Die Namen ihrer Eigenschaften (in diesem Fall nur ein Name) werden verwendet, um anzugeben, welche Spalten in der DataView als _Eingabe_ für die benutzerdefinierte Zuordnungsaktion verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="71a74-179">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _input_ to the custom mapping action.</span></span>

1. <span data-ttu-id="71a74-180">Erstellen Sie nach der `Main`-Methode eine Klasse für die Merkmale mit fester Länge:</span><span class="sxs-lookup"><span data-stu-id="71a74-180">Create a class for the fixed length features, after the `Main` method:</span></span>

    [!code-csharp[FixedLengthFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#FixedLengthFeatures)]

    <span data-ttu-id="71a74-181">Diese Klasse wird in der `ResizeFeatures`-Aktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="71a74-181">This class is used in the `ResizeFeatures` action.</span></span> <span data-ttu-id="71a74-182">Die Namen ihrer Eigenschaften (in diesem Fall nur ein Name) werden verwendet, um anzugeben, welche Spalten in der DataView als _Ausgabe_ für die benutzerdefinierte Zuordnungsaktion verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="71a74-182">The names of its properties (in this case only one) are used to indicate which columns in the DataView can be used as the _output_ of the custom mapping action.</span></span>

    <span data-ttu-id="71a74-183">Beachten Sie, dass der Name der `Features`-Eigenschaft durch das TensorFlow-Modell bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="71a74-183">Note that the name of the property `Features` is determined by the TensorFlow model.</span></span> <span data-ttu-id="71a74-184">Der Name dieser Eigenschaft kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="71a74-184">You cannot change this property name.</span></span>

1. <span data-ttu-id="71a74-185">Erstellen Sie eine Klasse für die Vorhersage nach der `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="71a74-185">Create a class for the prediction after the `Main` method:</span></span>

    [!code-csharp[Prediction](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Prediction "Declare prediction class")]

    <span data-ttu-id="71a74-186">`MovieReviewSentimentPrediction` ist die nach dem Modelltraining verwendete Vorhersageklasse.</span><span class="sxs-lookup"><span data-stu-id="71a74-186">`MovieReviewSentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="71a74-187">`MovieReviewSentimentPrediction` weist ein einzelnes `float`-Array (`Prediction`) und ein `VectorType`-Attribut auf.</span><span class="sxs-lookup"><span data-stu-id="71a74-187">`MovieReviewSentimentPrediction` has a single `float` array (`Prediction`) and a `VectorType` attribute.</span></span>

### <a name="create-the-mlcontext-lookup-dictionary-and-action-to-resize-features"></a><span data-ttu-id="71a74-188">Erstellen von der MLContext-Klasse, des Nachschlagewörterbuchs und der Aktion zum Ändern der Größe von Merkmalen</span><span class="sxs-lookup"><span data-stu-id="71a74-188">Create the MLContext, lookup dictionary, and action to resize features</span></span>

<span data-ttu-id="71a74-189">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Ausgangspunkt für alle ML.NET-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="71a74-189">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="71a74-190">Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="71a74-190">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="71a74-191">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="71a74-191">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

1. <span data-ttu-id="71a74-192">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die mlContext-Variable zu deklarieren und zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="71a74-192">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

   [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateMLContext "Create the ML Context")]

1. <span data-ttu-id="71a74-193">Erstellen Sie ein Wörterbuch, um Wörter als Integerwerte zu codieren, indem Sie die [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A)-Methode zum Laden von Zuordnungsdaten aus einer Datei verwenden, wie in der folgenden Tabelle gezeigt:</span><span class="sxs-lookup"><span data-stu-id="71a74-193">Create a dictionary to encode words as integers by using the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A) method to load mapping data from a file, as seen in the following table:</span></span>

    |<span data-ttu-id="71a74-194">Word</span><span class="sxs-lookup"><span data-stu-id="71a74-194">Word</span></span>     |<span data-ttu-id="71a74-195">Index</span><span class="sxs-lookup"><span data-stu-id="71a74-195">Index</span></span>    |
    |---------|---------|
    |<span data-ttu-id="71a74-196">kids</span><span class="sxs-lookup"><span data-stu-id="71a74-196">kids</span></span>     |  <span data-ttu-id="71a74-197">362</span><span class="sxs-lookup"><span data-stu-id="71a74-197">362</span></span>    |
    |<span data-ttu-id="71a74-198">want</span><span class="sxs-lookup"><span data-stu-id="71a74-198">want</span></span>     |  <span data-ttu-id="71a74-199">181</span><span class="sxs-lookup"><span data-stu-id="71a74-199">181</span></span>    |
    |<span data-ttu-id="71a74-200">wrong</span><span class="sxs-lookup"><span data-stu-id="71a74-200">wrong</span></span>    |  <span data-ttu-id="71a74-201">355</span><span class="sxs-lookup"><span data-stu-id="71a74-201">355</span></span>    |
    |<span data-ttu-id="71a74-202">effects</span><span class="sxs-lookup"><span data-stu-id="71a74-202">effects</span></span>  |  <span data-ttu-id="71a74-203">302</span><span class="sxs-lookup"><span data-stu-id="71a74-203">302</span></span>    |
    |<span data-ttu-id="71a74-204">feeling</span><span class="sxs-lookup"><span data-stu-id="71a74-204">feeling</span></span>  |  <span data-ttu-id="71a74-205">547</span><span class="sxs-lookup"><span data-stu-id="71a74-205">547</span></span>    |

    <span data-ttu-id="71a74-206">Fügen Sie den folgenden Code hinzu, um die Nachschlagezuordnung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="71a74-206">Add the code below to create the lookup map:</span></span>

    [!code-csharp[CreateLookupMap](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateLookupMap)]

1. <span data-ttu-id="71a74-207">Fügen Sie mit den nächsten Codezeilen eine `Action` hinzu, um die Größe des Wortintegerarrays variabler Länge in ein Integerarray fester Größe zu ändern:</span><span class="sxs-lookup"><span data-stu-id="71a74-207">Add an `Action` to resize the variable length word integer array to an integer array of fixed size, with the next lines of code:</span></span>

   [!code-csharp[ResizeFeatures](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ResizeFeatures)]

## <a name="load-the-pre-trained-tensorflow-model"></a><span data-ttu-id="71a74-208">Laden des vortrainierten TensorFlow-Modells</span><span class="sxs-lookup"><span data-stu-id="71a74-208">Load the pre-trained TensorFlow model</span></span>

1. <span data-ttu-id="71a74-209">Fügen Sie Code hinzu, um das TensorFlow-Modell zu laden:</span><span class="sxs-lookup"><span data-stu-id="71a74-209">Add code to load the TensorFlow model:</span></span>

    [!code-csharp[LoadTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#LoadTensorFlowModel)]

    <span data-ttu-id="71a74-210">Nachdem das Modell geladen wurde, können Sie sein Eingabe- und Ausgabeschema extrahieren.</span><span class="sxs-lookup"><span data-stu-id="71a74-210">Once the model is loaded, you can extract its input and output schema.</span></span> <span data-ttu-id="71a74-211">Die Schemas werden nur aus Interesse und zu Lernzwecken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71a74-211">The schemas are displayed for interest and learning only.</span></span> <span data-ttu-id="71a74-212">Sie benötigen diesen Code nicht, damit die endgültige Anwendung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="71a74-212">You do not need this code for the final application to function:</span></span>

    [!code-csharp[GetModelSchema](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#GetModelSchema)]

    <span data-ttu-id="71a74-213">Das Eingabeschema ist das Array fester Länge von ganzzahlig codierten Wörtern.</span><span class="sxs-lookup"><span data-stu-id="71a74-213">The input schema is the fixed-length array of integer encoded words.</span></span> <span data-ttu-id="71a74-214">Das Ausgabeschema ist ein Floatarray von Wahrscheinlichkeiten, das angibt, ob die Stimmung einer Kritik negativ oder positiv ist.</span><span class="sxs-lookup"><span data-stu-id="71a74-214">The output schema is a float array of probabilities indicating whether a review's sentiment is negative, or positive .</span></span> <span data-ttu-id="71a74-215">Die Summe dieser Werte ist 1, da die Wahrscheinlichkeit, dass die Kritik positiv ist, das Komplement für die Wahrscheinlichkeit ist, dass die Stimmung negativ ist.</span><span class="sxs-lookup"><span data-stu-id="71a74-215">These values sum to 1, as the probability of being positive is the complement of the probability of the sentiment being negative.</span></span>

## <a name="create-the-mlnet-pipeline"></a><span data-ttu-id="71a74-216">Erstellen der ML.NET-Pipeline</span><span class="sxs-lookup"><span data-stu-id="71a74-216">Create the ML.NET pipeline</span></span>

1. <span data-ttu-id="71a74-217">Erstellen Sie die Pipeline, und teilen Sie den Eingabetext mithilfe der Transformation [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) in der nächsten Codezeile in Wörter auf:</span><span class="sxs-lookup"><span data-stu-id="71a74-217">Create the pipeline and split the input text into words using [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform to break the text into words as the next line of code:</span></span>

   [!code-csharp[TokenizeIntoWords](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#TokenizeIntoWords)]

   <span data-ttu-id="71a74-218">Die Transformation [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) verwendet Leerzeichen, um den Text bzw. die Zeichenfolge in Wörter zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="71a74-218">The [TokenizeIntoWords](xref:Microsoft.ML.TextCatalog.TokenizeIntoWords%2A) transform uses spaces to parse the text/string into words.</span></span> <span data-ttu-id="71a74-219">Sie erstellt eine neue Spalte und teilt jede Eingabezeichenfolge in einen Vektor von Teilzeichenfolgen basierend auf dem benutzerdefinierten Trennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="71a74-219">It creates a new column and splits each input string to a vector of substrings based on the user-defined separator.</span></span>

1. <span data-ttu-id="71a74-220">Ordnen Sie die Wörter mithilfe der Nachschlagetabelle, die Sie oben deklariert haben, ihrer Integercodierung zu:</span><span class="sxs-lookup"><span data-stu-id="71a74-220">Map the words onto their integer encoding using the lookup table that you declared above:</span></span>

    [!code-csharp[MapValue](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#MapValue)]

1. <span data-ttu-id="71a74-221">Ändern Sie die Größe der Integercodierungen variabler Länge in die für das Modell erforderliche feste Länge:</span><span class="sxs-lookup"><span data-stu-id="71a74-221">Resize the variable length integer encodings to the fixed-length one required by the model:</span></span>

    [!code-csharp[CustomMapping](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CustomMapping)]

1. <span data-ttu-id="71a74-222">Klassifizieren Sie die Eingabe mit dem geladenen TensorFlow-Modell:</span><span class="sxs-lookup"><span data-stu-id="71a74-222">Classify the input with the loaded TensorFlow model:</span></span>

    [!code-csharp[ScoreTensorFlowModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="71a74-223">Die Ausgabe des TensorFlow-Modells wird als `Prediction/Softmax` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="71a74-223">The TensorFlow model output is called `Prediction/Softmax`.</span></span> <span data-ttu-id="71a74-224">Beachten Sie, dass der Name `Prediction/Softmax` durch das TensorFlow-Modell bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="71a74-224">Note that the name `Prediction/Softmax` is determined by the TensorFlow model.</span></span> <span data-ttu-id="71a74-225">Dieser Name kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="71a74-225">You cannot change this name.</span></span>

1. <span data-ttu-id="71a74-226">Erstellen Sie eine neue Spalte für die Ausgabevorhersage:</span><span class="sxs-lookup"><span data-stu-id="71a74-226">Create a new column for the output prediction:</span></span>

    [!code-csharp[SnippetCopyColumns](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCopyColumns)]

    <span data-ttu-id="71a74-227">Sie müssen die `Prediction/Softmax`-Spalte in eine Spalte mit einem Namen kopieren, der als Eigenschaft in einer C#-Klasse verwendet werden kann: `Prediction`.</span><span class="sxs-lookup"><span data-stu-id="71a74-227">You need to copy the `Prediction/Softmax` column into one with a name that can be used as a property in a C# class: `Prediction`.</span></span> <span data-ttu-id="71a74-228">Das Zeichen `/` ist in einem C# Eigenschaftsnamen unzulässig.</span><span class="sxs-lookup"><span data-stu-id="71a74-228">The `/` character is not allowed in a C# property name.</span></span>

## <a name="create-the-mlnet-model-from-the-pipeline"></a><span data-ttu-id="71a74-229">Erstellen des ML.NET-Modells aus der Pipeline</span><span class="sxs-lookup"><span data-stu-id="71a74-229">Create the ML.NET model from the pipeline</span></span>

1. <span data-ttu-id="71a74-230">Fügen Sie den Code hinzu, um das Modell aus der Pipeline zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="71a74-230">Add the code to create the model from the pipeline:</span></span>

    [!code-csharp[SnippetCreateModel](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#SnippetCreateModel)]

    <span data-ttu-id="71a74-231">Ein ML.NET-Modell wird aus der Kette der Kalkulatoren in der Pipeline erstellt, indem die `Fit`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="71a74-231">An ML.NET model is created from the chain of estimators in the pipeline by calling the `Fit` method.</span></span> <span data-ttu-id="71a74-232">In diesem Fall passen wir keine Daten an, um das Modell zu erstellen, da das TensorFlow-Modell bereits vortrainiert wurde.</span><span class="sxs-lookup"><span data-stu-id="71a74-232">In this case, we are not fitting any data to create the model, as the TensorFlow model has already been previously trained.</span></span> <span data-ttu-id="71a74-233">Wir stellen ein leeres Datenansichtsobjekt bereit, um die Anforderungen der `Fit`-Methode zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="71a74-233">We supply an empty data view object to satisfy the requirements of the `Fit` method.</span></span>

## <a name="use-the-model-to-make-a-prediction"></a><span data-ttu-id="71a74-234">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="71a74-234">Use the model to make a prediction</span></span>

1. <span data-ttu-id="71a74-235">Fügen Sie die `PredictSentiment`-Methode unter der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="71a74-235">Add the `PredictSentiment` method below the `Main` method:</span></span>

    ```csharp
    public static void PredictSentiment(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="71a74-236">Fügen wir den folgenden Code hinzu, um die `PredictionEngine` als erste Zeile in der `PredictSentiment()`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="71a74-236">Add the following code to create the `PredictionEngine` as the first line in the `PredictSentiment()` method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreatePredictionEngine)]

    <span data-ttu-id="71a74-237">Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können.</span><span class="sxs-lookup"><span data-stu-id="71a74-237">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="71a74-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="71a74-238">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="71a74-239">Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="71a74-239">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="71a74-240">Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="71a74-240">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="71a74-241">Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.</span><span class="sxs-lookup"><span data-stu-id="71a74-241">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="71a74-242">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="71a74-242">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="71a74-243">Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `Predict()`-Methode zu testen, indem Sie eine `MovieReview`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="71a74-243">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `MovieReview`:</span></span>

    [!code-csharp[CreateTestData](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CreateTestData)]

1. <span data-ttu-id="71a74-244">Übergeben Sie die Testkommentardaten an die `Prediction Engine`, indem Sie die folgenden Codezeilen in der `PredictSentiment()`-Methode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="71a74-244">Pass the test comment data to the `Prediction Engine` by adding the next lines of code in the `PredictSentiment()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#Predict)]

1. <span data-ttu-id="71a74-245">Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenzeile:</span><span class="sxs-lookup"><span data-stu-id="71a74-245">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data:</span></span>

    |<span data-ttu-id="71a74-246">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="71a74-246">Property</span></span>| <span data-ttu-id="71a74-247">Wert</span><span class="sxs-lookup"><span data-stu-id="71a74-247">Value</span></span>|<span data-ttu-id="71a74-248">Typ</span><span class="sxs-lookup"><span data-stu-id="71a74-248">Type</span></span>|
    |-------------|-----------------------|------|
    |<span data-ttu-id="71a74-249">Vorhersage</span><span class="sxs-lookup"><span data-stu-id="71a74-249">Prediction</span></span>|<span data-ttu-id="71a74-250">[0,5459937, 0,454006255]</span><span class="sxs-lookup"><span data-stu-id="71a74-250">[0.5459937, 0.454006255]</span></span>|<span data-ttu-id="71a74-251">float[]</span><span class="sxs-lookup"><span data-stu-id="71a74-251">float[]</span></span>|

1. <span data-ttu-id="71a74-252">Mithilfe des folgenden Codes können Sie die Stimmungsvorhersage anzeigen:</span><span class="sxs-lookup"><span data-stu-id="71a74-252">Display sentiment prediction using the following code:</span></span>

    [!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#DisplayPredictions)]

1. <span data-ttu-id="71a74-253">Fügen Sie am Ende der `Main`-Methode einen Aufruf von `PredictSentiment` hinzu:</span><span class="sxs-lookup"><span data-stu-id="71a74-253">Add a call to `PredictSentiment` at the end of the `Main` method:</span></span>

    [!code-csharp[CallPredictSentiment](~/samples/snippets/machine-learning/TextClassificationTF/csharp/Program.cs#CallPredictSentiment)]

## <a name="results"></a><span data-ttu-id="71a74-254">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="71a74-254">Results</span></span>

<span data-ttu-id="71a74-255">Erstellen Sie Ihre Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="71a74-255">Build and run your application.</span></span>

<span data-ttu-id="71a74-256">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="71a74-256">Your results should be similar to the following.</span></span> <span data-ttu-id="71a74-257">Während der Verarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71a74-257">During processing, messages are displayed.</span></span> <span data-ttu-id="71a74-258">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="71a74-258">You may see warnings, or processing messages.</span></span> <span data-ttu-id="71a74-259">Diese Nachrichten wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="71a74-259">These messages have been removed from the following results for clarity.</span></span>

```console
Number of classes: 2
Is sentiment/review positive ? Yes
```

<span data-ttu-id="71a74-260">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="71a74-260">Congratulations!</span></span> <span data-ttu-id="71a74-261">Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Stimmungen in Mitteilungen durch die Wiederverwendung eines vortrainierten `TensorFlow`-Modells in ML.NET erstellt.</span><span class="sxs-lookup"><span data-stu-id="71a74-261">You've now successfully built a machine learning model for classifying and predicting messages sentiment by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="71a74-262">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF).</span><span class="sxs-lookup"><span data-stu-id="71a74-262">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TextClassificationTF) repository.</span></span>

<span data-ttu-id="71a74-263">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="71a74-263">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="71a74-264">Laden eines vortrainierten TensorFlow-Modells</span><span class="sxs-lookup"><span data-stu-id="71a74-264">Load a pre-trained TensorFlow model</span></span>
> * <span data-ttu-id="71a74-265">Umwandeln von Websitekommentartext in für das Modell geeignete Merkmale</span><span class="sxs-lookup"><span data-stu-id="71a74-265">Transform website comment text into features suitable for the model</span></span>
> * <span data-ttu-id="71a74-266">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="71a74-266">Use the model to make a prediction</span></span>
