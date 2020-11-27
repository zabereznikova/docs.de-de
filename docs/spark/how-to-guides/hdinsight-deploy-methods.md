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
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="2c7c1-103">Senden eines .NET für Apache Spark-Auftrags an Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="2c7c1-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="2c7c1-104">Es gibt zwei Möglichkeiten, einen .NET für Apache Spark-Auftrag für HDInsight bereitzustellen: `spark-submit` und Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="2c7c1-105">Bereitstellen mit spark-submit</span><span class="sxs-lookup"><span data-stu-id="2c7c1-105">Deploy using spark-submit</span></span>

<span data-ttu-id="2c7c1-106">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Azure HDInsight übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>

1. <span data-ttu-id="2c7c1-107">Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **SSH und Clusteranmeldung** aus.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="2c7c1-108">Kopieren Sie die SSH-Anmeldeinformationen, und fügen Sie diese in ein Terminal ein.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="2c7c1-109">Melden Sie sich mit dem Kennwort, das Sie während der Clustererstellung festgelegt haben, bei Ihrem Cluster an.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="2c7c1-110">Es sollten Meldungen angezeigt werden, die Sie bei Ubuntu und Spark Willkommen heißen.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="2c7c1-111">Verwenden Sie den Befehl **spark-submit**, um Ihre App auf dem HDInsight-Cluster auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="2c7c1-112">Denken Sie daran, **mycontainer** und **mystorageaccount** im Beispielskript durch die tatsächlichen Namen Ihres Blobcontainers und Speicherkontos zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="2c7c1-113">Denken Sie auch daran, die JAR-Datei „microsoft-spark“ durch die Spark- und .NET-Versionen zu ersetzen, die für Apache Spark verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-113">Also remember to replace the microsoft-spark jar with the version of Spark and .NET for Apache Spark being used.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="2c7c1-114">Bereitstellen mit Apache Livy</span><span class="sxs-lookup"><span data-stu-id="2c7c1-114">Deploy using Apache Livy</span></span>

<span data-ttu-id="2c7c1-115">Mit der Apache Spark-Rest-API [Apache Livy](https://livy.incubator.apache.org/) können Sie .NET für Apache Spark-Aufträge an einen Azure HDInsight Spark-Cluster übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2c7c1-115">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="2c7c1-116">Weitere Informationen finden Sie unter [Remoteaufträge mit Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="2c7c1-116">For more information, see [Remote jobs with Apache Livy](/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="2c7c1-117">Sie können unter Linux den folgenden `curl`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="2c7c1-117">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="2c7c1-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2c7c1-118">Next steps</span></span>

* [<span data-ttu-id="2c7c1-119">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="2c7c1-119">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="2c7c1-120">Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="2c7c1-120">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="2c7c1-121">HDInsight-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="2c7c1-121">HDInsight Documentation</span></span>](/azure/hdinsight/)
