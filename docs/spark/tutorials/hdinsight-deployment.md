---
title: Bereitstellen einer .net for Apache Spark-Anwendung für Azure hdinsight
description: Erfahren Sie, wie Sie eine .net for Apache Spark-Anwendung in hdinsight bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4769c194520790ce217d46d1d3197b20742d4f1a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "69576947"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Bereitstellen einer .net for Apache Spark-Anwendung für Azure hdinsight

In diesem Tutorial erfahren Sie, wie Sie eine .net für Apache Spark-Anwendung in Azure hdinsight bereitstellen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Vorbereiten von Microsoft. Spark. Worker
> * Veröffentlichen Ihrer Spark .net-App
> * Bereitstellen der app in Azure hdinsight
> * Ausführen der App

## <a name="prerequisites"></a>Vorraussetzungen

Bevor Sie beginnen, gehen Sie folgendermaßen vor:

* Laden Sie [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/)herunter.
* Laden Sie [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter. Hierbei handelt es sich um ein Hilfsskript, das Sie später verwenden, um .net für Apache Spark abhängige Dateien in die workerknoten Ihres Spark-Clusters zu kopieren.

## <a name="prepare-worker-dependencies"></a>Vorbereiten von workerabhängigkeiten

**Microsoft. Spark. Worker** ist eine Back-End-Komponente, die sich auf den einzelnen workerknoten Ihres Spark-Clusters befindet. Wenn Sie eine C# benutzerdefinierte Funktion (User-Defined Function, UDF) ausführen möchten, muss Spark wissen, wie die .NET CLR gestartet werden muss, um die UDF auszuführen. **Microsoft. Spark. Worker** stellt eine Auflistung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.

1. Wählen Sie eine Version von [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp aus, die auf Ihrem Cluster bereitgestellt werden soll.

   Wenn Sie beispielsweise verwenden `.NET for Apache Spark v0.1.0` `netcoreapp2.1`möchten, laden Sie [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)herunter.

2. Hochladen `Microsoft.Spark.Worker.<release>.tar.gz` und [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in ein verteiltes Dateisystem (z. b. HDFS, wasb, ADLS), auf das Ihr Cluster Zugriff hat.

## <a name="prepare-your-net-for-apache-spark-app"></a>Vorbereiten von .net für Apache Spark-App

1. Befolgen Sie das Tutorial " [Get Started](get-started.md) ", um Ihre APP zu erstellen.

2. Veröffentlichen Sie Ihre Spark .net-App als eigenständig.

   Sie können den folgenden Befehl unter Linux ausführen.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Erzeugt `<your app>.zip` für die veröffentlichten Dateien.

   Sie können den folgenden Befehl unter Linux mit `zip`ausführen.

   ```bash
   zip -r <your app>.zip .
   ```

4. Laden Sie Folgendes in ein verteiltes Dateisystem (z. b. HDFS, wasb, ADLS) hoch, auf das Ihr Cluster Zugriff hat:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist als Teil des [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) -nuget-Pakets enthalten und wird im Buildausgabeverzeichnis Ihrer APP zusammengestellt.
   * `<your app>.zip`
   * Dateien (z. b. Abhängigkeits Dateien oder gemeinsame Daten, die für jeden Worker zugänglich sind) oder Assemblys (z. b. `app` DLLs, die die benutzerdefinierten Funktionen oder Bibliotheken enthalten, von denen abhängig ist), die im Arbeitsverzeichnis jedes Executor abgelegt werden sollen

## <a name="deploy-to-azure-hdinsight-spark"></a>In Azure HDInsight Spark bereitstellen

[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) ist die Microsoft-Implementierung von Apache Spark in der Cloud, die es Benutzern ermöglicht, Spark-Cluster in Azure zu starten und zu konfigurieren. Sie können hdinsight Spark-Cluster verwenden, um Ihre in [Azure Storage](https://azure.microsoft.com/services/storage/) oder [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2)gespeicherten Daten zu verarbeiten.

> [!NOTE]
> Azure HDInsight Spark ist Linux-basiert. Wenn Sie Ihre APP für Azure HDInsight Spark bereitstellen möchten, stellen Sie sicher, dass Ihre APP .NET Standard kompatibel ist und Sie den [.net Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer APP verwenden.

### <a name="deploy-microsoftsparkworker"></a>Bereitstellen von Microsoft. Spark. Worker

Dieser Schritt ist nur einmal für den Cluster erforderlich.

Führen `install-worker.sh` Sie im Cluster mithilfe von [hdinsight-Skript Aktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)aus.

|Einstellung|Wert|
|-------|-----|
|Skripttyp|Benutzerdefiniert|
|Name|Installieren von Microsoft. Spark. Worker|
|Bash-Skript-URI|Der URI, auf den Sie `install-worker.sh`hochgeladen haben. Beispiel: `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`|
|Knotentyp (e)|Arbeiter|
|Parameter|Parameter für `install-worker.sh`. Wenn Sie z `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`. b. `install-worker.sh` in Azure Data Lake Gen 2 hochgeladen haben, dann wäre es.|

![Skript Aktions Bild](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a>Ausführen der App

Sie können Ihren Auftrag mithilfe `spark-submit` von oder Apache Livy an Azure hdinsight übermitteln.

### <a name="use-spark-submit"></a>Verwenden von Spark-Submit

Sie können den Befehl " [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) " verwenden, um .net für Apache Spark Aufträge an Azure hdinsight zu übermitteln.
 
1. `ssh`zu einem der Haupt Knoten im Cluster.

1. Ausführen `spark-submit`:

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a>Verwenden von Apache Livy

Sie können [Apache Livy](https://livy.incubator.apache.org/), die Apache Spark Rest-API, verwenden, um .net für Apache Spark Aufträge an einen Azure HDInsight Spark-Cluster zu übermitteln. Weitere Informationen finden Sie unter [Remote Aufträge mit Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).

Sie können den folgenden Befehl unter Linux mithilfe `curl`von ausführen:

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Ihre .net for Apache Spark-Anwendung für Azure hdinsight bereitgestellt. Weitere Informationen zu hdinsight finden Sie in der Dokumentation zu Azure hdinsight.

> [!div class="nextstepaction"]
> [Azure hdinsight-Dokumentation](https://docs.microsoft.com/azure/hdinsight/)
