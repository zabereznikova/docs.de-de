---
title: AJAX-Dienst ohne Konfiguration
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: f12b0fad97c9f43397f3b202800943e6d061aa53
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45647394"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="189d7-102">AJAX-Dienst ohne Konfiguration</span><span class="sxs-lookup"><span data-stu-id="189d7-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="189d7-103">Dieses Beispiel veranschaulicht, wie Windows Communication Foundation (WCF) zum Erstellen eines einfachen (ASP.NET Asynchronous JavaScript and XML (AJAX)-Diensts (ein Dienst, die Sie mithilfe von JavaScript-Codes über einen Webbrowserclient zugreifen können) ohne Konfiguration Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="189d7-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="189d7-104">Der Dienst verwendet eine besondere Syntax in der .svc-Datei zur automatischen Aktivierung eines AJAX-Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="189d7-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="189d7-105">AJAX-Unterstützung in WCF ist optimiert für die Verwendung mit ASP.NET AJAX über das `ScriptManager` Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="189d7-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="189d7-106">Ein Beispiel der Verwendung von WCF mit ASP.NET AJAX finden Sie unter den [Ajax-Beispielen](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="189d7-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="189d7-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="189d7-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="189d7-108">Dieses Beispiel basiert auf dem Beispiel "AJAX-Dienst mit HTTP POST".</span><span class="sxs-lookup"><span data-stu-id="189d7-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="189d7-109">Siehe die [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> wird verwendet, um den Dienst zu hosten.</span><span class="sxs-lookup"><span data-stu-id="189d7-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="189d7-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> fügt dem Dienst automatisch einen <xref:System.ServiceModel.Description.WebScriptEndpoint> hinzu.</span><span class="sxs-lookup"><span data-stu-id="189d7-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="189d7-111">Wenn keine Konfigurationsänderungen am Endpunkt vorgenommen werden müssen, kann der Abschnitt `<system.ServiceModel>` vollständig aus der Datei "Web.config" für den Dienst entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="189d7-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="189d7-112">Die Datei Web.config enthält einige ASP.NET-Einstellungen, die von ConfigFreeClientPage.aspx verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="189d7-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="189d7-113">Wenn dies nicht der Fall wäre, könnte die gesamte Datei Web.config entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="189d7-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="189d7-114">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="189d7-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="189d7-115">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="189d7-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="189d7-116">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="189d7-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="189d7-117">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="189d7-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="189d7-118">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="189d7-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="189d7-119">Stellen Sie sicher, dass Sie die setupanweisungen in ausführen [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="189d7-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="189d7-120">Erstellen Sie die Lösung ConfigFreeAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="189d7-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="189d7-121">Navigieren Sie zu http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (Öffnen Sie ConfigFreeClientPage.aspx nicht im Browser aus dem Projektverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="189d7-121">Navigate to http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="189d7-122">Stellen Sie bei der Ausführung dieses Beispiels sicher, dass für den Ordner ServiceModelSamples in IIS nicht gleichzeitig anonyme Authentifizierung und Windows-Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="189d7-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="189d7-123">Wenn das der Fall ist, deaktivieren Sie die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="189d7-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="189d7-124">Sobald Sie das Beispiel ausgeführt haben, aktivieren Sie die Windows-Authentifizierung und führen "iisreset" aus.</span><span class="sxs-lookup"><span data-stu-id="189d7-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189d7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="189d7-125">See Also</span></span>  
 [<span data-ttu-id="189d7-126">Einfacher AJAX-Dienst</span><span class="sxs-lookup"><span data-stu-id="189d7-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
