---
title: Erstellen einer .NET für Apache Spark-Anwendung unter Ubuntu
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Ubuntu erstellen.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 6dd6f60bb89a51c47fe17182fc47de818cd00b80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187573"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a><span data-ttu-id="f8878-103">Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Ubuntu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8878-103">Learn how to build your .NET for Apache Spark application on Ubuntu</span></span>

<span data-ttu-id="f8878-104">Dieser Artikel erläutert, wie Sie .NET für Apache Spark-Anwendungen unter Ubuntu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8878-104">This article teaches you how to build your .NET for Apache Spark applications on Ubuntu.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8878-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f8878-105">Prerequisites</span></span>

<span data-ttu-id="f8878-106">Wenn bereits alle folgenden Voraussetzungen erfüllt sind, fahren Sie mit den Schritten zum [Erstellen](#build) fort.</span><span class="sxs-lookup"><span data-stu-id="f8878-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

1. <span data-ttu-id="f8878-107">Laden Sie das **[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** oder das **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** herunter, und installieren Sie es. Durch die Installation des SDK wird die Toolkette `dotnet` zum Pfad hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f8878-107">Download and install **[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** or the **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** - installing the SDK adds the `dotnet` toolchain to your path.</span></span>  <span data-ttu-id="f8878-108">Die .NET Core-Versionen 2.1, 2.2 und 3.1 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f8878-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>

2. <span data-ttu-id="f8878-109">Installieren Sie **[OpenJDK 8](https://openjdk.java.net/install/)** .</span><span class="sxs-lookup"><span data-stu-id="f8878-109">Install **[OpenJDK 8](https://openjdk.java.net/install/)**.</span></span>

   - <span data-ttu-id="f8878-110">Sie können den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="f8878-110">You can use the following command:</span></span>

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * <span data-ttu-id="f8878-111">Überprüfen Sie, ob Sie `java` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f8878-111">Verify you are able to run `java` from your command-line.</span></span>

      <span data-ttu-id="f8878-112">Beispielausgabe für die Java-Version:</span><span class="sxs-lookup"><span data-stu-id="f8878-112">Sample java -version output:</span></span>

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * <span data-ttu-id="f8878-113">Wenn Sie bereits mehrere OpenJDK-Versionen installiert haben und OpenJDK 8 auswählen möchten, verwenden Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f8878-113">If you already have multiple OpenJDK versions installed and want to select OpenJDK 8, use the following command:</span></span>

      ```bash
      sudo update-alternatives --config java
      ```

3. <span data-ttu-id="f8878-114">Installieren Sie **[Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi)** .</span><span class="sxs-lookup"><span data-stu-id="f8878-114">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>

   * <span data-ttu-id="f8878-115">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f8878-115">Run the following command:</span></span>

      ```bash
      mkdir -p ~/bin/maven
      cd ~/bin/maven
      wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
      tar -xvzf apache-maven-3.6.0-bin.tar.gz
      ln -s apache-maven-3.6.0 current
      export M2_HOME=~/bin/maven/current
      export PATH=${M2_HOME}/bin:${PATH}
      source ~/.bashrc
      ```

       <span data-ttu-id="f8878-116">Beachten Sie, dass diese Umgebungsvariablen beim Schließen des Terminals nicht gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f8878-116">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="f8878-117">Wenn Sie die Änderungen dauerhaft speichern möchten, fügen Sie `export`-Zeilen zu Ihrer `~/.bashrc`-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8878-117">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="f8878-118">Überprüfen Sie, ob Sie `mvn` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f8878-118">Verify you are able to run `mvn` from your command-line</span></span>

       <span data-ttu-id="f8878-119">Beispielausgabe für die MVN-Version:</span><span class="sxs-lookup"><span data-stu-id="f8878-119">Sample mvn -version output:</span></span>

       ```
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. <span data-ttu-id="f8878-120">Installieren Sie **[Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html)** .</span><span class="sxs-lookup"><span data-stu-id="f8878-120">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
<span data-ttu-id="f8878-121">Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei in einen lokalen Ordner (z. B. `~/bin/spark-2.3.2-bin-hadoop2.7`).</span><span class="sxs-lookup"><span data-stu-id="f8878-121">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (e.g., `~/bin/spark-2.3.2-bin-hadoop2.7`).</span></span> <span data-ttu-id="f8878-122">(Unterstützt werden die Spark-Versionen 2.3.\*, 2.4.0, 2.4.1, 2.4.3 und 2.4.4.)</span><span class="sxs-lookup"><span data-stu-id="f8878-122">(The supported spark versions are 2.3.\*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>

   ```bash
   tar -xvzf /path/to/spark-2.3.2-bin-hadoop2.7.tgz -C ~/bin/spark-2.3.2-bin-hadoop2.7
   ```

   * <span data-ttu-id="f8878-123">Fügen Sie die erforderlichen [Umgebungsvariablen](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (z. B. `~/bin/spark-2.3.2-bin-hadoop2.7/`) und `PATH` (z. B. `$SPARK_HOME/bin:$PATH`) hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8878-123">Add the necessary [environment variables](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (e.g., `~/bin/spark-2.3.2-bin-hadoop2.7/`) and `PATH` (e.g., `$SPARK_HOME/bin:$PATH`)</span></span>

      ```bash
      export SPARK_HOME=~/bin/spark-2.3.2-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      <span data-ttu-id="f8878-124">Beachten Sie, dass diese Umgebungsvariablen beim Schließen des Terminals nicht gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="f8878-124">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="f8878-125">Wenn Sie die Änderungen dauerhaft speichern möchten, fügen Sie `export`-Zeilen zu Ihrer `~/.bashrc`-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8878-125">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="f8878-126">Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f8878-126">Verify you are able to run `spark-shell` from your command-line.</span></span>

      <span data-ttu-id="f8878-127">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="f8878-127">Sample console output:</span></span>

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

<span data-ttu-id="f8878-128">Stellen Sie sicher, dass Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f8878-128">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command-line before you move to the next section.</span></span> <span data-ttu-id="f8878-129">Sind Sie der Meinung, dass es eine bessere Möglichkeit gibt?</span><span class="sxs-lookup"><span data-stu-id="f8878-129">Feel there is a better way?</span></span> <span data-ttu-id="f8878-130">Dann eröffnen Sie ein [Issue](https://github.com/dotnet/spark/issues), und teilen Sie uns diese mit.</span><span class="sxs-lookup"><span data-stu-id="f8878-130">Please [open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

## <a name="build"></a><span data-ttu-id="f8878-131">Build</span><span class="sxs-lookup"><span data-stu-id="f8878-131">Build</span></span>

<span data-ttu-id="f8878-132">Für den Rest des vorliegenden Leitfadens müssen Sie das .NET für Apache Spark-Repository auf Ihren Computer geklont haben (Beispiel: `~/dotnet.spark/`).</span><span class="sxs-lookup"><span data-stu-id="f8878-132">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine e.g., `~/dotnet.spark/`.</span></span>

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a><span data-ttu-id="f8878-133">Erstellen der Scala-Erweiterungsebene für .NET für Spark</span><span class="sxs-lookup"><span data-stu-id="f8878-133">Build .NET for Spark Scala extensions layer</span></span>

<span data-ttu-id="f8878-134">Wenn Sie eine .NET-Anwendung übermitteln, bietet .NET für Apache Spark die erforderliche, in Scala geschriebene Logik, die Apache Spark darüber informiert, wie Ihre Anforderungen verarbeitet werden sollen (z. B. Anforderungen zum Erstellen einer neuen Spark-Sitzung, zum Übertragen von Daten von .NET an JVM usw.).</span><span class="sxs-lookup"><span data-stu-id="f8878-134">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (e.g., request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="f8878-135">Diese Logik finden Sie im [.NET für Apache Spark-Scala-Quellcode](https://github.com/dotnet/spark/tree/master/src/scala).</span><span class="sxs-lookup"><span data-stu-id="f8878-135">This logic can be found in the [.NET for Apache Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="f8878-136">Der nächste Schritt besteht darin, die Erweiterungsebene für .NET für Apache Spark Scala zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="f8878-136">The next step is to build the .NET for Apache Spark Scala extension layer:</span></span>

```bash
cd src/scala
mvn clean package
```

<span data-ttu-id="f8878-137">Sie werden feststellen, dass JAR-Dateien für die unterstützten Spark-Versionen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="f8878-137">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x/target/microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x/target/microsoft-spark-2.4.x-<version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a><span data-ttu-id="f8878-138">Erstellen von .NET-Beispielanwendungen mit der .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="f8878-138">Build .NET sample applications using .NET Core CLI</span></span>

<span data-ttu-id="f8878-139">In diesem Abschnitt wird erläutert, wie Sie die [Beispielanwendungen](https://github.com/dotnet/spark/tree/master/examples) für .NET für Apache Spark erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8878-139">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="f8878-140">Diese Schritte tragen zu einem besseren Verständnis des gesamten Erstellungsprozesses für alle .NET für Spark-Anwendungen bei.</span><span class="sxs-lookup"><span data-stu-id="f8878-140">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

1. <span data-ttu-id="f8878-141">Erstellen des Workers:</span><span class="sxs-lookup"><span data-stu-id="f8878-141">Build the worker:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   <span data-ttu-id="f8878-142">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="f8878-142">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker$ dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 36.03 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker/Microsoft.Spark.Worker.csproj.
      Restore completed in 35.94 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.0/Microsoft.Spark.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/Microsoft.Spark.Worker.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish/
   ```

2. <span data-ttu-id="f8878-143">Kompilieren der Beispiele:</span><span class="sxs-lookup"><span data-stu-id="f8878-143">Build the samples:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   <span data-ttu-id="f8878-144">Beispiel für Konsolenausgabe:</span><span class="sxs-lookup"><span data-stu-id="f8878-144">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples$ dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 37.11 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Restore completed in 281.63 ms for /home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/Microsoft.Spark.CSharp.Examples.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.0/Microsoft.Spark.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/Microsoft.Spark.CSharp.Examples.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish/
   ```  

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="f8878-145">Ausführen der .NET für Spark-Beispielanwendungen</span><span class="sxs-lookup"><span data-stu-id="f8878-145">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="f8878-146">Nachdem Sie die Beispiele erstellt haben, können Sie `spark-submit` verwenden, um Ihre .NET Core-Apps zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="f8878-146">Once you build the samples, you can use `spark-submit` to submit your .NET Core apps.</span></span> <span data-ttu-id="f8878-147">Stellen Sie sicher, dass alle [Voraussetzungen](#prerequisites) erfüllt sind und Apache Spark installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f8878-147">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

1. <span data-ttu-id="f8878-148">Fügen Sie der Umgebungsvariable `DOTNET_WORKER_DIR` oder `PATH` den Pfad hinzu, in dem die `Microsoft.Spark.Worker`-Binärdatei generiert wurde (z. B. `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span><span class="sxs-lookup"><span data-stu-id="f8878-148">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

2. <span data-ttu-id="f8878-149">Öffnen Sie ein Terminal, und wechseln Sie zu dem Verzeichnis, in dem die Binärdatei Ihrer App generiert wurde (z. B. `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span><span class="sxs-lookup"><span data-stu-id="f8878-149">Open a terminal and go to the directory where your app binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

3. <span data-ttu-id="f8878-150">Die Ausführung Ihrer App folgt dieser grundlegenden Struktur:</span><span class="sxs-lookup"><span data-stu-id="f8878-150">Running your app follows the basic structure:</span></span>

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   <span data-ttu-id="f8878-151">Hier einige Beispiele, die Sie ausführen können:</span><span class="sxs-lookup"><span data-stu-id="f8878-151">Here are some examples you can run:</span></span>

   * <span data-ttu-id="f8878-152">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="f8878-152">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * <span data-ttu-id="f8878-153">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="f8878-153">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * <span data-ttu-id="f8878-154">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="f8878-154">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * <span data-ttu-id="f8878-155">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="f8878-155">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```
