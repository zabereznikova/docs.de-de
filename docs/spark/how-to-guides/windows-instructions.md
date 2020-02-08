---
title: Erstellen einer .NET für Apache Spark-Anwendung unter Windows
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows erstellen.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: e6dec09f7d3e8d478cdcccf9df1c3e72d5f884eb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76928061"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="3dd0a-103">Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="3dd0a-104">Dieser Artikel erläutert, wie Sie .NET für Apache Spark-Anwendungen unter Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3dd0a-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3dd0a-105">Prerequisites</span></span>

<span data-ttu-id="3dd0a-106">Wenn bereits alle folgenden Voraussetzungen erfüllt sind, fahren Sie mit den Schritten zum [Erstellen](#build) fort.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="3dd0a-107">Laden Sie das **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** herunter, und installieren Sie es. Durch die Installation des SDK wird die Toolkette `dotnet` zum Pfad hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="3dd0a-108">Die .NET Core-Versionen 2.1, 2.2 und 3.1 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="3dd0a-109">Installieren Sie **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 oder höher).</span><span class="sxs-lookup"><span data-stu-id="3dd0a-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="3dd0a-110">Die Community-Version ist vollkommen kostenlos.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-110">The Community version is completely free.</span></span> <span data-ttu-id="3dd0a-111">Schließen Sie beim Konfigurieren Ihrer Installation mindestens die folgenden Komponenten ein:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="3dd0a-112">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="3dd0a-112">.NET desktop development</span></span>
       * <span data-ttu-id="3dd0a-113">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="3dd0a-113">All Required Components</span></span>
         * <span data-ttu-id="3dd0a-114">.NET Framework 4.6.1-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="3dd0a-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="3dd0a-115">Plattformübergreifende .NET Core-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="3dd0a-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="3dd0a-116">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="3dd0a-116">All Required Components</span></span>
  3. <span data-ttu-id="3dd0a-117">Installieren Sie **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span> 
     - <span data-ttu-id="3dd0a-118">Wählen Sie eine geeignete Version für Ihr Betriebssystem aus, z. B. „jdk-8u201-windows-x64.exe“ für Windows-x64-Computer.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-118">Select the appropriate version for your operating system e.g., jdk-8u201-windows-x64.exe for Win x64 machine.</span></span>
     - <span data-ttu-id="3dd0a-119">Führen Sie die Installation mithilfe eines Installationsprogramms aus, und überprüfen Sie, ob Sie `java` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-119">Install using the installer and verify you are able to run `java` from your command-line.</span></span>
  4. <span data-ttu-id="3dd0a-120">Installieren Sie **[Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi)**.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-120">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="3dd0a-121">Laden Sie [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-121">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
     - <span data-ttu-id="3dd0a-122">Extrahieren Sie die Datei in ein lokales Verzeichnis, z. B. `C:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-122">Extract to a local directory e.g., `C:\bin\apache-maven-3.6.0\`.</span></span>
     - <span data-ttu-id="3dd0a-123">Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Maven hinzu, beispielsweise so: `C:\bin\apache-maven-3.6.0\bin`.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-123">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml) e.g., `C:\bin\apache-maven-3.6.0\bin`.</span></span>
     - <span data-ttu-id="3dd0a-124">Überprüfen Sie, ob Sie `mvn` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-124">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="3dd0a-125">Installieren Sie **[Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html)**.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-125">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="3dd0a-126">Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei mit einem Tool wie [7-Zip](https://www.7-zip.org/) in einen lokalen Ordner (z. B. `C:\bin\spark-2.3.2-bin-hadoop2.7\`).</span><span class="sxs-lookup"><span data-stu-id="3dd0a-126">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (e.g., `C:\bin\spark-2.3.2-bin-hadoop2.7\`) using [7-zip](https://www.7-zip.org/).</span></span> <span data-ttu-id="3dd0a-127">(Unterstützt werden die Spark-Versionen 2.3.\*, 2.4.0, 2.4.1, 2.4.3 und 2.4.4.)</span><span class="sxs-lookup"><span data-stu-id="3dd0a-127">(The supported spark versions are 2.3.\*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="3dd0a-128">Fügen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` hinzu, z. B. `C:\bin\spark-2.3.2-bin-hadoop2.7\`.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-128">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` e.g., `C:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\       
       ```

     - <span data-ttu-id="3dd0a-129">Fügen Sie Apache Spark zu Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) hinzu, z. B. `C:\bin\spark-2.3.2-bin-hadoop2.7\bin`.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-129">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml) e.g., `C:\bin\spark-2.3.2-bin-hadoop2.7\bin`.</span></span>

       ```powershell       
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```
     
     - <span data-ttu-id="3dd0a-130">Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-130">Verify you are able to run `spark-shell` from your command-line.</span></span>        
        <span data-ttu-id="3dd0a-131">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-131">Sample console output:</span></span>

        ```
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 2.3.2
              /_/

        Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. <span data-ttu-id="3dd0a-132">Installieren Sie **[WinUtils](https://github.com/steveloughran/winutils)**.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-132">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="3dd0a-133">Laden Sie die Binärdatei `winutils.exe` aus dem [WinUtils-Repository](https://github.com/steveloughran/winutils) herunter.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-133">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="3dd0a-134">Wählen Sie die Hadoop-Version aus, mit der die Spark-Distribution kompiliert wurde, z. B. „hadoop-2.7.1“ für Spark 2.3.2.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-134">You should select the version of Hadoop the Spark distribution was compiled with, e.g. use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="3dd0a-135">Speichern Sie die Binärdatei `winutils.exe` in einem Verzeichnis Ihrer Wahl, z. B. `C:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-135">Save `winutils.exe` binary to a directory of your choice e.g., `C:\hadoop\bin`.</span></span>
     - <span data-ttu-id="3dd0a-136">Legen Sie `HADOOP_HOME` auf das Verzeichnis fest, in dem sich „winutils.exe“ befindet, und lassen Sie „bin“ weg.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-136">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="3dd0a-137">Beispiel für die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-137">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="3dd0a-138">Fügen Sie der PATH-Umgebungsvariable `%HADOOP_HOME%\bin` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-138">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="3dd0a-139">Beispiel für die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-139">For instance, using command-line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="3dd0a-140">Stellen Sie sicher, dass Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-140">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command-line before you move to the next section.</span></span> <span data-ttu-id="3dd0a-141">Sind Sie der Meinung, dass es eine bessere Möglichkeit gibt?</span><span class="sxs-lookup"><span data-stu-id="3dd0a-141">Feel there is a better way?</span></span> <span data-ttu-id="3dd0a-142">Dann eröffnen Sie ein [Issue](https://github.com/dotnet/spark/issues), und teilen Sie uns diese mit.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-142">Please [open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="3dd0a-143">Möglicherweise ist eine neue Instanz der Befehlszeile erforderlich, wenn Umgebungsvariablen aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-143">A new instance of the command-line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="3dd0a-144">Build</span><span class="sxs-lookup"><span data-stu-id="3dd0a-144">Build</span></span>

<span data-ttu-id="3dd0a-145">Für den Rest des vorliegenden Leitfadens müssen Sie das .NET für Apache Spark-Repository auf Ihren Computer geklont haben.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-145">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="3dd0a-146">Sie können einen beliebigen Speicherort für das geklonte Repository auswählen, z. B. `C:\github\dotnet-spark\`.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-146">You can choose any location for the cloned repository, e.g., `C:\github\dotnet-spark\`.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="3dd0a-147">Erstellen der Scala-Erweiterungsebene für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="3dd0a-147">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="3dd0a-148">Wenn Sie eine .NET-Anwendung übermitteln, bietet .NET für Apache Spark die erforderliche, in Scala geschriebene Logik, die Apache Spark darüber informiert, wie Ihre Anforderungen verarbeitet werden sollen (z. B. Anforderungen zum Erstellen einer neuen Spark-Sitzung, zum Übertragen von Daten von .NET an JVM usw.).</span><span class="sxs-lookup"><span data-stu-id="3dd0a-148">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (e.g., request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="3dd0a-149">Diese Logik finden Sie im [.NET für Spark-Scala-Quellcode](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="3dd0a-149">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="3dd0a-150">Unabhängig davon, ob Sie .NET Framework oder .NET Core verwenden, müssen Sie die Scala-Erweiterungsebene für .NET für Apache Spark erstellen:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-150">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package 
```

<span data-ttu-id="3dd0a-151">Sie werden feststellen, dass JAR-Dateien für die unterstützten Spark-Versionen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-151">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="3dd0a-152">Erstellen der .NET für Spark-Beispielanwendungen</span><span class="sxs-lookup"><span data-stu-id="3dd0a-152">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="3dd0a-153">In diesem Abschnitt wird erläutert, wie Sie die [Beispielanwendungen](https://github.com/dotnet/spark/tree/master/examples) für .NET für Apache Spark erstellen.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-153">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="3dd0a-154">Diese Schritte tragen zu einem besseren Verständnis des gesamten Erstellungsprozesses für alle .NET für Spark-Anwendungen bei.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-154">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="3dd0a-155">Verwenden von Visual Studio für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3dd0a-155">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="3dd0a-156">Öffnen Sie `src\csharp\Microsoft.Spark.sln` in Visual Studio, und erstellen Sie das `Microsoft.Spark.CSharp.Examples`-Projekt im Ordner `examples` (damit wird auch das Projekt für die .NET-Bindungen erstellt).</span><span class="sxs-lookup"><span data-stu-id="3dd0a-156">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="3dd0a-157">Wenn Sie möchten, können Sie im `Microsoft.Spark.Examples`-Projekt auch selbst Code schreiben („input_file.json“ in diesem Beispiel ist eine JSON-Datei mit den Daten, mit denen Sie den Datenrahmen erstellen möchten):</span><span class="sxs-lookup"><span data-stu-id="3dd0a-157">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     <span data-ttu-id="3dd0a-158">Sobald der Buildvorgang erfolgreich abgeschlossen wurde, sehen Sie, dass die entsprechenden Binärdateien im Ausgabeverzeichnis erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-158">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>     
     <span data-ttu-id="3dd0a-159">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-159">Sample console output:</span></span>
     
      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```     

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="3dd0a-160">Verwenden der .NET Core-CLI für .NET Core</span><span class="sxs-lookup"><span data-stu-id="3dd0a-160">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="3dd0a-161">Wir arbeiten derzeit daran, die .NET Core-Builds für Spark. NET zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-161">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="3dd0a-162">Bis es soweit ist, müssen Sie leider noch einige Schritte manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-162">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="3dd0a-163">Erstellen des Workers:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-163">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
      
      <span data-ttu-id="3dd0a-164">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-164">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish\
      ```    

  2. <span data-ttu-id="3dd0a-165">Kompilieren der Beispiele:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-165">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
   
      <span data-ttu-id="3dd0a-166">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-166">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish\
      ```     

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="3dd0a-167">Ausführen der .NET für Spark-Beispielanwendungen</span><span class="sxs-lookup"><span data-stu-id="3dd0a-167">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="3dd0a-168">Nach dem Erstellen der Beispiele erfolgt deren Ausführung über `spark-submit` – unabhängig davon, ob .NET Framework oder .NET Core als Ziel dient.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-168">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="3dd0a-169">Stellen Sie sicher, dass alle [Voraussetzungen](#prerequisites) erfüllt sind und Apache Spark installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3dd0a-169">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="3dd0a-170">Fügen Sie der Umgebungsvariable `DOTNET_WORKER_DIR` oder `PATH` den Pfad hinzu, in dem die `Microsoft.Spark.Worker`-Binärdatei generiert wurde (z. B. `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461` für .NET Framework, `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish` für .NET Core):</span><span class="sxs-lookup"><span data-stu-id="3dd0a-170">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (e.g., `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461` for .NET Framework, `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish` for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="3dd0a-171">Öffnen Sie PowerShell, und wechseln Sie zu dem Verzeichnis, in dem die Binärdatei Ihrer App generiert wurde (z. B. `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461` für .NET Framework, `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish` für .NET Code):</span><span class="sxs-lookup"><span data-stu-id="3dd0a-171">Open Powershell and go to the directory where your app binary has been generated (e.g., `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461` for .NET Framework, `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish` for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="3dd0a-172">Die Ausführung Ihrer App folgt dieser grundlegenden Struktur:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-172">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="3dd0a-173">Hier einige Beispiele, die Sie ausführen können:</span><span class="sxs-lookup"><span data-stu-id="3dd0a-173">Here are some examples you can run:</span></span>

     - <span data-ttu-id="3dd0a-174">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="3dd0a-174">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="3dd0a-175">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="3dd0a-175">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="3dd0a-176">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="3dd0a-176">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="3dd0a-177">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="3dd0a-177">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd 
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
