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
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a>Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Ubuntu erstellen.

Dieser Artikel erläutert, wie Sie .NET für Apache Spark-Anwendungen unter Ubuntu erstellen.

## <a name="prerequisites"></a>Voraussetzungen

Wenn bereits alle folgenden Voraussetzungen erfüllt sind, fahren Sie mit den Schritten zum [Erstellen](#build) fort.

1. Laden Sie das **[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** oder das **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** herunter, und installieren Sie es. Durch die Installation des SDK wird die Toolkette `dotnet` zum Pfad hinzugefügt.  Die .NET Core-Versionen 2.1, 2.2 und 3.1 werden unterstützt.

2. Installieren Sie **[OpenJDK 8](https://openjdk.java.net/install/)** .

   - Sie können den folgenden Befehl verwenden:

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * Überprüfen Sie, ob Sie `java` über die Befehlszeile ausführen können.

      Beispielausgabe für die Java-Version:

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * Wenn Sie bereits mehrere OpenJDK-Versionen installiert haben und OpenJDK 8 auswählen möchten, verwenden Sie folgenden Befehl:

      ```bash
      sudo update-alternatives --config java
      ```

3. Installieren Sie **[Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi)** .

   * Führen Sie den folgenden Befehl aus:

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

       Beachten Sie, dass diese Umgebungsvariablen beim Schließen des Terminals nicht gespeichert werden. Wenn Sie die Änderungen dauerhaft speichern möchten, fügen Sie `export`-Zeilen zu Ihrer `~/.bashrc`-Datei hinzu.

   * Überprüfen Sie, ob Sie `mvn` über die Befehlszeile ausführen können.

       Beispielausgabe für die MVN-Version:

       ```
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. Installieren Sie **[Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html)** .
Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei in einen lokalen Ordner (z. B. `~/bin/spark-2.3.2-bin-hadoop2.7`). (Unterstützt werden die Spark-Versionen 2.3.*, 2.4.0, 2.4.1, 2.4.3 und 2.4.4.)

   ```bash
   tar -xvzf /path/to/spark-2.3.2-bin-hadoop2.7.tgz -C ~/bin/spark-2.3.2-bin-hadoop2.7
   ```

   * Fügen Sie die erforderlichen [Umgebungsvariablen](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (z. B. `~/bin/spark-2.3.2-bin-hadoop2.7/`) und `PATH` (z. B. `$SPARK_HOME/bin:$PATH`) hinzu.

      ```bash
      export SPARK_HOME=~/bin/spark-2.3.2-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      Beachten Sie, dass diese Umgebungsvariablen beim Schließen des Terminals nicht gespeichert werden. Wenn Sie die Änderungen dauerhaft speichern möchten, fügen Sie `export`-Zeilen zu Ihrer `~/.bashrc`-Datei hinzu.

   * Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.

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

Stellen Sie sicher, dass Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren. Sind Sie der Meinung, dass es eine bessere Möglichkeit gibt? Dann eröffnen Sie ein [Issue](https://github.com/dotnet/spark/issues), und teilen Sie uns diese mit.

## <a name="build"></a>Build

Für den Rest des vorliegenden Leitfadens müssen Sie das .NET für Apache Spark-Repository auf Ihren Computer geklont haben (Beispiel: `~/dotnet.spark/`).

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a>Erstellen der Scala-Erweiterungsebene für .NET für Spark

Wenn Sie eine .NET-Anwendung übermitteln, bietet .NET für Apache Spark die erforderliche, in Scala geschriebene Logik, die Apache Spark darüber informiert, wie Ihre Anforderungen verarbeitet werden sollen (z. B. Anforderungen zum Erstellen einer neuen Spark-Sitzung, zum Übertragen von Daten von .NET an JVM usw.). Diese Logik finden Sie im [.NET für Apache Spark-Scala-Quellcode](https://github.com/dotnet/spark/tree/master/src/scala).

Der nächste Schritt besteht darin, die Erweiterungsebene für .NET für Apache Spark Scala zu erstellen:

```bash
cd src/scala
mvn clean package
```

Sie werden feststellen, dass JAR-Dateien für die unterstützten Spark-Versionen erstellt werden:

* `microsoft-spark-2.3.x/target/microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x/target/microsoft-spark-2.4.x-<version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a>Erstellen von .NET-Beispielanwendungen mit der .NET Core-CLI

In diesem Abschnitt wird erläutert, wie Sie die [Beispielanwendungen](https://github.com/dotnet/spark/tree/master/examples) für .NET für Apache Spark erstellen. Diese Schritte tragen zu einem besseren Verständnis des gesamten Erstellungsprozesses für alle .NET für Spark-Anwendungen bei.

1. Erstellen des Workers:

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   Beispiel für Konsolenausgabe:

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

2. Kompilieren der Beispiele:

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```

   Beispiel für Konsolenausgabe:

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

## <a name="run-the-net-for-spark-sample-applications"></a>Ausführen der .NET für Spark-Beispielanwendungen

Nachdem Sie die Beispiele erstellt haben, können Sie `spark-submit` verwenden, um Ihre .NET Core-Apps zu übermitteln. Stellen Sie sicher, dass alle [Voraussetzungen](#prerequisites) erfüllt sind und Apache Spark installiert ist.

1. Fügen Sie der Umgebungsvariable `DOTNET_WORKER_DIR` oder `PATH` den Pfad hinzu, in dem die `Microsoft.Spark.Worker`-Binärdatei generiert wurde (z. B. `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

2. Öffnen Sie ein Terminal, und wechseln Sie zu dem Verzeichnis, in dem die Binärdatei Ihrer App generiert wurde (z. B. `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`).

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

3. Die Ausführung Ihrer App folgt dieser grundlegenden Struktur:

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   Hier einige Beispiele, die Sie ausführen können:

   * **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (zugänglich über Maven)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```
