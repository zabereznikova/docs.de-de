---
title: Tutorial zur Standpunktanalyse mit .NET für Apache Spark und ML.NET
description: In diesem Tutorial erfahren Sie, wie Sie ML.NET mit .NET für Apache Spark für eine Standpunktanalyse verwenden.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 1c2c966a4ff50a9d2f6951e20d909c5c20c75bfb
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688240"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a><span data-ttu-id="8a50f-103">Tutorial: Standpunktanalyse mit .NET für Apache Spark und ML.NET</span><span class="sxs-lookup"><span data-stu-id="8a50f-103">Tutorial: Sentiment analysis with .NET for Apache Spark and ML.NET</span></span>

<span data-ttu-id="8a50f-104">In diesem Tutorial erfahren Sie, wie Sie ML.NET mit .NET für Apache Spark eine Standpunktanalyse für Onlinebewertungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-104">This tutorial teaches you how to do sentiment analysis of online reviews using ML.NET and .NET for Apache Spark.</span></span> <span data-ttu-id="8a50f-105">[ML.NET](http://dot.net/ml) ist ein kostenloses, plattformübergreifendes Open Source-Framework für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-105">[ML.NET](http://dot.net/ml) is a free, cross-platform, open-source machine learning framework.</span></span> <span data-ttu-id="8a50f-106">Sie können ML.NET mit .NET für Apache Spark nutzen, um Training und Vorhersage von Machine Learning-Algorithmen zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="8a50f-106">You can use ML.NET with .NET for Apache Spark to scale the training and prediction of machine learning algorithms.</span></span>

<span data-ttu-id="8a50f-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="8a50f-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="8a50f-108">Erstellen eines Modells für die Standpunktanalyse mit dem ML.NET-Modell-Generator in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8a50f-108">Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.</span></span>
> * <span data-ttu-id="8a50f-109">Erstellen einer .NET für Apache Spark-Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="8a50f-109">Create a .NET for Apache Spark console app.</span></span>
> * <span data-ttu-id="8a50f-110">Schreiben und Implementieren einer benutzerdefinierten Funktion</span><span class="sxs-lookup"><span data-stu-id="8a50f-110">Write and implement a user-defined function.</span></span>
> * <span data-ttu-id="8a50f-111">Ausführen einer .NET für Apache Spark-Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="8a50f-111">Run a .NET for Apache Spark console app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a50f-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8a50f-112">Prerequisites</span></span>

* <span data-ttu-id="8a50f-113">Wenn Sie noch keine .NET für Apache Spark-Anwendung entwickelt haben, beginnen Sie mit dem [Tutorial „Erste Schritte“](get-started.md), um sich mit den Grundlagen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-113">If you haven't developed a .NET for Apache Spark application before, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span> <span data-ttu-id="8a50f-114">Sorgen Sie dafür, dass alle Voraussetzungen für das Tutorial „Erste Schritte“ erfüllt sind, bevor Sie mit diesem Tutorial fortfahren.</span><span class="sxs-lookup"><span data-stu-id="8a50f-114">Complete all of the prerequisites for the Getting Started tutorial before you continue with this tutorial.</span></span>

* <span data-ttu-id="8a50f-115">In diesem Tutorial wird der ML.NET-Modell-Generator (Vorschau) verwendet, eine grafische Benutzeroberfläche, die in Visual Studio zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="8a50f-115">This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio.</span></span> <span data-ttu-id="8a50f-116">Falls Sie Visual Studio noch nicht erworben haben, können Sie die [Community-Version von Visual Studio](https://visualstudio.microsoft.com/downloads/) kostenlos herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-116">If you don't already have Visual Studio, you can [download the Community version of Visual Studio](https://visualstudio.microsoft.com/downloads/) for free.</span></span>

* <span data-ttu-id="8a50f-117">Außerdem müssen Sie den ML.NET-Modell-Generator (Vorschau) [herunterladen und installieren](https://marketplace.visualstudio.com/items?itemName=MLNET.07).</span><span class="sxs-lookup"><span data-stu-id="8a50f-117">[Download and install](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (preview).</span></span>

* <span data-ttu-id="8a50f-118">Laden Sie die Yelp-Bewertungsdatasets [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) und [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) herunter.</span><span class="sxs-lookup"><span data-stu-id="8a50f-118">Download the [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) and [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp review datasets.</span></span>

## <a name="review-the-data"></a><span data-ttu-id="8a50f-119">Überprüfen der Daten</span><span class="sxs-lookup"><span data-stu-id="8a50f-119">Review the data</span></span>

<span data-ttu-id="8a50f-120">Die Yelp-Datasets enthalten Yelp-Onlinebewertungen zu verschiedenen Diensten.</span><span class="sxs-lookup"><span data-stu-id="8a50f-120">The Yelp reviews dataset contains online Yelp reviews about various services.</span></span> <span data-ttu-id="8a50f-121">Öffnen Sie [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv), und beachten Sie die Struktur der Daten.</span><span class="sxs-lookup"><span data-stu-id="8a50f-121">Open [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) and notice the structure of the data.</span></span> <span data-ttu-id="8a50f-122">Die erste Spalte enthält den Text der Bewertung, und die zweite Spalte enthält Stimmungspunktzahlen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-122">The first column contains review text, and the second column contains sentiment scores.</span></span> <span data-ttu-id="8a50f-123">Wenn die Stimmungspunktzahl 1 lautet, ist die Bewertung positiv. Lautet die Stimmungspunktzahl 0, ist die Bewertung negativ.</span><span class="sxs-lookup"><span data-stu-id="8a50f-123">If the sentiment score is 1, the review is positive, and if the sentiment score is 0, the review is negative.</span></span>

<span data-ttu-id="8a50f-124">Die folgende Tabelle enthält einige Beispieldaten:</span><span class="sxs-lookup"><span data-stu-id="8a50f-124">The following table contains sample data:</span></span>

|<span data-ttu-id="8a50f-125">ReviewText</span><span class="sxs-lookup"><span data-stu-id="8a50f-125">ReviewText</span></span>|<span data-ttu-id="8a50f-126">Standpunkt</span><span class="sxs-lookup"><span data-stu-id="8a50f-126">Sentiment</span></span>|
|-|-|
|<span data-ttu-id="8a50f-127">Toll... Mir hat das Restaurant gefallen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-127">Wow... Loved this place.</span></span>|    <span data-ttu-id="8a50f-128">1</span><span class="sxs-lookup"><span data-stu-id="8a50f-128">1</span></span>|
|<span data-ttu-id="8a50f-129">Die Kruste ist nicht gut.</span><span class="sxs-lookup"><span data-stu-id="8a50f-129">Crust is not good.</span></span>|    <span data-ttu-id="8a50f-130">0</span><span class="sxs-lookup"><span data-stu-id="8a50f-130">0</span></span>|

## <a name="build-your-machine-learning-model"></a><span data-ttu-id="8a50f-131">Erstellen Ihres Machine Learning-Modells</span><span class="sxs-lookup"><span data-stu-id="8a50f-131">Build your machine learning model</span></span>

1. <span data-ttu-id="8a50f-132">Öffnen Sie Visual Studio, und erstellen Sie eine neue C#-Konsolen-App (.NET Core).</span><span class="sxs-lookup"><span data-stu-id="8a50f-132">Open Visual Studio and create a new C# Console App (.NET Core).</span></span> <span data-ttu-id="8a50f-133">Geben Sie dem Projekt den Namen *MLSparkModel*.</span><span class="sxs-lookup"><span data-stu-id="8a50f-133">Name the project *MLSparkModel*.</span></span>

1. <span data-ttu-id="8a50f-134">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt *MLSparkModel*.</span><span class="sxs-lookup"><span data-stu-id="8a50f-134">In **Solution Explorer**, right-click the *MLSparkModel* project.</span></span> <span data-ttu-id="8a50f-135">Wählen Sie anschließend **hinzufügen > Machine Learning** aus.</span><span class="sxs-lookup"><span data-stu-id="8a50f-135">Then select **Add > Machine Learning**.</span></span>

1. <span data-ttu-id="8a50f-136">Wählen Sie im ML.NET-Modell-Generator die Kachel für das Szenario **Standpunktanalyse** aus.</span><span class="sxs-lookup"><span data-stu-id="8a50f-136">From the ML.NET Model Builder, select the **Sentiment Analysis** scenario tile.</span></span>

1. <span data-ttu-id="8a50f-137">Laden Sie auf der Seite **Daten hinzufügen** das Dataset *yelptrain.csv* hoch.</span><span class="sxs-lookup"><span data-stu-id="8a50f-137">On the **Add data** page, upload the *yelptrain.csv* data set.</span></span>

1. <span data-ttu-id="8a50f-138">Wählen Sie im Dropdownmenü **Vorherzusagende Spalten** die Option *Stimmung* aus.</span><span class="sxs-lookup"><span data-stu-id="8a50f-138">Choose *Sentiment* from the **Columns to Predict** dropdown.</span></span>

1. <span data-ttu-id="8a50f-139">Legen Sie auf der Seite **Trainieren** die Trainingszeit auf *60 Sekunden* fest, und klicken Sie auf **Training starten**.</span><span class="sxs-lookup"><span data-stu-id="8a50f-139">On the **Train** page, set the time to train to *60 seconds* and select **Start training**.</span></span> <span data-ttu-id="8a50f-140">Verfolgen Sie den Status Ihres Trainings unter **Fortschritt**.</span><span class="sxs-lookup"><span data-stu-id="8a50f-140">Notice the status of your training under **Progress**.</span></span>

1. <span data-ttu-id="8a50f-141">Sobald der Modell-Generator das Training abgeschlossen hat, können Sie die Trainingsergebnisse **Auswerten**.</span><span class="sxs-lookup"><span data-stu-id="8a50f-141">Once Model Builder is finished training, **Evaluate** the training results.</span></span> <span data-ttu-id="8a50f-142">Sie können in das Textfeld unter **Modell testen** einen Satz eingeben und auf **Vorhersage** klicken, um die Ausgabe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-142">You can type phrases into the text box below **Try your model** and select **Predict** to see the output.</span></span>

1. <span data-ttu-id="8a50f-143">Wählen Sie **Code** und anschließend **Projekte hinzufügen** aus, um das ML-Modell zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-143">Select **Code** and then select **Add Projects** to add the ML model to the solution.</span></span>

1. <span data-ttu-id="8a50f-144">Beachten Sie, dass Ihrer Projektmappe zwei Projekte hinzugefügt werden: **MLSparkModelML.ConsoleApp** und **MLSparkModelML.Model**.</span><span class="sxs-lookup"><span data-stu-id="8a50f-144">Notice that two projects are added to your solutions: **MLSparkModelML.ConsoleApp** and **MLSparkModelML.Model**.</span></span>

1. <span data-ttu-id="8a50f-145">Doppelklicken Sie auf Ihr C#-Projekt *MLSpark* und beachten Sie, dass der folgende Projektverweis hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a50f-145">Double-click on your *MLSpark* C# project and notice that the following project reference has been added.</span></span>

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a><span data-ttu-id="8a50f-146">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="8a50f-146">Create a console app</span></span>

<span data-ttu-id="8a50f-147">Der Modell-Generator erstellt eine Konsolen-App für Sie.</span><span class="sxs-lookup"><span data-stu-id="8a50f-147">Model Builder creates a console app for you.</span></span>

1. <span data-ttu-id="8a50f-148">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt **MLSparkModelML.Console**, und wählen Sie **NuGet-Pakete verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="8a50f-148">Right-click on **MLSparkModelML.Console** in Solution Explorer, and select **Manage NuGet Packages**.</span></span>

1. <span data-ttu-id="8a50f-149">Suchen Sie nach **Microsoft.Spark**, und installieren Sie das Paket.</span><span class="sxs-lookup"><span data-stu-id="8a50f-149">Search for **Microsoft.Spark** and install the package.</span></span> <span data-ttu-id="8a50f-150">**Microsoft.ML** wird vom Modell-Generator automatisch für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="8a50f-150">**Microsoft.ML** is automatically installed for you by Model Builder.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="8a50f-151">Erstellen einer SparkSession</span><span class="sxs-lookup"><span data-stu-id="8a50f-151">Create a SparkSession</span></span>

1. <span data-ttu-id="8a50f-152">Öffnen Sie die Datei *Program.cs* für **MLSparkModelML.ConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="8a50f-152">Open the *Program.cs* file for **MLSparkModelML.ConsoleApp**.</span></span> <span data-ttu-id="8a50f-153">Diese Datei wurde vom Modell-Generator automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="8a50f-153">This file was autogenerated by Model Builder.</span></span> <span data-ttu-id="8a50f-154">Löschen Sie die `using`-Anweisungen, die Inhalte der Main()-Methode und die `CreateSingleDataSample`-Region.</span><span class="sxs-lookup"><span data-stu-id="8a50f-154">Delete the `using` statements, the contents of the Main() method, and the `CreateSingleDataSample` region.</span></span>

1. <span data-ttu-id="8a50f-155">Fügen Sie am Anfang der Datei *Program.cs* folgende zusätzliche `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="8a50f-155">Add the following additional `using` statements to the top of the *Program.cs*:</span></span>

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. <span data-ttu-id="8a50f-156">Ändern Sie `DATA_FILEPATH` in den Pfad zu Ihrer Datei *yelptest.csv*.</span><span class="sxs-lookup"><span data-stu-id="8a50f-156">Change the `DATA_FILEPATH` to the path of your *yelptest.csv*.</span></span>

1. <span data-ttu-id="8a50f-157">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um eine neue `SparkSession` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-157">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="8a50f-158">Die Spark-Sitzung ist der Einstiegspunkt in die Programmierung von Spark mit der Dataset- und DataFrame-API.</span><span class="sxs-lookup"><span data-stu-id="8a50f-158">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   <span data-ttu-id="8a50f-159">Der Aufruf des oben erstellten *spark*-Objekts ermöglicht im gesamten Programm den Zugriff auf Spark- und DataFrame-Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="8a50f-159">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="create-a-dataframe-and-print-to-console"></a><span data-ttu-id="8a50f-160">Erstellen eines DataFrame und Ausgabe an die Konsole</span><span class="sxs-lookup"><span data-stu-id="8a50f-160">Create a DataFrame and print to console</span></span>

<span data-ttu-id="8a50f-161">Lesen Sie die Yelp-Bewertungsdaten aus der Datei *yelptest.csv* als `DataFrame` ein.</span><span class="sxs-lookup"><span data-stu-id="8a50f-161">Read in the Yelp review data from the *yelptest.csv* file as a `DataFrame`.</span></span> <span data-ttu-id="8a50f-162">Verwenden Sie die Optionen `header` und `inferSchema`.</span><span class="sxs-lookup"><span data-stu-id="8a50f-162">Include `header` and `inferSchema` options.</span></span> <span data-ttu-id="8a50f-163">Die Option `header` liest die erste Zeile von *yelptest.csv* als Spaltennamen anstelle von Daten.</span><span class="sxs-lookup"><span data-stu-id="8a50f-163">The `header` option reads the first line of *yelptest.csv* as column names instead of data.</span></span> <span data-ttu-id="8a50f-164">Mit der Option `inferSchema` werden Spaltentypen basierend auf den Daten abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8a50f-164">The `inferSchema` option infers column types based on the data.</span></span>

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a><span data-ttu-id="8a50f-165">Registrieren einer benutzerdefinierten Funktion</span><span class="sxs-lookup"><span data-stu-id="8a50f-165">Register a user-defined function</span></span>

<span data-ttu-id="8a50f-166">Sie können in Spark-Anwendungen mithilfe *benutzerdefinierter Funktionen* Berechnungen und Analysen für Ihre Daten ausführen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-166">You can use UDFs, *user-defined functions*, in Spark applications to do calculations and analysis on your data.</span></span> <span data-ttu-id="8a50f-167">In diesem Tutorial verwenden Sie ML.NET mit einer benutzerdefinierten Funktion, um jede Yelp-Bewertung auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="8a50f-167">In this tutorial, you use ML.NET with a UDF to evaluate each Yelp review.</span></span>

<span data-ttu-id="8a50f-168">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um die benutzerdefinierte Funktion `MLudf` zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="8a50f-168">Add the following code to your `Main` method to register a UDF called `MLudf`.</span></span>

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

<span data-ttu-id="8a50f-169">Diese benutzerdefinierte Funktion verwendet eine Yelp-Bewertungszeichenfolge als Eingabe und gibt für positive oder negative Standpunkte TRUE bzw. FALSE zurück.</span><span class="sxs-lookup"><span data-stu-id="8a50f-169">This UDF takes a Yelp review string as input, and outputs true or false for positive or negative sentiments, respectively.</span></span> <span data-ttu-id="8a50f-170">Die Funktion verwendet die *predict()* -Methode, die Sie in einem späteren Schritt definieren.</span><span class="sxs-lookup"><span data-stu-id="8a50f-170">It uses the *predict()* method that you define in a later step.</span></span>

### <a name="use-spark-sql-to-call-the-udf"></a><span data-ttu-id="8a50f-171">Verwenden von Spark SQL zum Aufrufen der benutzerdefinierten Funktion</span><span class="sxs-lookup"><span data-stu-id="8a50f-171">Use Spark SQL to call the UDF</span></span>

<span data-ttu-id="8a50f-172">Nachdem Sie Ihre Daten eingelesen und ML eingebunden haben, verwenden Sie Spark SQL, um die benutzerdefinierte Funktion aufzurufen, mit der eine Standpunktanalyse für jede Zeile Ihres DataFrame durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8a50f-172">Now that you've read in your data and incorporated ML, use Spark SQL to call the UDF that will run sentiment analysis on each row of your DataFrame.</span></span> <span data-ttu-id="8a50f-173">Fügen Sie der `Main`-Methode den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="8a50f-173">Add the following code to your `Main` method:</span></span>

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a><span data-ttu-id="8a50f-174">Erstellen der predict()-Methode</span><span class="sxs-lookup"><span data-stu-id="8a50f-174">Create predict() method</span></span>

<span data-ttu-id="8a50f-175">Fügen Sie vor Ihrer `Main()`-Methode den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="8a50f-175">Add the following code before your `Main()` method.</span></span> <span data-ttu-id="8a50f-176">Diese Code ähnelt der Ausgabe des Modell-Generators in *ConsumeModel.cs*.</span><span class="sxs-lookup"><span data-stu-id="8a50f-176">This code is similar to what is produced by Model Builder in *ConsumeModel.cs*.</span></span> <span data-ttu-id="8a50f-177">Durch das Verschieben dieser Methode in Ihre Konsole wird das Modell immer dann geladen, wenn Sie Ihre App ausführen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-177">Moving this method to your console loads the model loading each time you run your app.</span></span>

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a><span data-ttu-id="8a50f-178">Hinzufügen des Modells zu Ihrer Konsolen-App</span><span class="sxs-lookup"><span data-stu-id="8a50f-178">Add the model to your console app</span></span>

<span data-ttu-id="8a50f-179">Kopieren Sie im Projektmappen-Explorer die Datei *MLModel.zip* aus dem Projekt **MLSparkModelML.Model**, und fügen Sie sie in das Projekt **MLSparkModelML.ConsoleApp** ein.</span><span class="sxs-lookup"><span data-stu-id="8a50f-179">In Solution Explorer, copy the *MLModel.zip* file from the **MLSparkModelML.Model** project and paste it in the **MLSparkModelML.ConsoleApp** project.</span></span> <span data-ttu-id="8a50f-180">Es wird automatisch ein Verweis in *MLSparkModelML.ConsoleApp.csproj* eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8a50f-180">A reference is automatically added in *MLSparkModelML.ConsoleApp.csproj*.</span></span>

## <a name="run-your-code"></a><span data-ttu-id="8a50f-181">Ausführen Ihres Codes</span><span class="sxs-lookup"><span data-stu-id="8a50f-181">Run your code</span></span>

<span data-ttu-id="8a50f-182">Verwenden Sie `spark-submit`, um Ihren Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-182">Use `spark-submit` to run your code.</span></span> <span data-ttu-id="8a50f-183">Navigieren Sie mithilfe der Eingabeaufforderung zum Stammordner der App, und führen Sie die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="8a50f-183">Navigate to your console app's root folder using the command prompt and run the following commands.</span></span>

<span data-ttu-id="8a50f-184">Bereinigen Sie zunächst Ihre App, und veröffentlichen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="8a50f-184">First, clean and publish your app.</span></span>

```dotnetcli
dotnet clean
dotnet publish
```

<span data-ttu-id="8a50f-185">Navigieren Sie dann zum Veröffentlichungsordner der Konsolen-App, und führen Sie den folgenden `spark-submit`-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="8a50f-185">Then navigate to the console app's publish folder and run the following `spark-submit` command.</span></span> <span data-ttu-id="8a50f-186">Denken Sie daran, den obigen Befehl mit dem tatsächlichen Pfad zu Ihrer JAR-Datei für Microsoft Spark zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8a50f-186">Remember to update the command with the actual path of your Microsoft Spark jar file.</span></span>

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2-4_2.11-1.0.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a><span data-ttu-id="8a50f-187">Abrufen des Codes</span><span class="sxs-lookup"><span data-stu-id="8a50f-187">Get the code</span></span>

<span data-ttu-id="8a50f-188">Der Code in diesem Tutorial ähnelt dem im Beispiel [Standpunktanalyse mit Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment).</span><span class="sxs-lookup"><span data-stu-id="8a50f-188">This tutorial is similar to the code from the [Sentiment Analysis with Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a50f-189">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8a50f-189">Next steps</span></span>

<span data-ttu-id="8a50f-190">Fahren Sie mit dem nächsten Artikel fort, um zu erfahren, wie Sie ein strukturiertes Streaming mit .NET für Apache Spark durchführen.</span><span class="sxs-lookup"><span data-stu-id="8a50f-190">Advance to the next article to learn how to do Structured Streaming with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="8a50f-191">Tutorial: Strukturiertes Streaming mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="8a50f-191">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
