---
title: Konfigurationsbasierte Aktivierung
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: 3ac4edd2a51e4ed8a5c0b7e73d7d1afa31334c33
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809913"
---
# <a name="configuration-based-activation"></a><span data-ttu-id="4d544-102">Konfigurationsbasierte Aktivierung</span><span class="sxs-lookup"><span data-stu-id="4d544-102">Configuration-Based Activation</span></span>
<span data-ttu-id="4d544-103">Dieses Beispiel veranschaulicht die Windows Communication Foundation (WCF)-Dienste zu aktivieren, ohne eine SVC-Datei.</span><span class="sxs-lookup"><span data-stu-id="4d544-103">This sample demonstrates how to activate Windows Communication Foundation (WCF) services without requiring a .svc file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d544-104">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="4d544-104">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4d544-105">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="4d544-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4d544-106">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4d544-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4d544-107">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4d544-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="4d544-108">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="4d544-108">Sample Details</span></span>  
 <span data-ttu-id="4d544-109">In diesem Beispiel wird der Client den WCF-Testclient und der Dienst in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4d544-109">In this sample, the client is the WCF test client and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d544-110">Die Setup- und Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="4d544-110">The setup and build instructions for this sample are located at the end of this topic.</span></span>  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a><span data-ttu-id="4d544-111">Aktivierung von Diensten ohne SVC-Datei</span><span class="sxs-lookup"><span data-stu-id="4d544-111">Activation of services without requiring a .svc file</span></span>  
 <span data-ttu-id="4d544-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] war eine SVC-Datei zum Aktivieren eines Diensts erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d544-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], a .svc file was required for activating a service.</span></span> <span data-ttu-id="4d544-113">Das führte zu zusätzlichem Verwaltungsmehraufwand, da neben der Anwendung eine weitere Datei bereitgestellt und verwaltet werden musste.</span><span class="sxs-lookup"><span data-stu-id="4d544-113">This caused additional management overhead, because an additional file was required to be deployed and maintained along with the application.</span></span> <span data-ttu-id="4d544-114">Seit der Veröffentlichung von [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] können die Aktivierungskomponenten mit der Anwendungskonfigurationsdatei konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4d544-114">With the release of [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], the activation components can be configured using the application configuration file.</span></span>  
  
 <span data-ttu-id="4d544-115">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] wird ein neues Konfigurationselement (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in den <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> der Anwendungskonfigurationsdatei eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4d544-115">[!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] introduces a new configuration element (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in the <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> of the application configuration file.</span></span> <span data-ttu-id="4d544-116">Die <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>-Auflistung akzeptiert eine Auflistung von Diensten für die Aktivierung, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d544-116">The <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> collection accepts a collection of services to activate, as shown in the following code example.</span></span>  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 <span data-ttu-id="4d544-117">Die Konfiguration ähnelt offensichtlich der Konfiguration von SVC-Dateien.</span><span class="sxs-lookup"><span data-stu-id="4d544-117">The observation to make is the configuration looks very similar to the configuration of .svc files.</span></span> <span data-ttu-id="4d544-118">Ein zusätzliches Attribut, das eingeführt wird, ist das `relativeAddress`-Attribut, das die Adresse des Diensts bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4d544-118">An additional attribute that is introduced is the `relativeAddress` that provides the address of the service.</span></span> <span data-ttu-id="4d544-119">Die relative Adresse ist auch der virtuelle Pfad für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="4d544-119">The relative address is also the virtual path for the service.</span></span> <span data-ttu-id="4d544-120">Der Host ruft die Datei Web.config aus dem `virtualPath`-Speicherort ab, wenn sie vorhanden ist; andernfalls führt der Host im übergeordneten Ordner eine rekursive Suche durch.</span><span class="sxs-lookup"><span data-stu-id="4d544-120">The host retrieves the Web.config file of the file from the `virtualPath` location, if present; otherwise the host searches its parent folder recursively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d544-121">Dieses Beispiel muss in IIS gehostet werden, um zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="4d544-121">This sample requires hosting in IIS to function.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4d544-122">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d544-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="4d544-123">Öffnen Sie die Datei Service.csproj mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d544-123">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Service.csproj file.</span></span>  
  
2.  <span data-ttu-id="4d544-124">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d544-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4d544-125">Testen Sie den Dienst, indem Sie WCFTestClient.exe ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d544-125">Test the service by running WCFTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="4d544-126">Navigieren Sie im [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] zum Ordner %SystemDrive%\Programme\Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="4d544-126">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE folder.</span></span>  
  
5.  <span data-ttu-id="4d544-127">Führen Sie WcfTestClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="4d544-127">Run WcfTestClient.exe.</span></span>  
  
6.  <span data-ttu-id="4d544-128">Legen Sie die MEX-Adresse des Diensts fest.</span><span class="sxs-lookup"><span data-stu-id="4d544-128">Set the MEX address of the service.</span></span>  
  
7.  <span data-ttu-id="4d544-129">Drücken Sie STRG+UMSCHALT+A, um die Dienstadresse festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4d544-129">Press CTRL+SHIFT+A to set the service address.</span></span>  
  
8.  <span data-ttu-id="4d544-130">Legen Sie die Adresse http://localhost/ServiceModelSamples/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="4d544-130">Set the address to http://localhost/ServiceModelSamples/Calculator.svc.</span></span>  
  
9. <span data-ttu-id="4d544-131">Führen Sie den `Add`-Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="4d544-131">Perform the `Add` operation.</span></span> <span data-ttu-id="4d544-132">Legen Sie den Wert für den `n1`-Parameter auf 10 und den Wert für den `n2`-Parameter auf 15 fest.</span><span class="sxs-lookup"><span data-stu-id="4d544-132">Set value on the `n1` parameter to 10 and set value on the `n2` parameter to 15.</span></span>  
  
10. <span data-ttu-id="4d544-133">Drücken Sie **Aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="4d544-133">Press **Invoke**.</span></span>  
  
     <span data-ttu-id="4d544-134">Das erwartete Ergebnis lautet 25.</span><span class="sxs-lookup"><span data-stu-id="4d544-134">The expected result is 25.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4d544-135">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="4d544-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4d544-136">Achten Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4d544-136">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4d544-137">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4d544-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="4d544-138">Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples-Anwendung in IIS einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4d544-138">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS.</span></span> <span data-ttu-id="4d544-139">Das Verzeichnis ServiceModelSamples sollte jetzt als IIS-Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4d544-139">The ServiceModelSamples directory should now appear as an IIS Application.</span></span>  
  
4.  <span data-ttu-id="4d544-140">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4d544-140">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d544-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d544-141">See Also</span></span>  
 [<span data-ttu-id="4d544-142">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="4d544-142">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
