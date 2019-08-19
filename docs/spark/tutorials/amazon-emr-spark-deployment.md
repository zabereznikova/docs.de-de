---
title: Bereitstellen einer .net for Apache Spark-Anwendung in Amazon EMR Spark
description: Erfahren Sie, wie Sie eine .net for Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 5414bc20de3bb90a5d2144bd006d1b859e184a39
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "69576927"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="5fb89-103">Bereitstellen einer .net for Apache Spark-Anwendung in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="5fb89-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="5fb89-104">In diesem Tutorial erfahren Sie, wie Sie eine .NET-Anwendung für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5fb89-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="5fb89-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="5fb89-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5fb89-106">Vorbereiten von Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="5fb89-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="5fb89-107">Veröffentlichen Ihrer Spark .net-App</span><span class="sxs-lookup"><span data-stu-id="5fb89-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="5fb89-108">Bereitstellen Ihrer APP in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="5fb89-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="5fb89-109">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="5fb89-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5fb89-110">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5fb89-110">Prerequisites</span></span>

<span data-ttu-id="5fb89-111">Bevor Sie beginnen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="5fb89-111">Before you start, do the following:</span></span>

* <span data-ttu-id="5fb89-112">Laden Sie die [AWS-CLI](https://aws.amazon.com/cli/)herunter.</span><span class="sxs-lookup"><span data-stu-id="5fb89-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="5fb89-113">Laden Sie [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="5fb89-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="5fb89-114">Hierbei handelt es sich um ein Hilfsskript, das Sie später verwenden, um .net für Apache Spark abhängige Dateien in die workerknoten Ihres Spark-Clusters zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="5fb89-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="5fb89-115">Vorbereiten von workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="5fb89-115">Prepare worker dependencies</span></span>

<span data-ttu-id="5fb89-116">**Microsoft. Spark. Worker** ist eine Back-End-Komponente, die sich auf den einzelnen workerknoten Ihres Spark-Clusters befindet.</span><span class="sxs-lookup"><span data-stu-id="5fb89-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="5fb89-117">Wenn Sie eine C# benutzerdefinierte Funktion (User-Defined Function, UDF) ausführen möchten, muss Spark wissen, wie die .NET CLR gestartet werden muss, um die UDF auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5fb89-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="5fb89-118">**Microsoft. Spark. Worker** stellt eine Auflistung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5fb89-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="5fb89-119">Wählen Sie eine Version von [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp aus, die auf Ihrem Cluster bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5fb89-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="5fb89-120">Wenn Sie beispielsweise verwenden `.NET for Apache Spark v0.1.0` `netcoreapp2.1`möchten, laden Sie [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)herunter.</span><span class="sxs-lookup"><span data-stu-id="5fb89-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="5fb89-121">Hochladen `Microsoft.Spark.Worker.<release>.tar.gz` und [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in ein verteiltes Dateisystem (z. b. S3), auf das Ihr Cluster Zugriff hat.</span><span class="sxs-lookup"><span data-stu-id="5fb89-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="5fb89-122">Vorbereiten von .net für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="5fb89-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="5fb89-123">Befolgen Sie das Tutorial " [Get Started](get-started.md) ", um Ihre APP zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5fb89-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="5fb89-124">Veröffentlichen Sie Ihre Spark .net-App als eigenständig.</span><span class="sxs-lookup"><span data-stu-id="5fb89-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="5fb89-125">Führen Sie unter Linux den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="5fb89-125">Run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="5fb89-126">Erzeugt `<your app>.zip` für die veröffentlichten Dateien.</span><span class="sxs-lookup"><span data-stu-id="5fb89-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="5fb89-127">Führen Sie den folgenden Befehl unter Linux `zip`mit aus.</span><span class="sxs-lookup"><span data-stu-id="5fb89-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="5fb89-128">Laden Sie die folgenden Elemente in ein verteiltes Dateisystem (z. b. S3) hoch, auf das Ihr Cluster Zugriff hat:</span><span class="sxs-lookup"><span data-stu-id="5fb89-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="5fb89-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist als Teil des [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) -nuget-Pakets enthalten und wird im Buildausgabeverzeichnis Ihrer APP zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="5fb89-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="5fb89-130">Dateien (z. b. Abhängigkeits Dateien oder gemeinsame Daten, die für jeden Worker zugänglich sind) oder Assemblys (z. b. DLLs, die die benutzerdefinierten Funktionen oder Bibliotheken enthalten, von denen Ihre APP abhängt), die im Arbeitsverzeichnis jedes Executor abgelegt werden sollen</span><span class="sxs-lookup"><span data-stu-id="5fb89-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="5fb89-131">Bereitstellen in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="5fb89-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="5fb89-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) ist eine verwaltete Cluster Plattform, die die Ausführung Big Data Frameworks auf AWS vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="5fb89-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE] 
> <span data-ttu-id="5fb89-133">Amazon EMR Spark ist Linux-basiert.</span><span class="sxs-lookup"><span data-stu-id="5fb89-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="5fb89-134">Wenn Sie Ihre APP in Amazon EMR Spark bereitstellen möchten, müssen Sie daher sicherstellen, dass Ihre APP .NET Standard kompatibel ist und Sie den [.net Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer APP verwenden.</span><span class="sxs-lookup"><span data-stu-id="5fb89-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="5fb89-135">Bereitstellen von Microsoft. Spark. Worker</span><span class="sxs-lookup"><span data-stu-id="5fb89-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="5fb89-136">Dieser Schritt ist nur bei der Cluster Erstellung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5fb89-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="5fb89-137">Wird `install-worker.sh` während der Cluster Erstellung mithilfe von [Bootstrap-Aktionen](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5fb89-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="5fb89-138">Führen Sie den folgenden Befehl unter Linux mithilfe der AWS CLI aus.</span><span class="sxs-lookup"><span data-stu-id="5fb89-138">Run the following command on Linux using AWS CLI.</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="5fb89-139">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="5fb89-139">Run your app</span></span>

<span data-ttu-id="5fb89-140">Es gibt zwei Möglichkeiten, Ihre APP in Amazon EMR Spark auszuführen: Spark-Submit und Amazon EMR Steps.</span><span class="sxs-lookup"><span data-stu-id="5fb89-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="5fb89-141">Verwenden von Spark-Submit</span><span class="sxs-lookup"><span data-stu-id="5fb89-141">Use spark-submit</span></span>

<span data-ttu-id="5fb89-142">Mit dem Befehl " [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) " können Sie .net für Apache Spark Aufträge an Amazon EMR Spark übermitteln.</span><span class="sxs-lookup"><span data-stu-id="5fb89-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="5fb89-143">`ssh`in einen der Knoten im Cluster.</span><span class="sxs-lookup"><span data-stu-id="5fb89-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="5fb89-144">Führen Sie aus `spark-submit`.</span><span class="sxs-lookup"><span data-stu-id="5fb89-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="5fb89-145">Verwenden von Amazon EMR-Schritten</span><span class="sxs-lookup"><span data-stu-id="5fb89-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="5fb89-146">Mithilfe von [Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) können Aufträge an das Spark-Framework übermittelt werden, das auf dem EMR-Cluster installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5fb89-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="5fb89-147">Führen Sie den folgenden Befehl unter Linux mithilfe der AWS CLI aus.</span><span class="sxs-lookup"><span data-stu-id="5fb89-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="5fb89-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5fb89-148">Next steps</span></span>

<span data-ttu-id="5fb89-149">In diesem Tutorial haben Sie Ihre .net for Apache Spark-Anwendung in Amazon EMR Spark bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5fb89-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="5fb89-150">Weitere Informationen zu Apache Spark Beispielprojekten für .net finden Sie unter GitHub.</span><span class="sxs-lookup"><span data-stu-id="5fb89-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5fb89-151">.Net für Apache Spark-Beispiele</span><span class="sxs-lookup"><span data-stu-id="5fb89-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
