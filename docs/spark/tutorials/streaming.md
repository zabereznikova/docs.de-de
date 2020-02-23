---
title: Tutorial zu Structured Streaming mit .NET für Apache Spark
description: In diesem Tutorial erfahren Sie, wie Sie .NET für Apache Spark für Spark Structured Streaming verwenden.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: 83d44af080d95ab6f9311ddd3ca4860806757436
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504040"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a><span data-ttu-id="607f5-103">Tutorial: Structured Streaming mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="607f5-103">Tutorial: Structured Streaming with .NET for Apache Spark</span></span> 

<span data-ttu-id="607f5-104">Dieses Tutorial zeigt Ihnen, wie Sie Spark Structured Streaming mit .NET for Apache Spark aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="607f5-104">This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark.</span></span> <span data-ttu-id="607f5-105">Spark Structured Streaming ist die Unterstützung von Apache Spark für die Verarbeitung von Echtzeitdatenströmen.</span><span class="sxs-lookup"><span data-stu-id="607f5-105">Spark Structured Streaming is Apache Spark's support for processing real-time data streams.</span></span> <span data-ttu-id="607f5-106">Datenstromverarbeitung bedeutet, dass Livedaten während ihrer Erstellung analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="607f5-106">Stream processing means analyzing live data as it's being produced.</span></span>

<span data-ttu-id="607f5-107">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="607f5-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="607f5-108">Erstellen und Ausführen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="607f5-108">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="607f5-109">Verwenden von netcat zum Erstellen eines Datenstroms</span><span class="sxs-lookup"><span data-stu-id="607f5-109">Use netcat to create a data stream</span></span>
> * <span data-ttu-id="607f5-110">Verwenden von benutzerdefinierten Funktionen und SparkSQL zur Analyse von Streamingdaten</span><span class="sxs-lookup"><span data-stu-id="607f5-110">Use user-defined functions and SparkSQL to analyze streaming data</span></span>

## <a name="prerequisites"></a><span data-ttu-id="607f5-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="607f5-111">Prerequisites</span></span>

<span data-ttu-id="607f5-112">Wenn dies Ihre erste .NET für Apache Spark-Anwendung ist, beginnen Sie mit dem [Tutorial „Erste Schritte“](get-started.md), um sich mit den Grundlagen vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="607f5-112">If this is your first .NET for Apache Spark application, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="607f5-113">Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="607f5-113">Create a console application</span></span>

1. <span data-ttu-id="607f5-114">Führen Sie in der Eingabeaufforderung die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="607f5-114">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   <span data-ttu-id="607f5-115">Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`.</span><span class="sxs-lookup"><span data-stu-id="607f5-115">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="607f5-116">Der `-o`-Parameter erstellt ein Verzeichnis namens *mySparkStreamingApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="607f5-116">The `-o` parameter creates a directory named *mySparkStreamingApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="607f5-117">Mit dem Befehl `cd mySparkStreamingApp` wird das Verzeichnis in das soeben erstellte App-Verzeichnis geändert.</span><span class="sxs-lookup"><span data-stu-id="607f5-117">The `cd mySparkStreamingApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="607f5-118">Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket.</span><span class="sxs-lookup"><span data-stu-id="607f5-118">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="607f5-119">Führen Sie in der Konsole den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="607f5-119">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a><span data-ttu-id="607f5-120">Einrichten eines Datenstroms und Herstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="607f5-120">Establish and connect to a data stream</span></span>

<span data-ttu-id="607f5-121">Eine beliebte Methode zum Testen der Datenstromverarbeitung ist **netcat**.</span><span class="sxs-lookup"><span data-stu-id="607f5-121">One popular way to test stream processing is through **netcat**.</span></span> <span data-ttu-id="607f5-122">netcat (auch als *nc*bezeichnet) ermöglicht Ihnen das Lesen von Daten aus und Schreiben von Daten in Netzwerkverbindungen.</span><span class="sxs-lookup"><span data-stu-id="607f5-122">netcat (also known as *nc*) allows you to read from and write to network connections.</span></span> <span data-ttu-id="607f5-123">Sie stellen in einem Terminalfenster eine Netzwerkverbindung mit netcat her.</span><span class="sxs-lookup"><span data-stu-id="607f5-123">You establish a network connection with netcat through a terminal window.</span></span> 

### <a name="create-a-data-stream-with-netcat"></a><span data-ttu-id="607f5-124">Erstellen eines Datenstroms mit netcat</span><span class="sxs-lookup"><span data-stu-id="607f5-124">Create a data stream with netcat</span></span>

1. <span data-ttu-id="607f5-125">[Laden Sie netcat herunter](https://sourceforge.net/projects/nc110/files/).</span><span class="sxs-lookup"><span data-stu-id="607f5-125">[Download netcat](https://sourceforge.net/projects/nc110/files/).</span></span> <span data-ttu-id="607f5-126">Extrahieren Sie dann die Datei aus der heruntergeladenen ZIP-Datei, und fügen Sie das von Ihnen extrahierte Verzeichnis an Ihre Umgebungsvariable PATH an.</span><span class="sxs-lookup"><span data-stu-id="607f5-126">Then, extract the file from the zip download and append the directory you extracted to your "PATH" environment variable.</span></span>

2. <span data-ttu-id="607f5-127">Um eine neue Verbindung herzustellen, öffnen Sie eine neue Konsole und führen den folgenden Befehl aus, der sich an Port 9999 mit localhost verbindet.</span><span class="sxs-lookup"><span data-stu-id="607f5-127">To start a new connection, open a new console and run the following command which connects to localhost on port 9999.</span></span>

   <span data-ttu-id="607f5-128">Unter Windows:</span><span class="sxs-lookup"><span data-stu-id="607f5-128">On Windows:</span></span>

   ```console
   nc -vvv -l -p 9999
   ```

   <span data-ttu-id="607f5-129">Unter Linux:</span><span class="sxs-lookup"><span data-stu-id="607f5-129">On Linux:</span></span>

   ```console
   nc -lk 9999
   ```

   <span data-ttu-id="607f5-130">Ihr Spark-Programm lauscht auf Ihre Eingaben an dieser Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="607f5-130">Your Spark program listens for the input you type into this command prompt.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="607f5-131">Erstellen einer SparkSession</span><span class="sxs-lookup"><span data-stu-id="607f5-131">Create a SparkSession</span></span>

1. <span data-ttu-id="607f5-132">Fügen Sie in *mySparkStreamingApp* oben in der Datei *Program.cs* die folgenden zusätzlichen `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="607f5-132">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkStreamingApp*:</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="607f5-133">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um eine neue `SparkSession` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="607f5-133">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="607f5-134">Die Spark-Sitzung ist der Einstiegspunkt in die Programmierung von Spark mit der Dataset- und DataFrame-API.</span><span class="sxs-lookup"><span data-stu-id="607f5-134">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   <span data-ttu-id="607f5-135">Der Aufruf des oben erstellten *spark*-Objekts ermöglicht im gesamten Programm den Zugriff auf Spark- und DataFrame-Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="607f5-135">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="connect-to-a-stream-with-readstream"></a><span data-ttu-id="607f5-136">Herstellen einer Verbindung mit einem Datenstrom mit ReadStream()</span><span class="sxs-lookup"><span data-stu-id="607f5-136">Connect to a stream with ReadStream()</span></span>

<span data-ttu-id="607f5-137">Die `ReadStream()`-Methode gibt das Element `DataStreamReader` zurück, das zum Einlesen von Streamingdaten als `DataFrame` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="607f5-137">The `ReadStream()` method returns a `DataStreamReader` that can be used to read streaming data in as a `DataFrame`.</span></span> <span data-ttu-id="607f5-138">Fügen Sie die Host- und Portinformationen hinzu, um Ihrer Spark-App anzugeben, wo ihre Streamingdaten zu erwarten sind.</span><span class="sxs-lookup"><span data-stu-id="607f5-138">Include the host and port information to tell your Spark app where to expect its streaming data.</span></span>

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a><span data-ttu-id="607f5-139">Registrieren einer benutzerdefinierten Funktion</span><span class="sxs-lookup"><span data-stu-id="607f5-139">Register a user-defined function</span></span>

<span data-ttu-id="607f5-140">Sie können in Spark-Anwendungen mithilfe *benutzerdefinierter Funktionen* Berechnungen und Analysen Ihrer Daten durchführen.</span><span class="sxs-lookup"><span data-stu-id="607f5-140">You can use UDFs, *user-defined functions*, in Spark applications to perform calculations and analysis on your data.</span></span>

<span data-ttu-id="607f5-141">Fügen Sie der `Main`-Methode den folgenden Code hinzu, um die benutzerdefinierte Funktion `udfArray` zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="607f5-141">Add the following code to your `Main` method to register a UDF called `udfArray`.</span></span> 

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

<span data-ttu-id="607f5-142">Diese benutzerdefinierte Funktion verarbeitet jede vom netcat-Terminal empfangene Zeichenfolge, um ein Array zu erstellen. Es enthält (in *str*) die ursprüngliche Zeichenfolge gefolgt von der ursprünglichen Zeichenfolge verkettet mit der Länge der ursprünglichen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="607f5-142">This UDF processes each string it receives from the netcat terminal to produce an array that includes the original string (contained in *str*), followed by the original string concatenated with the length of the original string.</span></span> 

<span data-ttu-id="607f5-143">Wenn Sie beispielsweise im netcat-Terminal *Hello world* eingeben, wird ein Array mit den folgenden Elementen erzeugt:</span><span class="sxs-lookup"><span data-stu-id="607f5-143">For example, entering *Hello world* in the netcat terminal produces an array where:</span></span>

* <span data-ttu-id="607f5-144">array\[0] = Hello world</span><span class="sxs-lookup"><span data-stu-id="607f5-144">array\[0] = Hello world</span></span>
* <span data-ttu-id="607f5-145">array\[1] = Hello world 11</span><span class="sxs-lookup"><span data-stu-id="607f5-145">array\[1] = Hello world 11</span></span>

## <a name="use-sparksql"></a><span data-ttu-id="607f5-146">Verwenden von SparkSQL</span><span class="sxs-lookup"><span data-stu-id="607f5-146">Use SparkSQL</span></span>

<span data-ttu-id="607f5-147">Verwenden Sie SparkSQL, um verschiedene Funktionen auf die in Ihrem DataFrame gespeicherten Daten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="607f5-147">Use SparkSQL to perform various functions on the data stored in your DataFrame.</span></span> <span data-ttu-id="607f5-148">Es ist üblich, benutzerdefinierte Funktionen und SparkSQL zu kombinieren, um eine benutzerdefinierte Funktion auf jede Zeile in einem DataFrame anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="607f5-148">It's common to combine UDFs and SparkSQL to apply a UDF to each row of a DataFrame.</span></span>

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

<span data-ttu-id="607f5-149">Dieser Codeausschnitt wendet *udfArray* auf alle Werte in Ihrem DataFrame an, der alle Zeichenfolgen darstellt, die von Ihrem netcat-Terminal gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="607f5-149">This code snippet applies *udfArray* to each value in your DataFrame, which represents each string read from your netcat terminal.</span></span> <span data-ttu-id="607f5-150">Wenden Sie die SparkSQL-Methode <xref:Microsoft.Spark.Sql.Functions.Explode%2A> an, um jeden Eintrag Ihres Arrays in einer eigenen Zeile zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="607f5-150">Apply the SparkSQL method <xref:Microsoft.Spark.Sql.Functions.Explode%2A> to put each entry of your array in its own row.</span></span> <span data-ttu-id="607f5-151">Verwenden Sie schließlich <xref:Microsoft.Spark.Sql.DataFrame.Select%2A>, um die von Ihnen generierten Spalten im neuen DataFrame *arrayDF* zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="607f5-151">Finally, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> to place the columns you've produced in the new DataFrame *arrayDF.*</span></span>

## <a name="display-your-stream"></a><span data-ttu-id="607f5-152">Anzeigen Ihres Datenstroms</span><span class="sxs-lookup"><span data-stu-id="607f5-152">Display your stream</span></span>

<span data-ttu-id="607f5-153">Verwenden Sie <xref:Microsoft.Spark.Sql.DataFrame.WriteStream>, um Eigenschaften Ihrer Ausgabe festzulegen, wie z. B. das Ausgeben von Ergebnissen in der Konsole und das Anzeigen nur der letzten Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="607f5-153">Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> to establish characteristics of your output, such as printing results to the console and displaying only the most recent output.</span></span>

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a><span data-ttu-id="607f5-154">Ausführen Ihres Codes</span><span class="sxs-lookup"><span data-stu-id="607f5-154">Run your code</span></span>

<span data-ttu-id="607f5-155">Beim strukturierten Streaming in Spark werden die Daten in einer Folge kleiner **Batches** verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="607f5-155">Structured streaming in Spark processes data through a series of small **batches**.</span></span>  <span data-ttu-id="607f5-156">Wenn Sie Ihr Programm ausführen, können Sie an der Eingabeaufforderung, über die Sie die Verbindung mit netcat herstellen, mit der Eingabe beginnen.</span><span class="sxs-lookup"><span data-stu-id="607f5-156">When you run your program, the command prompt where you establish the netcat connection allows you to start typing.</span></span> <span data-ttu-id="607f5-157">Bei jedem Drücken der EINGABETASTE nach Eingabe von Daten in diese Eingabeaufforderung betrachtet Spark Ihre Eingabe als Batch und führt die benutzerdefinierte Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="607f5-157">Each time you press the Enter key after typing data in that command prompt, Spark considers your entry a batch and runs the UDF.</span></span>

### <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="607f5-158">Verwenden von spark-submit zum Ausführen Ihrer App</span><span class="sxs-lookup"><span data-stu-id="607f5-158">Use spark-submit to run your app</span></span>

<span data-ttu-id="607f5-159">Nach dem Start einer neuen netcat-Sitzung öffnen Sie ein neues Terminal, und führen Sie den Befehl `spark-submit` aus, der dem folgenden Befehl ähnelt:</span><span class="sxs-lookup"><span data-stu-id="607f5-159">After starting a new netcat session, open a new terminal and run your `spark-submit` command, similar to the following command:</span></span>

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> <span data-ttu-id="607f5-160">Aktualisieren Sie unbedingt den obigen Befehl mit dem aktuellen Pfad zu Ihrer JAR-Datei für Microsoft Spark.</span><span class="sxs-lookup"><span data-stu-id="607f5-160">Be sure to update the above command with the actual path to your Microsoft Spark jar file.</span></span> <span data-ttu-id="607f5-161">Der obige Befehl geht auch davon aus, dass Ihr netcat-Server auf localhost an Port 9999 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="607f5-161">The above command also assumes your netcat server is running on localhost port 9999.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="607f5-162">Abrufen des Codes</span><span class="sxs-lookup"><span data-stu-id="607f5-162">Get the code</span></span>

<span data-ttu-id="607f5-163">In diesem Tutorial wird das Beispiel [StructuredNetworkCharacterCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) verwendet. Auf GitHub gibt es jedoch drei weitere vollständige Beispiele für die Verarbeitung von Datenströmen:</span><span class="sxs-lookup"><span data-stu-id="607f5-163">This tutorial uses the [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) example, but there are three other full stream processing examples on GitHub:</span></span>

* <span data-ttu-id="607f5-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): dient zum Zählen der Wörter in Daten, die aus einer beliebigen Quell gestreamt werden</span><span class="sxs-lookup"><span data-stu-id="607f5-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): word count on data streamed from any source</span></span>
* <span data-ttu-id="607f5-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): dient zum Zählen der Wörter in Daten mit Windowinglogik</span><span class="sxs-lookup"><span data-stu-id="607f5-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): word count on data with windowing logic</span></span>
* <span data-ttu-id="607f5-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): dient zum Zählen der Wörter in Daten, die aus Kafka gestreamt werden</span><span class="sxs-lookup"><span data-stu-id="607f5-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): word count on data streamed from Kafka</span></span>

## <a name="next-steps"></a><span data-ttu-id="607f5-167">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="607f5-167">Next steps</span></span>

<span data-ttu-id="607f5-168">Fahren Sie mit dem nächsten Artikel fort, um zu erfahren, wie Sie Ihre .NET für Apache Spark-Anwendung in Databricks bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="607f5-168">Advance to the next article to learn how to deploy your .NET for Apache Spark application to Databricks.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="607f5-169">Tutorial: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks</span><span class="sxs-lookup"><span data-stu-id="607f5-169">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>](databricks-deployment.md)
