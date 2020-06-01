---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in HDInsight bereitstellen.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: edb876921030f5034d03c821051457ca111855f8
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144759"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="8ae0e-103">Tutorial: Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8ae0e-103">Tutorial: Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="8ae0e-104">In diesem Tutorial erfahren Sie, wie Sie Ihre .NET-App für Apache Spark über einen Azure HDInsight-Cluster in der Cloud bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-104">This tutorial teaches you how to deploy your .NET for Apache Spark app to the cloud through an Azure HDInsight cluster.</span></span> <span data-ttu-id="8ae0e-105">HDInsight erleichtert das Erstellen und Konfigurieren eines Spark-Clusters in Azure, da Spark-Cluster in HDInsight mit Azure Storage und Azure Data Lake Storage kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-105">HDInsight makes it easier to create and configure a Spark cluster in Azure since Spark clusters in HDInsight are compatible with Azure Storage and Azure Data Lake Storage.</span></span>

<span data-ttu-id="8ae0e-106">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-106">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="8ae0e-107">Zugreifen über Azure Storage-Explorer auf Ihre Speicherkonten.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-107">Access your storage accounts using Azure Storage Explorer.</span></span>
> * <span data-ttu-id="8ae0e-108">Erstellen eines Azure HDInsight-Clusters.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-108">Create an Azure HDInsight cluster.</span></span>
> * <span data-ttu-id="8ae0e-109">Veröffentlichen der .NET-App für Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-109">Publish your .NET for Apache Spark app.</span></span>
> * <span data-ttu-id="8ae0e-110">Erstellen und Ausführen einer HDInsight-Skriptaktion.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-110">Create and run an HDInsight script action.</span></span>
> * <span data-ttu-id="8ae0e-111">Ausführen einer .NET-App für Apache Spark in einem HDInsight-Cluster.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-111">Run a .NET for Apache Spark app on an HDInsight cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ae0e-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8ae0e-112">Prerequisites</span></span>

<span data-ttu-id="8ae0e-113">Führen Sie die folgenden Schritte aus, bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-113">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="8ae0e-114">Wenn Sie kein Azure-Abonnement besitzen, können Sie ein [kostenloses Konto](https://azure.microsoft.com/free/dotnet/) erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-114">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/dotnet/).</span></span>
* <span data-ttu-id="8ae0e-115">Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) an.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-115">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="8ae0e-116">Installieren Sie Azure Storage-Explorer auf Ihrem [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409)-, [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)- oder [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409)-Computer.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-116">Install Azure Storage Explorer on your [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409), [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409), or [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409) computer.</span></span>
* <span data-ttu-id="8ae0e-117">Vervollständigen Sie das Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="8ae0e-117">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="access-your-storage-accounts"></a><span data-ttu-id="8ae0e-118">Zugreifen auf Ihre Speicherkonten</span><span class="sxs-lookup"><span data-stu-id="8ae0e-118">Access your storage accounts</span></span>

1. <span data-ttu-id="8ae0e-119">Öffnen Sie den Azure Storage-Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-119">Open Azure Storage Explorer.</span></span>

2. <span data-ttu-id="8ae0e-120">Wählen Sie im linken Menü **Konto hinzufügen** aus, und melden Sie sich bei Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-120">Select **Add Account** on the left menu, and sign in to your Azure account.</span></span>

    ![Anmelden bei einem Azure-Konto über Storage-Explorer](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   <span data-ttu-id="8ae0e-122">Nachdem Sie sich angemeldet haben, sollten alle Speicherkonten in Ihrem Besitz und alle Ressourcen angezeigt werden, die Sie in Ihre Speicherkonten hochgeladen haben.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-122">After you sign in, you should see all storage accounts you have and any resources you have uploaded to your storage accounts.</span></span>

## <a name="create-an-hdinsight-cluster"></a><span data-ttu-id="8ae0e-123">Erstellen eines HDInsight-Clusters</span><span class="sxs-lookup"><span data-stu-id="8ae0e-123">Create an HDInsight cluster</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ae0e-124">Die Abrechnung für die HDInsight-Cluster erfolgt anteilsmäßig auf Minutenbasis und ist unabhängig von ihrer Verwendung.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-124">Billing for HDInsight clusters is prorated per minute, even if you're not using them.</span></span> <span data-ttu-id="8ae0e-125">Daher sollten Sie Ihren Cluster nach der Verwendung unbedingt wieder löschen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-125">Be sure to delete your cluster after you have finished using it.</span></span> <span data-ttu-id="8ae0e-126">Weitere Informationen finden Sie im Abschnitt [Bereinigen von Ressourcen](#clean-up-resources) in diesem Tutorial.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-126">For more information, see the [Clean up resources](#clean-up-resources) section of this tutorial.</span></span>

1. <span data-ttu-id="8ae0e-127">Besuchen Sie das [Azure-Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8ae0e-127">Visit the [Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="8ae0e-128">Wählen Sie **+ Ressource erstellen**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-128">Select **+ Create a resource**.</span></span> <span data-ttu-id="8ae0e-129">Wählen Sie dann **HDInsight** aus der Kategorie **Analyse** aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-129">Then, select **HDInsight** from the **Analytics** category.</span></span>

    ![Erstellen einer HDInsight-Ressource über das Azure-Portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. <span data-ttu-id="8ae0e-131">Geben Sie unter **Grundlagen** die folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-131">Under **Basics**, provide the following values:</span></span>

    |<span data-ttu-id="8ae0e-132">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8ae0e-132">Property</span></span>  |<span data-ttu-id="8ae0e-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ae0e-133">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8ae0e-134">Abonnement</span><span class="sxs-lookup"><span data-stu-id="8ae0e-134">Subscription</span></span>  | <span data-ttu-id="8ae0e-135">Wählen Sie in der Dropdownliste eines Ihrer aktiven Azure-Abonnements aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-135">From the drop-down, choose one of your active Azure subscriptions.</span></span> |
    |<span data-ttu-id="8ae0e-136">Resource group</span><span class="sxs-lookup"><span data-stu-id="8ae0e-136">Resource group</span></span> | <span data-ttu-id="8ae0e-137">Geben Sie an, ob Sie eine neue Ressourcengruppe erstellen oder eine vorhandene Ressourcengruppe verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-137">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="8ae0e-138">Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-138">A resource group is a container that holds related resources for an Azure solution.</span></span> |
    |<span data-ttu-id="8ae0e-139">Clustername</span><span class="sxs-lookup"><span data-stu-id="8ae0e-139">Cluster name</span></span> | <span data-ttu-id="8ae0e-140">Geben Sie einen Namen für den HDInsight Spark-Cluster an.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-140">Give a name to your HDInsight Spark cluster.</span></span>|
    |<span data-ttu-id="8ae0e-141">Speicherort</span><span class="sxs-lookup"><span data-stu-id="8ae0e-141">Location</span></span>   | <span data-ttu-id="8ae0e-142">Wählen Sie einen Speicherort für die Ressourcengruppe aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-142">Select a location for the resource group.</span></span> <span data-ttu-id="8ae0e-143">Die Vorlage verwendet diesen Standort sowohl für die Erstellung des Clusters als auch für den Standardclusterspeicher.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-143">The template uses this location for creating the cluster as well as for the default cluster storage.</span></span> |
    |<span data-ttu-id="8ae0e-144">Clustertyp</span><span class="sxs-lookup"><span data-stu-id="8ae0e-144">Cluster type</span></span>| <span data-ttu-id="8ae0e-145">Wählen Sie als Clustertyp **Spark** aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-145">Select **Spark** as the cluster type.</span></span>|
    |<span data-ttu-id="8ae0e-146">Clusterversion</span><span class="sxs-lookup"><span data-stu-id="8ae0e-146">Cluster version</span></span>|<span data-ttu-id="8ae0e-147">Nach der Auswahl des Clustertyps wird dieses Feld automatisch mit der Standardversion aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-147">This field will autopopulate with the default version once the cluster type has been selected.</span></span> <span data-ttu-id="8ae0e-148">Wählen Sie eine Version 2.3 oder 2.4 von Spark aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-148">Select a 2.3 or 2.4 version of Spark.</span></span>|
    |<span data-ttu-id="8ae0e-149">Benutzername für Clusteranmeldung</span><span class="sxs-lookup"><span data-stu-id="8ae0e-149">Cluster login username</span></span>| <span data-ttu-id="8ae0e-150">Geben Sie den Anmeldebenutzernamen für den Cluster ein.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-150">Enter the cluster login username.</span></span>  <span data-ttu-id="8ae0e-151">Der Standardname lautet *admin*.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-151">The default name is *admin*.</span></span> |
    |<span data-ttu-id="8ae0e-152">Kennwort für Clusteranmeldung</span><span class="sxs-lookup"><span data-stu-id="8ae0e-152">Cluster login password</span></span>| <span data-ttu-id="8ae0e-153">Geben Sie das Kennwort für die Anmeldung ein.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-153">Enter any login password.</span></span> |
    |<span data-ttu-id="8ae0e-154">SSH-Benutzername (Secure Shell)</span><span class="sxs-lookup"><span data-stu-id="8ae0e-154">Secure Shell (SSH) username</span></span>| <span data-ttu-id="8ae0e-155">Geben Sie den SSH-Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-155">Enter the SSH username.</span></span> <span data-ttu-id="8ae0e-156">Standardmäßig gilt für dieses Konto dasselbe Kennwort wie für das Konto mit dem *Benutzernamen für die Clusteranmeldung*.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-156">By default, this account shares the same password as the *Cluster Login username* account.</span></span> |

4. <span data-ttu-id="8ae0e-157">Klicken Sie auf **Weiter: Speicher >>** , um zur Seite **Speicher** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-157">Select **Next: Storage >>** to continue to the **Storage** page.</span></span> <span data-ttu-id="8ae0e-158">Geben Sie unter **Speicher** die folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-158">Under **Storage**, provide the following values:</span></span>

    |<span data-ttu-id="8ae0e-159">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8ae0e-159">Property</span></span>  |<span data-ttu-id="8ae0e-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ae0e-160">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="8ae0e-161">Primärer Speichertyp</span><span class="sxs-lookup"><span data-stu-id="8ae0e-161">Primary storage type</span></span>|<span data-ttu-id="8ae0e-162">Übernehmen Sie den Standardwert **Azure Storage**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-162">Use the default value **Azure Storage**.</span></span>|
    |<span data-ttu-id="8ae0e-163">Auswahlmethode</span><span class="sxs-lookup"><span data-stu-id="8ae0e-163">Selection method</span></span>|<span data-ttu-id="8ae0e-164">Übernehmen Sie den Standardwert **Aus Liste auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-164">Use the default value **Select from list**.</span></span>|
    |<span data-ttu-id="8ae0e-165">Primäres Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="8ae0e-165">Primary storage account</span></span>|<span data-ttu-id="8ae0e-166">Wählen Sie Ihr Abonnement und eines Ihrer aktiven Speicherkonten in diesem Abonnement aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-166">Choose your subscription and one of your active storage accounts within that subscription.</span></span>|
    |<span data-ttu-id="8ae0e-167">Container</span><span class="sxs-lookup"><span data-stu-id="8ae0e-167">Container</span></span>|<span data-ttu-id="8ae0e-168">Dieser Container ist der spezifische Blobcontainer in Ihrem Speicherkonto, in dem Ihr Cluster nach Dateien sucht, um Ihre App in der Cloud auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-168">This container is the specific blob container in your storage account where your cluster looks for files to run your app in the cloud.</span></span> <span data-ttu-id="8ae0e-169">Sie können ihm einen beliebigen verfügbaren Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-169">You can give it any available name.</span></span>|

5. <span data-ttu-id="8ae0e-170">Wählen Sie unter **Überprüfen + erstellen** die Option **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-170">Under **Review + create**, select **Create**.</span></span> <span data-ttu-id="8ae0e-171">Das Erstellen des Clusters dauert ca. 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-171">It takes about 20 minutes to create the cluster.</span></span> <span data-ttu-id="8ae0e-172">Der Cluster muss erstellt werden, bevor Sie mit dem nächsten Schritt fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-172">The cluster must be created before you can continue to the next step.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="8ae0e-173">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="8ae0e-173">Publish your app</span></span>

<span data-ttu-id="8ae0e-174">Anschließend veröffentlichen Sie die *mySparkApp*, die im Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) erstellt wurde, die Ihrem Spark-Cluster Zugriff auf alle Dateien ermöglicht, die er zum Ausführen Ihrer App benötigt.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-174">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial, which gives your Spark cluster access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="8ae0e-175">Führen Sie zum Veröffentlichen der *mySparkApp* die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-175">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="8ae0e-176">**Unter Windows:**</span><span class="sxs-lookup"><span data-stu-id="8ae0e-176">**On Windows:**</span></span>

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   <span data-ttu-id="8ae0e-177">**Unter Linux:**</span><span class="sxs-lookup"><span data-stu-id="8ae0e-177">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="8ae0e-178">Führen Sie die folgenden Aufgaben aus, um die veröffentlichten App-Dateien zu komprimieren, damit Sie sie problemlos in ihren HDInsight-Cluster hochladen können.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-178">Do the following tasks to zip your published app files so that you can easily upload them to your HDInsight cluster.</span></span>

   <span data-ttu-id="8ae0e-179">**Unter Windows:**</span><span class="sxs-lookup"><span data-stu-id="8ae0e-179">**On Windows:**</span></span>

   <span data-ttu-id="8ae0e-180">Navigieren Sie zu *MySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-180">Navigate to *mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*.</span></span> <span data-ttu-id="8ae0e-181">Klicken Sie dann mit der rechten Maustaste auf den Ordner **Veröffentlichen**, und wählen Sie **Senden an > Komprimierter Ordner (ZIP-Ordner)** aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-181">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="8ae0e-182">Nennen Sie den neuen Ordner **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-182">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="8ae0e-183">**Führen Sie unter Linux den folgenden Befehl aus:**</span><span class="sxs-lookup"><span data-stu-id="8ae0e-183">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a><span data-ttu-id="8ae0e-184">Hochladen von Dateien in Azure</span><span class="sxs-lookup"><span data-stu-id="8ae0e-184">Upload files to Azure</span></span>

<span data-ttu-id="8ae0e-185">Im nächsten Schritt verwenden Sie Azure Storage-Explorer, um die folgenden fünf Dateien in den Blobcontainer hochzuladen, den Sie als Speicher für Ihren Cluster ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-185">Next, you use the Azure Storage Explorer to upload the following five files to the blob container you chose for your cluster's storage:</span></span>

* <span data-ttu-id="8ae0e-186">Microsoft.Spark.Worker</span><span class="sxs-lookup"><span data-stu-id="8ae0e-186">Microsoft.Spark.Worker</span></span>
* <span data-ttu-id="8ae0e-187">install-worker.sh</span><span class="sxs-lookup"><span data-stu-id="8ae0e-187">install-worker.sh</span></span>
* <span data-ttu-id="8ae0e-188">publish.zip</span><span class="sxs-lookup"><span data-stu-id="8ae0e-188">publish.zip</span></span>
* <span data-ttu-id="8ae0e-189">microsoft-spark-2.3.x-0.3.0.jar</span><span class="sxs-lookup"><span data-stu-id="8ae0e-189">microsoft-spark-2.3.x-0.3.0.jar</span></span>
* <span data-ttu-id="8ae0e-190">input.txt.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-190">input.txt.</span></span>

1. <span data-ttu-id="8ae0e-191">Öffnen Sie Azure Storage-Explorer, und navigieren Sie im Menü auf der linken Seite zu Ihrem Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-191">Open Azure Storage Explorer and navigate to your storage account from the left menu.</span></span> <span data-ttu-id="8ae0e-192">Führen Sie einen Drilldown zum Blobcontainer für Ihren Cluster unter **Blobcontainer** in Ihrem Speicherkonto aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-192">Drill down to the blob container for your cluster under **Blob Containers** in your storage account.</span></span>

2. <span data-ttu-id="8ae0e-193">*Microsoft.Spark.Worker* unterstützt Apache Spark bei der Ausführung Ihrer App, z.B. für benutzerdefinierte Funktionen (User-Defined Functions, UDFs), die Sie ggf. geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-193">*Microsoft.Spark.Worker* helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="8ae0e-194">Laden Sie [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz) herunter.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-194">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz).</span></span> <span data-ttu-id="8ae0e-195">Wählen Sie dann in Azure Storage-Explorer **Hochladen** aus, um den Worker hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-195">Then, select **Upload** in Azure Storage Explorer to upload the worker.</span></span>

   ![Hochladen von Dateien in Azure Storage-Explorer](./media/hdinsight-deployment/upload-files-to-storage.png)

3. <span data-ttu-id="8ae0e-197">*install-worker.sh* ist ein Skript, mit dem Sie von .NET für Apache Spark abhängige Dateien in die Knoten Ihres Clusters kopieren können.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-197">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="8ae0e-198">Erstellen Sie eine neue Datei mit dem Namen **install-worker.sh** auf Ihrem lokalen Computer, und fügen Sie den [Inhalt von install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) auf GitHub ein.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-198">Create a new file named **install-worker.sh** your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span> <span data-ttu-id="8ae0e-199">Laden Sie dann *install-worker.sh* in Ihren Blobcontainer hoch.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-199">Then, upload *install-worker.sh* to your blob container.</span></span>

4. <span data-ttu-id="8ae0e-200">Ihr Cluster benötigt die Datei „publish.zip“, die die veröffentlichten Dateien Ihrer App enthält.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-200">Your cluster needs the publish.zip file that contains your app's published files.</span></span> <span data-ttu-id="8ae0e-201">Navigieren Sie zu Ihrem veröffentlichten Ordner **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, und suchen Sie nach **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-201">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **publish.zip**.</span></span> <span data-ttu-id="8ae0e-202">Laden Sie dann *publish.zip* in Ihren Blobcontainer hoch.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-202">Then upload *publish.zip* to your blob container.</span></span>

5. <span data-ttu-id="8ae0e-203">Ihr Cluster benötigt den Anwendungscode, der in einer JAR-Datei gepackt wurde.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-203">Your cluster needs the application code that was packaged into a jar file.</span></span> <span data-ttu-id="8ae0e-204">Navigieren Sie zu Ihrem veröffentlichten Ordner **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, und suchen Sie nach **microsoft-spark-2.3.x-0.3.0.jar**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-204">Navigate to your published folder, **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, and locate **microsoft-spark-2.3.x-0.3.0.jar**.</span></span> <span data-ttu-id="8ae0e-205">Laden Sie die JAR-Datei dann in Ihren Blobcontainer hoch.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-205">Then, upload the jar file to your blob container.</span></span>

   <span data-ttu-id="8ae0e-206">Möglicherweise gibt es mehrere JAR-Dateien (für die Versionen 2.3.x und 2.4.x von Spark).</span><span class="sxs-lookup"><span data-stu-id="8ae0e-206">There may be multiple .jar files (for versions 2.3.x and 2.4.x of Spark).</span></span> <span data-ttu-id="8ae0e-207">Sie müssen die JAR-Datei auswählen, die mit der Version von Spark übereinstimmt, die Sie während der Clustererstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-207">You need to choose the .jar file that matches the version of Spark you chose during cluster creation.</span></span> <span data-ttu-id="8ae0e-208">Wählen Sie beispielsweise *microsoft-spark-2.3.x-0.3.0.jar* aus, wenn Sie Spark 2.3.2 während der Clustererstellung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-208">For example, choose *microsoft-spark-2.3.x-0.3.0.jar* if you chose Spark 2.3.2 during cluster creation.</span></span>

6. <span data-ttu-id="8ae0e-209">Ihr Cluster benötigt die Eingabe in Ihre App.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-209">Your cluster needs the input to your app.</span></span> <span data-ttu-id="8ae0e-210">Navigieren Sie zu Ihrem Verzeichnis **mySparkApp**, und suchen Sie nach **input.txt**.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-210">Navigate to your **mySparkApp** directory and locate **input.txt**.</span></span> <span data-ttu-id="8ae0e-211">Laden Sie die Eingabedatei in das Verzeichnis **user/sshuser** in Ihren Blobcontainer hoch.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-211">Upload your input file to the **user/sshuser** directory in your blob container.</span></span> <span data-ttu-id="8ae0e-212">Sie stellen über SSH eine Verbindung mit Ihrem Cluster her, und in diesem Ordner sucht der Cluster nach der Eingabe.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-212">You will be connecting to your cluster through ssh, and this folder is where your cluster looks for its input.</span></span> <span data-ttu-id="8ae0e-213">Die Datei *input.txt* ist die einzige Datei, die in ein bestimmtes Verzeichnis hochgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-213">The *input.txt* file is the only file uploaded to a specific directory.</span></span>

## <a name="run-the-hdinsight-script-action"></a><span data-ttu-id="8ae0e-214">Ausführen der HDInsight-Skriptaktion</span><span class="sxs-lookup"><span data-stu-id="8ae0e-214">Run the HDInsight script action</span></span>

<span data-ttu-id="8ae0e-215">Sobald der Cluster ausgeführt wird und Sie Ihre Dateien in Azure hochgeladen haben, führen Sie das Skript **install-worker.sh** auf dem Cluster aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-215">Once your cluster is running and you've uploaded your files to Azure, you run the **install-worker.sh** script on the cluster.</span></span>

1. <span data-ttu-id="8ae0e-216">Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **Skriptaktionen**aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-216">Navigate to your HDInsight Spark cluster in Azure portal, and then select **Script actions**.</span></span>

2. <span data-ttu-id="8ae0e-217">Wählen Sie **+ Neue übermitteln** aus, und geben Sie die folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="8ae0e-217">Select **+ Submit new** and provide the following values:</span></span>

   |<span data-ttu-id="8ae0e-218">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8ae0e-218">Property</span></span>  |<span data-ttu-id="8ae0e-219">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ae0e-219">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="8ae0e-220">Skripttyp</span><span class="sxs-lookup"><span data-stu-id="8ae0e-220">Script type</span></span> |<span data-ttu-id="8ae0e-221">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="8ae0e-221">Custom</span></span>|
   | <span data-ttu-id="8ae0e-222">name</span><span class="sxs-lookup"><span data-stu-id="8ae0e-222">Name</span></span> | <span data-ttu-id="8ae0e-223">Installieren des Workers</span><span class="sxs-lookup"><span data-stu-id="8ae0e-223">Install Worker</span></span>|
   | <span data-ttu-id="8ae0e-224">Bash-Skript-URI</span><span class="sxs-lookup"><span data-stu-id="8ae0e-224">Bash script URI</span></span> |`https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh` </br> <span data-ttu-id="8ae0e-225">Klicken Sie zum Bestätigen dieses URIs in Azure Storage-Explorer mit der rechten Maustaste auf „install-Worker.sh“, und wählen Sie „Eigenschaften“ aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-225">To confirm this URI, right-click on install-worker.sh in Azure Storage Explorer and select Properties.</span></span> |
   | <span data-ttu-id="8ae0e-226">Knotentyp(en)</span><span class="sxs-lookup"><span data-stu-id="8ae0e-226">Node type(s)</span></span>| <span data-ttu-id="8ae0e-227">Worker</span><span class="sxs-lookup"><span data-stu-id="8ae0e-227">Worker</span></span>|
   | <span data-ttu-id="8ae0e-228">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ae0e-228">Parameters</span></span> | <span data-ttu-id="8ae0e-229">azure</span><span class="sxs-lookup"><span data-stu-id="8ae0e-229">azure</span></span> </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> <span data-ttu-id="8ae0e-230">/usr/local/bin</span><span class="sxs-lookup"><span data-stu-id="8ae0e-230">/usr/local/bin</span></span>

3. <span data-ttu-id="8ae0e-231">Wählen Sie **Erstellen** aus, um das Skript zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-231">Select **Create** to submit your script.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="8ae0e-232">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="8ae0e-232">Run your app</span></span>

1. <span data-ttu-id="8ae0e-233">Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **SSH und Clusteranmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-233">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="8ae0e-234">Kopieren Sie die SSH-Anmeldeinformationen, und fügen Sie diese in ein Terminal ein.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-234">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="8ae0e-235">Melden Sie sich mit dem Kennwort, das Sie während der Clustererstellung festgelegt haben, bei Ihrem Cluster an.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-235">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="8ae0e-236">Es sollten Meldungen angezeigt werden, die Sie bei Ubuntu und Spark Willkommen heißen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-236">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="8ae0e-237">Verwenden Sie den Befehl **spark-submit**, um Ihre App auf dem HDInsight-Cluster auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-237">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="8ae0e-238">Denken Sie daran, **mycontainer** und **mystorageaccount** im Beispielskript durch die tatsächlichen Namen Ihres Blobcontainers und Speicherkontos zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-238">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   <span data-ttu-id="8ae0e-239">Wenn Ihre App ausgeführt wird, wird die gleiche Wortzahltabelle aus der lokalen Ausführung von „Erste Schritte“ in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-239">When your app runs, you see the same word count table from the getting started local run written to the console.</span></span> <span data-ttu-id="8ae0e-240">Herzlichen Glückwunsch, Sie haben Ihre erste .NET-Anwendung für Apache Spark in der Cloud ausgeführt!</span><span class="sxs-lookup"><span data-stu-id="8ae0e-240">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="8ae0e-241">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8ae0e-241">Clean up resources</span></span>

<span data-ttu-id="8ae0e-242">HDInsight speichert Ihre Daten in Azure Storage, sodass Sie einen Cluster problemlos löschen können, wenn er nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-242">HDInsight saves your data in Azure Storage, so you can safely delete a cluster when it is not in use.</span></span> <span data-ttu-id="8ae0e-243">Für einen HDInsight-Cluster fallen auch dann Gebühren an, wenn er nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-243">You are also charged for an HDInsight cluster, even when it is not in use.</span></span> <span data-ttu-id="8ae0e-244">Da die Gebühren für den Cluster erheblich höher sind als die Kosten für den Speicher, ist es sinnvoll, nicht verwendete Cluster zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-244">Since the charges for the cluster are many times more than the charges for storage, it makes economic sense to delete clusters when they are not in use.</span></span>

<span data-ttu-id="8ae0e-245">Sie können auch den Namen der Ressourcengruppe auswählen, um die Seite für die Ressourcengruppe zu öffnen, und dann **Ressourcengruppe löschen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-245">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span> <span data-ttu-id="8ae0e-246">Indem Sie die Ressourcengruppe löschen, löschen Sie sowohl den HDInsight Spark-Cluster als auch das Standardspeicherkonto.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-246">By deleting the resource group, you delete both the HDInsight Spark cluster, and the default storage account.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ae0e-247">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8ae0e-247">Next steps</span></span>

<span data-ttu-id="8ae0e-248">In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Azure HDInsight bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-248">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="8ae0e-249">Weitere Informationen finden Sie in der Dokumentation zu Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="8ae0e-249">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8ae0e-250">Azure HDInsight-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="8ae0e-250">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
