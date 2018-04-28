---
title: AJAX-Dienst ohne Konfiguration
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae16dc38c5508eac4a94d464e818f0b97d3b9e3b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="fabe3-102">AJAX-Dienst ohne Konfiguration</span><span class="sxs-lookup"><span data-stu-id="fabe3-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="fabe3-103">In diesem Beispiel wird die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zum Erstellen eines grundlegenden AJAX-Diensts (ASP.NET Asynchronous JavaScript and XML) ohne Verwendung von Konfigurationseinstellungen beschrieben. Ein AJAX-Dienst ist ein Dienst, auf den Sie durch die Verwendung eines JavaScript-Codes über einen Webbrowserclient zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fabe3-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="fabe3-104">Der Dienst verwendet eine besondere Syntax in der .svc-Datei zur automatischen Aktivierung eines AJAX-Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="fabe3-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="fabe3-105">Die AJAX-Unterstützung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist für die Verwendung mit ASP.NET AJAX über das `ScriptManager`-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="fabe3-105">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="fabe3-106">Ein Beispiel der Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter der [Ajax-Beispielen](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="fabe3-106">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fabe3-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="fabe3-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fabe3-108">Dieses Beispiel basiert auf dem Beispiel "AJAX-Dienst mit HTTP POST".</span><span class="sxs-lookup"><span data-stu-id="fabe3-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="fabe3-109">Wie in beschrieben die [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> wird verwendet, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="fabe3-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="fabe3-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> fügt dem Dienst automatisch einen <xref:System.ServiceModel.Description.WebScriptEndpoint> hinzu.</span><span class="sxs-lookup"><span data-stu-id="fabe3-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="fabe3-111">Wenn keine Konfigurationsänderungen am Endpunkt vorgenommen werden müssen, kann der Abschnitt `<system.ServiceModel>` vollständig aus der Datei "Web.config" für den Dienst entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fabe3-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="fabe3-112">Die Datei Web.config enthält einige ASP.NET-Einstellungen, die von ConfigFreeClientPage.aspx verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fabe3-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="fabe3-113">Wenn dies nicht der Fall wäre, könnte die gesamte Datei Web.config entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fabe3-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fabe3-114">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fabe3-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fabe3-115">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fabe3-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fabe3-116">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fabe3-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fabe3-117">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fabe3-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fabe3-118">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fabe3-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fabe3-119">Stellen Sie sicher, dass Sie die installationsanweisungen im ausführen [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fabe3-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fabe3-120">Erstellen Sie die Projektmappe ConfigFreeAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fabe3-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="fabe3-121">Navigieren Sie zu http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (Öffnen Sie ConfigFreeClientPage.aspx nicht im Browser aus dem Projektverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="fabe3-121">Navigate to http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fabe3-122">Stellen Sie bei der Ausführung dieses Beispiels sicher, dass für den Ordner ServiceModelSamples in IIS nicht gleichzeitig anonyme Authentifizierung und Windows-Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fabe3-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="fabe3-123">Wenn das der Fall ist, deaktivieren Sie die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fabe3-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="fabe3-124">Sobald Sie das Beispiel ausgeführt haben, aktivieren Sie die Windows-Authentifizierung und führen "iisreset" aus.</span><span class="sxs-lookup"><span data-stu-id="fabe3-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabe3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fabe3-125">See Also</span></span>  
 [<span data-ttu-id="fabe3-126">Einfacher AJAX-Dienst</span><span class="sxs-lookup"><span data-stu-id="fabe3-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
