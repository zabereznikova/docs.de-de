---
title: Senden eines .NET für Apache Spark-Auftrags an Azure HDInsight
description: Hier erfahren Sie, wie Sie einen .NET für Apache Spark-Auftrag mit spark-submit und Apache Livy an Azure HDInsight senden.
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: cdd5e15ffde78ccb8b3156ee047b8ca98f7320b8
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74553022"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="8a758-103">Senden eines .NET für Apache Spark-Auftrags an Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8a758-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="8a758-104">Es gibt zwei Möglichkeiten, einen .NET für Apache Spark-Auftrag für HDInsight bereitzustellen: `spark-submit` und Apache Livy.</span><span class="sxs-lookup"><span data-stu-id="8a758-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="8a758-105">Bereitstellen mit spark-submit</span><span class="sxs-lookup"><span data-stu-id="8a758-105">Deploy using spark-submit</span></span>

<span data-ttu-id="8a758-106">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Azure HDInsight übermitteln.</span><span class="sxs-lookup"><span data-stu-id="8a758-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="8a758-107">Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **SSH und Clusteranmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="8a758-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="8a758-108">Kopieren Sie die SSH-Anmeldeinformationen, und fügen Sie diese in ein Terminal ein.</span><span class="sxs-lookup"><span data-stu-id="8a758-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="8a758-109">Melden Sie sich mit dem Kennwort, das Sie während der Clustererstellung festgelegt haben, bei Ihrem Cluster an.</span><span class="sxs-lookup"><span data-stu-id="8a758-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="8a758-110">Es sollten Meldungen angezeigt werden, die Sie bei Ubuntu und Spark Willkommen heißen.</span><span class="sxs-lookup"><span data-stu-id="8a758-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="8a758-111">Verwenden Sie den Befehl **spark-submit**, um Ihre App auf dem HDInsight-Cluster auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8a758-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="8a758-112">Denken Sie daran, **mycontainer** und **mystorageaccount** im Beispielskript durch die tatsächlichen Namen Ihres Blobcontainers und Speicherkontos zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8a758-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="8a758-113">Außerdem müssen Sie `microsoft-spark-2.3.x-0.6.0.jar` durch die entsprechende JAR-Datei ersetzen, die Sie für die Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a758-113">Also, be sure to replace `microsoft-spark-2.3.x-0.6.0.jar` with the appropriate jar file you're using for deployment.</span></span> <span data-ttu-id="8a758-114">`2.3.x` stellt die Version von Apache Spark und `0.6.0` die Version des [.NET für Apache Spark Workers](https://github.com/dotnet/spark/releases) dar.</span><span class="sxs-lookup"><span data-stu-id="8a758-114">`2.3.x` represents the version of Apache Spark, and `0.6.0` represents the version of the [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases).</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="8a758-115">Bereitstellen mit Apache Livy</span><span class="sxs-lookup"><span data-stu-id="8a758-115">Deploy using Apache Livy</span></span>

<span data-ttu-id="8a758-116">Mit der Apache Spark-Rest-API [Apache Livy](https://livy.incubator.apache.org/) können Sie .NET für Apache Spark-Aufträge an einen Azure HDInsight Spark-Cluster übermitteln.</span><span class="sxs-lookup"><span data-stu-id="8a758-116">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="8a758-117">Weitere Informationen finden Sie unter [Remoteaufträge mit Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="8a758-117">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="8a758-118">Sie können unter Linux den folgenden `curl`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a758-118">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="8a758-119">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8a758-119">Next steps</span></span>

* [<span data-ttu-id="8a758-120">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="8a758-120">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="8a758-121">Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8a758-121">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="8a758-122">HDInsight-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="8a758-122">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
