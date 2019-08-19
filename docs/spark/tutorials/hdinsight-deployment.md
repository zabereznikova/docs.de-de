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
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="fcfc6-103">Bereitstellen einer .net for Apache Spark-Anwendung für Azure hdinsight</span><span class="sxs-lookup"><span data-stu-id="fcfc6-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="fcfc6-104">In diesem Tutorial erfahren Sie, wie Sie eine .net für Apache Spark-Anwendung in Azure hdinsight bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="fcfc6-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fcfc6-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="fcfc6-106">Vorbereiten von Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="fcfc6-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="fcfc6-107">Veröffentlichen Ihrer Spark .net-App</span><span class="sxs-lookup"><span data-stu-id="fcfc6-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="fcfc6-108">Bereitstellen der app in Azure hdinsight</span><span class="sxs-lookup"><span data-stu-id="fcfc6-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="fcfc6-109">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="fcfc6-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fcfc6-110">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fcfc6-110">Prerequisites</span></span>

<span data-ttu-id="fcfc6-111">Bevor Sie beginnen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="fcfc6-111">Before you start, do the following:</span></span>

* <span data-ttu-id="fcfc6-112">Laden Sie [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/)herunter.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="fcfc6-113">Laden Sie [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="fcfc6-114">Hierbei handelt es sich um ein Hilfsskript, das Sie später verwenden, um .net für Apache Spark abhängige Dateien in die workerknoten Ihres Spark-Clusters zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="fcfc6-115">Vorbereiten von workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="fcfc6-115">Prepare worker dependencies</span></span>

<span data-ttu-id="fcfc6-116">**Microsoft. Spark. Worker** ist eine Back-End-Komponente, die sich auf den einzelnen workerknoten Ihres Spark-Clusters befindet.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="fcfc6-117">Wenn Sie eine C# benutzerdefinierte Funktion (User-Defined Function, UDF) ausführen möchten, muss Spark wissen, wie die .NET CLR gestartet werden muss, um die UDF auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="fcfc6-118">**Microsoft. Spark. Worker** stellt eine Auflistung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="fcfc6-119">Wählen Sie eine Version von [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp aus, die auf Ihrem Cluster bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="fcfc6-120">Wenn Sie beispielsweise verwenden `.NET for Apache Spark v0.1.0` `netcoreapp2.1`möchten, laden Sie [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)herunter.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="fcfc6-121">Hochladen `Microsoft.Spark.Worker.<release>.tar.gz` und [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in ein verteiltes Dateisystem (z. b. HDFS, wasb, ADLS), auf das Ihr Cluster Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="fcfc6-122">Vorbereiten von .net für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="fcfc6-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="fcfc6-123">Befolgen Sie das Tutorial " [Get Started](get-started.md) ", um Ihre APP zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="fcfc6-124">Veröffentlichen Sie Ihre Spark .net-App als eigenständig.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="fcfc6-125">Sie können den folgenden Befehl unter Linux ausführen.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="fcfc6-126">Erzeugt `<your app>.zip` für die veröffentlichten Dateien.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="fcfc6-127">Sie können den folgenden Befehl unter Linux mit `zip`ausführen.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="fcfc6-128">Laden Sie Folgendes in ein verteiltes Dateisystem (z. b. HDFS, wasb, ADLS) hoch, auf das Ihr Cluster Zugriff hat:</span><span class="sxs-lookup"><span data-stu-id="fcfc6-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="fcfc6-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist als Teil des [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) -nuget-Pakets enthalten und wird im Buildausgabeverzeichnis Ihrer APP zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="fcfc6-130">Dateien (z. b. Abhängigkeits Dateien oder gemeinsame Daten, die für jeden Worker zugänglich sind) oder Assemblys (z. b. `app` DLLs, die die benutzerdefinierten Funktionen oder Bibliotheken enthalten, von denen abhängig ist), die im Arbeitsverzeichnis jedes Executor abgelegt werden sollen</span><span class="sxs-lookup"><span data-stu-id="fcfc6-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="fcfc6-131">In Azure HDInsight Spark bereitstellen</span><span class="sxs-lookup"><span data-stu-id="fcfc6-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="fcfc6-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) ist die Microsoft-Implementierung von Apache Spark in der Cloud, die es Benutzern ermöglicht, Spark-Cluster in Azure zu starten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="fcfc6-133">Sie können hdinsight Spark-Cluster verwenden, um Ihre in [Azure Storage](https://azure.microsoft.com/services/storage/) oder [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2)gespeicherten Daten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="fcfc6-134">Azure HDInsight Spark ist Linux-basiert.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="fcfc6-135">Wenn Sie Ihre APP für Azure HDInsight Spark bereitstellen möchten, stellen Sie sicher, dass Ihre APP .NET Standard kompatibel ist und Sie den [.net Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer APP verwenden.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="fcfc6-136">Bereitstellen von Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="fcfc6-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="fcfc6-137">Dieser Schritt ist nur einmal für den Cluster erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="fcfc6-138">Führen `install-worker.sh` Sie im Cluster mithilfe von [hdinsight-Skript Aktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)aus.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="fcfc6-139">Einstellung</span><span class="sxs-lookup"><span data-stu-id="fcfc6-139">Setting</span></span>|<span data-ttu-id="fcfc6-140">Wert</span><span class="sxs-lookup"><span data-stu-id="fcfc6-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="fcfc6-141">Skripttyp</span><span class="sxs-lookup"><span data-stu-id="fcfc6-141">Script type</span></span>|<span data-ttu-id="fcfc6-142">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="fcfc6-142">Custom</span></span>|
|<span data-ttu-id="fcfc6-143">Name</span><span class="sxs-lookup"><span data-stu-id="fcfc6-143">Name</span></span>|<span data-ttu-id="fcfc6-144">Installieren von Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="fcfc6-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="fcfc6-145">Bash-Skript-URI</span><span class="sxs-lookup"><span data-stu-id="fcfc6-145">Bash script URI</span></span>|<span data-ttu-id="fcfc6-146">Der URI, auf den Sie `install-worker.sh`hochgeladen haben.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="fcfc6-147">Beispiel: `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="fcfc6-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="fcfc6-148">Knotentyp (e)</span><span class="sxs-lookup"><span data-stu-id="fcfc6-148">Node type(s)</span></span>|<span data-ttu-id="fcfc6-149">Arbeiter</span><span class="sxs-lookup"><span data-stu-id="fcfc6-149">Worker</span></span>|
|<span data-ttu-id="fcfc6-150">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcfc6-150">Parameters</span></span>|<span data-ttu-id="fcfc6-151">Parameter für `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="fcfc6-152">Wenn Sie z `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`. b. `install-worker.sh` in Azure Data Lake Gen 2 hochgeladen haben, dann wäre es.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![Skript Aktions Bild](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="fcfc6-154">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="fcfc6-154">Run your app</span></span>

<span data-ttu-id="fcfc6-155">Sie können Ihren Auftrag mithilfe `spark-submit` von oder Apache Livy an Azure hdinsight übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="fcfc6-156">Verwenden von Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="fcfc6-156">Use spark-submit</span></span>

<span data-ttu-id="fcfc6-157">Sie können den Befehl " [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) " verwenden, um .net für Apache Spark Aufträge an Azure hdinsight zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="fcfc6-158">`ssh`zu einem der Haupt Knoten im Cluster.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="fcfc6-159">Ausführen `spark-submit`:</span><span class="sxs-lookup"><span data-stu-id="fcfc6-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="fcfc6-160">Verwenden von Apache Livy</span><span class="sxs-lookup"><span data-stu-id="fcfc6-160">Use Apache Livy</span></span>

<span data-ttu-id="fcfc6-161">Sie können [Apache Livy](https://livy.incubator.apache.org/), die Apache Spark Rest-API, verwenden, um .net für Apache Spark Aufträge an einen Azure HDInsight Spark-Cluster zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="fcfc6-162">Weitere Informationen finden Sie unter [Remote Aufträge mit Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="fcfc6-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="fcfc6-163">Sie können den folgenden Befehl unter Linux mithilfe `curl`von ausführen:</span><span class="sxs-lookup"><span data-stu-id="fcfc6-163">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="fcfc6-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fcfc6-164">Next steps</span></span>

<span data-ttu-id="fcfc6-165">In diesem Tutorial haben Sie Ihre .net for Apache Spark-Anwendung für Azure hdinsight bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="fcfc6-166">Weitere Informationen zu hdinsight finden Sie in der Dokumentation zu Azure hdinsight.</span><span class="sxs-lookup"><span data-stu-id="fcfc6-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcfc6-167">Azure hdinsight-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="fcfc6-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
