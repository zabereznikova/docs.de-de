---
title: Installieren von .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight Spark-Clustern
description: Erfahren Sie, wie Sie .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight installieren.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 14babf7a551192b286f309393e3bbff25d4745d5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617742"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a><span data-ttu-id="fd3df-103">Installieren von .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight Spark-Clustern</span><span class="sxs-lookup"><span data-stu-id="fd3df-103">Install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters</span></span>

<span data-ttu-id="fd3df-104">In diesem Artikel erfahren Sie, wie Sie .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight Spark-Clustern installieren.</span><span class="sxs-lookup"><span data-stu-id="fd3df-104">This article teaches you how to install .NET for Apache Spark on Jupyter notebooks on Azure HDInsight Spark clusters.</span></span> <span data-ttu-id="fd3df-105">Sie können .NET für Apache Spark über eine Kombination aus der Befehlszeile und dem Azure-Portal in Azure HDInsight-Clustern bereitstellen (weitere Informationen finden Sie unter [Bereitstellen einer .NET für Apache Spark-Anwendung für Azure HDInsight](../tutorials/hdinsight-deployment.md)), aber Notebooks ermöglichen iterative Funktionen mit mehr Interaktion.</span><span class="sxs-lookup"><span data-stu-id="fd3df-105">You can deploy .NET for Apache Spark on Azure HDInsight clusters through a combination of the command line and the Azure portal (for more information, see [how to deploy a .NET for Apache Spark application to Azure HDInsight](../tutorials/hdinsight-deployment.md)), but notebooks provide a more interactive and iterative experience.</span></span>

<span data-ttu-id="fd3df-106">Jupyter Notebooks ist bereits in Azure HDInsight-Clustern integriert, deshalb müssen Sie es lediglich für die Ausführung von .NET für Apache Spark konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fd3df-106">Azure HDInsight clusters already come with Jupyter notebooks, so all you have to do is configure the Jupyter notebooks to run .NET for Apache Spark.</span></span> <span data-ttu-id="fd3df-107">Um .NET für Apache Spark in Ihren Jupyter Notebooks zu verwenden, wird eine C#-REPL benötigt, um Ihren C#-Code Zeile für Zeile auszuführen und bei Bedarf den Ausführungsstatus beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="fd3df-107">To use .NET for Apache Spark in your Jupyter notebooks, a C# REPL is needed to execute your C# code line-by-line and to preserve execution state when necessary.</span></span> <span data-ttu-id="fd3df-108">[Try .NET](https://github.com/dotnet/try) wurde als offizielle .NET-REPL integriert.</span><span class="sxs-lookup"><span data-stu-id="fd3df-108">[Try .NET](https://github.com/dotnet/try) has been integrated as the official .NET REPL.</span></span>

<span data-ttu-id="fd3df-109">Um .NET für Apache Spark über die Jupyter Notebooks-Benutzeroberfläche zu aktivieren, müssen Sie einige manuelle Schritte über [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) ausführen und [Skriptaktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) im HDInsight Spark-Cluster ausführen.</span><span class="sxs-lookup"><span data-stu-id="fd3df-109">To enable .NET for Apache Spark through the Jupyter Notebooks experience, you need to follow a few manual steps through [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) and submit [script actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) on the HDInsight Spark cluster.</span></span>

> [!NOTE]
> <span data-ttu-id="fd3df-110">Dieses Feature ist *experimentell* und wird nicht vom HDInsight Spark-Team unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fd3df-110">This feature is *experimental* and is not supported by the HDInsight Spark team.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="fd3df-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fd3df-111">Prerequisites</span></span>

<span data-ttu-id="fd3df-112">Sofern noch nicht vorhanden, erstellen Sie einen [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight)-Cluster.</span><span class="sxs-lookup"><span data-stu-id="fd3df-112">If you don't already have one, create an [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight) cluster.</span></span>

1. <span data-ttu-id="fd3df-113">Wechseln Sie zum [Azure-Portal](https://portal.azure.com), und klicken Sie auf **+ Ressource erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fd3df-113">Visit the [Azure portal](https://portal.azure.com) and select **+ Create a Resource**.</span></span>

1. <span data-ttu-id="fd3df-114">Erstellen Sie eine neue Azure HDInsight-Clusterressource.</span><span class="sxs-lookup"><span data-stu-id="fd3df-114">Create a new Azure HDInsight cluster resource.</span></span> <span data-ttu-id="fd3df-115">Wählen Sie während der Clustererstellung **Spark 2.4** und **HDI 4.0** aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-115">Select **Spark 2.4** and **HDI 4.0** during cluster creation.</span></span>

## <a name="install-net-for-apache-spark"></a><span data-ttu-id="fd3df-116">Installieren von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="fd3df-116">Install .NET for Apache Spark</span></span>

<span data-ttu-id="fd3df-117">Wählen Sie im Azure-Portal den im vorherigen Schritt erstellten **HDInsight Spark-Cluster** aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-117">In the Azure portal, select the **HDInsight Spark cluster** you created in the previous step.</span></span>

### <a name="stop-the-livy-server"></a><span data-ttu-id="fd3df-118">Beenden des Livy-Servers</span><span class="sxs-lookup"><span data-stu-id="fd3df-118">Stop the Livy server</span></span>

1. <span data-ttu-id="fd3df-119">Klicken Sie im Portal auf **Übersicht** und dann auf **Ambari-Homepage**.</span><span class="sxs-lookup"><span data-stu-id="fd3df-119">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="fd3df-120">Geben Sie bei Aufforderung die Anmeldeinformationen für den Cluster ein.</span><span class="sxs-lookup"><span data-stu-id="fd3df-120">If prompted, enter the login credentials for the cluster.</span></span>

   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/select-ambari.png)

2. <span data-ttu-id="fd3df-122">Wählen Sie im links angezeigten Navigationsmenü **Spark2** aus, und klicken Sie auf **LIVY FOR SPARK2 SERVER**.</span><span class="sxs-lookup"><span data-stu-id="fd3df-122">Select **Spark2** from the left navigation menu, and select **LIVY FOR SPARK2 SERVER**.</span></span>

   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/select-livyserver.png)

3. <span data-ttu-id="fd3df-124">Wählen Sie **hn0... host** aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-124">Select **hn0... host**.</span></span>

   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/select-host.png)

4. <span data-ttu-id="fd3df-126">Klicken Sie auf die Auslassungspunkte neben **Livy for Spark2 Server**, und klicken Sie auf **Stop** (Beenden).</span><span class="sxs-lookup"><span data-stu-id="fd3df-126">Select the ellipsis next to **Livy for Spark2 Server** and select **Stop**.</span></span> <span data-ttu-id="fd3df-127">Klicken Sie in der Aufforderung auf **OK**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="fd3df-127">When prompted, select **OK** to proceed.</span></span>

   <span data-ttu-id="fd3df-128">Beenden Sie den Server „Livy for Spark2“.</span><span class="sxs-lookup"><span data-stu-id="fd3df-128">Stop Livy for Spark2 Server.</span></span>
   <span data-ttu-id="fd3df-129">![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/stop-server.png)</span><span class="sxs-lookup"><span data-stu-id="fd3df-129">![Stop Livy Server](./media/hdinsight-notebook-installation/stop-server.png)</span></span>

5. <span data-ttu-id="fd3df-130">Wiederholen Sie die vorherigen Schritte für **hn1... host**.</span><span class="sxs-lookup"><span data-stu-id="fd3df-130">Repeat the previous steps for **hn1... host**.</span></span>

### <a name="submit-an-hdinsight-script-action"></a><span data-ttu-id="fd3df-131">Übermitteln einer HDInsight-Skriptaktion</span><span class="sxs-lookup"><span data-stu-id="fd3df-131">Submit an HDInsight script action</span></span>

1. <span data-ttu-id="fd3df-132">`install-interactive-notebook.sh` ist ein Skript, mit dem .NET for Apache Spark installiert wird und Änderungen an Apache Livy und sparkmagic durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fd3df-132">The `install-interactive-notebook.sh` is a script that installs .NET for Apache Spark and makes changes to Apache Livy and sparkmagic.</span></span> <span data-ttu-id="fd3df-133">Bevor Sie eine Skriptaktion an HDInsight übermitteln, müssen Sie `install-interactive-notebook.sh` erstellen und hochladen.</span><span class="sxs-lookup"><span data-stu-id="fd3df-133">Before you submit a script action to HDInsight, you need to create and upload `install-interactive-notebook.sh`.</span></span>

   <span data-ttu-id="fd3df-134">Erstellen Sie eine neue Datei namens **install-interactive-notebook.sh** auf Ihrem lokalen Computer, und fügen Sie die Inhalte von [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh) darin ein.</span><span class="sxs-lookup"><span data-stu-id="fd3df-134">Create a new file named **install-interactive-notebook.sh** in your local computer and paste the contents of [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh).</span></span>

   <span data-ttu-id="fd3df-135">Laden Sie das Skript an einen [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) hoch, der für den HDInsight-Cluster zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="fd3df-135">Upload the script to a [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) that's accessible from the HDInsight cluster.</span></span> <span data-ttu-id="fd3df-136">Beispielsweise `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="fd3df-136">For example, `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.</span></span>

2. <span data-ttu-id="fd3df-137">Führen Sie mithilfe der [HDInsight-Skriptaktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)`install-interactive-notebook.sh` auf dem Cluster aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-137">Run `install-interactive-notebook.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

   <span data-ttu-id="fd3df-138">Wechseln Sie zurück zum HDI-Cluster im Azure-Portal, und wählen Sie aus den links angezeigten Optionen **Skriptaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-138">Return to your HDI cluster in the Azure portal, and select **Script actions** from the options on the left.</span></span> <span data-ttu-id="fd3df-139">Sie übermitteln eine Skriptaktion zum Bereitstellen der .NET für Apache Spark-REPL für Ihren HDInsight Spark-Cluster.</span><span class="sxs-lookup"><span data-stu-id="fd3df-139">You submit one script action to deploy the .NET for Apache Spark REPL on your HDInsight Spark cluster.</span></span> <span data-ttu-id="fd3df-140">Verwenden Sie folgende Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fd3df-140">Use the following settings:</span></span>

   |<span data-ttu-id="fd3df-141">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="fd3df-141">Property</span></span>  |<span data-ttu-id="fd3df-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd3df-142">Description</span></span>  |
   |---------|---------|
   | <span data-ttu-id="fd3df-143">Skripttyp</span><span class="sxs-lookup"><span data-stu-id="fd3df-143">Script type</span></span> | <span data-ttu-id="fd3df-144">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="fd3df-144">Custom</span></span> |
   | <span data-ttu-id="fd3df-145">Name</span><span class="sxs-lookup"><span data-stu-id="fd3df-145">Name</span></span> | <span data-ttu-id="fd3df-146">*Installation der interaktiven Notebook-Benutzeroberfläche für .NET for Apache Spark*</span><span class="sxs-lookup"><span data-stu-id="fd3df-146">*Install .NET for Apache Spark Interactive Notebook Experience*</span></span> |
   | <span data-ttu-id="fd3df-147">Bash-Skript-URI</span><span class="sxs-lookup"><span data-stu-id="fd3df-147">Bash script URI</span></span> | <span data-ttu-id="fd3df-148">Der URI für die hochgeladene Datei `install-interactive-notebook.sh`.</span><span class="sxs-lookup"><span data-stu-id="fd3df-148">The URI to which you uploaded `install-interactive-notebook.sh`.</span></span> |
   | <span data-ttu-id="fd3df-149">Knotentyp(en)</span><span class="sxs-lookup"><span data-stu-id="fd3df-149">Node type(s)</span></span>| <span data-ttu-id="fd3df-150">Hauptknoten und Worker</span><span class="sxs-lookup"><span data-stu-id="fd3df-150">Head and Worker</span></span> |
   | <span data-ttu-id="fd3df-151">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd3df-151">Parameters</span></span> | <span data-ttu-id="fd3df-152">Version von .NET für Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="fd3df-152">.NET for Apache Spark version.</span></span> <span data-ttu-id="fd3df-153">Überprüfen Sie ggf. die [.NET für Apache Spark-Releases](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="fd3df-153">You can check [.NET for Apache Spark releases](https://github.com/dotnet/spark/releases).</span></span> <span data-ttu-id="fd3df-154">Wenn Sie beispielsweise Sparkdotnet 0.6.0 installieren möchten, wäre dies `0.6.0`.</span><span class="sxs-lookup"><span data-stu-id="fd3df-154">For example, if you want to install Sparkdotnet version 0.6.0 then it would be `0.6.0`.</span></span>

   <span data-ttu-id="fd3df-155">Wechseln Sie zum nächsten Schritt, wenn ein grünes Häkchen neben dem Status der Skriptaktion angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fd3df-155">Move to the next step when green checkmarks appear next to the status of the script action.</span></span>

### <a name="start-the-livy-server"></a><span data-ttu-id="fd3df-156">Starten des Livy-Servers</span><span class="sxs-lookup"><span data-stu-id="fd3df-156">Start the Livy server</span></span>

<span data-ttu-id="fd3df-157">Folgen Sie den Anweisungen im Abschnitt [Beenden des Livy-Servers](#stop-the-livy-server), um den Livy for Spark2-Server für die Hosts **hn0** und **hn1** zu **Starten** (statt sie wie vorher zu **Beenden**).</span><span class="sxs-lookup"><span data-stu-id="fd3df-157">Follow the instructions in the [Stop Livy server](#stop-the-livy-server) section to **Start** (rather than **Stop**) the Livy for Spark2 Server for hosts **hn0** and **hn1**.</span></span>

### <a name="set-up-spark-default-configurations"></a><span data-ttu-id="fd3df-158">Einrichten der Spark-Standardkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="fd3df-158">Set up Spark default configurations</span></span>

1. <span data-ttu-id="fd3df-159">Klicken Sie im Portal auf **Übersicht** und dann auf **Ambari-Homepage**.</span><span class="sxs-lookup"><span data-stu-id="fd3df-159">From the portal, select **Overview**, and then select **Ambari home**.</span></span> <span data-ttu-id="fd3df-160">Geben Sie die Anmeldeinformationen für den Cluster ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="fd3df-160">If prompted, enter the cluster login credentials for the cluster.</span></span>

2. <span data-ttu-id="fd3df-161">Wählen Sie **Spark2** und **CONFIGS** aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-161">Select **Spark2** and **CONFIGS**.</span></span> <span data-ttu-id="fd3df-162">Klicken Sie dann auf **Custom spark2-defaults**.</span><span class="sxs-lookup"><span data-stu-id="fd3df-162">Then, select **Custom spark2-defaults**.</span></span>

   ![Festlegen der Konfigurationen](./media/hdinsight-notebook-installation/spark-configs.png)

3. <span data-ttu-id="fd3df-164">Wählen Sie **Add Property** (Eigenschaft hinzufügen) aus, um Spark-Standardeinstellungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fd3df-164">Select **Add Property...** to add Spark default settings.</span></span>

   ![Hinzufügen einer Eigenschaft](./media/hdinsight-notebook-installation/add-property.png)

   <span data-ttu-id="fd3df-166">Es sind drei Eigenschaften vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fd3df-166">There are three individual properties.</span></span> <span data-ttu-id="fd3df-167">Fügen Sie diese nacheinander mit dem Eigenschaftstyp **TEXT** im Modus zum Hinzufügen einzelner Eigenschaften hinzu.</span><span class="sxs-lookup"><span data-stu-id="fd3df-167">Add them one at a time using the **TEXT** property type in Single property add mode.</span></span> <span data-ttu-id="fd3df-168">Vergewissern Sie sich, dass vor und nach den Schlüsseln/Werten keine Leerzeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fd3df-168">Check that you don't have any extra spaces before or after any of the keys/values.</span></span>

   * <span data-ttu-id="fd3df-169">**Eigenschaft 1**</span><span class="sxs-lookup"><span data-stu-id="fd3df-169">**Property 1**</span></span>
       * <span data-ttu-id="fd3df-170">Schlüssel:&ensp;&ensp;`spark.dotnet.shell.command`</span><span class="sxs-lookup"><span data-stu-id="fd3df-170">Key:&ensp;&ensp;`spark.dotnet.shell.command`</span></span>
       * <span data-ttu-id="fd3df-171">Wert: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span><span class="sxs-lookup"><span data-stu-id="fd3df-171">Value: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`</span></span>

   * <span data-ttu-id="fd3df-172">**Eigenschaft 2** Verwenden Sie die Version von .NET für Apache Spark, die Sie in der vorherigen Skriptaktion verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="fd3df-172">**Property 2** Use the version of .NET for Apache Spark which you had included in the previous script action.</span></span>
       * <span data-ttu-id="fd3df-173">Schlüssel:&ensp;&ensp;`spark.dotnet.packages`</span><span class="sxs-lookup"><span data-stu-id="fd3df-173">Key:&ensp;&ensp;`spark.dotnet.packages`</span></span>
       * <span data-ttu-id="fd3df-174">Wert: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`</span><span class="sxs-lookup"><span data-stu-id="fd3df-174">Value: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`</span></span>

   * <span data-ttu-id="fd3df-175">**Eigenschaft 3**</span><span class="sxs-lookup"><span data-stu-id="fd3df-175">**Property 3**</span></span>
       * <span data-ttu-id="fd3df-176">Schlüssel:&ensp;&ensp;`spark.dotnet.interpreter`</span><span class="sxs-lookup"><span data-stu-id="fd3df-176">Key:&ensp;&ensp;`spark.dotnet.interpreter`</span></span>
       * <span data-ttu-id="fd3df-177">Wert: `try`</span><span class="sxs-lookup"><span data-stu-id="fd3df-177">Value: `try`</span></span>

   <span data-ttu-id="fd3df-178">Die folgende Abbildung zeigt beispielsweise die Einstellung für die hinzugefügte Eigenschaft 1:</span><span class="sxs-lookup"><span data-stu-id="fd3df-178">For example, the following image captures the setting for adding property 1:</span></span>

   ![Festlegen der Konfigurationen](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   <span data-ttu-id="fd3df-180">Nachdem Sie die drei Eigenschaften hinzugefügt haben, klicken Sie auf **SAVE** (Speichern).</span><span class="sxs-lookup"><span data-stu-id="fd3df-180">After adding the three properties, select **SAVE**.</span></span> <span data-ttu-id="fd3df-181">Falls eine Warnung mit Konfigurationsempfehlungen angezeigt wird, klicken Sie auf **PROCEED ANYWAY** (Vorgang trotzdem fortsetzen).</span><span class="sxs-lookup"><span data-stu-id="fd3df-181">If you see a warning screen of config recommendations, select **PROCEED ANYWAY**.</span></span>

4. <span data-ttu-id="fd3df-182">Starten Sie die betroffenen Komponenten neu.</span><span class="sxs-lookup"><span data-stu-id="fd3df-182">Restart affected components.</span></span>

   <span data-ttu-id="fd3df-183">Nach dem Hinzufügen neuer Eigenschaften müssen Sie Komponenten neu starten, die von den Änderungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="fd3df-183">After adding the new properties, you need to restart components that were affected by the changes.</span></span> <span data-ttu-id="fd3df-184">Wählen Sie im oberen Bereich **RESTART** (Neu starten) und dann in der Dropdownliste **Restart All Affected** (Alle betroffenen neu starten) aus.</span><span class="sxs-lookup"><span data-stu-id="fd3df-184">At the top, select **RESTART**, and then **Restart All Affected** from the drop-down.</span></span>

   ![Festlegen der Konfigurationen](./media/hdinsight-notebook-installation/restart-affected.png)

   <span data-ttu-id="fd3df-186">Wählen Sie bei Aufforderung **CONFIRM RESTART ALL** (Neustart für alle bestätigen) und **OK** aus, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="fd3df-186">When prompted, select **CONFIRM RESTART ALL** to continue, then click **OK** to finish.</span></span>

## <a name="submit-jobs-through-a-jupyter-notebook"></a><span data-ttu-id="fd3df-187">Übermitteln von Aufträgen über ein Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="fd3df-187">Submit jobs through a Jupyter notebook</span></span>

<span data-ttu-id="fd3df-188">Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie jetzt Ihre .NET für Apache Spark-Aufträge über Jupyter Notebooks übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fd3df-188">After finishing the previous steps, you can now submit your .NET for Apache Spark jobs through Jupyter notebooks.</span></span>

1. <span data-ttu-id="fd3df-189">Erstellen Sie ein neues .NET für Apache Spark-Notebook.</span><span class="sxs-lookup"><span data-stu-id="fd3df-189">Create a new .NET for Apache Spark notebook.</span></span> <span data-ttu-id="fd3df-190">Starten Sie ein Jupyter Notebook aus Ihrem HDI-Cluster im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="fd3df-190">Launch a Jupyter notebook from your HDI cluster in the Azure portal.</span></span>

   ![Jupyter Notebook starten](./media/hdinsight-notebook-installation/launch-notebook.png)

   <span data-ttu-id="fd3df-192">Wählen Sie **Neu** >  **.NET Spark (C#)** aus, um ein Notebook zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd3df-192">Then, select **New** > **.NET Spark (C#)** to create a notebook.</span></span>

   ![Jupyter Notebook](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. <span data-ttu-id="fd3df-194">Übermitteln Sie Aufträge mit .NET for Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="fd3df-194">Submit jobs using .NET for Apache Spark.</span></span>

   <span data-ttu-id="fd3df-195">Verwenden Sie den folgenden Codeausschnitt, um einen DataFrame zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fd3df-195">Use the following code snippet to create a DataFrame:</span></span>

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Übermitteln eines Spark-Auftrags](./media/hdinsight-notebook-installation/create-df.png)

   <span data-ttu-id="fd3df-197">Verwenden Sie den folgenden Codeausschnitt, um eine benutzerdefinierte Funktion zu erstellen und diese mit DataFrames zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="fd3df-197">Use the following code snippet to register a user-defined function (UDF) and use the UDF with DataFrames:</span></span>

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Übermitteln eines Spark-Auftrags](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a><span data-ttu-id="fd3df-199">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fd3df-199">Next steps</span></span>

* [<span data-ttu-id="fd3df-200">Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="fd3df-200">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="fd3df-201">HDInsight-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="fd3df-201">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
