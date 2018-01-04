---
title: Verwenden von Leistungsindikatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef5a499e6d940e45e0c9aab093b0a1c00bb6cc32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-performance-counters"></a><span data-ttu-id="5b71f-102">Verwenden von Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="5b71f-102">Using Performance Counters</span></span>
<span data-ttu-id="5b71f-103">In diesem Beispiel wird veranschaulicht, wie auf [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Leistungsindikatoren zugegriffen wird und wie benutzerdefinierte Leistungsindikatoren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5b71f-103">This sample demonstrates how to access [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="5b71f-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5b71f-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b71f-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="5b71f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="5b71f-106">In diesem Beispiel ruft der Client die vier Methoden des `ICalculator`-Diensts auf.</span><span class="sxs-lookup"><span data-stu-id="5b71f-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="5b71f-107">Der Client setzt dies fort, bis er vom Benutzer unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="5b71f-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="5b71f-108">Der Dienst bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="5b71f-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="5b71f-109">Die Leistungsindikatoren sind im Diagnoseabschnitt der Datei "Web.config" für diesen Dienst aktiviert, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5b71f-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="5b71f-110">Diese Aufgabe kann auch erfolgen mithilfe der [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5b71f-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="5b71f-111">Wenn Leistungsindikatoren aktiviert sind, wird die ganze Suite von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Leistungsindikatoren für den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b71f-111">When performance counters are enabled, the entire suite of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters is enabled for the service.</span></span> <span data-ttu-id="5b71f-112">.NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="5b71f-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="5b71f-113">Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="5b71f-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5b71f-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="5b71f-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5b71f-115">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5b71f-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="5b71f-116">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5b71f-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="5b71f-117">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5b71f-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="5b71f-118">So zeigen Sie Leistungsdaten an</span><span class="sxs-lookup"><span data-stu-id="5b71f-118">To view performance data</span></span>  
  
1.  <span data-ttu-id="5b71f-119">Starten Sie das Leistungsmonitor-Tool, indem Sie auf **starten**, **ausführen...** , geben Sie `perfmon` , und klicken Sie auf **"OK".** , oder wählen Sie in der Systemsteuerung **Verwaltung** und doppelklicken Sie auf **Leistung**.</span><span class="sxs-lookup"><span data-stu-id="5b71f-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b71f-120">Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b71f-120">You cannot add counters until the sample code is running.</span></span>  
  
2.  <span data-ttu-id="5b71f-121">Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="5b71f-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3.  <span data-ttu-id="5b71f-122">Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Leistungsindikatoren, indem Sie mit der rechten Maustaste in des Diagrammbereich klicken und auswählen **Leistungsindikatoren hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5b71f-122">Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="5b71f-123">In der **Leistungsindikatoren hinzufügen** wählen Sie im Dialogfeld **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 oder ServiceModelService 3.0.0.0** in das Leistungsobjekt "" im Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="5b71f-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="5b71f-124">Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5b71f-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b71f-125">Es werden keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Leistungsindikatoren für einen Dienst angezeigt, wenn keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b71f-125">There are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters for a service if there are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="5b71f-126">So aktivieren Sie Indikatoren mit dem Konfigurations-Editor</span><span class="sxs-lookup"><span data-stu-id="5b71f-126">To use the Configuration Editor to enable counters</span></span>  
  
1.  <span data-ttu-id="5b71f-127">Öffnen Sie eine Instanz von SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="5b71f-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2.  <span data-ttu-id="5b71f-128">Klicken Sie auf das Menü Datei auf **öffnen** , und klicken Sie dann auf **Datei "App.config"...** .</span><span class="sxs-lookup"><span data-stu-id="5b71f-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3.  <span data-ttu-id="5b71f-129">Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".</span><span class="sxs-lookup"><span data-stu-id="5b71f-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4.  <span data-ttu-id="5b71f-130">Klicken Sie auf **Diagnose** in der Konfigurationsstruktur.</span><span class="sxs-lookup"><span data-stu-id="5b71f-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5.  <span data-ttu-id="5b71f-131">Zum ein-/ausschalten **Leistungsindikator** in der **Diagnose** Fenster werden "All" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b71f-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6.  <span data-ttu-id="5b71f-132">Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.</span><span class="sxs-lookup"><span data-stu-id="5b71f-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b71f-133">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5b71f-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5b71f-134">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5b71f-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5b71f-135">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5b71f-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5b71f-136">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5b71f-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="5b71f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b71f-137">See Also</span></span>  
 [<span data-ttu-id="5b71f-138">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="5b71f-138">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
