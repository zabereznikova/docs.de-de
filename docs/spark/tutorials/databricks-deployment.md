---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Databricks bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c1c1a57fb2b79826218f8ed94d568b37d4689560
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454272"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="7dcb8-103">Tutorial: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks</span><span class="sxs-lookup"><span data-stu-id="7dcb8-103">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="7dcb8-104">In diesem Tutorial erfahren Sie, wie Sie Ihre App über Azure Databricks (eine auf Apache Spark basierende Analyseplattform, die Sie mit einem Mausklick einrichten können, die optimierte Workflows und einen interaktiven Arbeitsbereich bietet, der die Zusammenarbeit ermöglicht) in der Cloud bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-104">This tutorial teaches you how to deploy your app to the cloud through Azure Databricks, an Apache Spark-based analytics platform with one-click setup, streamlined workflows, and interactive workspace that enables collaboration.</span></span>

<span data-ttu-id="7dcb8-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7dcb8-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="7dcb8-106">Erstellen eines Azure Databricks-Arbeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="7dcb8-106">Create an Azure Databricks workspace.</span></span>
> - <span data-ttu-id="7dcb8-107">Veröffentlichen der .NET-App für Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-107">Publish your .NET for Apache Spark app.</span></span>
> - <span data-ttu-id="7dcb8-108">Erstellen eines Spark-Auftrags und eines Spark-Clusters.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-108">Create a Spark job and Spark cluster.</span></span>
> - <span data-ttu-id="7dcb8-109">Ausführen Ihrer App auf dem Spark-Cluster.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-109">Run your app on the Spark cluster.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7dcb8-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="7dcb8-110">Prerequisites</span></span>

<span data-ttu-id="7dcb8-111">Führen Sie die folgenden Schritte aus, bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="7dcb8-111">Before you start, do the following tasks:</span></span>

* <span data-ttu-id="7dcb8-112">Falls Sie noch kein Azure-Konto besitzen, erstellen Sie ein [kostenloses Konto](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-112">If you don't have an Azure account, create a [free account](https://azure.microsoft.com/free/).</span></span>
* <span data-ttu-id="7dcb8-113">Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) an.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-113">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
* <span data-ttu-id="7dcb8-114">Vervollständigen Sie das Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-114">Complete the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial.</span></span>

## <a name="create-an-azure-databricks-workspace"></a><span data-ttu-id="7dcb8-115">Erstellen eines Azure Databricks-Arbeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="7dcb8-115">Create an Azure Databricks workspace</span></span>

> [!Note]
> <span data-ttu-id="7dcb8-116">Dieses Tutorial kann nicht mit dem **kostenlosen Azure-Testabonnement** absolviert werden.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-116">This tutorial cannot be carried out using **Azure Free Trial Subscription**.</span></span>
> <span data-ttu-id="7dcb8-117">Wenn Sie ein kostenloses Konto haben, rufen Sie Ihr Profil auf, und ändern Sie Ihr Abonnement auf **Nutzungsbasierte Bezahlung**.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-117">If you have a free account, go to your profile and change your subscription to **pay-as-you-go**.</span></span> <span data-ttu-id="7dcb8-118">Weitere Informationen finden Sie unter [Kostenloses Azure-Konto](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-118">For more information, see [Azure free account](https://azure.microsoft.com/free/).</span></span> <span data-ttu-id="7dcb8-119">[Entfernen Sie das dann Ausgabenlimit](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), und [fordern Sie die Erhöhung des Kontingents](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) für vCPUs in Ihrer Region an.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-119">Then, [remove the spending limit](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), and [request a quota increase](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) for vCPUs in your region.</span></span> <span data-ttu-id="7dcb8-120">Wenn Sie Ihren Azure Databricks-Arbeitsbereich erstellen, können Sie den Tarif **Testversion (Premium – 14 Tage kostenlosen DBUs)** auswählen, damit Sie über den Arbeitsbereich 14 Tage lang auf kostenlose Premium Azure Databricks-DBUs zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-120">When you create your Azure Databricks workspace, you can select the **Trial (Premium - 14-Days Free DBUs)** pricing tier to give the workspace access to free Premium Azure Databricks DBUs for 14 days.</span></span>

<span data-ttu-id="7dcb8-121">In diesem Abschnitt erstellen Sie einen Azure Databricks-Arbeitsbereich über das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-121">In this section, you create an Azure Databricks workspace using the Azure portal.</span></span>

1. <span data-ttu-id="7dcb8-122">Klicken Sie im Azure-Portal auf **Ressource erstellen** > **Analysen** > **Azure Databricks**.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-122">In the Azure portal, select **Create a resource** > **Analytics** > **Azure Databricks**.</span></span>

   ![Erstellen einer Azure Databricks-Ressource im Azure-Portal](./media/databricks-deployment/create-databricks-resource.png)

2. <span data-ttu-id="7dcb8-124">Geben Sie unter **Azure Databricks-Dienst** die Werte für die Erstellung eines Databricks-Arbeitsbereichs an.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-124">Under **Azure Databricks Service**, provide the values to create a Databricks workspace.</span></span>

    |<span data-ttu-id="7dcb8-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7dcb8-125">Property</span></span>  |<span data-ttu-id="7dcb8-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7dcb8-126">Description</span></span>  |
    |---------|---------|
    |<span data-ttu-id="7dcb8-127">**Arbeitsbereichsname**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-127">**Workspace name**</span></span>     | <span data-ttu-id="7dcb8-128">Geben Sie einen Namen für Ihren Databricks-Arbeitsbereich an.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-128">Provide a name for your Databricks workspace.</span></span>        |
    |<span data-ttu-id="7dcb8-129">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-129">**Subscription**</span></span>     | <span data-ttu-id="7dcb8-130">Wählen Sie in der Dropdownliste Ihr Azure-Abonnement aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-130">From the drop-down, select your Azure subscription.</span></span>        |
    |<span data-ttu-id="7dcb8-131">**Ressourcengruppe**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-131">**Resource group**</span></span>     | <span data-ttu-id="7dcb8-132">Geben Sie an, ob Sie eine neue Ressourcengruppe erstellen oder eine vorhandene Ressourcengruppe verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-132">Specify whether you want to create a new resource group or use an existing one.</span></span> <span data-ttu-id="7dcb8-133">Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-133">A resource group is a container that holds related resources for an Azure solution.</span></span> <span data-ttu-id="7dcb8-134">Weitere Informationen finden Sie in der [Übersicht über den Azure Resource Manager](/azure/azure-databricks/azure-resource-manager/resource-group-overview).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-134">For more information, see [Azure Resource Group overview](/azure/azure-databricks/azure-resource-manager/resource-group-overview).</span></span> |
    |<span data-ttu-id="7dcb8-135">**Position**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-135">**Location**</span></span>     | <span data-ttu-id="7dcb8-136">Wählen Sie Ihre bevorzugte Region aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-136">Select your preferred region.</span></span> <span data-ttu-id="7dcb8-137">Informationen zu allen verfügbaren Regionen finden Sie unter [Verfügbare Azure-Dienste nach Region](https://azure.microsoft.com/regions/services/).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-137">For information about available regions, see [Azure services available by region](https://azure.microsoft.com/regions/services/).</span></span>        |
    |<span data-ttu-id="7dcb8-138">**Tarif**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-138">**Pricing Tier**</span></span>     |  <span data-ttu-id="7dcb8-139">Wählen Sie zwischen **Standard**, **Premium** oder **Testversion**.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-139">Choose between **Standard**, **Premium**, or **Trial**.</span></span> <span data-ttu-id="7dcb8-140">Weitere Informationen zu diesen Tarifen, finden Sie unter [Azure Databricks – Preise](https://azure.microsoft.com/pricing/details/databricks/).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-140">For more information on these tiers, see [Databricks pricing page](https://azure.microsoft.com/pricing/details/databricks/).</span></span>       |
    |<span data-ttu-id="7dcb8-141">**Virtual Network**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-141">**Virtual Network**</span></span>     |   <span data-ttu-id="7dcb8-142">Nein</span><span class="sxs-lookup"><span data-stu-id="7dcb8-142">No</span></span>       |

3. <span data-ttu-id="7dcb8-143">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-143">Select **Create**.</span></span> <span data-ttu-id="7dcb8-144">Die Erstellung des Arbeitsbereichs dauert einige Minuten.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-144">The workspace creation takes a few minutes.</span></span> <span data-ttu-id="7dcb8-145">Während der Erstellung des Arbeitsbereichs können Sie den Bereitstellungsstatus in **Benachrichtigungen** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-145">During workspace creation, you can view the deployment status in **Notifications**.</span></span>

## <a name="install-azure-databricks-tools"></a><span data-ttu-id="7dcb8-146">Installieren von Azure Databricks-Tools</span><span class="sxs-lookup"><span data-stu-id="7dcb8-146">Install Azure Databricks tools</span></span>

<span data-ttu-id="7dcb8-147">Mit der **Databricks CLI** können Sie eine Verbindung mit Azure Databricks-Clustern herstellen und Dateien in diese von Ihrem lokalen Computer hochladen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-147">You can use the **Databricks CLI** to connect to Azure Databricks clusters and upload files to them from your local machine.</span></span> <span data-ttu-id="7dcb8-148">Databricks-Cluster greifen über DBFS (Databricks File System) auf Dateien zu.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-148">Databricks clusters access files through DBFS (Databricks File System).</span></span>

1. <span data-ttu-id="7dcb8-149">Die Databricks CLI erfordert Python 3.6 oder höher.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-149">The Databricks CLI requires Python 3.6 or above.</span></span> <span data-ttu-id="7dcb8-150">Wenn Sie Python bereits installiert haben, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-150">If you already have Python installed, you can skip this step.</span></span>

   <span data-ttu-id="7dcb8-151">**Für Windows:**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-151">**For Windows:**</span></span>

   <span data-ttu-id="7dcb8-152">[Laden Sie Python für Windows herunter](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe).</span><span class="sxs-lookup"><span data-stu-id="7dcb8-152">[Download Python for Windows](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe)</span></span>

   <span data-ttu-id="7dcb8-153">**Für Linux:** Python ist in den meisten Linux-Distributionen bereits vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-153">**For Linux:** Python comes preinstalled on most Linux distributions.</span></span> <span data-ttu-id="7dcb8-154">Führen Sie den folgenden Befehl aus, um festzustellen, welche Version Sie installiert haben:</span><span class="sxs-lookup"><span data-stu-id="7dcb8-154">Run the following command to see which version you have installed:</span></span>

   ```bash
   python3 --version
   ```

2. <span data-ttu-id="7dcb8-155">Verwenden Sie pip zum Installieren der Databricks CLI.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-155">Use pip to install the Databricks CLI.</span></span> <span data-ttu-id="7dcb8-156">Python 3.4 oder höher enthält pip standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-156">Python 3.4 and later include pip by default.</span></span> <span data-ttu-id="7dcb8-157">Verwenden Sie pip3 für Python 3.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-157">Use pip3 for Python 3.</span></span> <span data-ttu-id="7dcb8-158">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7dcb8-158">Run the following command:</span></span>

   ```bash
   pip3 install databricks-cli
   ```

3. <span data-ttu-id="7dcb8-159">Nachdem Sie die Databricks CLI installiert haben, öffnen Sie eine neue Eingabeaufforderung, und führen Sie den Befehl `databricks` aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-159">Once you've installed the Databricks CLI, open a new command prompt and run the command `databricks`.</span></span> <span data-ttu-id="7dcb8-160">Wenn Sie eine Fehlermeldung **'databricks' is not recognized as an internal or external command error** („Databricks“ wird nicht als interner oder externer Befehl erkannt: Fehler) erhalten, stellen Sie sicher, dass Sie eine neue Eingabeaufforderung geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-160">If you receive a **'databricks' is not recognized as an internal or external command error**, make sure you opened a new command prompt.</span></span>

## <a name="set-up-azure-databricks"></a><span data-ttu-id="7dcb8-161">Einrichten von Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="7dcb8-161">Set up Azure Databricks</span></span>

<span data-ttu-id="7dcb8-162">Nachdem Sie die Databricks CLI installiert haben, müssen Sie Authentifizierungsdetails einrichten.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-162">Now that you have the Databricks CLI installed, you need to set up authentication details.</span></span>

1. <span data-ttu-id="7dcb8-163">Führen Sie den Befehl `databricks configure --token` der Databricks CLI aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-163">Run the Databricks CLI command `databricks configure --token`.</span></span>

2. <span data-ttu-id="7dcb8-164">Nachdem Sie den Konfigurstionsbefehl ausgeführt haben, werden Sie zur Eingabe eines Hosts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-164">After running the configure command, you are prompted to enter a host.</span></span> <span data-ttu-id="7dcb8-165">Die Host-URL verwendet das folgende Format: **https://<\Speicherort >.azuredatabricks.net**.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-165">Your host URL uses the format: **https://<\Location>.azuredatabricks.net**.</span></span> <span data-ttu-id="7dcb8-166">Wenn Sie beispielsweise während der Azure Databricks-Diensterstellung **eastus2** (USA, Osten 2) ausgewählt haben, wäre der Host **https://eastus2.azuredatabricks.net** .</span><span class="sxs-lookup"><span data-stu-id="7dcb8-166">For instance, if you selected **eastus2** during Azure Databricks Service creation, the host would be **https://eastus2.azuredatabricks.net**.</span></span>

3. <span data-ttu-id="7dcb8-167">Nachdem Sie den Host eingegeben haben, werden Sie zur Eingabe eines Tokens aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-167">After entering your host, you are prompted to enter a token.</span></span> <span data-ttu-id="7dcb8-168">Wählen Sie im Azure-Portal **Arbeitsbereich starten** aus, um den Azure Databricks-Arbeitsbereich zu starten.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-168">In the Azure portal, select **Launch Workspace** to launch your Azure Databricks workspace.</span></span>

   ![Starten des Azure Databricks-Arbeitsbereichs](./media/databricks-deployment/launch-databricks-workspace.png)

4. <span data-ttu-id="7dcb8-170">Wählen Sie auf der Startseite Ihres Arbeitsbereichs **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-170">On the home page of your workspace, select **User Settings**.</span></span>

   ![Benutzereinstellungen in einem Azure Databricks-Arbeitsbereich](./media/databricks-deployment/databricks-user-settings.png)

5. <span data-ttu-id="7dcb8-172">Auf der Seite „Benutzereinstellungen“ können Sie ein neues Token generieren.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-172">On the User Settings page, you can generate a new token.</span></span> <span data-ttu-id="7dcb8-173">Kopieren Sie das generierte Token, und fügen Sie es dann in die Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-173">Copy the generated token and paste it back into your command prompt.</span></span>

   ![Generieren eines neuen Zugriffstokens im Azure Databricks-Arbeitsbereich](./media/databricks-deployment/generate-token.png)

<span data-ttu-id="7dcb8-175">Sie sollten jetzt in der Lage sein, auf alle Azure Databricks-Cluster zuzugreifen, die Sie erstellen, und Dateien in DBFS hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-175">You should now be able to access any Azure Databricks clusters you create and upload files to the DBFS.</span></span>

## <a name="download-worker-dependencies"></a><span data-ttu-id="7dcb8-176">Herunterladen von Workerabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7dcb8-176">Download worker dependencies</span></span>

1. <span data-ttu-id="7dcb8-177">Microsoft.Spark.Worker unterstützt Apache Spark bei der Ausführung Ihrer App, z.B. für benutzerdefinierte Funktionen (User-Defined Functions, UDFs), die Sie ggf. geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-177">Microsoft.Spark.Worker helps Apache Spark execute your app, such as any user-defined functions (UDFs) you may have written.</span></span> <span data-ttu-id="7dcb8-178">Laden Sie [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz) herunter.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-178">Download [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz).</span></span>

2. <span data-ttu-id="7dcb8-179">*install-worker.sh* ist ein Skript, mit dem Sie von .NET für Apache Spark abhängige Dateien in die Knoten Ihres Clusters kopieren können.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-179">The *install-worker.sh* is a script that lets you copy .NET for Apache Spark dependent files into the nodes of your cluster.</span></span>

   <span data-ttu-id="7dcb8-180">Erstellen Sie eine neue Datei mit dem Namen **install-worker.sh** auf Ihrem lokalen Computer, und fügen Sie den [Inhalt von install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) auf GitHub ein.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-180">Create a new file named **install-worker.sh** on your local computer, and paste the [install-worker.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) located on GitHub.</span></span>

3. <span data-ttu-id="7dcb8-181">*db-init.sh* ist ein Skript, mit dem Abhängigkeiten auf Ihrem Databricks Spark-Cluster installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-181">The *db-init.sh* is a script that installs dependencies onto your Databricks Spark cluster.</span></span>

   <span data-ttu-id="7dcb8-182">Erstellen Sie eine neue Datei mit dem Namen **db-init.sh** auf Ihrem lokalen Computer, und fügen Sie den [Inhalt von „db-init.sh“](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) auf GitHub ein.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-182">Create a new file named **db-init.sh** on your local computer, and paste the [db-init.sh contents](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) located on GitHub.</span></span>

   <span data-ttu-id="7dcb8-183">Legen Sie in der soeben erstellten Datei die `DOTNET_SPARK_RELEASE`-Variable auf `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz` fest.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-183">In the file you just created, set the `DOTNET_SPARK_RELEASE` variable to `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz`.</span></span> <span data-ttu-id="7dcb8-184">Lassen Sie den Rest der Datei *db-init.sh* unverändert.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-184">Leave the rest of the *db-init.sh* file as-is.</span></span>

> [!Note]
> <span data-ttu-id="7dcb8-185">Wenn Sie Windows verwenden, stellen Sie sicher, dass die Zeilenenden in Ihren *install-worker.sh*- und *db-init.sh*-Skripts den Unix-Stil (LF) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-185">If you are using Windows, verify that the line-endings in your *install-worker.sh* and *db-init.sh* scripts are Unix-style (LF).</span></span> <span data-ttu-id="7dcb8-186">Sie können die Zeilenenden mit Text-Editoren wie Notepad++ oder Atom ändern.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-186">You can change line endings through text editors like Notepad++ and Atom.</span></span>

## <a name="publish-your-app"></a><span data-ttu-id="7dcb8-187">Veröffentlichen der App</span><span class="sxs-lookup"><span data-stu-id="7dcb8-187">Publish your app</span></span>

<span data-ttu-id="7dcb8-188">Anschließend veröffentlichen Sie die *mySparkApp*, die im Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) erstellt wurde, um sicherzustellen, dass Ihr Spark-Cluster Zugriff auf alle Dateien besitzt, die er zum Ausführen Ihrer App benötigt.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-188">Next, you publish the *mySparkApp* created in the [.NET for Apache Spark - Get Started in 10-Minutes](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) tutorial to ensure your Spark cluster has access to all the files it needs to run your app.</span></span>

1. <span data-ttu-id="7dcb8-189">Führen Sie zum Veröffentlichen der *mySparkApp* die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="7dcb8-189">Run the following commands to publish the *mySparkApp*:</span></span>

   <span data-ttu-id="7dcb8-190">**Unter Windows:**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-190">**On Windows:**</span></span>

   ```console
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x6
   ```

   <span data-ttu-id="7dcb8-191">**Unter Linux:**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-191">**On Linux:**</span></span>

   ```bash
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. <span data-ttu-id="7dcb8-192">Führen Sie die folgenden Aufgaben aus, um die veröffentlichten App-Dateien zu komprimieren, damit Sie sie problemlos in ihren Databricks Spark-Cluster hochladen können.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-192">Do the following tasks to zip your published app files so that you can easily upload them to your Databricks Spark cluster.</span></span>

   <span data-ttu-id="7dcb8-193">**Unter Windows:**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-193">**On Windows:**</span></span>

   <span data-ttu-id="7dcb8-194">Navigieren Sie zu „MySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64“.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-194">Navigate to mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64.</span></span> <span data-ttu-id="7dcb8-195">Klicken Sie dann mit der rechten Maustaste auf den Ordner **Veröffentlichen**, und wählen Sie **Senden an > Komprimierter Ordner (ZIP-Ordner)** aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-195">Then, right-click on **Publish** folder and select **Send to > Compressed (zipped) folder**.</span></span> <span data-ttu-id="7dcb8-196">Nennen Sie den neuen Ordner **publish.zip**.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-196">Name the new folder **publish.zip**.</span></span>

   <span data-ttu-id="7dcb8-197">**Führen Sie unter Linux den folgenden Befehl aus:**</span><span class="sxs-lookup"><span data-stu-id="7dcb8-197">**On Linux, run the following command:**</span></span>

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a><span data-ttu-id="7dcb8-198">Hochladen von Dateien</span><span class="sxs-lookup"><span data-stu-id="7dcb8-198">Upload files</span></span>

<span data-ttu-id="7dcb8-199">In diesem Abschnitt laden Sie mehrere Dateien in DBFS hoch, sodass Ihr Cluster über alles verfügt, was er benötigt, um Ihre App in der Cloud auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-199">In this section, you upload several files to DBFS so that your cluster has everything it needs to run your app in the cloud.</span></span> <span data-ttu-id="7dcb8-200">Stellen Sie bei jedem Hochladen einer Datei in DBFS sicher, dass Sie sich in dem Verzeichnis befinden, in dem diese Datei auf Ihrem Computer gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-200">Each time you upload a file to the DBFS, make sure you are in the directory where that file is located on your computer.</span></span>

1. <span data-ttu-id="7dcb8-201">Führen Sie die folgenden Befehle aus, um die Dateien *db-init.sh*, *install-worker.sh* und *Microsoft.Spark.Worker* in DBFS hochzuladen:</span><span class="sxs-lookup"><span data-stu-id="7dcb8-201">Run the following commands to upload the *db-init.sh*, *install-worker.sh*, and *Microsoft.Spark.Worker* to DBFS:</span></span>

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. <span data-ttu-id="7dcb8-202">Führen Sie die folgenden Befehle aus, um die verbleibenden Dateien hochzuladen, die Ihr Cluster zum Ausführen der App benötigt: den gezippten Veröffentlichungsordner, *input.txt* und *microsoft-spark-2.4.x-0.3.0.jar*.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-202">Run the following commands to upload the remaining files your cluster will need to run your app: the zipped publish folder, *input.txt*, and *microsoft-spark-2.4.x-0.3.0.jar*.</span></span>

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a><span data-ttu-id="7dcb8-203">Erstellen eines Auftrags</span><span class="sxs-lookup"><span data-stu-id="7dcb8-203">Create a job</span></span>

<span data-ttu-id="7dcb8-204">Ihre App wird in Azure Databricks durch einen Auftrag ausgeführt, der **spark-submit** ausführt. Dies ist der Befehl, mit dem Sie .NET-Aufträge für Apache Spark ausführen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-204">Your app runs on Azure Databricks through a job that runs **spark-submit**, which is the command you use to run .NET for Apache Spark jobs.</span></span>

1. <span data-ttu-id="7dcb8-205">Wählen Sie im Azure Databricks-Arbeitsbereich das Symbol **Aufträge** aus, und klicken Sie dann auf **+ Auftrag erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-205">In your Azure Databricks Workspace, select the **Jobs** icon and then **+ Create Job**.</span></span>

   ![Erstellen eines Azure Databricks-Auftrags](./media/databricks-deployment/create-job.png)

2. <span data-ttu-id="7dcb8-207">Wählen Sie einen Titel für Ihren Auftrag aus, und wählen Sie dann **spark-submit konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-207">Choose a title for your job, and then select **Configure spark-submit**.</span></span>

   ![Konfigurieren von spark-submit für den Databricks-Auftrag](./media/databricks-deployment/configure-spark-submit.png)

3. <span data-ttu-id="7dcb8-209">Fügen Sie die folgenden Parameter in die Auftragskonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-209">Paste the following parameters in the job configuration.</span></span> <span data-ttu-id="7dcb8-210">Wählen Sie dann **Bestätigen** aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-210">Then, select **Confirm**.</span></span>

   ```
   ["--class","org.apache.spark.deploy.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a><span data-ttu-id="7dcb8-211">Erstellen eines Clusters</span><span class="sxs-lookup"><span data-stu-id="7dcb8-211">Create a cluster</span></span>

1. <span data-ttu-id="7dcb8-212">Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Bearbeiten** aus, um den Cluster Ihres Auftrags zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-212">Navigate to your job and select **Edit** to configure your job's cluster.</span></span>

2. <span data-ttu-id="7dcb8-213">Legen Sie den Cluster auf **Spark 2.4.1** fest.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-213">Set your cluster to **Spark 2.4.1**.</span></span> <span data-ttu-id="7dcb8-214">Wählen Sie dann **Erweiterte Optionen** > **Init-Skripts** aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-214">Then, select **Advanced Options** > **Init Scripts**.</span></span> <span data-ttu-id="7dcb8-215">Legen Sie den init-Skriptpfad auf `dbfs:/spark-dotnet/db-init.sh` fest.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-215">Set Init Script Path as `dbfs:/spark-dotnet/db-init.sh`.</span></span>

   ![Konfigurieren eines Spark-Clusters in Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. <span data-ttu-id="7dcb8-217">Wählen Sie **Bestätigen** aus, um die Clustereinstellungen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-217">Select **Confirm** to confirm your cluster settings.</span></span>

## <a name="run-your-app"></a><span data-ttu-id="7dcb8-218">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="7dcb8-218">Run your app</span></span>

1. <span data-ttu-id="7dcb8-219">Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Jetzt ausführen** aus, um den Auftrag auf dem neu konfigurierten Spark-Cluster auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-219">Navigate to your job and select **Run Now** to run your job on your newly configured Spark cluster.</span></span>

2. <span data-ttu-id="7dcb8-220">Es dauert einige Minuten, bis der Cluster des Auftrags erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-220">It takes a few minutes for the job's cluster to create.</span></span> <span data-ttu-id="7dcb8-221">Nachdem der Auftrag erstellt wurde, wird er übermittelt, und Sie können die Ausgabe anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-221">Once it is created, your job will be submitted, and you can view the output.</span></span>

3. <span data-ttu-id="7dcb8-222">Wählen Sie im Menü auf der linken Seite **Cluster** und dann den Namen aus, und führen Sie den Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-222">Select **Clusters** from the left menu, and then the name and run of your job.</span></span>

4. <span data-ttu-id="7dcb8-223">Wählen Sie **Treiberprotokolle** aus, um die Ausgabe des Auftrags anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-223">Select **Driver Logs** to view the output of your job.</span></span> <span data-ttu-id="7dcb8-224">Nachdem die Ausführung Ihrer App abgeschlossen wurde, wird die gleiche Wortzahltabelle aus der lokalen Ausführung von „Erste Schritte“ in der Standardausgabekonsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-224">When your app finishes executing, you see the same word count table from the getting started local run written to the standard output console.</span></span>

   ![Tabelle der Azure Databricks-Auftragsausgabe](./media/databricks-deployment/table-output.png)

   <span data-ttu-id="7dcb8-226">Herzlichen Glückwunsch, Sie haben Ihre erste .NET-Anwendung für Apache Spark in der Cloud ausgeführt!</span><span class="sxs-lookup"><span data-stu-id="7dcb8-226">Congratulations, you've run your first .NET for Apache Spark application in the cloud!</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="7dcb8-227">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7dcb8-227">Clean up resources</span></span>

<span data-ttu-id="7dcb8-228">Wenn Sie den Databricks-Arbeitsbereich nicht mehr benötigen, können Sie die Azure Databricks-Ressource im Azure-Portal löschen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-228">If you no longer need the Databricks workspace, you can delete your Azure Databricks resource in the Azure portal.</span></span> <span data-ttu-id="7dcb8-229">Sie können auch den Namen der Ressourcengruppe auswählen, um die Seite für die Ressourcengruppe zu öffnen, und dann **Ressourcengruppe löschen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-229">You can also select the resource group name to open the resource group page, and then select **Delete resource group**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7dcb8-230">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7dcb8-230">Next steps</span></span>

<span data-ttu-id="7dcb8-231">In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Databricks bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-231">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="7dcb8-232">Weitere Informationen zu Databricks finden Sie in der Dokumentation zu Azure Databricks.</span><span class="sxs-lookup"><span data-stu-id="7dcb8-232">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7dcb8-233">Dokumentation zu Azure Databricks</span><span class="sxs-lookup"><span data-stu-id="7dcb8-233">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
