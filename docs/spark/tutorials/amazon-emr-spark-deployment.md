---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dd1cfdf12266b55d9dbc0210479b89ba68c59a38
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688071"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="b4ccf-103">Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="b4ccf-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="b4ccf-104">In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="b4ccf-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) ist eine verwaltete Clusterplattform, die die Ausführung von Big-Data-Frameworks in AWS vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-105">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

<span data-ttu-id="b4ccf-106">In diesem Tutorial erhalten Sie Informationen zu den folgenden Vorgängen:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="b4ccf-107">Vorbereiten von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="b4ccf-107">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="b4ccf-108">Veröffentlichen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b4ccf-108">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="b4ccf-109">Bereitstellen einer App in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="b4ccf-109">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="b4ccf-110">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="b4ccf-110">Run your app</span></span>

> [!Note]
> <span data-ttu-id="b4ccf-111">AWS EMR Spark basiert auf Linux.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-111">AWS EMR Spark is Linux-based.</span></span> <span data-ttu-id="b4ccf-112">Wenn Sie Ihre App in AWS EMR Spark bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den .NET Core-Compiler zum Kompilieren Ihrer App verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-112">Therefore, if you are interested in deploying your app to AWS EMR Spark, make sure your app is .NET Standard compatible and that you use .NET Core compiler to compile your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4ccf-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b4ccf-113">Prerequisites</span></span>

<span data-ttu-id="b4ccf-114">Führen Sie zunächst folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-114">Before you start, do the following:</span></span>

* <span data-ttu-id="b4ccf-115">Laden Sie die [AWS CLI](https://aws.amazon.com/cli/) herunter.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-115">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="b4ccf-116">Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-116">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="b4ccf-117">Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-117">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="b4ccf-118">Vorbereiten von Workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b4ccf-118">Prepare worker dependencies</span></span>

<span data-ttu-id="b4ccf-119">**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-119">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="b4ccf-120">Wenn Sie eine benutzerdefinierte C#-Funktion (User-defined Function, UDF) ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-120">When you want to execute a C# UDF (User-Defined Function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="b4ccf-121">**Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-121">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="b4ccf-122">Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-122">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="b4ccf-123">Wenn z. B. `netcoreapp3.1` für `.NET for Apache Spark v1.0.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz) herunter.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-123">For example, if you want `.NET for Apache Spark v1.0.0` using `netcoreapp3.1`, you'd download [Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz](https://github.com/dotnet/spark/releases/download/v1.0.0/Microsoft.Spark.Worker.netcoreapp3.1.linux-x64-1.0.0.tar.gz).</span></span>

2. <span data-ttu-id="b4ccf-124">Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise S3) hoch, auf das Ihr Cluster zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-124">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="b4ccf-125">Vorbereiten der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="b4ccf-125">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="b4ccf-126">Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-126">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="b4ccf-127">Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-127">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="b4ccf-128">Führen Sie unter Linux den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-128">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp3.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="b4ccf-129">Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-129">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="b4ccf-130">Führen Sie unter Linux den folgenden `zip`-Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-130">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="b4ccf-131">Laden Sie die folgenden Dateien auf ein verteiltes Dateisystem (beispielsweise S3) hoch, auf das Ihr Cluster zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-131">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="b4ccf-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-132">`microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="b4ccf-133">Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit benutzerdefinierten Funktionen oder Bibliotheken, von denen Ihre App abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-133">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="b4ccf-134">Bereitstellen einer App in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="b4ccf-134">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="b4ccf-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) ist eine verwaltete Clusterplattform, die die Ausführung von Big-Data-Frameworks in AWS vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-135">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="b4ccf-136">Amazon EMR Spark basiert auf Linux.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-136">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="b4ccf-137">Wenn Sie Ihre App in Amazon EMR Spark bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-137">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="b4ccf-138">Bereitstellen von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="b4ccf-138">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="b4ccf-139">Dieser Schritt ist nur bei der Erstellung des Clusters erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-139">This step is only required at cluster creation.</span></span>

<span data-ttu-id="b4ccf-140">Führen Sie mithilfe der [Bootstrapaktionen](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)`install-worker.sh` bei der Erstellung des Clusters aus.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-140">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="b4ccf-141">Führen Sie unter Linux den folgenden Befehl mit der AWS CLI aus:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-141">Run the following command on Linux using AWS CLI.</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="b4ccf-142">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="b4ccf-142">Run your app</span></span>

<span data-ttu-id="b4ccf-143">Sie können Ihre App in Amazon EMR Spark entweder mit „spark-submit“ oder mit Amazon EMR-Schritten ausführen.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-143">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="b4ccf-144">Verwenden von „spark-submit“</span><span class="sxs-lookup"><span data-stu-id="b4ccf-144">Use spark-submit</span></span>

<span data-ttu-id="b4ccf-145">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Amazon EMR Spark übermitteln.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-145">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="b4ccf-146">Stellen Sie mit `ssh` eine Verbindung mit einem Knoten Ihres Clusters her.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-146">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="b4ccf-147">Führen Sie `spark-submit` aus.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-147">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="b4ccf-148">Verwenden von Amazon EMR-Schritten</span><span class="sxs-lookup"><span data-stu-id="b4ccf-148">Use Amazon EMR Steps</span></span>

<span data-ttu-id="b4ccf-149">Mithilfe von [Amazon EMR-Schritten](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) können Sie Aufträge an das Spark-Framework übermitteln, das auf dem EMR-Cluster installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-149">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="b4ccf-150">Führen Sie unter Linux den folgenden Befehl mit der AWS CLI aus:</span><span class="sxs-lookup"><span data-stu-id="b4ccf-150">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="b4ccf-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b4ccf-151">Next steps</span></span>

<span data-ttu-id="b4ccf-152">In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-152">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="b4ccf-153">Beispielprojekte für .NET für Apache Spark finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="b4ccf-153">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4ccf-154">Beispiele für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b4ccf-154">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
