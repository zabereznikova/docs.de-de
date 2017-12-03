---
title: SOAP- und HTTP-Endpunkte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d122512a16a0959d60bfa658d96aa87a52e40299
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="soap-and-http-endpoints"></a><span data-ttu-id="31b86-102">SOAP- und HTTP-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="31b86-102">SOAP and HTTP Endpoints</span></span>
<span data-ttu-id="31b86-103">In diesem Beispiel wird veranschaulicht, wie ein RPC-basierter Dienst implementiert und im SOAP-Format verfügbar gemacht und die "Plain Old XML" (POX) formatieren Sie mit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Webprogrammiermodell.</span><span class="sxs-lookup"><span data-stu-id="31b86-103">This sample demonstrates how to implement an RPC-based service and expose it in the SOAP format and the "Plain Old XML" (POX) format using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Programming model.</span></span> <span data-ttu-id="31b86-104">Finden Sie unter der [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Sample detaillierte Informationen über die HTTP-Bindung für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="31b86-104">See the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample for more details about the HTTP binding for the service.</span></span> <span data-ttu-id="31b86-105">Dieses Beispiel befasst sich mit den Details der Bereitstellung des gleichen Diensts über SOAP und HTTP, allerdings mit unterschiedlichen Bindungen.</span><span class="sxs-lookup"><span data-stu-id="31b86-105">This sample focuses on the details that pertain to exposing the same service over SOAP and HTTP using different bindings.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="31b86-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="31b86-106">Demonstrates</span></span>  
 <span data-ttu-id="31b86-107">Die Bereitstellung eines RPC-Diensts über SOAP und HTTP mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31b86-107">Exposing an RPC service over SOAP and HTTP using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="31b86-108">Diskussion</span><span class="sxs-lookup"><span data-stu-id="31b86-108">Discussion</span></span>  
 <span data-ttu-id="31b86-109">Dieses Beispiel besteht aus zwei Komponenten: einem Webanwendungsprojekt (Dienst), das einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst enthält, und einer Konsolenanwendung (Client), mit dem Dienstvorgänge mit SOAP- und HTTP-Bindungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="31b86-109">This sample consists of two components: a Web Application project (Service) that contains a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service and a console application (Client) that invokes service operations using SOAP and HTTP bindings.</span></span>  
  
 <span data-ttu-id="31b86-110">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst macht 2 Vorgänge verfügbar – `GetData` und `PutData` –, die die als Eingabe übergebene Zeichenfolge wiederholen.</span><span class="sxs-lookup"><span data-stu-id="31b86-110">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service exposes 2 operations –`GetData` and `PutData` – that echo the string that was passed as input.</span></span> <span data-ttu-id="31b86-111">Die Dienstvorgänge werden mit <xref:System.ServiceModel.Web.WebGetAttribute> und <xref:System.ServiceModel.Web.WebInvokeAttribute> kommentiert.</span><span class="sxs-lookup"><span data-stu-id="31b86-111">The service operations are annotated with <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="31b86-112">Diese Attribute steuern die HTTP-Projektion dieser Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="31b86-112">These attributes control the HTTP projection of these operations.</span></span> <span data-ttu-id="31b86-113">Außerdem werden sie mit <xref:System.ServiceModel.OperationContractAttribute> kommentiert, sodass sie über SOAP-Bindungen verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="31b86-113">In addition, they are annotated with <xref:System.ServiceModel.OperationContractAttribute>, which enables them to be exposed over SOAP bindings.</span></span> <span data-ttu-id="31b86-114">Die `PutData`-Methode des Diensts löst eine <xref:System.ServiceModel.Web.WebFaultException> aus, die mithilfe des HTTP-Statuscodes über HTTP zurückgesendet und als SOAP-Fehler über SOAP zurückgesendet wird.</span><span class="sxs-lookup"><span data-stu-id="31b86-114">The service’s `PutData` method throws a <xref:System.ServiceModel.Web.WebFaultException>, which gets sent back over HTTP using the HTTP status code and gets sent back over SOAP as a SOAP fault.</span></span>  
  
 <span data-ttu-id="31b86-115">Mit der Datei Web.config wird der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst mit 3 Endpunkten konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="31b86-115">The Web.config file configures the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with 3 endpoints:</span></span>  
  
-   <span data-ttu-id="31b86-116">Der ~/service.svc/mex-Endpunkt, der die Dienstmetadaten für den Zugriff durch SOAP-basierte Clients verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="31b86-116">The ~/service.svc/mex endpoint that exposes the service metadata for access by SOAP-based clients.</span></span>  
  
-   <span data-ttu-id="31b86-117">Der ~/service.svc/http-Endpunkt, der es Clients ermöglicht, über die HTTP-Bindung auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="31b86-117">The ~/service.svc/http endpoint that enables clients to access the service using the HTTP binding.</span></span>  
  
-   <span data-ttu-id="31b86-118">Der ~/service.svc/soap-Endpunkt, der es den Clients ermöglicht, über die SOAP über HTTP-Bindung auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="31b86-118">The ~/service.svc/soap endpoint that allows the clients to access the service using the SOAP over HTTP binding.</span></span>  
  
 <span data-ttu-id="31b86-119">Der HTTP-Endpunkt wird mit einem <`webHttp`>-Standardendpunkt konfiguriert, bei dem `helpEnabled` auf `true` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="31b86-119">The HTTP endpoint is configured with a <`webHttp`> standard endpoint which has `helpEnabled` set to `true`.</span></span> <span data-ttu-id="31b86-120">Als Ergebnis stellt der Dienst eine XHTML-basierte Hilfeseite unter ~/service.svc/http/help bereit, mit der HTTP-basierte Clients auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="31b86-120">As a result, the service exposes an XHTML based help page at ~/service.svc/http/help that HTTP-based clients can use to access the service.</span></span>  
  
 <span data-ttu-id="31b86-121">Das Clientprojekt veranschaulicht den Zugriff auf den Dienst über einen SOAP-Proxy (generiert durch **Hinzufügen eines Dienstverweises**) und den Zugriff auf den Dienst mit <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="31b86-121">The client project demonstrates accessing the service using a SOAP proxy (generated through **Add Service Reference**) and accessing the service using <xref:System.Net.WebClient>.</span></span>  
  
 <span data-ttu-id="31b86-122">Das Beispiel besteht aus einem im Web gehosteten Dienst und einer Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="31b86-122">The sample consists of a Web-hosted service and a console application.</span></span> <span data-ttu-id="31b86-123">Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="31b86-123">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="31b86-124">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="31b86-124">To run the sample</span></span>  
  
1.  <span data-ttu-id="31b86-125">Öffnen Sie die Projektmappe für das Beispiel mit den SOAP- und HTTP-Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="31b86-125">Open the solution for the SOAP and HTTP Endpoints Sample.</span></span>  
  
2.  <span data-ttu-id="31b86-126">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="31b86-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="31b86-127">Wenn es nicht bereits geöffnet ist, drücken Sie STRG + W, S, öffnen Sie die **Projektmappen-Explorer** Fenster.</span><span class="sxs-lookup"><span data-stu-id="31b86-127">If it is not already open, press CTRL+W, S to open the **Solution Explorer** window.</span></span>  
  
4.  <span data-ttu-id="31b86-128">Aus der **Projektmappen-Explorer** Fenster mit der rechten Maustaste die **Service** Projekt, und platzieren Sie den Cursor über die **Debuggen** Kontextmenüoption, damit die **neue starten Instanz** Kontextmenü wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31b86-128">From the **Solution Explorer** window, right-click the **Service** project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="31b86-129">Klicken Sie auf **neue Instanz starten**.</span><span class="sxs-lookup"><span data-stu-id="31b86-129">Click **Start New Instance**.</span></span> <span data-ttu-id="31b86-130">Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="31b86-130">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="31b86-131">Aus dem Projektmappen-Explorer-Fenster mit der rechten Maustaste des Clientprojekts, und platzieren Sie den Cursor über die **Debuggen** Kontextmenüoption, damit die **neue Instanz starten** Kontextmenü wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31b86-131">From the Solution Explorer windows, right-click the Client project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="31b86-132">Klicken Sie auf **neue Instanz starten**.</span><span class="sxs-lookup"><span data-stu-id="31b86-132">Click **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="31b86-133">Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31b86-133">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="31b86-134">Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.</span><span class="sxs-lookup"><span data-stu-id="31b86-134">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="31b86-135">Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="31b86-135">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="31b86-136">Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="31b86-136">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="31b86-137">Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.</span><span class="sxs-lookup"><span data-stu-id="31b86-137">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="31b86-138">Klicken Sie im Windows-Infobereich mit der rechten Maustaste des Symbol "ASP.NET Development Server", und wählen **beenden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="31b86-138">In the Windows Notification Area, right-click the ASP.NET development server icon and select **Stop** from the context menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31b86-139">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="31b86-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="31b86-140">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="31b86-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="31b86-141">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="31b86-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="31b86-142">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="31b86-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
