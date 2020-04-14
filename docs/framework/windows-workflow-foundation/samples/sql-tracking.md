---
title: SQL-Nachverfolgung
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243179"
---
# <a name="sql-tracking"></a><span data-ttu-id="87d6f-102">SQL-Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="87d6f-102">SQL tracking</span></span>

<span data-ttu-id="87d6f-103">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter SQL-Tracking-Teilnehmer geschrieben wird, der Tracking-Datensätze in eine SQL-Datenbank schreibt.</span><span class="sxs-lookup"><span data-stu-id="87d6f-103">This sample demonstrates how to write a custom SQL tracking participant that writes tracking records to a SQL database.</span></span> <span data-ttu-id="87d6f-104">Windows Workflow Foundation (WF) bietet Workflow-Nachverfolgung, um Einblick in die Ausführung einer Workflowinstanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="87d6f-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="87d6f-105">Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="87d6f-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="87d6f-106">Weitere Informationen zur Workflowverfolgung finden Sie unter [Workflowverfolgung und Ablaufverfolgung](../workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="87d6f-106">For more information about workflow tracking, see [Workflow Tracking and Tracing](../workflow-tracking-and-tracing.md).</span></span>

## <a name="use-the-sample"></a><span data-ttu-id="87d6f-107">Verwenden sie des Beispiels</span><span class="sxs-lookup"><span data-stu-id="87d6f-107">Use the sample</span></span>

1. <span data-ttu-id="87d6f-108">Überprüfen Sie, ob Sie SQL Server 2008, SQL Server 2008 Express oder eine höhere Version installiert haben.</span><span class="sxs-lookup"><span data-stu-id="87d6f-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="87d6f-109">In den mit dem Beispiel verpackten Skripts wird davon ausgegangen, dass auf dem lokalen Computer eine SQL Express-Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87d6f-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="87d6f-110">Wenn Sie eine andere Instanz verwenden, ändern Sie die datenbankbezogenen Skripts vor dem Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="87d6f-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>

2. <span data-ttu-id="87d6f-111">Erstellen Sie die SQL Server-Nachverfolgungsdatenbank, indem Sie "Trackingsetup.cmd" im Skripteverzeichnis (\WF\Basic\Tracking\SqlTracking\CS\Scripts) ausführen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="87d6f-112">Dadurch wird eine Datenbank mit dem Namen "TrackingSample" erstellt.</span><span class="sxs-lookup"><span data-stu-id="87d6f-112">This creates a database called TrackingSample.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87d6f-113">Das Skript erstellt die Datenbank auf der Standardinstanz von SQL Express.</span><span class="sxs-lookup"><span data-stu-id="87d6f-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="87d6f-114">Wenn Sie sie auf einer anderen Datenbankinstanz installieren möchten, bearbeiten Sie das Skript "Trackingsetup.cmd".</span><span class="sxs-lookup"><span data-stu-id="87d6f-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>

3. <span data-ttu-id="87d6f-115">Öffnen Sie SqlTrackingSample.sln in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="87d6f-115">Open SqlTrackingSample.sln in Visual Studio 2010.</span></span>

4. <span data-ttu-id="87d6f-116">Drücken Sie **Strg-Umschalttaste**+**Shift**+**B,** um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-116">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

5. <span data-ttu-id="87d6f-117">Drücken Sie **F5**, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-117">Press **F5** to run the application.</span></span>

   <span data-ttu-id="87d6f-118">Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="87d6f-118">The browser window opens and shows the directory listing for the application.</span></span>

6. <span data-ttu-id="87d6f-119">Klicken Sie im Browser auf "StockPriceService.xamlx".</span><span class="sxs-lookup"><span data-stu-id="87d6f-119">In the browser, click StockPriceService.xamlx.</span></span>

7. <span data-ttu-id="87d6f-120">Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="87d6f-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="87d6f-121">Kopieren Sie diese Adresse.</span><span class="sxs-lookup"><span data-stu-id="87d6f-121">Copy this address.</span></span>

   <span data-ttu-id="87d6f-122">Ein Beispiel für die WSDL-Adresse des lokalen Dienstes ist `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="87d6f-122">An example of the local service WSDL address is `http://localhost:65193/StockPriceService.xamlx?wsdl`.</span></span>

8. <span data-ttu-id="87d6f-123">Führen Sie mit dem Datei-Explorer den WCF-Testclient (WcfTestClient.exe) aus.</span><span class="sxs-lookup"><span data-stu-id="87d6f-123">Using File Explorer, run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="87d6f-124">Es befindet sich im *Verzeichnis Microsoft Visual Studio 10.0 - Common7-IDE*.</span><span class="sxs-lookup"><span data-stu-id="87d6f-124">It's located in the *Microsoft Visual Studio 10.0\Common7\IDE directory*.</span></span>

9. <span data-ttu-id="87d6f-125">Klicken Sie im WCF-Testclient auf das Menü **Datei,** und wählen Sie **Dienst hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="87d6f-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="87d6f-126">Fügen Sie die lokale Dienstadresse in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="87d6f-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="87d6f-127">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-127">Click **OK** to close the dialog.</span></span>

10. <span data-ttu-id="87d6f-128">Doppelklicken Sie im WCF-Testclient auf **GetStockPrice**.</span><span class="sxs-lookup"><span data-stu-id="87d6f-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="87d6f-129">Dadurch wird `GetStockPrice` der Vorgang geöffnet, der `Contoso` einen Parameter annimmt, geben Sie den Wert ein, und klicken Sie auf **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="87d6f-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>

11. <span data-ttu-id="87d6f-130">Die ausgegebenen Nachverfolgungsdatensätze werden in eine SQL-Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="87d6f-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="87d6f-131">Um die Nachverfolgungsdatensätze anzuzeigen, öffnen Sie die Datenbank "TrackingSample" in SQL Management Studio, und navigieren Sie zu den Tabellen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> <span data-ttu-id="87d6f-132">Durch Ausführen einer Select-Abfrage in den Tabellen werden die Daten in den Nachverfolgungsdatensätzen angezeigt, die in den jeweiligen Tabellen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="87d6f-132">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>

   <span data-ttu-id="87d6f-133">Weitere Informationen zu SQL Server Management Studio finden Sie [unter Einführung in SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms).</span><span class="sxs-lookup"><span data-stu-id="87d6f-133">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms).</span></span> <span data-ttu-id="87d6f-134">Laden Sie SQL Server Management Studio [hier](https://aka.ms/ssmsfullsetup)herunter .</span><span class="sxs-lookup"><span data-stu-id="87d6f-134">Download SQL Server Management Studio [here](https://aka.ms/ssmsfullsetup).</span></span>

## <a name="uninstall-the-sample"></a><span data-ttu-id="87d6f-135">Deinstallieren des Beispiels</span><span class="sxs-lookup"><span data-stu-id="87d6f-135">Uninstall the sample</span></span>

1. <span data-ttu-id="87d6f-136">Führen Sie das SkriptTrackingcleanup.cmd im Beispielverzeichnis aus ( . . . . . . . . . .*. . . . . . . . . . . . . . . .*. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .</span><span class="sxs-lookup"><span data-stu-id="87d6f-136">Run theTrackingcleanup.cmd script in the sample directory (*\WF\Basic\Tracking\SqlTracking*).</span></span>

    > [!NOTE]
    > <span data-ttu-id="87d6f-137">"Trackingcleanup.cmd" versucht, die Datenbank in SQL Express auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="87d6f-138">Wenn Sie eine andere SQL Server-Instanz verwenden, bearbeiten Sie "Trackingcleanup.cmd".</span><span class="sxs-lookup"><span data-stu-id="87d6f-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87d6f-139">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="87d6f-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="87d6f-140">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="87d6f-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="87d6f-141">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="87d6f-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="87d6f-142">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="87d6f-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a><span data-ttu-id="87d6f-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87d6f-143">See also</span></span>

- <span data-ttu-id="87d6f-144">[AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="87d6f-144">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
