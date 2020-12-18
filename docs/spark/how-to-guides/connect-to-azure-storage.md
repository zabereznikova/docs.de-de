---
title: Herstellen einer Verbindung mit Remotespeicher über Ihren lokalen Computer
description: Stellen Sie mithilfe von .NET für Apache Spark eine Verbindung mit Azure Storage-Konten über Ihren lokalen Computer her.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dc0c3b44279756596f3d456616821e690710ae04
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224010"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a>Herstellen einer Verbindung mit einem Azure Data Lake Storage Gen2- oder WASB-Konto

In diesem Artikel erfahren Sie, wie Sie eine Verbindung mit einem ADLS Gen2- (Azure Data Lake Storage Gen2) oder WASB-Konto (Azure Storage Blob) über eine Instanz von [.NET für Apache Spark](https://github.com/dotnet/spark) herstellen, die lokal auf Ihrem Windows-Computer ausgeführt wird.

## <a name="set-up-the-environment"></a>Einrichten der Umgebung

1. Laden Sie die Apache Spark-Distribution ohne Hadoop von der [offiziellen Website](https://archive.apache.org/dist/spark/) herunter (wählen Sie eine Version aus, die [von .NET für Apache Spark unterstützt wird](https://github.com/dotnet/spark#supported-apache-spark)), und extrahieren Sie sie in ein Verzeichnis. Legen Sie die Umgebungsvariable `SPARK_HOME` auf dieses Verzeichnis fest.
2. Laden Sie die Apache Hadoop-Binärdatei [hier](http://hadoop.apache.org/releases.html) herunter, extrahieren Sie sie in einen Ordner, und legen Sie die Umgebungsvariable `HADOOP_HOME` auf diesen Ordner fest.
3. Laden Sie die Dateien `winutils.exe` und `hadoop.dll` von [diesem Speicherort](https://github.com/cdarlint/winutils) herunter (abhängig von der Hadoop-Version, die Sie im vorherigen Schritt installiert haben), und fügen Sie diese in den bin-Ordner Ihrer Hadoop-Instanz ein. Diese Binärdateien werden unter Windows benötigt, um alles ordnungsgemäß einzurichten (dies wird im [Apache-Wiki](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems) ausführlich erläutert).
4. Konfigurieren Sie Ihre Hadoop-Installation, indem Sie die folgenden Änderungen an Ihrer `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`-Datei vornehmen:
    1. Legen Sie die `JAVA_HOME`-Eigenschaft mithilfe des DOS-Pfads fest (da Hadoop keine Leerzeichen in `JAVA_HOME` akzeptiert). Dies sollte in etwa wie folgt aussehen: `C:\Progra~1\Java\jdk1.8.0_241` (Verweist auf die jeweilige auf Ihrem lokalen Computer installierte Version von Java).
    2. Fügen Sie `%HADOOP_HOME%\share\hadoop\tools\lib\*` an `HADOOP_CLASSPATH` an.
    Ihre endgültige `hadoop-env.cmd`-Datei sollte in etwa wie folgt aussehen:

    ![Finale Datei „hadoop-env.cmd“](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a>Konfigurieren Ihres Speicherkontos in Hadoop

1. Öffnen Sie das ADLS Gen2- oder WASB-Speicherkonto, mit dem Sie eine Verbindung über das [Azure-Portal](https://portal.azure.com) herstellen möchten, öffnen Sie das Panel **Zugriffsschlüssel** auf dem Blatt **Einstellungen**, und kopieren Sie den Wert von **Key** (Schlüssel) unter key1.
2. Zum Konfigurieren des Zugriffs auf Ihr ADLS Gen2-Konto für Hadoop müssen Sie die unter `%HADOOP_HOME%\etc\hadoop\` gespeicherte Datei „`core-site.xml`“ bearbeiten, die eine clusterweite Konfiguration enthält. Fügen Sie die folgenden Eigenschaften innerhalb der `<configuration>`-Tags in dieser Datei ein:

    ```xml
    <configuration>
      <property>
        <name>fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>SharedKey</value>
        <description></description>
      </property>
      <property>
        <name>fs.azure.account.key.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>YOUR ACCESS KEY (copied from Step 1)</value>
        <description>The secret password. Never share these.</description>
      </property>
    </configuration>
    ```

    Wenn Sie versuchen, eine Verbindung mit einem WASB-Konto herzustellen, ersetzen Sie `dfs` in den Eigenschaftennamen durch `blob`. Beispiel: `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.
3. Sie können die Konnektivität Ihres Speicherkontos über Hadoop testen, indem Sie den folgenden Befehl in Ihrem `%HADOOP_HOME%`-Verzeichnis ausführen:

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

Dadurch sollte eine Liste aller Dateien/Ordner im Pfad angezeigt werden, der von Ihrem URI bereitgestellt wird.

> [!NOTE]
> Das Format zum Ableiten des URI für Ihr Speicherkonto lautet wie folgt:
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a>Herstellen einer Verbindung mit Ihrem Speicherkonto

1. Wenn der obige Befehl funktioniert hat, können Sie nun über Spark auf das Speicherkonto zugreifen. Führen Sie zuerst den Befehl `hadoop classpath` über die Befehlszeile in `%HADOOP_HOME%` aus, und kopieren Sie die Ausgabe.
2. Legen Sie die Ausgabe des in Schritt 1 ausgeführten Befehls auf den Wert der Umgebungsvariable `SPARK_DIST_CLASSPATH` fest.
3. Sie sollten nun dazu in der Lage sein, wie im folgenden Beispiel gezeigt mithilfe des abfs-URIs über Spark .NET auf Ihr ADLS- oder WASB-Speicherkonto zuzugreifen. (In diesem Beispiel wird die Standardbeispieldatei [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) verwendet, die in jeder Installation von Apache Spark enthalten ist.)

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    Das Ergebnis wird wie im folgenden DataFrame (`df`) angezeigt:

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
