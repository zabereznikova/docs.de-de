---
title: 'Tutorial: Batchverarbeitung mit .NET für Apache Spark'
description: Erfahren Sie, wie Sie Batchverarbeitung mithilfe von .NET für Apache Spark ausführen.
author: mamccrea
ms.author: mamccrea
ms.date: 12/13/2019
ms.topic: tutorial
ms.openlocfilehash: 460c37e66c2c0a8a9b197a9abaff9eead842bdeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187550"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a><span data-ttu-id="966fd-103">Tutorial: Ausführen von Batchverarbeitung mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="966fd-103">Tutorial: Do batch processing with .NET for Apache Spark</span></span>

<span data-ttu-id="966fd-104">In diesem Tutorial erfahren Sie, wie Sie Batchverarbeitung mithilfe von .NET für Apache Spark ausführen.</span><span class="sxs-lookup"><span data-stu-id="966fd-104">In this tutorial, you learn how to do batch processing using .NET for Apache Spark.</span></span> <span data-ttu-id="966fd-105">Batchverarbeitung ist die Transformation von ruhenden Daten, was bedeutet, dass die Quelldaten bereits in den Datenspeicher geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="966fd-105">Batch processing is the transformation of data at rest, meaning that the source data has already been loaded into data storage.</span></span>

<span data-ttu-id="966fd-106">Batchverarbeitung erfolgt in der Regel über große, flache Datasets, die für eine weitere Analyse vorbereitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="966fd-106">Batch processing is generally performed over large, flat datasets that need to be prepared for further analysis.</span></span> <span data-ttu-id="966fd-107">Protokollverarbeitung und Data Warehousing sind gängige Batchverarbeitungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="966fd-107">Log processing and data warehousing are common batch processing scenarios.</span></span> <span data-ttu-id="966fd-108">In diesem Szenario analysieren Sie Informationen zu GitHub-Projekten, z. B. wie häufig verschiedene Projekte geforkt oder wann Projekte zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="966fd-108">In this scenario, you analyze information about GitHub projects, such as the number of time different projects have been forked or how recently projects have been updated.</span></span>

<span data-ttu-id="966fd-109">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="966fd-109">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="966fd-110">Erstellen und Ausführen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="966fd-110">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="966fd-111">Lesen von Daten in einen DataFrame und Aufbereiten der Daten für die Analyse</span><span class="sxs-lookup"><span data-stu-id="966fd-111">Read data into a DataFrame and prepare it for analysis</span></span>
> * <span data-ttu-id="966fd-112">Verarbeiten der Daten mithilfe von Spark SQL</span><span class="sxs-lookup"><span data-stu-id="966fd-112">Process the data using Spark SQL</span></span>

## <a name="prerequisites"></a><span data-ttu-id="966fd-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="966fd-113">Prerequisites</span></span>

<span data-ttu-id="966fd-114">Wenn Sie zum ersten Mal mit .NET für Apache Spark arbeiten, lesen Sie das Tutorial [Erste Schritte mit .NET for Apache Spark](../tutorials/get-started.md), um zu erfahren, wie Sie Ihre Umgebung vorbereiten und Ihre erste .NET für Apache Spark-Anwendung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="966fd-114">If this is your first time using .NET for Apache Spark, check out the [Get started with .NET for Apache Spark](../tutorials/get-started.md) tutorial to learn how to prepare your environment and run your first .NET for Apache Spark application.</span></span>

## <a name="download-the-sample-data"></a><span data-ttu-id="966fd-115">Herunterladen der Beispieldaten</span><span class="sxs-lookup"><span data-stu-id="966fd-115">Download the sample data</span></span>

<span data-ttu-id="966fd-116">[GHTorrent](http://ghtorrent.org/) überwacht alle öffentlichen GitHub-Ereignisse, z. B. Informationen zu Projekten, Commits und Watchern, und speichert die Ereignisse und deren Struktur in Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="966fd-116">[GHTorrent](http://ghtorrent.org/) monitors all public GitHub events, such as info about projects, commits, and watchers, and stores the events and their structure in databases.</span></span> <span data-ttu-id="966fd-117">Daten, die über verschiedene Zeiträume erfasst werden, sind als herunterladbare Archive verfügbar.</span><span class="sxs-lookup"><span data-stu-id="966fd-117">Data collected over different time periods is available as downloadable archives.</span></span> <span data-ttu-id="966fd-118">Da die Speicherabbilddateien sehr groß sind, wird in diesem Leitfaden eine [gekürzte Version der Speicherabbilddatei](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) verwendet, die von GitHub heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="966fd-118">Because the dump files are very large, this guide uses a [truncated version of the dump file](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) that can be downloaded from GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="966fd-119">Das GHTorrent-DataSet wird in einem dualen Lizenzierungsschema ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)) verteilt.</span><span class="sxs-lookup"><span data-stu-id="966fd-119">The GHTorrent dataset is distributed under a dual licensing scheme ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span></span> <span data-ttu-id="966fd-120">Bei nichtkommerzieller Verwendung (einschließlich, aber nicht beschränkt auf Schulungs-, Forschungs- oder persönliche Zwecke) wird das DataSet unter der [CC-BY-SA-Lizenz](https://creativecommons.org/licenses/by-sa/4.0/) verteilt.</span><span class="sxs-lookup"><span data-stu-id="966fd-120">For non-commercial uses (including, but not limited to, educational, research or personal uses), the dataset is distributed under the [CC-BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="966fd-121">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="966fd-121">Create a console application</span></span>

1. <span data-ttu-id="966fd-122">Führen Sie in der Eingabeaufforderung die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="966fd-122">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   <span data-ttu-id="966fd-123">Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`.</span><span class="sxs-lookup"><span data-stu-id="966fd-123">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="966fd-124">Der `-o`-Parameter erstellt ein Verzeichnis namens *mySparkBatchApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="966fd-124">The `-o` parameter creates a directory named *mySparkBatchApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="966fd-125">Mit dem Befehl `cd mySparkBatchApp` wird das Verzeichnis in das soeben erstellte App-Verzeichnis geändert.</span><span class="sxs-lookup"><span data-stu-id="966fd-125">The `cd mySparkBatchApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="966fd-126">Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket.</span><span class="sxs-lookup"><span data-stu-id="966fd-126">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="966fd-127">Führen Sie in der Konsole den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="966fd-127">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a><span data-ttu-id="966fd-128">Erstellen einer SparkSession</span><span class="sxs-lookup"><span data-stu-id="966fd-128">Create a SparkSession</span></span>

1. <span data-ttu-id="966fd-129">Fügen Sie in *mySparkBatchApp* oben in der Datei *Program.cs* die folgenden zusätzlichen `using`-Anweisungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="966fd-129">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkBatchApp*.</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="966fd-130">Fügen Sie Ihrem Projektnamespace den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="966fd-130">Add the following code to your project namespace.</span></span> <span data-ttu-id="966fd-131">*s_referenceData* wird später im Programm verwendet, um basierend auf dem Datum zu filtern.</span><span class="sxs-lookup"><span data-stu-id="966fd-131">*s_referenceData* is used later in the program to filter based on date.</span></span>

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. <span data-ttu-id="966fd-132">Fügen Sie in der Main-Methode den folgenden Code hinzu, um eine neue SparkSession einzurichten.</span><span class="sxs-lookup"><span data-stu-id="966fd-132">Add the following code inside your Main method to establish a new SparkSession.</span></span> <span data-ttu-id="966fd-133">Die SparkSession ist der Einstiegspunkt in die Programmierung von Spark mit dem Dataset und der DataFrame-API.</span><span class="sxs-lookup"><span data-stu-id="966fd-133">The SparkSession is the entry point to programming Spark with the Dataset and DataFrame API.</span></span> <span data-ttu-id="966fd-134">Der Aufruf des `spark`-Objekts ermöglicht im gesamten Programm den Zugriff auf Spark- und DataFrame-Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="966fd-134">By calling the `spark` object, you can access Spark and DataFrame functionality throughout your program.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a><span data-ttu-id="966fd-135">Vorbereiten der Daten</span><span class="sxs-lookup"><span data-stu-id="966fd-135">Prepare the data</span></span>

1. <span data-ttu-id="966fd-136">Lesen Sie die Eingabedatei in ein `DataFrame`-Objekt, bei dem es sich um eine verteilte Sammlung von Daten handelt, die in benannten Spalten organisiert ist.</span><span class="sxs-lookup"><span data-stu-id="966fd-136">Read the input file into a `DataFrame`, which is a distributed collection of data organized into named columns.</span></span> <span data-ttu-id="966fd-137">Sie können die Spalten für die Daten über <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="966fd-137">You can set the columns for your data through <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>.</span></span> <span data-ttu-id="966fd-138">Verwenden Sie die <xref:Microsoft.Spark.Sql.DataFrame.Show%2A>-Methode, um die Daten in Ihrem DataFrame anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="966fd-138">Use the <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> method to display the data in your DataFrame.</span></span> <span data-ttu-id="966fd-139">Stellen Sie sicher, dass Sie den Pfad der CSV-Datei auf den Speicherort der von Ihnen heruntergeladenen GitHub-Daten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="966fd-139">Be sure to update the CSV file path to the location of the GitHub data you downloaded.</span></span>

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. <span data-ttu-id="966fd-140">Verwenden Sie die <xref:Microsoft.Spark.Sql.DataFrame.Na%2A>-Methode, um Zeilen mit N/V-Werten (NULL-Werten) zu löschen, und die <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A>-Methode, um bestimmte Spalten aus den Daten zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="966fd-140">Use the <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> method to drop rows with NA (null) values, and the <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> method to remove certain columns from your data.</span></span> <span data-ttu-id="966fd-141">Dies hilft, Fehler zu vermeiden, wenn Sie versuchen, NULL-Daten oder Spalten zu analysieren, die für die endgültige Analyse nicht relevant sind.</span><span class="sxs-lookup"><span data-stu-id="966fd-141">This helps prevent errors if you try to analyze null data or columns that are not relevant to your final analysis.</span></span>

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a><span data-ttu-id="966fd-142">Analysieren der Daten</span><span class="sxs-lookup"><span data-stu-id="966fd-142">Analyze the data</span></span>

<span data-ttu-id="966fd-143">Spark SQL ermöglicht Ihnen, SQL-Aufrufe für Ihre Daten durchführen.</span><span class="sxs-lookup"><span data-stu-id="966fd-143">Spark SQL allows you to make SQL calls on your data.</span></span> <span data-ttu-id="966fd-144">Es ist üblich, benutzerdefinierte Funktionen und Spark SQL zu kombinieren, um eine benutzerdefinierte Funktion auf alle Zeilen Ihres DataFrame anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="966fd-144">It's common to combine user-defined functions and Spark SQL to apply a user-defined function to all rows of your DataFrame.</span></span>

<span data-ttu-id="966fd-145">Sie können `spark.Sql` speziell aufrufen, um standardmäßige SQL-Aufrufe in anderen App-Typen zu imitieren.</span><span class="sxs-lookup"><span data-stu-id="966fd-145">You can specifically call `spark.Sql` to mimic standard SQL calls seen in other types of apps.</span></span> <span data-ttu-id="966fd-146">Sie können auch Methoden wie <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> und <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> zum speziellen Kombinieren, Filtern und Ausführen von Berechnungen für Ihre Daten aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="966fd-146">You can also call methods like <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> and <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> to specifically combine, filter, and perform calculations on your data.</span></span>

<span data-ttu-id="966fd-147">Das Ziel dieser App besteht darin, Einblicke in die GitHub-Projektdaten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="966fd-147">The goal of this app is to gain some insights about the GitHub projects data.</span></span> <span data-ttu-id="966fd-148">Fügen Sie dem Programm die folgenden Codeausschnitte hinzu, um die Daten zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="966fd-148">Add the following code snippets to your program to analyze the data.</span></span>

1. <span data-ttu-id="966fd-149">Durch Hinzufügen des folgenden Codeblocks wird ermittelt, wie oft jede Sprache geforkt wurde.</span><span class="sxs-lookup"><span data-stu-id="966fd-149">Add the following block of code finds the number of times each language has been forked.</span></span> <span data-ttu-id="966fd-150">Zunächst werden die Daten nach der Sprache gruppiert.</span><span class="sxs-lookup"><span data-stu-id="966fd-150">First, the data is grouped by language.</span></span> <span data-ttu-id="966fd-151">Anschließend wird die durchschnittliche Anzahl der Forks aus jeder Sprache ermittelt.</span><span class="sxs-lookup"><span data-stu-id="966fd-151">Then, the average number of forks from each language is taken.</span></span>

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. <span data-ttu-id="966fd-152">Fügen Sie den folgenden Codeblock hinzu, um die durchschnittliche Anzahl der Forks in absteigender Reihenfolge zu sortieren, um zu ermitteln, welche Sprachen am meisten geforkt werden.</span><span class="sxs-lookup"><span data-stu-id="966fd-152">Add the following block of code to order the average number of forks in descending order to see which languages are the most forked.</span></span> <span data-ttu-id="966fd-153">Dies bedeutet, die größte Anzahl von Forks zuerst angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="966fd-153">That is, the largest number of forks will appear first.</span></span>

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. <span data-ttu-id="966fd-154">Der nächste Codeblock zeigt Ihnen, wann Projekte zuletzt aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="966fd-154">The next block of code shows you how recently projects have been updated.</span></span> <span data-ttu-id="966fd-155">Sie registrieren eine neue benutzerdefinierte Funktion namens *MyUDF* und vergleichen sie mit einem Datum (*s_referenceDate*), das am Anfang des Tutorials deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="966fd-155">You register a new user-defined function called *MyUDF* and compare it with a date, *s_referenceDate*, which was declared at the beginning of the tutorial.</span></span> <span data-ttu-id="966fd-156">Das Datum für jedes Projekt wird mit dem Verweisdatum verglichen.</span><span class="sxs-lookup"><span data-stu-id="966fd-156">The date for each project is compared against the reference date.</span></span> <span data-ttu-id="966fd-157">Anschließend wird Spark SQL verwendet, um die benutzerdefinierte Funktion für jede Zeile der Daten aufzurufen, um jedes Projekt im Dataset zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="966fd-157">Then, Spark SQL is used to call the UDF on each row of the data to analyze each project in the data set.</span></span>

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);
   cleanedProjects.CreateOrReplaceTempView("dateView");

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. <span data-ttu-id="966fd-158">Rufen Sie `spark.Stop()` auf, um die SparkSession zu beenden.</span><span class="sxs-lookup"><span data-stu-id="966fd-158">Call `spark.Stop()` to end the SparkSession.</span></span>

## <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="966fd-159">Verwenden von spark-submit zum Ausführen Ihrer App</span><span class="sxs-lookup"><span data-stu-id="966fd-159">Use spark-submit to run your app</span></span>

1. <span data-ttu-id="966fd-160">Verwenden Sie den folgenden Befehl, um die .NET-App zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="966fd-160">Use the following command to build your .NET app:</span></span>

   ```dotnetcli
   dotnet build
   ```

1. <span data-ttu-id="966fd-161">Führen Sie Ihre App mit `spark-submit` aus.</span><span class="sxs-lookup"><span data-stu-id="966fd-161">Run your app with `spark-submit`.</span></span> <span data-ttu-id="966fd-162">Aktualisieren Sie unbedingt den folgenden Befehl mit dem aktuellen Pfad zu Ihrer JAR-Datei für Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="966fd-162">Be sure to update the following command with the actual paths to your Microsoft Spark jar file.</span></span>

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<version>.jar dotnet /<path>/to/netcoreapp<version>/GitHubProjects.dll
   ```

## <a name="get-the-code"></a><span data-ttu-id="966fd-163">Abrufen des Codes</span><span class="sxs-lookup"><span data-stu-id="966fd-163">Get the code</span></span>

<span data-ttu-id="966fd-164">Die [vollständige Lösung](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="966fd-164">You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.</span></span>

## <a name="next-steps"></a><span data-ttu-id="966fd-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="966fd-165">Next steps</span></span>

<span data-ttu-id="966fd-166">Fahren Sie mit dem nächsten Artikel fort, um zu erfahren, wie Sie Streamingdaten mit .NET für Apache Spark verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="966fd-166">Advance to the next article to learn how to process streaming data with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="966fd-167">Tutorial: Strukturiertes Streaming mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="966fd-167">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
