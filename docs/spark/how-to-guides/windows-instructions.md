---
title: Erstellen einer .NET für Apache Spark-Anwendung unter Windows
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows erstellen.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: cb7154185fc9aa08bc447cb846798995301a6651
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185756"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a>Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows erstellen.

Dieser Artikel erläutert, wie Sie .NET für Apache Spark-Anwendungen unter Windows erstellen.

## <a name="prerequisites"></a>Voraussetzungen

Wenn bereits alle folgenden Voraussetzungen erfüllt sind, fahren Sie mit den Schritten zum [Erstellen](#build) fort.

  1. Laden Sie das **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** herunter, und installieren Sie es. Durch die Installation des SDK wird die Toolkette `dotnet` zum Pfad hinzugefügt. Die .NET Core-Versionen 2.1, 2.2 und 3.1 werden unterstützt.
  2. Installieren Sie **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 oder höher). Die Community-Version ist vollkommen kostenlos. Schließen Sie beim Konfigurieren Ihrer Installation mindestens die folgenden Komponenten ein:
     * .NET-Desktopentwicklung
       * Alle erforderlichen Komponenten
         * .NET Framework 4.6.1-Entwicklungstools
     * Plattformübergreifende .NET Core-Entwicklung
       * Alle erforderlichen Komponenten
  3. Installieren Sie **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** .
     - Wählen Sie die für Ihr Betriebssystem geeignete Version aus. Zum Beispiel *jdk-8u201-windows-x64.exe* für Windows x64-Computer.
     - Führen Sie die Installation mithilfe des Installationsprogramms aus, und überprüfen Sie, ob Sie `java` über die Befehlszeile ausführen können.
  4. Installieren Sie **[Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi)** .
     - Laden Sie [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip) herunter.
     - Extrahieren Sie die Datei in ein lokales Verzeichnis. Zum Beispiel *C:\bin\apache-maven-3.6.0\*
     - Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Maven hinzu. Zum Beispiel *C:\bin\apache-maven-3.6.0\bin*
     - Überprüfen Sie, ob Sie `mvn` über die Befehlszeile ausführen können.
  5. Installieren Sie **[Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html)** .
     - Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei mit [7-zip](https://www.7-zip.org/) in einen lokalen Ordner (zum Beispiel *C:\bin\spark-2.3.2-bin-hadoop2.7\*). (Die folgenden Spark-Versionen werden unterstützt: 2.3.* , 2.4.0, 2.4.1, 2.4.3 and 2.4.4)
     - Fügen Sie eine [neue Umgebungsvariable hinzu](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`, z. B. *C:\bin\spark-2.3.2-bin-hadoop2.7\*.

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\
       ```

     - Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Spark hinzu. Zum Beispiel *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.
        Beispiel für Konsolenausgabe:

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

  6. Installieren Sie **[WinUtils](https://github.com/steveloughran/winutils)** .
     - Laden Sie die Binärdatei `winutils.exe` aus dem [WinUtils-Repository](https://github.com/steveloughran/winutils) herunter. Sie sollten die Hadoop-Version auswählen, mit der die Spark-Distribution kompiliert wurde. Für Spark 2.3.2 verwenden Sie beispielsweise hadoop-2.7.1.
     - Speichern Sie die Binärdatei `winutils.exe` in einem Verzeichnis Ihrer Wahl, z. B. *C:\hadoop\bin*.
     - Legen Sie `HADOOP_HOME` auf das Verzeichnis fest, in dem sich „winutils.exe“ befindet, und lassen Sie „bin“ weg. Beispiel für die Befehlszeile:

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - Fügen Sie der PATH-Umgebungsvariable `%HADOOP_HOME%\bin` hinzu. Beispiel für die Befehlszeile:

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

Stellen Sie sicher, dass Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren. Sind Sie der Meinung, dass es eine bessere Möglichkeit gibt? Dann [eröffnen Sie ein Issue](https://github.com/dotnet/spark/issues), und teilen Sie uns diese mit.

> [!NOTE]
> Möglicherweise ist eine neue Instanz der Befehlszeile erforderlich, wenn Umgebungsvariablen aktualisiert wurden.

## <a name="build"></a>Build

Für den Rest des vorliegenden Leitfadens müssen Sie das .NET für Apache Spark-Repository auf Ihren Computer geklont haben. Sie können einen beliebigen Speicherort für das geklonte Repository auswählen, z. B. *C:\github\dotnet-spark\*.

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a>Erstellen der Scala-Erweiterungsebene für .NET für Apache Spark

Wenn Sie eine .NET-Anwendung übermitteln, bietet .NET für Apache Spark die erforderliche, in Scala geschriebene Logik, die Apache Spark darüber informiert, wie Ihre Anforderungen verarbeitet werden sollen (z. B. Anforderungen zum Erstellen einer neuen Spark-Sitzung, zum Übertragen von Daten von .NET an JVM usw.). Diese Logik finden Sie im [.NET für Spark-Scala-Quellcode](https://github.com/dotnet/spark/tree/master/src/scala).

Unabhängig davon, ob Sie .NET Framework oder .NET Core verwenden, müssen Sie die Scala-Erweiterungsebene für .NET für Apache Spark erstellen:

```powershell
cd src\scala
mvn clean package
```

Sie werden feststellen, dass JAR-Dateien für die unterstützten Spark-Versionen erstellt werden:

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a>Erstellen der .NET für Spark-Beispielanwendungen

In diesem Abschnitt wird erläutert, wie Sie die [Beispielanwendungen](https://github.com/dotnet/spark/tree/master/examples) für .NET für Apache Spark erstellen. Diese Schritte tragen zu einem besseren Verständnis des gesamten Erstellungsprozesses für alle .NET für Spark-Anwendungen bei.

#### <a name="using-visual-studio-for-net-framework"></a>Verwenden von Visual Studio für .NET Framework

  1. Öffnen Sie `src\csharp\Microsoft.Spark.sln` in Visual Studio, und erstellen Sie das `Microsoft.Spark.CSharp.Examples`-Projekt im Ordner `examples` (damit wird auch das Projekt für die .NET-Bindungen erstellt). Wenn Sie möchten, können Sie im `Microsoft.Spark.Examples`-Projekt auch selbst Code schreiben („input_file.json“ in diesem Beispiel ist eine JSON-Datei mit den Daten, mit denen Sie den Datenrahmen erstellen möchten):
  
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

     Sobald der Buildvorgang erfolgreich abgeschlossen wurde, sehen Sie, dass die entsprechenden Binärdateien im Ausgabeverzeichnis erstellt wurden.
     Beispiel für Konsolenausgabe:

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

#### <a name="using-net-core-cli-for-net-core"></a>Verwenden der .NET Core-CLI für .NET Core

> [!NOTE]
> Wir arbeiten derzeit daran, die .NET Core-Builds für Spark. NET zu automatisieren. Bis es soweit ist, müssen Sie leider noch einige Schritte manuell ausführen.

  1. Erstellen des Workers:

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      Beispiel für Konsolenausgabe:

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

  2. Kompilieren der Beispiele:

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      Beispiel für Konsolenausgabe:

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

## <a name="run-the-net-for-spark-sample-applications"></a>Ausführen der .NET für Spark-Beispielanwendungen

Nach dem Erstellen der Beispiele erfolgt deren Ausführung über `spark-submit` – unabhängig davon, ob .NET Framework oder .NET Core als Ziel dient. Stellen Sie sicher, dass alle [Voraussetzungen](#prerequisites) erfüllt sind und Apache Spark installiert ist.

  1. Legen Sie die Umgebungsvariable `DOTNET_WORKER_DIR` oder `PATH` fest, um den Pfad einzufügen, in dem die Binärdatei `Microsoft.Spark.Worker` erstellt wurde (z. B. *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* für .NET Framework oder *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* für .NET Core):

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. Öffnen Sie PowerShell, und navigieren Sie zum Verzeichnis, in dem die Binärdatei für Ihre App erstellt wurde (z. B. *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* für .NET Framework oder *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* für .NET Core):

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. Die Ausführung Ihrer App folgt dieser grundlegenden Struktur:

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     Hier einige Beispiele, die Sie ausführen können:

     - **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
