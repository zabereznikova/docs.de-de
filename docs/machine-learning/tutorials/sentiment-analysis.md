---
title: 'Tutorial: Analysieren von Websitekommentaren – binäre Klassifizierung'
description: Dieses Tutorial zeigt Ihnen, wie Sie eine .NET Core-Konsolenanwendung erstellen, die den Standpunkt in Websitekommentaren klassifiziert und die entsprechenden Maßnahmen ergreift. Die binäre Standpunktklassifizierung verwendet C# in Visual Studio.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 1b5a3f6c7d70c95916b99d386924347642e6d7e3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974774"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="4e91b-104">Tutorial: Standpunktanalyse für Websitekommentare mit binärer Klassifikation in ML.NET</span><span class="sxs-lookup"><span data-stu-id="4e91b-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="4e91b-105">Dieses Tutorial zeigt Ihnen, wie Sie eine .NET Core-Konsolenanwendung erstellen, die den Standpunkt in Websitekommentaren klassifiziert und die entsprechenden Maßnahmen ergreift.</span><span class="sxs-lookup"><span data-stu-id="4e91b-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="4e91b-106">Die binäre Standpunktklassifizierung verwendet C# in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="4e91b-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="4e91b-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4e91b-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="4e91b-108">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4e91b-108">Create a console application</span></span>
> - <span data-ttu-id="4e91b-109">Vorbereiten von Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-109">Prepare data</span></span>
> - <span data-ttu-id="4e91b-110">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-110">Load the data</span></span>
> - <span data-ttu-id="4e91b-111">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-111">Build and train the model</span></span>
> - <span data-ttu-id="4e91b-112">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-112">Evaluate the model</span></span>
> - <span data-ttu-id="4e91b-113">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="4e91b-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="4e91b-114">Anzeigen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="4e91b-114">See the results</span></span>

<span data-ttu-id="4e91b-115">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="4e91b-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e91b-116">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="4e91b-116">Prerequisites</span></span>

- <span data-ttu-id="4e91b-117">[Visual Studio 2017 Version 15.6 oder höher](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit installierter Workload „Plattformübergreifende .NET Core-Entwicklung“</span><span class="sxs-lookup"><span data-stu-id="4e91b-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="4e91b-118">[Dataset „UCI Sentiment Labeled Sentences“](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP-Datei)</span><span class="sxs-lookup"><span data-stu-id="4e91b-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="4e91b-119">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4e91b-119">Create a console application</span></span>

1. <span data-ttu-id="4e91b-120">Erstellen Sie eine **.NET Core-Konsolenanwendung** mit dem Namen „SentimentAnalysis“.</span><span class="sxs-lookup"><span data-stu-id="4e91b-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="4e91b-121">Erstellen Sie ein Verzeichnis mit dem Namen *Data* in Ihrem Projekt, um die Datasetdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4e91b-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="4e91b-122">Installieren des **Microsoft.ML NuGet-Pakets**:</span><span class="sxs-lookup"><span data-stu-id="4e91b-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="4e91b-123">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="4e91b-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4e91b-124">Wählen Sie „nuget.org“ als Paketquelle aus und anschließend die Registerkarte **Durchsuchen**. Suchen Sie nach **Microsoft.ML**, wählen Sie das gewünschte Paket aus, und wählen Sie dann die Schaltfläche **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="4e91b-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="4e91b-125">Fahren Sie mit der Installation fort, indem Sie den Lizenzbedingungen für das von Ihnen gewählte Paket zustimmen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="4e91b-126">Gehen Sie für das NuGet-Paket **Microsoft.ML.FastTreee** genauso vor.</span><span class="sxs-lookup"><span data-stu-id="4e91b-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="4e91b-127">Vorbereiten Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="4e91b-128">Die für dieses Tutorial verwendeten Datasets stammen aus „From Group to Individual Labels using Deep Features“, Kotzias et.</span><span class="sxs-lookup"><span data-stu-id="4e91b-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="4e91b-129">al.,</span><span class="sxs-lookup"><span data-stu-id="4e91b-129">al,.</span></span> <span data-ttu-id="4e91b-130">KDD 2015, und werden im UCI Machine Learning Repository – Dua, D. und Karra Taniskidou, E. gehostet. (2017).</span><span class="sxs-lookup"><span data-stu-id="4e91b-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="4e91b-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml ].</span><span class="sxs-lookup"><span data-stu-id="4e91b-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="4e91b-132">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="4e91b-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="4e91b-133">Laden Sie die ZIP-Datei des [Datasets „UCI Sentiment Labeled Sentences“](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) herunter, und entzippen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="4e91b-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="4e91b-134">Kopieren Sie die `yelp_labelled.txt`-Datei in das Verzeichnis *Data*, das Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4e91b-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="4e91b-135">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die Datei `yelp_labeled.txt`, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="4e91b-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="4e91b-136">Ändern Sie unter **Erweitert** den Wert von **In Ausgabeverzeichnis kopieren** in **Kopieren, wenn neuer**.</span><span class="sxs-lookup"><span data-stu-id="4e91b-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="4e91b-137">Erstellen von Klassen und Definieren von Pfaden</span><span class="sxs-lookup"><span data-stu-id="4e91b-137">Create classes and define paths</span></span>

1. <span data-ttu-id="4e91b-138">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="4e91b-139">Fügen Sie den folgenden Code in der Zeile direkt über der `Main`-Methode hinzu, um ein Feld zu erstellen, das den Dateipfad des zuletzt heruntergeladenen Datasets enthält:</span><span class="sxs-lookup"><span data-stu-id="4e91b-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="4e91b-140">Erstellen Sie anschließend Klassen für Ihre Eingabedaten und Vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="4e91b-141">Fügen Sie dem Projekt eine neue Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="4e91b-142">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie dann **Hinzufügen** > **Neues Element** aus.</span><span class="sxs-lookup"><span data-stu-id="4e91b-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="4e91b-143">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Option **Klasse** aus, und ändern Sie das Feld **Name** in *SentimentData.cs*.</span><span class="sxs-lookup"><span data-stu-id="4e91b-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="4e91b-144">Wählen Sie dann die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4e91b-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="4e91b-145">Die Datei *SentimentData.cs* wird im Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4e91b-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="4e91b-146">Fügen Sie am Anfang der Datei *SentimentData.cs* die folgende `using`-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="4e91b-147">Entfernen Sie die vorhandene Klassendefinition, und fügen Sie den folgenden Code mit den beiden Klassen `SentimentData` und `SentimentPrediction` der Datei *SentimentData.cs* hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="4e91b-148">Vorbereitung der Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-148">How the data was prepared</span></span>

<span data-ttu-id="4e91b-149">Die `SentimentData`-Klasse des Eingabedatasets hat eine `string` für Benutzerkommentare (`SentimentText`) und einen `bool` (`Sentiment`) Wert von entweder 1 (positiv) oder 0 (negativ) für den Standpunkt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="4e91b-150">Beide Felder haben [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29)-Attribute, die an sie angefügt sind, wodurch die Reihenfolge der Datendateien für jedes Feld beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4e91b-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="4e91b-151">Darüber hinaus hat die `Sentiment`-Eigenschaft ein [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A)-Attribut, um es als `Label`-Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="4e91b-152">Die folgende Beispieldatei verfügt nicht über eine Kopfzeile und sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4e91b-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="4e91b-153">SentimentText</span><span class="sxs-lookup"><span data-stu-id="4e91b-153">SentimentText</span></span>                         |<span data-ttu-id="4e91b-154">Standpunkt (Bezeichnung)</span><span class="sxs-lookup"><span data-stu-id="4e91b-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="4e91b-155">Die Kellnerin hat etwas langsam bedient.</span><span class="sxs-lookup"><span data-stu-id="4e91b-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="4e91b-156">0</span><span class="sxs-lookup"><span data-stu-id="4e91b-156">0</span></span>     |
|<span data-ttu-id="4e91b-157">Die Kruste ist nicht gut.</span><span class="sxs-lookup"><span data-stu-id="4e91b-157">Crust is not good.</span></span>                    |    <span data-ttu-id="4e91b-158">0</span><span class="sxs-lookup"><span data-stu-id="4e91b-158">0</span></span>     |
|<span data-ttu-id="4e91b-159">Toll... Mir hat das Restaurant gefallen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="4e91b-160">1</span><span class="sxs-lookup"><span data-stu-id="4e91b-160">1</span></span>     |
|<span data-ttu-id="4e91b-161">Wir wurden schnell bedient.</span><span class="sxs-lookup"><span data-stu-id="4e91b-161">Service was very prompt.</span></span>              |    <span data-ttu-id="4e91b-162">1</span><span class="sxs-lookup"><span data-stu-id="4e91b-162">1</span></span>     |

<span data-ttu-id="4e91b-163">`SentimentPrediction` ist die nach dem Modelltraining verwendete Vorhersageklasse.</span><span class="sxs-lookup"><span data-stu-id="4e91b-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="4e91b-164">Diese erbt von `SentimentData`, sodass die Eingabe `SentimentText` zusammen mit der Ausgabevorhersage angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e91b-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="4e91b-165">Der boolesche Wert `Prediction` ist der Wert, den das Modell vorhersagt, wenn für dieses eine neue Eingabe für `SentimentText` bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4e91b-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="4e91b-166">Die Ausgabeklasse `SentimentPrediction` enthält zwei weitere Eigenschaften, die von dem Modell berechnet werden: `Score`, die Rohbewertung, die vom Modell berechnet wird, und `Probability`, der für die Wahrscheinlichkeit, dass der Text eine positive Stimmung vermittelt, kalibrierte Wert.</span><span class="sxs-lookup"><span data-stu-id="4e91b-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="4e91b-167">Für dieses Tutorial ist `Prediction` die wichtigste Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4e91b-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="4e91b-168">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-168">Load the data</span></span>

<span data-ttu-id="4e91b-169">Daten werden in ML.NET als [IDataView-Klasse](xref:Microsoft.ML.IDataView) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="4e91b-170">Mit `IDataView` können Tabellendaten (Zahlen und Text) flexibel und effizient beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="4e91b-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="4e91b-171">Daten können aus einer Textdatei oder in Echtzeit (z. B. aus einer SQL-Datenbank oder aus Protokolldateien) in ein `IDataView`-Objekt geladen werden.</span><span class="sxs-lookup"><span data-stu-id="4e91b-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="4e91b-172">Die [MLContext-Klasse](xref:Microsoft.ML.MLContext) ist der Ausgangspunkt für alle ML.NET-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="4e91b-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="4e91b-173">Beim Initialisieren von `mlContext` wird eine neue ML.NET-Umgebung erstellt, die für alle Objekte des Workflows für die Modellerstellung gemeinsam genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e91b-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="4e91b-174">Die Klasse ähnelt dem Konzept von `DBContext` in Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4e91b-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="4e91b-175">Sie bereiten die App vor und laden anschließend die Daten:</span><span class="sxs-lookup"><span data-stu-id="4e91b-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="4e91b-176">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!")` in der `Main`-Methode durch den folgenden Code, um die mlContext-Variable zu deklarieren und zu initialisieren:</span><span class="sxs-lookup"><span data-stu-id="4e91b-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="4e91b-177">Fügen Sie den folgenden Text als nächste Codezeile in die `Main()`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="4e91b-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

3. <span data-ttu-id="4e91b-178">Erstellen Sie die `LoadData()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="4e91b-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="4e91b-179">Die `LoadData()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="4e91b-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="4e91b-180">Laden der Daten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-180">Loads the data.</span></span>
    - <span data-ttu-id="4e91b-181">Teilt das geladene Dataset in Trainings- und Testdatasets auf.</span><span class="sxs-lookup"><span data-stu-id="4e91b-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="4e91b-182">Gibt die aufgeteilten Trainings- und Testdatasets zurück.</span><span class="sxs-lookup"><span data-stu-id="4e91b-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="4e91b-183">Fügen Sie den folgenden Code am Ende der ersten Zeile der `LoadData()`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e91b-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="4e91b-184">Die [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)-Methode definiert das Datenschema und liest die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="4e91b-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="4e91b-185">Diese Methode akzeptiert Datenpfadvariablen und gibt ein `IDataView`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="4e91b-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="4e91b-186">Aufteilen des Datasets für Modelltraining und -test</span><span class="sxs-lookup"><span data-stu-id="4e91b-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="4e91b-187">Wenn Sie ein Modell vorbereiten, verwenden Sie einen Teil des Datasets, um es zu trainieren, und einen anderen Teil, um die Genauigkeit des Modells zu testen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="4e91b-188">Um die geladenen Daten in die erforderlichen Datasets aufzuteilen, fügen Sie den folgenden Code als nächste Zeile in die `LoadData()`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="4e91b-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="4e91b-189">Der vorherige Code verwendet die [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A)-Methode, um das geladene Dataset in Trainings- und Testdatasets aufzuteilen und in der [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData)-Klasse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4e91b-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="4e91b-190">Geben Sie den Prozentsatz der Daten des Testsatzes mit dem `testFraction`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="4e91b-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="4e91b-191">Der Standard ist 10 %. In diesem Fall verwenden Sie 20 %, um mehr Daten auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="4e91b-192">Geben Sie `splitDataView` am Ende der `LoadData()`-Methode zurück:</span><span class="sxs-lookup"><span data-stu-id="4e91b-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="4e91b-193">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-193">Build and train the model</span></span>

1. <span data-ttu-id="4e91b-194">Fügen Sie der `BuildAndTrainModel`-Methode den folgenden Aufruf als nächste Codezeile der `Main()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="4e91b-195">Die `BuildAndTrainModel()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="4e91b-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="4e91b-196">Extrahieren und Transformieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="4e91b-197">Trainieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="4e91b-197">Trains the model.</span></span>
    - <span data-ttu-id="4e91b-198">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="4e91b-199">Zurückgeben des Modells.</span><span class="sxs-lookup"><span data-stu-id="4e91b-199">Returns the model.</span></span>

2. <span data-ttu-id="4e91b-200">Erstellen Sie die `BuildAndTrainModel()`-Methode mit dem folgenden Code direkt nach der `Main()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="4e91b-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="4e91b-201">Extrahieren und Transformieren der Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-201">Extract and transform the data</span></span>

1. <span data-ttu-id="4e91b-202">Rufen Sie `FeaturizeText` als die nächste Codezeile auf:</span><span class="sxs-lookup"><span data-stu-id="4e91b-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="4e91b-203">Die `FeaturizeText()`-Methode im vorherigen Code konvertiert die Textspalte (`SentimentText`) in eine Spalte vom Typ `Features` mit numerischem Schlüssel, die vom Machine Learning-Algorithmus verwendet wird, und fügt sie als neue Datasetspalte hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="4e91b-204">SentimentText</span><span class="sxs-lookup"><span data-stu-id="4e91b-204">SentimentText</span></span>                         |<span data-ttu-id="4e91b-205">Standpunkt</span><span class="sxs-lookup"><span data-stu-id="4e91b-205">Sentiment</span></span> |<span data-ttu-id="4e91b-206">Features</span><span class="sxs-lookup"><span data-stu-id="4e91b-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="4e91b-207">Die Kellnerin hat etwas langsam bedient.</span><span class="sxs-lookup"><span data-stu-id="4e91b-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="4e91b-208">0</span><span class="sxs-lookup"><span data-stu-id="4e91b-208">0</span></span>     |<span data-ttu-id="4e91b-209">[0,76, 0,65, 0,44, …]</span><span class="sxs-lookup"><span data-stu-id="4e91b-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="4e91b-210">Die Kruste ist nicht gut.</span><span class="sxs-lookup"><span data-stu-id="4e91b-210">Crust is not good.</span></span>                    |    <span data-ttu-id="4e91b-211">0</span><span class="sxs-lookup"><span data-stu-id="4e91b-211">0</span></span>     |<span data-ttu-id="4e91b-212">[0,98, 0,43, 0,54, …]</span><span class="sxs-lookup"><span data-stu-id="4e91b-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="4e91b-213">Toll... Mir hat das Restaurant gefallen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="4e91b-214">1</span><span class="sxs-lookup"><span data-stu-id="4e91b-214">1</span></span>     |<span data-ttu-id="4e91b-215">[0,35, 0,73, 0,46, …]</span><span class="sxs-lookup"><span data-stu-id="4e91b-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="4e91b-216">Wir wurden schnell bedient.</span><span class="sxs-lookup"><span data-stu-id="4e91b-216">Service was very prompt.</span></span>              |    <span data-ttu-id="4e91b-217">1</span><span class="sxs-lookup"><span data-stu-id="4e91b-217">1</span></span>     |<span data-ttu-id="4e91b-218">[0,39, 0, 0,75, …]</span><span class="sxs-lookup"><span data-stu-id="4e91b-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="4e91b-219">Hinzufügen eines Lernalgorithmus</span><span class="sxs-lookup"><span data-stu-id="4e91b-219">Add a learning algorithm</span></span>

<span data-ttu-id="4e91b-220">Diese App verwendet einen Klassifizierungsalgorithmus, der Elemente oder Datenzeilen kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="4e91b-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="4e91b-221">Die App kategorisiert Websitekommentare entweder als positiv oder negativ. Also verwenden Sie die binäre Klassifizierungsaufgabe.</span><span class="sxs-lookup"><span data-stu-id="4e91b-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="4e91b-222">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in `BuildAndTrainModel()` ein, um die Machine Learning-Aufgabe festzulegen und ihn an die Datentransformationsdefinitionen anzufügen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="4e91b-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) ist Ihr Klassifizierungsalgorithmus für das Training.</span><span class="sxs-lookup"><span data-stu-id="4e91b-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="4e91b-224">Dieser wird an den `estimator` angefügt, und akzeptiert den mit Features ausgestatteten `SentimentText` (`Features`) und die `Label`-Eingabeparameter, um aus den historischen Daten zu lernen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="4e91b-225">Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-225">Train the model</span></span>

<span data-ttu-id="4e91b-226">Fügen Sie den unten aufgeführten Code als nächste Codezeilen in die `BuildAndTrainModel()`-Methode ein, um das Modell an die `splitTrainSet`-Daten anzupassen und das trainierte Modell zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="4e91b-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="4e91b-227">Mit der [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29)-Methode wird Ihr Modell trainiert, indem das Dataset transformiert und das Training angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e91b-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="4e91b-228">Zurückgeben des für die Evaluierung trainierten Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="4e91b-229">Geben Sie das Modell am Ende der `BuildAndTrainModel()`-Methode zurück:</span><span class="sxs-lookup"><span data-stu-id="4e91b-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="4e91b-230">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-230">Evaluate the model</span></span>

<span data-ttu-id="4e91b-231">Verwenden Sie nach dem Training Ihres Modells Ihre Testdaten, um die Leistung Ihres Modells zu validieren.</span><span class="sxs-lookup"><span data-stu-id="4e91b-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="4e91b-232">Erstellen Sie mit dem folgenden Code die `Evaluate()`-Methode direkt nach `BuildAndTrainModel()`:</span><span class="sxs-lookup"><span data-stu-id="4e91b-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="4e91b-233">Die `Evaluate()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="4e91b-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="4e91b-234">Laden des Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="4e91b-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="4e91b-235">Erstellen des Auswerters der binären Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="4e91b-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="4e91b-236">Evaluieren des Modells und Erstellen von Metriken.</span><span class="sxs-lookup"><span data-stu-id="4e91b-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="4e91b-237">Anzeigen der Metriken.</span><span class="sxs-lookup"><span data-stu-id="4e91b-237">Displays the metrics.</span></span>

2. <span data-ttu-id="4e91b-238">Fügen Sie einen Aufruf der neuen Methode aus der `Main()`-Methode mit dem folgenden Code direkt unter dem `BuildAndTrainModel()`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="4e91b-239">Fügen Sie `Evaluate()` den folgenden Code hinzu, um die `splitTestSet`-Daten zu transformieren:</span><span class="sxs-lookup"><span data-stu-id="4e91b-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="4e91b-240">Der vorherige Code verwendet die [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode trifft Vorhersagen für mehrere bereitgestellte Eingabezeilen eines Testdatasets.</span><span class="sxs-lookup"><span data-stu-id="4e91b-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="4e91b-241">Fügen Sie den unten aufgeführten Code als nächste Codezeile in die `Evaluate()`-Methode ein, um das Modell auszuwerten:</span><span class="sxs-lookup"><span data-stu-id="4e91b-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="4e91b-242">Nach der Vorhersagekonfiguration (`predictions`) wertet die [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A)-Methode das Modell aus. Dabei werden die Vorhersagewerte mit den tatsächlichen `Labels` im Testdataset verglichen und die [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) für das Modell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4e91b-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="4e91b-243">Anzeigen der Metriken zur Modellvalidierung</span><span class="sxs-lookup"><span data-stu-id="4e91b-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="4e91b-244">Zeigen Sie die Metriken mithilfe des folgenden Codes an:</span><span class="sxs-lookup"><span data-stu-id="4e91b-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="4e91b-245">Die `Accuracy`-Metrik ermittelt die Genauigkeit eines Modells, d.h. den Anteil der korrekten Vorhersagen im Testsatz.</span><span class="sxs-lookup"><span data-stu-id="4e91b-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="4e91b-246">Die `AreaUnderRocCurve`-Metrik gibt an, wie sicher das Modell die positiven und negativen Klassen korrekt klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="4e91b-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="4e91b-247">Sie möchten, dass der `AreaUnderRocCurve` so nah wie möglich bei 1 liegt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="4e91b-248">Die `F1Score`-Metrik ermittelt den F1-Score des Modells, der ein Maß für das Gleichgewicht zwischen [Genauigkeit](../resources/glossary.md#precision) und [Wiederkennung](../resources/glossary.md#recall) ist.</span><span class="sxs-lookup"><span data-stu-id="4e91b-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="4e91b-249">Sie möchten, dass der `F1Score` so nah wie möglich bei 1 liegt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="4e91b-250">Vorhersagen der Testdatenergebnisse</span><span class="sxs-lookup"><span data-stu-id="4e91b-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="4e91b-251">Erstellen Sie die `UseModelWithSingleItem()`-Methode mit dem folgenden Code direkt nach der `Evaluate()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="4e91b-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="4e91b-252">Die `UseModelWithSingleItem()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="4e91b-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="4e91b-253">Erstellen eines einzelnen Kommentars aus Testdaten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="4e91b-254">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="4e91b-255">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="4e91b-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="4e91b-256">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="4e91b-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="4e91b-257">Fügen Sie einen Aufruf der neuen Methode aus der `Main()`-Methode mit dem folgenden Code direkt unter dem `Evaluate()`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="4e91b-258">Fügen Sie den folgenden Code hinzu, um die erste Zeile in der `UseModelWithSingleItem()`-Methode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="4e91b-259">Die [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) ist eine Hilfs-API, mit der Sie eine Vorhersage für eine einzelne Instanz der Daten treffen können.</span><span class="sxs-lookup"><span data-stu-id="4e91b-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="4e91b-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) ist nicht threadsicher.</span><span class="sxs-lookup"><span data-stu-id="4e91b-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="4e91b-261">Die Verwendung in Singlethread-oder Prototypumgebungen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e91b-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="4e91b-262">Zur Verbesserung der Leistung und Threadsicherheit in Produktionsumgebungen verwenden Sie den `PredictionEnginePool`-Dienst, der einen [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) aus [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)-Objekten für die Verwendung in Ihrer gesamten Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="4e91b-263">Informationen zur [Verwendung von `PredictionEnginePool` in einer ASP.NET Core-Web-API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application) finden Sie in dieser Anleitung.</span><span class="sxs-lookup"><span data-stu-id="4e91b-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="4e91b-264">Die `PredictionEnginePool`-Diensterweiterung ist derzeit als Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e91b-264">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="4e91b-265">Fügen Sie einen Kommentar hinzu, um die Vorhersage des trainierten Modells in der `UseModelWithSingleItem()`-Methode zu testen, indem Sie eine `SentimentData`-Instanz erstellen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="4e91b-266">Übergeben Sie die Testkommentardaten an die [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602), indem Sie Folgendes als nächste Codezeilen in der `UseModelWithSingleItem()`-Methode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="4e91b-267">Die [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A)-Funktion trifft eine Vorhersage für eine einzelne Datenzeile.</span><span class="sxs-lookup"><span data-stu-id="4e91b-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="4e91b-268">Mithilfe des folgenden Codes können Sie den `SentimentText` und den dazugehörige Standpunkt anzeigen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="4e91b-269">Verwenden des Modells für eine Vorhersage</span><span class="sxs-lookup"><span data-stu-id="4e91b-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="4e91b-270">Bereitstellen und Vorhersagen von Batchelementen</span><span class="sxs-lookup"><span data-stu-id="4e91b-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="4e91b-271">Erstellen Sie die `UseModelWithBatchItems()`-Methode mit dem folgenden Code direkt nach der `UseModelWithSingleItem()`-Methode:</span><span class="sxs-lookup"><span data-stu-id="4e91b-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="4e91b-272">Die `UseModelWithBatchItems()`-Methode führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="4e91b-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="4e91b-273">Erstellen von Batchtestdaten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-273">Creates batch test data.</span></span>
    - <span data-ttu-id="4e91b-274">Vorhersagen des Standpunkts anhand der Testdaten.</span><span class="sxs-lookup"><span data-stu-id="4e91b-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="4e91b-275">Kombinieren von Testdaten und Vorhersagen für die Berichterstattung.</span><span class="sxs-lookup"><span data-stu-id="4e91b-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="4e91b-276">Anzeigen der vorhergesagten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="4e91b-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="4e91b-277">Fügen Sie einen Aufruf der neuen Methode aus der `Main`-Methode mit dem folgenden Code direkt unter dem `UseModelWithSingleItem()`-Methodenaufruf hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="4e91b-278">Fügen Sie einige Kommentare zum Testen der Vorhersagen des trainierten Modells in der `UseModelWithBatchItems()`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="4e91b-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="4e91b-279">Vorhersagen des Standpunkts in einem Kommentar</span><span class="sxs-lookup"><span data-stu-id="4e91b-279">Predict comment sentiment</span></span>

<span data-ttu-id="4e91b-280">Verwenden Sie das Modell, um den Standpunkt der Kommentardaten mit der [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A)-Methode vorherzusagen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="4e91b-281">Kombinieren und Anzeigen von Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="4e91b-281">Combine and display the predictions</span></span>

<span data-ttu-id="4e91b-282">Erstellen Sie mit dem folgenden Code einen Header für die Vorhersagen:</span><span class="sxs-lookup"><span data-stu-id="4e91b-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="4e91b-283">Da `SentimentPrediction` von `SentimentData` geerbt wird, füllt die `Transform()`-Methode den `SentimentText` mit den vorhergesagten Feldern aus.</span><span class="sxs-lookup"><span data-stu-id="4e91b-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="4e91b-284">Im Laufe des ML.NET-Prozesses fügt jede Komponente Spalten hinzu, sodass die Ergebnisse leicht angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="4e91b-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="4e91b-285">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="4e91b-285">Results</span></span>

<span data-ttu-id="4e91b-286">Die Ergebnisse sollten den unten dargestellten ähneln.</span><span class="sxs-lookup"><span data-stu-id="4e91b-286">Your results should be similar to the following.</span></span> <span data-ttu-id="4e91b-287">Während der Verarbeitung werden Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-287">During processing, messages are displayed.</span></span> <span data-ttu-id="4e91b-288">Sie können Warnungen oder Verarbeitungsmeldungen sehen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="4e91b-289">Diese wurden der Übersichtlichkeit halber aus den folgenden Ergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-289">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="4e91b-290">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="4e91b-290">Congratulations!</span></span> <span data-ttu-id="4e91b-291">Sie haben jetzt erfolgreich ein Machine Learning-Modell zum Klassifizieren und Vorhersagen von Standpunkten in Mitteilungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4e91b-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="4e91b-292">Erfolgreiche Modelle zu erstellen ist ein iterativer Prozess.</span><span class="sxs-lookup"><span data-stu-id="4e91b-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="4e91b-293">Dieses Modell hat erst geringere Qualität, da das Tutorial kleine Datasets verwendet, um schnelles Modelltraining zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4e91b-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="4e91b-294">Wenn Sie nicht mit der Modellqualität zufrieden sind, können Sie versuchen, sie durch die Bereitstellung größerer Trainingsdatasets oder die Auswahl anderer Trainingsalgorithmen mit anderen [Hyperparametern](../resources/glossary.md##hyperparameter) für jeden Algorithmus zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4e91b-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md##hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="4e91b-295">Sie finden den Quellcode für dieses Tutorial im Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis).</span><span class="sxs-lookup"><span data-stu-id="4e91b-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e91b-296">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4e91b-296">Next steps</span></span>

<span data-ttu-id="4e91b-297">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4e91b-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="4e91b-298">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4e91b-298">Create a console application</span></span>
> - <span data-ttu-id="4e91b-299">Vorbereiten von Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-299">Prepare data</span></span>
> - <span data-ttu-id="4e91b-300">Laden der Daten</span><span class="sxs-lookup"><span data-stu-id="4e91b-300">Load the data</span></span>
> - <span data-ttu-id="4e91b-301">Erstellen und Trainieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-301">Build and train the model</span></span>
> - <span data-ttu-id="4e91b-302">Evaluieren des Modells</span><span class="sxs-lookup"><span data-stu-id="4e91b-302">Evaluate the model</span></span>
> - <span data-ttu-id="4e91b-303">Verwenden des Modells für Vorhersagen</span><span class="sxs-lookup"><span data-stu-id="4e91b-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="4e91b-304">Anzeigen der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="4e91b-304">See the results</span></span>

<span data-ttu-id="4e91b-305">Wechseln Sie zum nächsten Tutorial, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="4e91b-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="4e91b-306">Klassifizierung von Issues</span><span class="sxs-lookup"><span data-stu-id="4e91b-306">Issue Classification</span></span>](github-issue-classification.md)
