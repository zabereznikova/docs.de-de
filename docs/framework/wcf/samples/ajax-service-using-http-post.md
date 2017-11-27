---
title: AJAX-Dienst mit HTTP POST
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 004bb41ad1662ddd6518c25acc1cac36dda3339c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="c00d2-102">AJAX-Dienst mit HTTP POST</span><span class="sxs-lookup"><span data-stu-id="c00d2-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="c00d2-103">In diesem Beispiel wird die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zum Erstellen eines [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX)-Diensts veranschaulicht, der HTTP POST verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00d2-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="c00d2-104">Bei einem AJAX-Dienst handelt es sich um einen Dienst, auf den Sie mit einfachem JavaScript-Code von einem Webbrowserclient aus zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c00d2-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="c00d2-105">Dieses Beispiel baut auf den [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ; der einzige Unterschied zwischen den zwei Beispielen wird die Verwendung von HTTP POST anstelle von HTTP GET-Sample.</span><span class="sxs-lookup"><span data-stu-id="c00d2-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="c00d2-106">Die AJAX-Unterstützung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist für die Verwendung mit ASP.NET AJAX über das `ScriptManager`-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="c00d2-106">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="c00d2-107">Ein Beispiel der Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit ASP.NET AJAX finden Sie unter der [Ajax-Beispielen](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="c00d2-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c00d2-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c00d2-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c00d2-109">Der Dienst im folgenden Beispiel ist ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst ohne AJAX-spezifischen Code.</span><span class="sxs-lookup"><span data-stu-id="c00d2-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="c00d2-110">Wenn die <xref:System.ServiceModel.Web.WebInvokeAttribute> -Attribut angewendet wird, in einem Vorgang oder die <xref:System.ServiceModel.Web.WebGetAttribute> -Attribut nicht angewendet wird, wird das standardmäßige HTTP-Verb ("POST") verwendet.</span><span class="sxs-lookup"><span data-stu-id="c00d2-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="c00d2-111">POST-Anforderungen sind schwieriger zu erstellen als GET-Anforderungen, sie werden jedoch nicht zwischengespeichert. Verwenden Sie POST-Anforderungen für alle Vorgänge, bei denen keine Zwischenspeicherung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c00d2-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
```  
  
 <span data-ttu-id="c00d2-112">Erstellen Sie im Dienst mithilfe von <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> einen AJAX-Endpunkt wie im Beispiel "Einfacher AJAX-Dienst".</span><span class="sxs-lookup"><span data-stu-id="c00d2-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="c00d2-113">Im Gegensatz zu GET-Anforderungen können Sie POST-Dienste nicht aus dem Browser aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c00d2-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="c00d2-114">Das Navigieren zu http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 führt beispielsweise zu einem Fehler, da der POST-Dienst erwartet, dass der `n1`-Parameter und der `n2`-Parameter im Nachrichtentext (im JSON-Format) und nicht in der URL gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c00d2-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="c00d2-115">Die Clientwebseite "PostAjaxClientPage.aspx" enthält ASP.NET-Code zum Aufrufen des Diensts, wenn der Benutzer auf eine der Vorgangsschaltflächen auf der Seite klickt.</span><span class="sxs-lookup"><span data-stu-id="c00d2-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="c00d2-116">Der Dienst reagiert auf die gleiche Weise wie in der [einfacher AJAX-Dienst](../../../../docs/framework/wcf/samples/basic-ajax-service.md) Beispiel mit dem GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c00d2-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c00d2-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c00d2-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c00d2-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c00d2-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c00d2-119">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="c00d2-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c00d2-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c00d2-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c00d2-121">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c00d2-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c00d2-122">Stellen Sie sicher, dass Sie die setupanweisungen ausführen [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c00d2-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c00d2-123">Erstellen Sie die Projektmappe PostAjaxService.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c00d2-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="c00d2-124">Navigieren Sie zu http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (öffnen Sie "PostAjaxClientPage.aspx" nicht aus dem Projektverzeichnis im Browser).</span><span class="sxs-lookup"><span data-stu-id="c00d2-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00d2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c00d2-125">See Also</span></span>
