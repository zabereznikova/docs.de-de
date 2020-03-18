---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a1ff1ba4d5e855e0ac36b99b0c9d63adfaaaac1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73454938"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="36b32-103">Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="36b32-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="36b32-104">In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="36b32-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="36b32-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="36b32-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="36b32-106">Vorbereiten von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="36b32-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="36b32-107">Veröffentlichen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="36b32-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="36b32-108">Bereitstellen einer App in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="36b32-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="36b32-109">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="36b32-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36b32-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="36b32-110">Prerequisites</span></span>

<span data-ttu-id="36b32-111">Führen Sie zunächst folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="36b32-111">Before you start, do the following:</span></span>

* <span data-ttu-id="36b32-112">Laden Sie die [AWS CLI](https://aws.amazon.com/cli/) herunter.</span><span class="sxs-lookup"><span data-stu-id="36b32-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="36b32-113">Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="36b32-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="36b32-114">Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.</span><span class="sxs-lookup"><span data-stu-id="36b32-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="36b32-115">Vorbereiten von Workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="36b32-115">Prepare worker dependencies</span></span>

<span data-ttu-id="36b32-116">**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet.</span><span class="sxs-lookup"><span data-stu-id="36b32-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="36b32-117">Wenn Sie eine benutzerdefinierte C#-Funktion ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="36b32-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="36b32-118">**Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="36b32-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="36b32-119">Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="36b32-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="36b32-120">Wenn z. B. `netcoreapp2.1` für `.NET for Apache Spark v0.1.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) herunter.</span><span class="sxs-lookup"><span data-stu-id="36b32-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="36b32-121">Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise S3) hoch, auf das Ihr Cluster zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="36b32-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="36b32-122">Vorbereiten der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="36b32-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="36b32-123">Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="36b32-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="36b32-124">Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="36b32-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="36b32-125">Führen Sie unter Linux den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="36b32-125">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="36b32-126">Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.</span><span class="sxs-lookup"><span data-stu-id="36b32-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="36b32-127">Führen Sie unter Linux den folgenden `zip`-Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="36b32-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="36b32-128">Laden Sie die folgenden Dateien auf ein verteiltes Dateisystem (beispielsweise S3) hoch, auf das Ihr Cluster zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="36b32-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="36b32-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="36b32-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="36b32-130">Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit benutzerdefinierten Funktionen oder Bibliotheken, von denen Ihre App abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="36b32-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="36b32-131">Bereitstellen einer App in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="36b32-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="36b32-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) ist eine verwaltete Clusterplattform, die die Ausführung von Big-Data-Frameworks in AWS vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="36b32-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="36b32-133">Amazon EMR Spark basiert auf Linux.</span><span class="sxs-lookup"><span data-stu-id="36b32-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="36b32-134">Wenn Sie Ihre App in Amazon EMR Spark bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.</span><span class="sxs-lookup"><span data-stu-id="36b32-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="36b32-135">Bereitstellen von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="36b32-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="36b32-136">Dieser Schritt ist nur bei der Erstellung des Clusters erforderlich.</span><span class="sxs-lookup"><span data-stu-id="36b32-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="36b32-137">Führen Sie mithilfe der [Bootstrapaktionen](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)`install-worker.sh` bei der Erstellung des Clusters aus.</span><span class="sxs-lookup"><span data-stu-id="36b32-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="36b32-138">Führen Sie unter Linux den folgenden Befehl mit der AWS CLI aus:</span><span class="sxs-lookup"><span data-stu-id="36b32-138">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="36b32-139">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="36b32-139">Run your app</span></span>

<span data-ttu-id="36b32-140">Sie können Ihre App in Amazon EMR Spark entweder mit „spark-submit“ oder mit Amazon EMR-Schritten ausführen.</span><span class="sxs-lookup"><span data-stu-id="36b32-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="36b32-141">Verwenden von „spark-submit“</span><span class="sxs-lookup"><span data-stu-id="36b32-141">Use spark-submit</span></span>

<span data-ttu-id="36b32-142">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Amazon EMR Spark übermitteln.</span><span class="sxs-lookup"><span data-stu-id="36b32-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="36b32-143">Stellen Sie mit `ssh` eine Verbindung mit einem Knoten Ihres Clusters her.</span><span class="sxs-lookup"><span data-stu-id="36b32-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="36b32-144">Führen Sie aus `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="36b32-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="36b32-145">Verwenden von Amazon EMR-Schritten</span><span class="sxs-lookup"><span data-stu-id="36b32-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="36b32-146">Mithilfe von [Amazon EMR-Schritten](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) können Sie Aufträge an das Spark-Framework übermitteln, das auf dem EMR-Cluster installiert ist.</span><span class="sxs-lookup"><span data-stu-id="36b32-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="36b32-147">Führen Sie unter Linux den folgenden Befehl mit der AWS CLI aus:</span><span class="sxs-lookup"><span data-stu-id="36b32-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="36b32-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="36b32-148">Next steps</span></span>

<span data-ttu-id="36b32-149">In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="36b32-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="36b32-150">Beispielprojekte für .NET für Apache Spark finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="36b32-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="36b32-151">Beispiele für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="36b32-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
