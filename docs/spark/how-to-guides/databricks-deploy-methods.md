---
title: Senden eines .NET für Apache Spark-Auftrags an Databricks
description: Erfahren Sie, wie Sie mit spark-submit und Set JAR einen .NET für Apache Spark-Auftrag an Databricks übermitteln.
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 4d37383ccb3c9b311e0fbd0ada195ac20113e505
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688201"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a><span data-ttu-id="44a39-103">Übermitteln eines .NET für Apache Spark-Auftrags an Databricks</span><span class="sxs-lookup"><span data-stu-id="44a39-103">Submit a .NET for Apache Spark job to Databricks</span></span>

<span data-ttu-id="44a39-104">Sie können .NET für Apache Spark-Aufträge in Databricks-Clustern ausführen, jedoch ist dies nicht sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44a39-104">You can run your .NET for Apache Spark jobs on Databricks clusters, but it is not available out-of-the-box.</span></span> <span data-ttu-id="44a39-105">Es gibt zwei Möglichkeiten, einen .NET für Apache Spark-Auftrag für Databricks bereitzustellen: `spark-submit` und Set JAR.</span><span class="sxs-lookup"><span data-stu-id="44a39-105">There are two ways to deploy your .NET for Apache Spark job to Databricks: `spark-submit` and Set Jar.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="44a39-106">Bereitstellen mit spark-submit</span><span class="sxs-lookup"><span data-stu-id="44a39-106">Deploy using spark-submit</span></span>

<span data-ttu-id="44a39-107">Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Databricks übermitteln.</span><span class="sxs-lookup"><span data-stu-id="44a39-107">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="44a39-108">`spark-submit` ermöglicht die Übermittlung nur an einen Cluster, der bedarfsgesteuert erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="44a39-108">`spark-submit` allows submission only to a cluster that gets created on-demand.</span></span>

1. <span data-ttu-id="44a39-109">Wechseln Sie zu Ihrem Databricks-Arbeitsbereich, und erstellen Sie einen Auftrag.</span><span class="sxs-lookup"><span data-stu-id="44a39-109">Navigate to your Databricks Workspace and create a job.</span></span> <span data-ttu-id="44a39-110">Wählen Sie einen Titel für Ihren Auftrag aus, und wählen Sie dann **spark-submit konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="44a39-110">Choose a title for your job, and then select **Configure spark-submit**.</span></span> <span data-ttu-id="44a39-111">Fügen Sie die folgenden Parameter in die Auftragskonfiguration ein, und wählen Sie dann **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="44a39-111">Paste the following parameters in the job configuration, then select **Confirm**.</span></span>

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > <span data-ttu-id="44a39-112">Aktualisieren Sie den Inhalt des obigen Parameters basierend auf Ihren spezifischen Dateien und Ihrer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="44a39-112">Update the contents of the above parameter based on your specific files and configuration.</span></span> <span data-ttu-id="44a39-113">Verweisen Sie beispielsweise auf die Version der JAR-Datei „Microsoft.Spark“, die Sie in Databricks File System (DBFS) hochgeladen haben, und verwenden Sie den entsprechenden Namen Ihrer App und der ZIP-Datei der veröffentlichten App.</span><span class="sxs-lookup"><span data-stu-id="44a39-113">For instance, reference the version of the Microsoft.Spark jar file that you uploaded to DBFS, and use the appropriate name of your app and published app zip file.</span></span>

2. <span data-ttu-id="44a39-114">Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Bearbeiten** aus, um den Cluster Ihres Auftrags zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44a39-114">Navigate to your job and select **Edit** to configure your job's cluster.</span></span> <span data-ttu-id="44a39-115">Legen Sie die Databricks Runtime-Version basierend auf der Version von Apache Spark fest, die Sie in Ihrer Bereitstellung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="44a39-115">Set the Databricks Runtime Version based on the version of Apache Spark you wish to use in your deployment.</span></span> <span data-ttu-id="44a39-116">Wählen Sie dann **Advanced Options > Init Scripts** (Erweiterte Optionen > Initialisierungsskripts) aus, und legen Sie den Pfad des Initialisierungsskripts auf `dbfs:/spark-dotnet/db-init.sh` fest.</span><span class="sxs-lookup"><span data-stu-id="44a39-116">Then select **Advanced Options > Init Scripts**, and set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span> <span data-ttu-id="44a39-117">Wählen Sie **Bestätigen** aus, um die Clustereinstellungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="44a39-117">Select **Confirm** to confirm your cluster settings.</span></span>

3. <span data-ttu-id="44a39-118">Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Jetzt ausführen** aus, um den Auftrag auf dem neu konfigurierten Spark-Cluster auszuführen.</span><span class="sxs-lookup"><span data-stu-id="44a39-118">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span> <span data-ttu-id="44a39-119">Es dauert einige Minuten, bis der Cluster des Auftrags erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="44a39-119">It takes a few minutes for the job's cluster to be created.</span></span> <span data-ttu-id="44a39-120">Nach seiner Erstellung wird Ihr Auftrag übermittelt.</span><span class="sxs-lookup"><span data-stu-id="44a39-120">Once it is created, your job will be submitted.</span></span> <span data-ttu-id="44a39-121">Sie können die Ausgabe anzeigen, indem Sie im linken Menü Ihres Databricks-Arbeitsbereichs **Clusters** (Cluster) und dann **Driver Logs** (Treiberprotokolle) auswählen.</span><span class="sxs-lookup"><span data-stu-id="44a39-121">You can view the output by selecting **Clusters** from the left menu of your Databricks workspace, then select **Driver Logs**.</span></span>

## <a name="deploy-using-set-jar"></a><span data-ttu-id="44a39-122">Bereitstellen mithilfe von Set JAR</span><span class="sxs-lookup"><span data-stu-id="44a39-122">Deploy using Set Jar</span></span>

<span data-ttu-id="44a39-123">Alternativ können Sie in Ihrem Databricks-Arbeitsbereich [Set JAR](/azure/databricks/jobs#--create-a-job) verwenden, um .NET für Apache Spark-Aufträge an Databricks zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="44a39-123">Alternatively, you can use [Set Jar](/azure/databricks/jobs#--create-a-job) in your Databricks workspace to submit .NET for Apache Spark jobs to Databricks.</span></span> <span data-ttu-id="44a39-124">*Set JAR* ermöglicht das Übermitteln eines Auftrags an einen vorhandenen aktiven Cluster.</span><span class="sxs-lookup"><span data-stu-id="44a39-124">*Set Jar* allows job submission to an existing active cluster.</span></span>

### <a name="one-time-setup"></a><span data-ttu-id="44a39-125">Einmalige Konfiguration</span><span class="sxs-lookup"><span data-stu-id="44a39-125">One-time setup</span></span>

1. <span data-ttu-id="44a39-126">Wechseln Sie zu Ihrem Databricks-Cluster, und klicken Sie im Menü auf der linken Seite erst auf **Jobs** (Aufträge) und dann auf **Set JAR**.</span><span class="sxs-lookup"><span data-stu-id="44a39-126">Navigate to your Databricks cluster and select **Jobs** from the left-side menu, followed by **Set JAR**.</span></span>

2. <span data-ttu-id="44a39-127">Laden Sie die entsprechende Datei `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` hoch.</span><span class="sxs-lookup"><span data-stu-id="44a39-127">Upload the appropriate `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar`.</span></span>

3. <span data-ttu-id="44a39-128">Ändern Sie die folgenden Parameter so, dass sie den richtigen Namen für die ausführbare Datei enthalten, die Sie anstelle von `<your-app-name>` veröffentlicht haben:</span><span class="sxs-lookup"><span data-stu-id="44a39-128">Modify the following parameters to include the correct name for the executable that you published in place of `<your-app-name>`:</span></span>

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. <span data-ttu-id="44a39-129">Konfigurieren Sie den Cluster so, dass er auf einen bestehenden Cluster zeigt, für den Sie das Initialisierungsskript bereits festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="44a39-129">Configure the cluster to point to an existing cluster for which you have already set the init script.</span></span>

### <a name="publish-and-run-your-app"></a><span data-ttu-id="44a39-130">Veröffentlichen und Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="44a39-130">Publish and run your app</span></span>

1. <span data-ttu-id="44a39-131">Vergewissern Sie sich, dass Sie Ihre App veröffentlicht haben und Ihr Anwendungscode nicht `SparkSession.Stop()` verwendet.</span><span class="sxs-lookup"><span data-stu-id="44a39-131">Ensure you have published your app, and that your application code does not use `SparkSession.Stop()`.</span></span>

2. <span data-ttu-id="44a39-132">Verwenden Sie die [Databricks CLI](/azure/databricks/dev-tools/databricks-cli), um Ihre Anwendung in Ihren Databricks-Cluster hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="44a39-132">Use [Databricks CLI](/azure/databricks/dev-tools/databricks-cli) to upload your application to your Databricks cluster.</span></span> <span data-ttu-id="44a39-133">Mit dem folgenden Befehl können Sie beispielsweise Ihre veröffentlichte Anwendung in Ihren Cluster hochladen:</span><span class="sxs-lookup"><span data-stu-id="44a39-133">For example, use the following command to upload your published app to your cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. <span data-ttu-id="44a39-134">Wenn es in Ihrer App benutzerdefinierte Funktionen gibt, müssen die App-Assemblys, wie z.B. DLLs, die benutzerdefinierte Funktionen und deren Abhängigkeiten enthalten, in das Arbeitsverzeichnis der einzelnen *Microsoft.Spark.Worker*-Elemente verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="44a39-134">If you have any user-defined functions in your app, the app assemblies, such as DLLs that contain user-defined functions along with their dependencies, need to be placed in the working directory of each *Microsoft.Spark.Worker*.</span></span>

    <span data-ttu-id="44a39-135">Laden Sie Ihre Anwendungsassemblys in Ihren Databricks-Cluster hoch:</span><span class="sxs-lookup"><span data-stu-id="44a39-135">Upload your application assemblies to your Databricks cluster:</span></span>

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    <span data-ttu-id="44a39-136">Heben Sie die Auskommentierung auf, und ändern Sie den Abschnitt mit den App-Abhängigkeiten in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), um auf den Pfad Ihrer App-Abhängigkeiten zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="44a39-136">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path.</span></span> <span data-ttu-id="44a39-137">Laden Sie dann die aktualisierte Datei *db-init.sh* in Ihren Cluster hoch:</span><span class="sxs-lookup"><span data-stu-id="44a39-137">Then, upload the updated *db-init.sh* to your cluster:</span></span>

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. <span data-ttu-id="44a39-138">Navigieren Sie zu **Databricks cluster > Jobs > [Job-name] > Run Now** (Databricks-Cluster > Aufträge > [Name des Auftrags]), um Ihren Auftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="44a39-138">Navigate to **Databricks cluster > Jobs > [Job-name] > Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44a39-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="44a39-139">Next steps</span></span>

* [<span data-ttu-id="44a39-140">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="44a39-140">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="44a39-141">Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks</span><span class="sxs-lookup"><span data-stu-id="44a39-141">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="44a39-142">Dokumentation zu Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="44a39-142">Azure Databricks Documentation</span></span>](/azure/azure-databricks/)
