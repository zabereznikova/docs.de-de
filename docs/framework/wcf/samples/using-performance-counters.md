---
title: Verwenden von Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 787a3d08b463980721fb207d029057e14618db5e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44214198"
---
# <a name="using-performance-counters"></a><span data-ttu-id="ea632-102">Verwenden von Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="ea632-102">Using Performance Counters</span></span>
<span data-ttu-id="ea632-103">In diesem Beispiel wird veranschaulicht, wie Zugriff auf Windows Communication Foundation (WCF)-Leistungsindikatoren und benutzerdefinierte Leistungsindikatoren erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea632-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="ea632-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ea632-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea632-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ea632-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ea632-106">In diesem Beispiel ruft der Client die vier Methoden des `ICalculator`-Diensts auf.</span><span class="sxs-lookup"><span data-stu-id="ea632-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="ea632-107">Der Client setzt dies fort, bis er vom Benutzer unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="ea632-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="ea632-108">Der Dienst bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="ea632-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="ea632-109">Die Leistungsindikatoren sind im Diagnoseabschnitt der Datei "Web.config" für diesen Dienst aktiviert, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ea632-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="ea632-110">Diese Aufgabe kann auch erfolgen mithilfe der [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ea632-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="ea632-111">Wenn Leistungsindikatoren aktiviert sind, wird die gesamte Suite von WCF-Leistungsindikatoren für den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ea632-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="ea632-112">.NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="ea632-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="ea632-113">Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="ea632-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ea632-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ea632-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ea632-115">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea632-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ea632-116">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ea632-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ea632-117">Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea632-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="ea632-118">So zeigen Sie Leistungsdaten an</span><span class="sxs-lookup"><span data-stu-id="ea632-118">To view performance data</span></span>  
  
1.  <span data-ttu-id="ea632-119">Starten Sie das Leistungsmonitor-Tool, indem Sie auf **starten**, **ausführen...** , geben Sie `perfmon` , und klicken Sie auf **"OK".** , oder wählen Sie in der Systemsteuerung, **Verwaltung** und doppelklicken Sie auf **Leistung**.</span><span class="sxs-lookup"><span data-stu-id="ea632-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea632-120">Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea632-120">You cannot add counters until the sample code is running.</span></span>  
  
2.  <span data-ttu-id="ea632-121">Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="ea632-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3.  <span data-ttu-id="ea632-122">Fügen Sie WCF-Leistungsindikatoren hinzu, indem Sie mit der rechten Maustaste in des Diagrammbereich klicken und auswählen **Leistungsindikatoren hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ea632-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="ea632-123">In der **Leistungsindikatoren hinzufügen** wählen Sie im Dialogfeld **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 oder ServiceModelService 3.0.0.0** im Leistungsobjekt im Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="ea632-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="ea632-124">Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ea632-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea632-125">Es sind keine WCF-Leistungsindikatoren für einen Dienst auf, wenn keine WCF-Dienste, die auf dem Computer vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ea632-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="ea632-126">So aktivieren Sie Indikatoren mit dem Konfigurations-Editor</span><span class="sxs-lookup"><span data-stu-id="ea632-126">To use the Configuration Editor to enable counters</span></span>  
  
1.  <span data-ttu-id="ea632-127">Öffnen Sie eine Instanz von SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="ea632-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2.  <span data-ttu-id="ea632-128">Klicken Sie auf im Menü Datei auf **öffnen** , und klicken Sie dann auf **Config-Datei...** .</span><span class="sxs-lookup"><span data-stu-id="ea632-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3.  <span data-ttu-id="ea632-129">Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".</span><span class="sxs-lookup"><span data-stu-id="ea632-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4.  <span data-ttu-id="ea632-130">Klicken Sie auf **Diagnose** in der Konfigurationsstruktur.</span><span class="sxs-lookup"><span data-stu-id="ea632-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5.  <span data-ttu-id="ea632-131">Umschalten **Leistungsindikator** in die **Diagnose** Fenster 'All' angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea632-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6.  <span data-ttu-id="ea632-132">Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.</span><span class="sxs-lookup"><span data-stu-id="ea632-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea632-133">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ea632-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ea632-134">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ea632-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ea632-135">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ea632-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ea632-136">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ea632-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="ea632-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea632-137">See Also</span></span>  
 [<span data-ttu-id="ea632-138">AppFabric-Überwachungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="ea632-138">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
