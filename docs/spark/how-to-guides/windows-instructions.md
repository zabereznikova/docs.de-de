---
title: Erstellen einer .NET für Apache Spark-Anwendung unter Windows
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows erstellen.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: 6d52e5be8c8e528880eece5a9b46fb08933c1eb3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617664"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="0510e-103">Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="0510e-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="0510e-104">Dieser Artikel erläutert, wie Sie .NET für Apache Spark-Anwendungen unter Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="0510e-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="0510e-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0510e-105">Prerequisites</span></span>

<span data-ttu-id="0510e-106">Wenn bereits alle folgenden Voraussetzungen erfüllt sind, fahren Sie mit den Schritten zum [Erstellen](#build) fort.</span><span class="sxs-lookup"><span data-stu-id="0510e-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="0510e-107">Laden Sie das **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** herunter, und installieren Sie es. Durch die Installation des SDK wird die Toolkette `dotnet` zum Pfad hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0510e-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="0510e-108">Die .NET Core-Versionen 2.1, 2.2 und 3.1 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0510e-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="0510e-109">Installieren Sie **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 oder höher).</span><span class="sxs-lookup"><span data-stu-id="0510e-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="0510e-110">Die Community-Version ist vollkommen kostenlos.</span><span class="sxs-lookup"><span data-stu-id="0510e-110">The Community version is completely free.</span></span> <span data-ttu-id="0510e-111">Schließen Sie beim Konfigurieren Ihrer Installation mindestens die folgenden Komponenten ein:</span><span class="sxs-lookup"><span data-stu-id="0510e-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="0510e-112">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="0510e-112">.NET desktop development</span></span>
       * <span data-ttu-id="0510e-113">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="0510e-113">All Required Components</span></span>
         * <span data-ttu-id="0510e-114">.NET Framework 4.6.1-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="0510e-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="0510e-115">Plattformübergreifende .NET Core-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="0510e-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="0510e-116">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="0510e-116">All Required Components</span></span>
  3. <span data-ttu-id="0510e-117">Installieren Sie **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** .</span><span class="sxs-lookup"><span data-stu-id="0510e-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span>
     - <span data-ttu-id="0510e-118">Wählen Sie die für Ihr Betriebssystem geeignete Version aus.</span><span class="sxs-lookup"><span data-stu-id="0510e-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0510e-119">Zum Beispiel *jdk-8u201-windows-x64.exe* für Windows x64-Computer.</span><span class="sxs-lookup"><span data-stu-id="0510e-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="0510e-120">Führen Sie die Installation mithilfe des Installationsprogramms aus, und überprüfen Sie, ob Sie `java` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0510e-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="0510e-121">Installieren Sie **[Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi)** .</span><span class="sxs-lookup"><span data-stu-id="0510e-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="0510e-122">Laden Sie [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="0510e-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="0510e-123">Extrahieren Sie die Datei in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0510e-123">Extract to a local directory.</span></span> <span data-ttu-id="0510e-124">Zum Beispiel \*C:\bin\apache-maven-3.6.0\*</span><span class="sxs-lookup"><span data-stu-id="0510e-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="0510e-125">Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Maven hinzu.</span><span class="sxs-lookup"><span data-stu-id="0510e-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0510e-126">Zum Beispiel *C:\bin\apache-maven-3.6.0\bin*</span><span class="sxs-lookup"><span data-stu-id="0510e-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="0510e-127">Überprüfen Sie, ob Sie `mvn` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0510e-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="0510e-128">Installieren Sie **[Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html)** .</span><span class="sxs-lookup"><span data-stu-id="0510e-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="0510e-129">Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei mit [7-zip](https://www.7-zip.org/) in einen lokalen Ordner (zum Beispiel *C:\bin\spark-2.3.2-bin-hadoop2.7\*). (Die folgenden Spark-Versionen werden unterstützt: 2.3.* , 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span><span class="sxs-lookup"><span data-stu-id="0510e-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-2.3.2-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="0510e-130">Fügen Sie eine [neue Umgebungsvariable hinzu](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`,</span><span class="sxs-lookup"><span data-stu-id="0510e-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="0510e-131">z. B. \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span><span class="sxs-lookup"><span data-stu-id="0510e-131">For example, \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\
       ```

     - <span data-ttu-id="0510e-132">Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Spark hinzu.</span><span class="sxs-lookup"><span data-stu-id="0510e-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0510e-133">Zum Beispiel *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*</span><span class="sxs-lookup"><span data-stu-id="0510e-133">For example, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span></span>

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - <span data-ttu-id="0510e-134">Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0510e-134">Verify you are able to run `spark-shell` from your command-line.</span></span>
        <span data-ttu-id="0510e-135">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="0510e-135">Sample console output:</span></span>

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

  6. <span data-ttu-id="0510e-136">Installieren Sie **[WinUtils](https://github.com/steveloughran/winutils)** .</span><span class="sxs-lookup"><span data-stu-id="0510e-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="0510e-137">Laden Sie die Binärdatei `winutils.exe` aus dem [WinUtils-Repository](https://github.com/steveloughran/winutils) herunter.</span><span class="sxs-lookup"><span data-stu-id="0510e-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="0510e-138">Sie sollten die Hadoop-Version auswählen, mit der die Spark-Distribution kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="0510e-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="0510e-139">Für Spark 2.3.2 verwenden Sie beispielsweise hadoop-2.7.1.</span><span class="sxs-lookup"><span data-stu-id="0510e-139">For exammple, use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="0510e-140">Speichern Sie die Binärdatei `winutils.exe` in einem Verzeichnis Ihrer Wahl,</span><span class="sxs-lookup"><span data-stu-id="0510e-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="0510e-141">z. B. *C:\hadoop\bin*.</span><span class="sxs-lookup"><span data-stu-id="0510e-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="0510e-142">Legen Sie `HADOOP_HOME` auf das Verzeichnis fest, in dem sich „winutils.exe“ befindet, und lassen Sie „bin“ weg.</span><span class="sxs-lookup"><span data-stu-id="0510e-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="0510e-143">Beispiel für die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="0510e-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="0510e-144">Fügen Sie der PATH-Umgebungsvariable `%HADOOP_HOME%\bin` hinzu.</span><span class="sxs-lookup"><span data-stu-id="0510e-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="0510e-145">Beispiel für die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="0510e-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="0510e-146">Stellen Sie sicher, dass Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0510e-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="0510e-147">Sind Sie der Meinung, dass es eine bessere Möglichkeit gibt?</span><span class="sxs-lookup"><span data-stu-id="0510e-147">Feel there is a better way?</span></span> <span data-ttu-id="0510e-148">Dann [eröffnen Sie ein Issue](https://github.com/dotnet/spark/issues), und teilen Sie uns diese mit.</span><span class="sxs-lookup"><span data-stu-id="0510e-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="0510e-149">Möglicherweise ist eine neue Instanz der Befehlszeile erforderlich, wenn Umgebungsvariablen aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0510e-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="0510e-150">Build</span><span class="sxs-lookup"><span data-stu-id="0510e-150">Build</span></span>

<span data-ttu-id="0510e-151">Für den Rest des vorliegenden Leitfadens müssen Sie das .NET für Apache Spark-Repository auf Ihren Computer geklont haben.</span><span class="sxs-lookup"><span data-stu-id="0510e-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="0510e-152">Sie können einen beliebigen Speicherort für das geklonte Repository auswählen,</span><span class="sxs-lookup"><span data-stu-id="0510e-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="0510e-153">z. B. \*C:\github\dotnet-spark\*.</span><span class="sxs-lookup"><span data-stu-id="0510e-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="0510e-154">Erstellen der Scala-Erweiterungsebene für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="0510e-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="0510e-155">Wenn Sie eine .NET-Anwendung übermitteln, bietet .NET für Apache Spark die erforderliche, in Scala geschriebene Logik, die Apache Spark darüber informiert, wie Ihre Anforderungen verarbeitet werden sollen (z. B. Anforderungen zum Erstellen einer neuen Spark-Sitzung, zum Übertragen von Daten von .NET an JVM usw.).</span><span class="sxs-lookup"><span data-stu-id="0510e-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="0510e-156">Diese Logik finden Sie im [.NET für Spark-Scala-Quellcode](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="0510e-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="0510e-157">Unabhängig davon, ob Sie .NET Framework oder .NET Core verwenden, müssen Sie die Scala-Erweiterungsebene für .NET für Apache Spark erstellen:</span><span class="sxs-lookup"><span data-stu-id="0510e-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package
```

<span data-ttu-id="0510e-158">Sie werden feststellen, dass JAR-Dateien für die unterstützten Spark-Versionen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="0510e-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="0510e-159">Erstellen der .NET für Spark-Beispielanwendungen</span><span class="sxs-lookup"><span data-stu-id="0510e-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="0510e-160">In diesem Abschnitt wird erläutert, wie Sie die [Beispielanwendungen](https://github.com/dotnet/spark/tree/master/examples) für .NET für Apache Spark erstellen.</span><span class="sxs-lookup"><span data-stu-id="0510e-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="0510e-161">Diese Schritte tragen zu einem besseren Verständnis des gesamten Erstellungsprozesses für alle .NET für Spark-Anwendungen bei.</span><span class="sxs-lookup"><span data-stu-id="0510e-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="0510e-162">Verwenden von Visual Studio für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0510e-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="0510e-163">Öffnen Sie `src\csharp\Microsoft.Spark.sln` in Visual Studio, und erstellen Sie das `Microsoft.Spark.CSharp.Examples`-Projekt im Ordner `examples` (damit wird auch das Projekt für die .NET-Bindungen erstellt).</span><span class="sxs-lookup"><span data-stu-id="0510e-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="0510e-164">Wenn Sie möchten, können Sie im `Microsoft.Spark.Examples`-Projekt auch selbst Code schreiben („input_file.json“ in diesem Beispiel ist eine JSON-Datei mit den Daten, mit denen Sie den Datenrahmen erstellen möchten):</span><span class="sxs-lookup"><span data-stu-id="0510e-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
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

     <span data-ttu-id="0510e-165">Sobald der Buildvorgang erfolgreich abgeschlossen wurde, sehen Sie, dass die entsprechenden Binärdateien im Ausgabeverzeichnis erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0510e-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>
     <span data-ttu-id="0510e-166">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="0510e-166">Sample console output:</span></span>

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

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="0510e-167">Verwenden der .NET Core-CLI für .NET Core</span><span class="sxs-lookup"><span data-stu-id="0510e-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="0510e-168">Wir arbeiten derzeit daran, die .NET Core-Builds für Spark. NET zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="0510e-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="0510e-169">Bis es soweit ist, müssen Sie leider noch einige Schritte manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="0510e-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="0510e-170">Erstellen des Workers:</span><span class="sxs-lookup"><span data-stu-id="0510e-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="0510e-171">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="0510e-171">Sample console output:</span></span>

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

  2. <span data-ttu-id="0510e-172">Kompilieren der Beispiele:</span><span class="sxs-lookup"><span data-stu-id="0510e-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      <span data-ttu-id="0510e-173">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="0510e-173">Sample console output:</span></span>

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

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="0510e-174">Ausführen der .NET für Spark-Beispielanwendungen</span><span class="sxs-lookup"><span data-stu-id="0510e-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="0510e-175">Nach dem Erstellen der Beispiele erfolgt deren Ausführung über `spark-submit` – unabhängig davon, ob .NET Framework oder .NET Core als Ziel dient.</span><span class="sxs-lookup"><span data-stu-id="0510e-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="0510e-176">Stellen Sie sicher, dass alle [Voraussetzungen](#prerequisites) erfüllt sind und Apache Spark installiert ist.</span><span class="sxs-lookup"><span data-stu-id="0510e-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="0510e-177">Legen Sie die Umgebungsvariable `DOTNET_WORKER_DIR` oder `PATH` fest, um den Pfad einzufügen, in dem die Binärdatei `Microsoft.Spark.Worker` erstellt wurde (z. B. *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* für .NET Framework oder *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* für .NET Core):</span><span class="sxs-lookup"><span data-stu-id="0510e-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="0510e-178">Öffnen Sie PowerShell, und navigieren Sie zum Verzeichnis, in dem die Binärdatei für Ihre App erstellt wurde (z. B. *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* für .NET Framework oder *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* für .NET Core):</span><span class="sxs-lookup"><span data-stu-id="0510e-178">Open Powershell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="0510e-179">Die Ausführung Ihrer App folgt dieser grundlegenden Struktur:</span><span class="sxs-lookup"><span data-stu-id="0510e-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="0510e-180">Hier einige Beispiele, die Sie ausführen können:</span><span class="sxs-lookup"><span data-stu-id="0510e-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="0510e-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="0510e-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="0510e-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="0510e-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="0510e-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="0510e-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="0510e-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="0510e-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
