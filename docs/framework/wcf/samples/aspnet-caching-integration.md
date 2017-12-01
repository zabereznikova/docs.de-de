---
title: ASP.NET-Zwischenspeicherungsintegration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8830f1c19b7a91d6c22d3b5955624c7d8a86f5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="ecf0c-102">ASP.NET-Zwischenspeicherungsintegration</span><span class="sxs-lookup"><span data-stu-id="ecf0c-102">ASP.NET Caching Integration</span></span>
<span data-ttu-id="ecf0c-103">In diesem Beispiel wird gezeigt, wie der ASP.NET-Ausgabecache mit dem WCF-WEB HTTP-Programmiermodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="ecf0c-104">Finden Sie unter der [grundlegenden Ressourcendiensts](../../../../docs/framework/wcf/samples/basic-resource-service.md) Beispiel eine selbst gehostete Version dieses Szenarios, die die dienstimplementierung ausführlich erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-104">Please see the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample for a self-hosted version of this scenario that discusses the service implementation in depth.</span></span> <span data-ttu-id="ecf0c-105">Dieses Thema befasst sich mit den Integrationsfunktion des ASP.NET-Ausgabecaches.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-105">This topic focuses on the ASP.NET output cache integration feature.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ecf0c-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="ecf0c-106">Demonstrates</span></span>  
 <span data-ttu-id="ecf0c-107">Integration in den ASP.NET-Ausgabecache</span><span class="sxs-lookup"><span data-stu-id="ecf0c-107">Integration with the ASP.NET Output Cache</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ecf0c-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ecf0c-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ecf0c-110">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ecf0c-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a><span data-ttu-id="ecf0c-112">Diskussion</span><span class="sxs-lookup"><span data-stu-id="ecf0c-112">Discussion</span></span>  
 <span data-ttu-id="ecf0c-113">Im Beispiel wird das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> verwendet, um den ASP.NET-Ausgabecache mit dem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-113">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="ecf0c-114">Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> wird auf Dienstvorgänge angewendet und gibt den Namen eines Cacheprofils in einer Konfigurationsdatei an, die auf Antworten vom angegebenen Vorgang angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-114">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>  
  
 <span data-ttu-id="ecf0c-115">In der Datei Service.cs des Beispielprojekts Dienst sowohl den `GetCustomer` und `GetCustomers` Vorgänge sind mit markierten der <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, stellt den cacheprofilnamen "CacheFor60Seconds".</span><span class="sxs-lookup"><span data-stu-id="ecf0c-115">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="ecf0c-116">In der Datei "Web.config" des Dienstprojekts wird das Cacheprofil "CacheFor60Seconds" bereitgestellt, unter dem <`caching`> Element des <`system.web`>.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-116">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="ecf0c-117">Für dieses Cacheprofil wird der Wert der `duration` -Attribut ist "60", dieses Profil zugeordnete Antworten 60 Sekunden lang im ASP.NET-Ausgabecache zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-117">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="ecf0c-118">Für dieses Cacheprofil der `varmByParam` -Attribut festgelegt ist; bei Anforderungen mit anderen Werten für "formatieren" der `format` -Abfragezeichenfolgenparameter die Antworten getrennt zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-118">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="ecf0c-119">Abschließend wird des Cacheprofils des `varyByHeader` -Attribut auf "Akzeptieren" festgelegt ist, müssen Anforderungen mit anderen Accept-Headerwerten getrennt zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-119">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>  
  
 <span data-ttu-id="ecf0c-120">Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-120">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="ecf0c-121">Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-121">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="ecf0c-122">Es ist auch möglich, mit anderen .NET Framework-Klassen wie der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Kanalfactory und <xref:System.Net.WebClient> auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-122">It is also possible to access the service using other .NET Framework classes like the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="ecf0c-123">Weitere Beispiele im SDK (z. B. die [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) Beispiel und die [automatische Formatauswahl](../../../../docs/framework/wcf/samples/automatic-format-selection.md) Beispiel) veranschaulicht, wie diese Klassen verwenden, um die Kommunikation mit einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-123">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample and the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample) illustrate how to use these classes to communicate with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
## <a name="to-run-the-sample"></a><span data-ttu-id="ecf0c-124">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="ecf0c-124">To run the sample</span></span>  
 <span data-ttu-id="ecf0c-125">Das Beispiel umfasst drei Projekte:</span><span class="sxs-lookup"><span data-stu-id="ecf0c-125">The sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="ecf0c-126">**Dienst**: ein Webanwendungsprojekt, der einen gehosteten WCF-HTTP-Dienst in ASP.NET enthält.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-126">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>  
  
-   <span data-ttu-id="ecf0c-127">**Client**: ein Konsolenanwendungsprojekt, das Aufrufe an den Dienst ausführt.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-127">**Client**: A console application project that makes calls to the service.</span></span>  
  
-   <span data-ttu-id="ecf0c-128">**Allgemeine**: eine freigegebene Bibliothek, die die vom Client und Dienst verwendeten Kundentyp enthält.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-128">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>  
  
 <span data-ttu-id="ecf0c-129">Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-129">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="ecf0c-130">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="ecf0c-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="ecf0c-131">Öffnen Sie die Projektmappe für das Beispiel der Integration von ASP.NET-Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-131">Open the solution for the ASP.NET Caching Integration Sample.</span></span>  
  
2.  <span data-ttu-id="ecf0c-132">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="ecf0c-133">Wenn die **Projektmappen-Explorer** Fenster nicht bereits geöffnet ist, drücken Sie STRG + W + s..</span><span class="sxs-lookup"><span data-stu-id="ecf0c-133">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>  
  
4.  <span data-ttu-id="ecf0c-134">Aus der **Projektmappen-Explorer** Fenster, mit der rechten Maustaste die **Service** Projekt, und wählen Sie **neue Instanz starten**.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-134">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="ecf0c-135">Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-135">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="ecf0c-136">Aus der **Projektmappen-Explorer** Fenster, mit der rechten Maustaste die **Client** Projekt, und wählen Sie **neue Instanz starten**.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-136">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="ecf0c-137">Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-137">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="ecf0c-138">Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-138">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="ecf0c-139">Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-139">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="ecf0c-140">Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-140">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="ecf0c-141">Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-141">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="ecf0c-142">Klicken Sie im Windows-Infobereich mit der rechten Maustaste, klicken Sie auf das Symbol "ASP.NET Development Server", und wählen **beenden**.</span><span class="sxs-lookup"><span data-stu-id="ecf0c-142">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
