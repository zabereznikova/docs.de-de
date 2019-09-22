---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in HDInsight bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2e8da5497035a83fde75bf91a7d21437d510b480
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117980"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight

In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Azure HDInsight bereitstellen.

In diesem Tutorial lernen Sie Folgendes:

> [!div class="checklist"]
>
> * Vorbereiten von Microsoft.Spark.Worker
> * Veröffentlichen einer .NET für Apache Spark-Anwendung
> * Bereitstellen einer App in Azure HDInsight
> * Führen Sie Ihre App aus.

## <a name="prerequisites"></a>Erforderliche Komponenten

Führen Sie zunächst folgende Schritte aus:

* Laden Sie den [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/) herunter.
* Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter. Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.

## <a name="prepare-worker-dependencies"></a>Vorbereiten von Workerabhängigkeiten

**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet. Wenn Sie eine benutzerdefinierte C#-Funktion ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird. **Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.

1. Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.

   Wenn z. B. `netcoreapp2.1` für `.NET for Apache Spark v0.1.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) herunter.

2. Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise HDFS, WASB, ADLS) hoch, auf das Ihr Cluster zugreifen kann.

## <a name="prepare-your-net-for-apache-spark-app"></a>Vorbereiten der .NET für Apache Spark-App

1. Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.

2. Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.

   Sie können unter Linux den folgenden Befehl ausführen:

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.

   Sie können unter Linux den folgenden `zip`-Befehl ausführen:

   ```bash
   zip -r <your app>.zip .
   ```

4. Laden Sie die folgenden Dateien auf ein verteiltes Dateisystem (beispielsweise HDFS, WASB, ADLS) hoch, auf das Ihr Cluster zugreifen kann:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.
   * `<your app>.zip`
   * Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit den benutzerdefinierten Funktionen oder Bibliotheken, von denen `app` abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.

## <a name="deploy-to-azure-hdinsight-spark"></a>Bereitstellen einer App in Azure HDInsight Spark

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) ist die Microsoft-Cloudimplementierung von Apache Spark, mit der Benutzer Spark-Cluster in Azure starten und konfigurieren können. Sie können HDInsight Spark-Cluster verwenden, um Daten zu verarbeiten, die in [Azure Storage](https://azure.microsoft.com/services/storage/) oder [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2) gespeichert sind.

> [!NOTE]
> Azure HDInsight Spark basiert auf Linux. Wenn Sie Ihre App in Azure HDInsight Spark bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.

### <a name="deploy-microsoftsparkworker"></a>Bereitstellen von Microsoft.Spark.Worker

Dieser Schritt ist nur einmal für Ihren Cluster erforderlich.

Führen Sie mithilfe der [HDInsight-Skriptaktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) `install-worker.sh` auf dem Cluster aus.

|Einstellung|Wert|
|-------|-----|
|Skripttyp|Benutzerdefiniert|
|NAME|Installation von Microsoft.Spark.Worker.|
|Bash-Skript-URI|Der URI für die hochgeladene Datei `install-worker.sh`. Zum Beispiel, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`|
|Knotentyp(en)|Worker|
|Parameter|Parameter für `install-worker.sh`. Wenn Sie z. B. `install-worker.sh` in Azure Data Lake Gen 2 hochgeladen haben, würden folgende Parameter verwendet werden: `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.|

![Screenshot mit Skriptaktion](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Führen Sie Ihre App aus.

Sie können einen Auftrag mit `spark-submit` oder Apache Livy an Azure HDInsight übermitteln.

### <a name="use-spark-submit"></a>Verwenden von „spark-submit“

Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Azure HDInsight übermitteln.
 
1. Stellen Sie mit `ssh` eine Verbindung mit einem Hauptknoten Ihres Clusters her.

1. Führen Sie `spark-submit` aus:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Verwenden von Apache Livy

Mit der Apache Spark-Rest-API [Apache Livy](https://livy.incubator.apache.org/) können Sie .NET für Apache Spark-Aufträge an einen Azure HDInsight Spark-Cluster übermitteln. Weitere Informationen finden Sie unter [Remoteaufträge mit Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

Sie können unter Linux den folgenden `curl`-Befehl ausführen:

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Azure HDInsight bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu Azure HDInsight.

> [!div class="nextstepaction"]
> [Azure HDInsight-Dokumentation](https://docs.microsoft.com/azure/hdinsight/)
