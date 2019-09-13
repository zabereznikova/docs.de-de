---
title: AJAX-Dienst ohne Konfiguration
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 06af14ad551de0e56700b044aea25b59dbf890ce
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895133"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="d3cc5-102">AJAX-Dienst ohne Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d3cc5-102">AJAX Service Without Configuration</span></span>

<span data-ttu-id="d3cc5-103">In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) verwendet wird, um einen grundlegenden ASP.NET Asynchronous JavaScript and XML (Ajax)-Dienst (einen Dienst, auf den Sie mithilfe von JavaScript-Code von einem Webbrowser Client aus zugreifen können) zu erstellen, ohne eine Konfiguration zu verwenden. Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="d3cc5-104">Der Dienst verwendet eine besondere Syntax in der .svc-Datei zur automatischen Aktivierung eines AJAX-Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>

<span data-ttu-id="d3cc5-105">Die AJAX-Unterstützung in WCF ist für die Verwendung mit ASP.net `ScriptManager` AJAX über das-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="d3cc5-106">Ein Beispiel für die Verwendung von WCF mit ASP.NET AJAX finden Sie in den [AJAX-Beispielen](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="d3cc5-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d3cc5-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="d3cc5-108">Dieses Beispiel basiert auf dem Beispiel "AJAX-Dienst mit HTTP POST".</span><span class="sxs-lookup"><span data-stu-id="d3cc5-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="d3cc5-109">Wie im Beispiel für den [grundlegenden AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) - <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> Dienst beschrieben, wird zum Hosten des Diensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

<span data-ttu-id="d3cc5-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> fügt dem Dienst automatisch einen <xref:System.ServiceModel.Description.WebScriptEndpoint> hinzu.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="d3cc5-111">Wenn keine Konfigurationsänderungen am Endpunkt vorgenommen werden müssen, kann der Abschnitt `<system.ServiceModel>` vollständig aus der Datei "Web.config" für den Dienst entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="d3cc5-112">Die Datei Web.config enthält einige ASP.NET-Einstellungen, die von ConfigFreeClientPage.aspx verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="d3cc5-113">Wenn dies nicht der Fall wäre, könnte die gesamte Datei Web.config entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-113">If that were not the case, the entire Web.config file could be removed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3cc5-114">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d3cc5-115">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="d3cc5-116">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d3cc5-117">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d3cc5-118">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d3cc5-118">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="d3cc5-119">Stellen Sie sicher, dass Sie die Setup Anweisungen [für die Windows Communication Foundation Beispiele im einmaligen Setup Verfahren](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="d3cc5-120">Erstellen Sie die Projekt Mappe ConfigFreeAjaxService. sln, wie unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="d3cc5-121">Navigieren Sie `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` zu (Öffnen Sie ConfigFreeClientPage. aspx nicht innerhalb des Projektverzeichnisses im Browser).</span><span class="sxs-lookup"><span data-stu-id="d3cc5-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>

> [!NOTE]
> <span data-ttu-id="d3cc5-122">Stellen Sie bei der Ausführung dieses Beispiels sicher, dass für den Ordner ServiceModelSamples in IIS nicht gleichzeitig anonyme Authentifizierung und Windows-Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="d3cc5-123">Wenn das der Fall ist, deaktivieren Sie die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="d3cc5-124">Sobald Sie das Beispiel ausgeführt haben, aktivieren Sie die Windows-Authentifizierung und führen "iisreset" aus.</span><span class="sxs-lookup"><span data-stu-id="d3cc5-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>

## <a name="see-also"></a><span data-ttu-id="d3cc5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3cc5-125">See also</span></span>

- [<span data-ttu-id="d3cc5-126">Einfacher AJAX-Dienst</span><span class="sxs-lookup"><span data-stu-id="d3cc5-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
