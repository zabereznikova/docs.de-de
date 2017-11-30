---
title: SQL-Nachverfolgung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dcffb306c8466e63e0d5888c91d5f6015845d81c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="sql-tracking"></a><span data-ttu-id="25f47-102">SQL-Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="25f47-102">SQL Tracking</span></span>
<span data-ttu-id="25f47-103">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter SQL-Nachverfolgungsteilnehmer, der Nachverfolgungsdatensätze in eine SQL-Datenbank schreibt, geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="25f47-103">This sample demonstrates how to write a custom SQL tracking participant, that writes tracking records to a SQL database.</span></span> [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="25f47-104"> stellt die Workflowüberwachung bereit, um einen Einblick in die Ausführung einer Workflowinstanz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25f47-104"> provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="25f47-105">Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus.</span><span class="sxs-lookup"><span data-stu-id="25f47-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="25f47-106">workflownachverfolgung verwendet wird, finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="25f47-106"> workflow tracking, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="25f47-107">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="25f47-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="25f47-108">Überprüfen Sie, ob Sie SQL Server 2008, SQL Server 2008 Express oder eine höhere Version installiert haben.</span><span class="sxs-lookup"><span data-stu-id="25f47-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="25f47-109">In den mit dem Beispiel verpackten Skripts wird davon ausgegangen, dass auf dem lokalen Computer eine SQL Express-Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25f47-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="25f47-110">Wenn Sie eine andere Instanz verwenden, ändern Sie die datenbankbezogenen Skripts vor dem Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="25f47-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>  
  
2.  <span data-ttu-id="25f47-111">Erstellen Sie die SQL Server-Nachverfolgungsdatenbank, indem Sie "Trackingsetup.cmd" im Skripteverzeichnis (\WF\Basic\Tracking\SqlTracking\CS\Scripts) ausführen.</span><span class="sxs-lookup"><span data-stu-id="25f47-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="25f47-112">Dadurch wird eine Datenbank mit dem Namen "TrackingSample" erstellt.</span><span class="sxs-lookup"><span data-stu-id="25f47-112">This creates a database called TrackingSample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25f47-113">Das Skript erstellt die Datenbank auf der Standardinstanz von SQL Express.</span><span class="sxs-lookup"><span data-stu-id="25f47-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="25f47-114">Wenn Sie sie auf einer anderen Datenbankinstanz installieren möchten, bearbeiten Sie das Skript "Trackingsetup.cmd".</span><span class="sxs-lookup"><span data-stu-id="25f47-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>  
  
3.  <span data-ttu-id="25f47-115">Öffnen Sie "SqlTrackingSample.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25f47-115">Open SqlTrackingSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="25f47-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25f47-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="25f47-117">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="25f47-117">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="25f47-118">Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="25f47-118">The browser window opens and shows the directory listing for the application.</span></span>  
  
6.  <span data-ttu-id="25f47-119">Klicken Sie im Browser auf "StockPriceService.xamlx".</span><span class="sxs-lookup"><span data-stu-id="25f47-119">In the browser, click StockPriceService.xamlx.</span></span>  
  
7.  <span data-ttu-id="25f47-120">Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält.</span><span class="sxs-lookup"><span data-stu-id="25f47-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="25f47-121">Kopieren Sie diese Adresse.</span><span class="sxs-lookup"><span data-stu-id="25f47-121">Copy this address.</span></span>  
  
     <span data-ttu-id="25f47-122">Ein Beispiel für die WSDL-Adresse des lokalen Diensts ist "http://localhost:65193/StockPriceService.xamlx?wsdl".</span><span class="sxs-lookup"><span data-stu-id="25f47-122">An example of the local service WSDL address is http://localhost:65193/StockPriceService.xamlx?wsdl.</span></span>  
  
8.  <span data-ttu-id="25f47-123">Führen Sie den WCF-Testclient (WcfTestClient.exe) über [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] aus.</span><span class="sxs-lookup"><span data-stu-id="25f47-123">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="25f47-124">Er befindet im Verzeichnis "Microsoft Visual Studio 10.0 \Common7\IDE".</span><span class="sxs-lookup"><span data-stu-id="25f47-124">It is located in the Microsoft Visual Studio 10.0\Common7\IDE directory.</span></span>  
  
9. <span data-ttu-id="25f47-125">Klicken Sie in der WCF-Testclient auf die **Datei** Menü **Dienst hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="25f47-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="25f47-126">Fügen Sie die lokale Dienstadresse in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="25f47-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="25f47-127">Klicken Sie auf **OK** um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="25f47-127">Click **OK** to close the dialog.</span></span>  
  
10. <span data-ttu-id="25f47-128">Klicken Sie im WCF-Testclient, doppelklicken auf **GetStockPrice**.</span><span class="sxs-lookup"><span data-stu-id="25f47-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="25f47-129">Daraufhin wird die `GetStockPrice` Vorgang, der einen, geben Sie den Wert Parameter `Contoso` , und klicken Sie auf **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="25f47-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>  
  
11. <span data-ttu-id="25f47-130">Die ausgegebenen Nachverfolgungsdatensätze werden in eine SQL-Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="25f47-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="25f47-131">Um die Nachverfolgungsdatensätze anzuzeigen, öffnen Sie die Datenbank "TrackingSample" in SQL Management Studio, und navigieren Sie zu den Tabellen.</span><span class="sxs-lookup"><span data-stu-id="25f47-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="25f47-132">SQL Server Management Studio finden Sie unter [Einführung in SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span><span class="sxs-lookup"><span data-stu-id="25f47-132"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span></span> <span data-ttu-id="25f47-133">SQL Server 2008 Management Studio Express kann heruntergeladen werden [hier](http://go.microsoft.com/fwlink/?LinkId=180520).</span><span class="sxs-lookup"><span data-stu-id="25f47-133">SQL Server 2008 Management Studio Express can be downloaded [here](http://go.microsoft.com/fwlink/?LinkId=180520).</span></span> <span data-ttu-id="25f47-134">Durch Ausführen einer Select-Abfrage in den Tabellen werden die Daten in den Nachverfolgungsdatensätzen angezeigt, die in den jeweiligen Tabellen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="25f47-134">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="25f47-135">So installieren Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="25f47-135">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="25f47-136">Führen Sie das Skript "Tdrackingcleanup.cmd" im Beispielverzeichnis (\WF\Basic\Tracking\SqlTracking) aus.</span><span class="sxs-lookup"><span data-stu-id="25f47-136">Run theTrackingcleanup.cmd script in the sample directory (\WF\Basic\Tracking\SqlTracking).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25f47-137">"Trackingcleanup.cmd" versucht, die Datenbank in SQL Express auf dem lokalen Computer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="25f47-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="25f47-138">Wenn Sie eine andere SQL Server-Instanz verwenden, bearbeiten Sie "Trackingcleanup.cmd".</span><span class="sxs-lookup"><span data-stu-id="25f47-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="25f47-139">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="25f47-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="25f47-140">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="25f47-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="25f47-141">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="25f47-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="25f47-142">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="25f47-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a><span data-ttu-id="25f47-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25f47-143">See Also</span></span>  
 [<span data-ttu-id="25f47-144">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="25f47-144">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
