---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in HDInsight bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9da0e0fd83d70887109c63a5e95ec0b0b31a2edd
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928471"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="ac66f-103">Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="ac66f-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="ac66f-104">In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Azure HDInsight bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ac66f-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="ac66f-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="ac66f-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="ac66f-106">Vorbereiten von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="ac66f-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="ac66f-107">Veröffentlichen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ac66f-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="ac66f-108">Bereitstellen einer App in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="ac66f-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="ac66f-109">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="ac66f-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac66f-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ac66f-110">Prerequisites</span></span>

<span data-ttu-id="ac66f-111">Führen Sie zunächst folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ac66f-111">Before you start, do the following:</span></span>

* <span data-ttu-id="ac66f-112">Laden Sie den [Azure Storage-Explorer](https://azure.microsoft.com/features/storage-explorer/) herunter.</span><span class="sxs-lookup"><span data-stu-id="ac66f-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="ac66f-113">Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="ac66f-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="ac66f-114">Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.</span><span class="sxs-lookup"><span data-stu-id="ac66f-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="ac66f-115">Vorbereiten von Workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="ac66f-115">Prepare worker dependencies</span></span>

<span data-ttu-id="ac66f-116">**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet.</span><span class="sxs-lookup"><span data-stu-id="ac66f-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="ac66f-117">Wenn Sie eine benutzerdefinierte C#-Funktion ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ac66f-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="ac66f-118">**Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ac66f-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="ac66f-119">Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac66f-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="ac66f-120">Wenn z. B. `netcoreapp2.1` für `.NET for Apache Spark v0.1.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) herunter.</span><span class="sxs-lookup"><span data-stu-id="ac66f-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="ac66f-121">Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise HDFS, WASB, ADLS) hoch, auf das Ihr Cluster zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ac66f-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="ac66f-122">Vorbereiten der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="ac66f-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="ac66f-123">Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac66f-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="ac66f-124">Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ac66f-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="ac66f-125">Sie können unter Linux den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ac66f-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="ac66f-126">Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.</span><span class="sxs-lookup"><span data-stu-id="ac66f-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="ac66f-127">Sie können unter Linux den folgenden `zip`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ac66f-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="ac66f-128">Laden Sie die folgenden Dateien auf ein verteiltes Dateisystem (beispielsweise HDFS, WASB, ADLS) hoch, auf das Ihr Cluster zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="ac66f-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="ac66f-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="ac66f-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="ac66f-130">Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit den benutzerdefinierten Funktionen oder Bibliotheken, von denen `app` abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ac66f-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="ac66f-131">Bereitstellen einer App in Azure HDInsight Spark</span><span class="sxs-lookup"><span data-stu-id="ac66f-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="ac66f-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) ist die Microsoft-Cloudimplementierung von Apache Spark, mit der Benutzer Spark-Cluster in Azure starten und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="ac66f-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="ac66f-133">Sie können HDInsight Spark-Cluster verwenden, um Daten zu verarbeiten, die in [Azure Storage](https://azure.microsoft.com/services/storage/) oder [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2) gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="ac66f-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="ac66f-134">Azure HDInsight Spark basiert auf Linux.</span><span class="sxs-lookup"><span data-stu-id="ac66f-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="ac66f-135">Wenn Sie Ihre App in Azure HDInsight Spark bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac66f-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="ac66f-136">Bereitstellen von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="ac66f-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="ac66f-137">Dieser Schritt ist nur einmal für Ihren Cluster erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac66f-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="ac66f-138">Führen Sie mithilfe der [HDInsight-Skriptaktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) `install-worker.sh` auf dem Cluster aus.</span><span class="sxs-lookup"><span data-stu-id="ac66f-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="ac66f-139">Einstellung</span><span class="sxs-lookup"><span data-stu-id="ac66f-139">Setting</span></span>|<span data-ttu-id="ac66f-140">Wert</span><span class="sxs-lookup"><span data-stu-id="ac66f-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="ac66f-141">Skripttyp</span><span class="sxs-lookup"><span data-stu-id="ac66f-141">Script type</span></span>|<span data-ttu-id="ac66f-142">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="ac66f-142">Custom</span></span>|
|<span data-ttu-id="ac66f-143">name</span><span class="sxs-lookup"><span data-stu-id="ac66f-143">Name</span></span>|<span data-ttu-id="ac66f-144">Installation von Microsoft.Spark.Worker.</span><span class="sxs-lookup"><span data-stu-id="ac66f-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="ac66f-145">Bash-Skript-URI</span><span class="sxs-lookup"><span data-stu-id="ac66f-145">Bash script URI</span></span>|<span data-ttu-id="ac66f-146">Der URI für die hochgeladene Datei `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="ac66f-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="ac66f-147">Beispiel: `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="ac66f-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="ac66f-148">Knotentyp(en)</span><span class="sxs-lookup"><span data-stu-id="ac66f-148">Node type(s)</span></span>|<span data-ttu-id="ac66f-149">Worker</span><span class="sxs-lookup"><span data-stu-id="ac66f-149">Worker</span></span>|
|<span data-ttu-id="ac66f-150">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac66f-150">Parameters</span></span>|<span data-ttu-id="ac66f-151">Parameter für `install-worker.sh`.</span><span class="sxs-lookup"><span data-stu-id="ac66f-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="ac66f-152">Wenn Sie z. B. `install-worker.sh` in Azure Data Lake Gen 2 hochgeladen haben, würden folgende Parameter verwendet werden: `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span><span class="sxs-lookup"><span data-stu-id="ac66f-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![Screenshot mit Skriptaktion](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="ac66f-154">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="ac66f-154">Run your app</span></span>

<span data-ttu-id="ac66f-155">Sie können einen Auftrag mit `spark-submit` oder Apache Livy an Azure HDInsight übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ac66f-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="ac66f-156">Verwenden von „spark-submit“</span><span class="sxs-lookup"><span data-stu-id="ac66f-156">Use spark-submit</span></span>

<span data-ttu-id="ac66f-157">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Azure HDInsight übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ac66f-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="ac66f-158">Stellen Sie mit `ssh` eine Verbindung mit einem Hauptknoten Ihres Clusters her.</span><span class="sxs-lookup"><span data-stu-id="ac66f-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="ac66f-159">Führen Sie `spark-submit` aus:</span><span class="sxs-lookup"><span data-stu-id="ac66f-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="ac66f-160">Verwenden von Apache Livy</span><span class="sxs-lookup"><span data-stu-id="ac66f-160">Use Apache Livy</span></span>

<span data-ttu-id="ac66f-161">Mit der Apache Spark-Rest-API [Apache Livy](https://livy.incubator.apache.org/) können Sie .NET für Apache Spark-Aufträge an einen Azure HDInsight Spark-Cluster übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ac66f-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="ac66f-162">Weitere Informationen finden Sie unter [Remoteaufträge mit Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span><span class="sxs-lookup"><span data-stu-id="ac66f-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="ac66f-163">Sie können unter Linux den folgenden `curl`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ac66f-163">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="ac66f-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ac66f-164">Next steps</span></span>

<span data-ttu-id="ac66f-165">In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Azure HDInsight bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ac66f-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="ac66f-166">Weitere Informationen finden Sie in der Dokumentation zu Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="ac66f-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ac66f-167">Azure HDInsight-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ac66f-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
