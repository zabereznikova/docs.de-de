---
title: Senden eines .NET für Apache Spark-Auftrags an Azure HDInsight
description: Hier erfahren Sie, wie Sie einen .NET für Apache Spark-Auftrag mit spark-submit und Apache Livy an Azure HDInsight senden.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 74be4ecf33a9a881633da0630fa1c1a4bf0b19c6
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688162"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a>Senden eines .NET für Apache Spark-Auftrags an Azure HDInsight

Es gibt zwei Möglichkeiten, einen .NET für Apache Spark-Auftrag für HDInsight bereitzustellen: `spark-submit` und Apache Livy.

## <a name="deploy-using-spark-submit"></a>Bereitstellen mit spark-submit

Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Azure HDInsight übermitteln.

1. Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **SSH und Clusteranmeldung** aus.

2. Kopieren Sie die SSH-Anmeldeinformationen, und fügen Sie diese in ein Terminal ein. Melden Sie sich mit dem Kennwort, das Sie während der Clustererstellung festgelegt haben, bei Ihrem Cluster an. Es sollten Meldungen angezeigt werden, die Sie bei Ubuntu und Spark Willkommen heißen.

3. Verwenden Sie den Befehl **spark-submit**, um Ihre App auf dem HDInsight-Cluster auszuführen. Denken Sie daran, **mycontainer** und **mystorageaccount** im Beispielskript durch die tatsächlichen Namen Ihres Blobcontainers und Speicherkontos zu ersetzen. Denken Sie auch daran, die JAR-Datei „microsoft-spark“ durch die Spark- und .NET-Versionen zu ersetzen, die für Apache Spark verwendet werden.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a>Bereitstellen mit Apache Livy

Mit der Apache Spark-Rest-API [Apache Livy](https://livy.incubator.apache.org/) können Sie .NET für Apache Spark-Aufträge an einen Azure HDInsight Spark-Cluster übermitteln. Weitere Informationen finden Sie unter [Remoteaufträge mit Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).

Sie können unter Linux den folgenden `curl`-Befehl ausführen:

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a>Nächste Schritte

* [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
* [Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [HDInsight-Dokumentation](/azure/hdinsight/)
