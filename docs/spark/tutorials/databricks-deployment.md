---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Databricks bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 77c2d93ae324b6acbf8fc8dc25cd3e4d1a652f48
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107351"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="94777-103">Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks</span><span class="sxs-lookup"><span data-stu-id="94777-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="94777-104">In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Databricks bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="94777-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="94777-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="94777-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="94777-106">Vorbereiten von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="94777-106">Prepare Microsoft.Spark.Worker</span></span>
> - <span data-ttu-id="94777-107">Veröffentlichen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="94777-107">Publish your Spark .NET app</span></span>
> - <span data-ttu-id="94777-108">Bereitstellen der App in Databricks</span><span class="sxs-lookup"><span data-stu-id="94777-108">Deploy your app to Databricks</span></span>
> - <span data-ttu-id="94777-109">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="94777-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94777-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="94777-110">Prerequisites</span></span>

<span data-ttu-id="94777-111">Führen Sie zunächst folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="94777-111">Before you start, do the following:</span></span>

- <span data-ttu-id="94777-112">Laden Sie die [Databricks-Befehlszeilenschnittstelle](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) herunter.</span><span class="sxs-lookup"><span data-stu-id="94777-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
- <span data-ttu-id="94777-113">Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="94777-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="94777-114">Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.</span><span class="sxs-lookup"><span data-stu-id="94777-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="94777-115">Vorbereiten von Workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="94777-115">Prepare worker dependencies</span></span>

<span data-ttu-id="94777-116">**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet.</span><span class="sxs-lookup"><span data-stu-id="94777-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="94777-117">Wenn Sie eine benutzerdefinierte C#-Funktion ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="94777-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="94777-118">**Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="94777-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="94777-119">Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="94777-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="94777-120">Wenn z. B. `netcoreapp2.1` für `.NET for Apache Spark v0.1.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) herunter.</span><span class="sxs-lookup"><span data-stu-id="94777-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="94777-121">Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise dBFS) hoch, auf das Ihr Cluster zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="94777-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="94777-122">Vorbereiten der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="94777-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="94777-123">Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="94777-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="94777-124">Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="94777-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="94777-125">Sie können unter Linux den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="94777-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="94777-126">Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.</span><span class="sxs-lookup"><span data-stu-id="94777-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="94777-127">Sie können unter Linux den folgenden `zip`-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="94777-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="94777-128">Laden Sie Folgendes auf ein verteiltes Dateisystem (beispielsweise dBFS) hoch, auf das Ihr Cluster zugreifen kann:</span><span class="sxs-lookup"><span data-stu-id="94777-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   - <span data-ttu-id="94777-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="94777-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   - `<your app>.zip`
   - <span data-ttu-id="94777-130">Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit benutzerdefinierten Funktionen oder Bibliotheken, von denen Ihre App abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="94777-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="94777-131">Bereitstellen in Databricks</span><span class="sxs-lookup"><span data-stu-id="94777-131">Deploy to Databricks</span></span>

<span data-ttu-id="94777-132">[Databricks](https://databricks.com) ist eine Plattform, die cloudbasierte Big Data-Verarbeitung mithilfe von Apache Spark ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="94777-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="94777-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) und [AWS Databricks](https://databricks.com/aws) sind Linux-basiert.</span><span class="sxs-lookup"><span data-stu-id="94777-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="94777-134">Wenn Sie Ihre App in Databricks bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.</span><span class="sxs-lookup"><span data-stu-id="94777-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="94777-135">Mit Databricks können Sie .NET für Apache Spark-Apps an einen vorhandenen aktiven Cluster übermitteln oder jedes Mal, wenn Sie einen Auftrag starten, einen neuen Cluster erstellen.</span><span class="sxs-lookup"><span data-stu-id="94777-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="94777-136">Hierfür muss **Microsoft.Spark.Worker** installiert sein, bevor Sie eine .NET für Apache Spark-App übermitteln.</span><span class="sxs-lookup"><span data-stu-id="94777-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="94777-137">Bereitstellen von Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="94777-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="94777-138">Der folgende Schritt ist nur einmal für einen Cluster erforderlich.</span><span class="sxs-lookup"><span data-stu-id="94777-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="94777-139">Laden Sie [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="94777-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="94777-140">Ändern Sie **db-init.sh**, um auf das **Microsoft.Spark.Worker**-Release zu verweisen, das Sie herunterladen und auf Ihrem Cluster installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="94777-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="94777-141">Installieren Sie die [Databricks-Befehlszeilenschnittstelle](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span><span class="sxs-lookup"><span data-stu-id="94777-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="94777-142">[Richten Sie Authentifizierungsdetails](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) für die Databricks-Befehlszeilenschnittstelle ein.</span><span class="sxs-lookup"><span data-stu-id="94777-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="94777-143">Laden Sie die Dateien mithilfe des folgenden Befehls in Ihren Databricks-Cluster hoch:</span><span class="sxs-lookup"><span data-stu-id="94777-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="94777-144">Greifen Sie auf Ihren Databricks-Arbeitsbereich zu.</span><span class="sxs-lookup"><span data-stu-id="94777-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="94777-145">Klicken Sie im Menü links auf **Cluster** und anschließend auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="94777-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="94777-146">Nachdem Sie den Cluster entsprechend konfiguriert haben, legen Sie das **Init-Skript** fest, und erstellen Sie den Cluster.</span><span class="sxs-lookup"><span data-stu-id="94777-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![Screenshot mit Skriptaktion](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="94777-148">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="94777-148">Run your app</span></span> 

<span data-ttu-id="94777-149">Sie können `set JAR` oder `spark-submit` verwenden, um Ihren Auftrag an Databricks zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="94777-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="94777-150">Verwenden von Set JAR</span><span class="sxs-lookup"><span data-stu-id="94777-150">Use Set JAR</span></span>

<span data-ttu-id="94777-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) ermöglicht das Übermitteln eines Auftrags an einen vorhandenen aktiven Cluster.</span><span class="sxs-lookup"><span data-stu-id="94777-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="94777-152">Einmalige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="94777-152">One-time setup</span></span>

1. <span data-ttu-id="94777-153">Wechseln Sie zu Ihrem Databricks-Cluster, und klicken Sie im Menü auf der linken Seite auf **Aufträge**.</span><span class="sxs-lookup"><span data-stu-id="94777-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="94777-154">Klicken Sie dann auf **Set JAR** (JAR festlegen).</span><span class="sxs-lookup"><span data-stu-id="94777-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="94777-155">Laden Sie die entsprechende Datei `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` hoch.</span><span class="sxs-lookup"><span data-stu-id="94777-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="94777-156">Legen Sie die entsprechenden Parameter fest.</span><span class="sxs-lookup"><span data-stu-id="94777-156">Set the parameters appropriately.</span></span>

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. <span data-ttu-id="94777-157">Konfigurieren Sie den **Cluster**, um auf den vorhandenen Cluster zu verweisen, für den Sie im vorherigen Abschnitt das **Init-Skript** erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="94777-157">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="94777-158">Veröffentlichen und Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="94777-158">Publish and run your app</span></span>

1. <span data-ttu-id="94777-159">Verwenden Sie die [Databricks-Befehlszeilenschnittstelle](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html), um Ihre Anwendung in Ihren Databricks-Cluster hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="94777-159">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="94777-160">Dieser Schritt ist nur erforderlich, wenn Ihre App-Assemblys (z. B. DLLs, die benutzerdefinierte Funktionen zusammen mit ihren Abhängigkeiten enthalten) im Arbeitsverzeichnis jeder **Microsoft.Spark.Worker**-Komponente abgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="94777-160">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="94777-161">Laden Sie Ihre Anwendungsassemblys in Ihren Databricks-Cluster hoch.</span><span class="sxs-lookup"><span data-stu-id="94777-161">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="94777-162">Heben Sie die Auskommentierung auf, und ändern Sie den Abschnitt „App-Abhängigkeiten“ zu [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), um auf den Pfad Ihrer App-Abhängigkeiten zu verweisen und in Ihren Databricks-Cluster hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="94777-162">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="94777-163">Starten Sie Ihren Cluster neu.</span><span class="sxs-lookup"><span data-stu-id="94777-163">Restart your cluster.</span></span>

3. <span data-ttu-id="94777-164">Navigieren Sie zu Ihrem Databricks-Cluster in Ihrem Databricks-Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="94777-164">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="94777-165">Klicken Sie unter **Aufträge** auf Ihren Auftrag und anschließend auf **Jetzt ausführen**, um Ihren Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="94777-165">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="94777-166">Verwenden von „spark-submit“</span><span class="sxs-lookup"><span data-stu-id="94777-166">Use spark-submit</span></span>

<span data-ttu-id="94777-167">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie einen Auftrag an einen neuen Cluster übermitteln.</span><span class="sxs-lookup"><span data-stu-id="94777-167">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="94777-168">[Erstellen Sie einen Auftrag](https://docs.databricks.com/user-guide/jobs.html), und klicken Sie auf **Configure spark-submit** (spark-submit konfigurieren).</span><span class="sxs-lookup"><span data-stu-id="94777-168">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="94777-169">Konfigurieren Sie `spark-submit` mit den folgenden Parametern:</span><span class="sxs-lookup"><span data-stu-id="94777-169">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="94777-170">Navigieren Sie zu Ihrem Databricks-Cluster in Ihrem Databricks-Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="94777-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="94777-171">Klicken Sie unter **Aufträge** auf Ihren Auftrag und anschließend auf **Jetzt ausführen**, um Ihren Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="94777-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94777-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="94777-172">Next steps</span></span>

<span data-ttu-id="94777-173">In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Databricks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="94777-173">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="94777-174">Weitere Informationen zu Databricks finden Sie in der Dokumentation zu Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="94777-174">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="94777-175">Dokumentation zu Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="94777-175">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
