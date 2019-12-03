---
title: ASP.NET-Zwischenspeicherungsintegration
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 23c10e56dba7daec2d1027de92e8252c8fe69055
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716175"
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="e6518-102">ASP.NET-Zwischenspeicherungsintegration</span><span class="sxs-lookup"><span data-stu-id="e6518-102">ASP.NET Caching Integration</span></span>

<span data-ttu-id="e6518-103">In diesem Beispiel wird gezeigt, wie der ASP.NET-Ausgabecache mit dem WCF-WEB HTTP-Programmiermodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6518-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="e6518-104">Dieses Thema befasst sich mit den Integrationsfunktion des ASP.NET-Ausgabecaches.</span><span class="sxs-lookup"><span data-stu-id="e6518-104">This topic focuses on the ASP.NET output cache integration feature.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e6518-105">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="e6518-105">Demonstrates</span></span>

<span data-ttu-id="e6518-106">Integration in den ASP.NET-Ausgabecache</span><span class="sxs-lookup"><span data-stu-id="e6518-106">Integration with the ASP.NET Output Cache</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6518-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e6518-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e6518-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e6518-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e6518-109">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e6518-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e6518-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e6518-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a><span data-ttu-id="e6518-111">Diskussion</span><span class="sxs-lookup"><span data-stu-id="e6518-111">Discussion</span></span>

<span data-ttu-id="e6518-112">Das Beispiel verwendet die <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, um das ASP.net-Ausgabe Caching mit dem Windows Communication Foundation (WCF)-Dienst zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="e6518-112">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="e6518-113">Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> wird auf Dienstvorgänge angewendet und gibt den Namen eines Cacheprofils in einer Konfigurationsdatei an, die auf Antworten vom angegebenen Vorgang angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6518-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>

<span data-ttu-id="e6518-114">In der Service.cs-Datei des Beispiel Dienst Projekts werden die `GetCustomer`-und `GetCustomers` Vorgänge mit dem <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>gekennzeichnet, das den Cache Profilnamen "CacheFor60Seconds" bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e6518-114">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="e6518-115">In der Datei "Web. config" des Dienst Projekts wird das Cache Profil "CacheFor60Seconds" unter dem <`caching`>-Element <`system.web`> bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e6518-115">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="e6518-116">Für dieses Cache Profil lautet der Wert des `duration`-Attributs "60", sodass die diesem Profil zugeordneten Antworten für 60 Sekunden im ASP.net-Ausgabe Cache zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e6518-116">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="e6518-117">Außerdem wird für dieses Cache Profil das `varmByParam`-Attribut auf "Format" festgelegt, sodass Anforderungen mit unterschiedlichen Werten für den `format` Abfrage Zeichenfolgen-Parameter separat zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e6518-117">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="e6518-118">Schließlich wird das `varyByHeader`-Attribut des Cache Profils auf "Accept" festgelegt, sodass Anforderungen mit unterschiedlichen Accept-Header Werten separat zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e6518-118">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>

<span data-ttu-id="e6518-119">Program.cs im Clientprojekt zeigt, wie ein Client dieser Art mit <xref:System.Net.HttpWebRequest> erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6518-119">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="e6518-120">Beachten Sie, dass dies nur eine Möglichkeit für den Zugriff auf einen WCF-Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6518-120">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="e6518-121">Es ist auch möglich, mit anderen .NET Framework Klassen wie der WCF-Kanalfactory und <xref:System.Net.WebClient>auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e6518-121">It is also possible to access the service using other .NET Framework classes like the WCF channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="e6518-122">Andere Beispiele im SDK (z. b. das Beispiel für den [grundlegenden HTTP-Dienst](../../../../docs/framework/wcf/samples/basic-http-service.md) ) veranschaulichen, wie diese Klassen verwendet werden, um mit einem WCF-Dienst zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e6518-122">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample) illustrate how to use these classes to communicate with a WCF service.</span></span>

## <a name="to-run-the-sample"></a><span data-ttu-id="e6518-123">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="e6518-123">To run the sample</span></span>

<span data-ttu-id="e6518-124">Das Beispiel umfasst drei Projekte:</span><span class="sxs-lookup"><span data-stu-id="e6518-124">The sample consists of three projects:</span></span>

- <span data-ttu-id="e6518-125">**Service**: ein Webanwendungs Projekt, das einen in ASP.net gehosteten WCF-HTTP-Dienst enthält.</span><span class="sxs-lookup"><span data-stu-id="e6518-125">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>

- <span data-ttu-id="e6518-126">**Client**: ein Konsolen Anwendungsprojekt, das Aufrufe an den Dienst ausführt.</span><span class="sxs-lookup"><span data-stu-id="e6518-126">**Client**: A console application project that makes calls to the service.</span></span>

- <span data-ttu-id="e6518-127">**Common**: eine freigegebene Bibliothek, die den vom Client und Dienst verwendeten Customer-Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="e6518-127">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>

<span data-ttu-id="e6518-128">Während die Clientkonsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="e6518-128">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>

#### <a name="to-run-the-sample"></a><span data-ttu-id="e6518-129">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="e6518-129">To run the sample</span></span>

1. <span data-ttu-id="e6518-130">Öffnen Sie die Projektmappe für das Beispiel der Integration von ASP.NET-Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="e6518-130">Open the solution for the ASP.NET Caching Integration Sample.</span></span>

2. <span data-ttu-id="e6518-131">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6518-131">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="e6518-132">Wenn das **Projektmappen-Explorer** Fenster nicht bereits geöffnet ist, drücken Sie STRG + W + S.</span><span class="sxs-lookup"><span data-stu-id="e6518-132">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>

4. <span data-ttu-id="e6518-133">Klicken Sie im **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **neue Instanz starten**aus.</span><span class="sxs-lookup"><span data-stu-id="e6518-133">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="e6518-134">Der ASP.NET-Entwicklungsserver, der den Dienst hostet, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="e6518-134">This launches the ASP.NET development server, which hosts the service.</span></span>

5. <span data-ttu-id="e6518-135">Klicken Sie im **Projektmappen-Explorer** Fenster mit der rechten Maustaste auf das **Client** Projekt, und wählen Sie **neue Instanz starten**aus.</span><span class="sxs-lookup"><span data-stu-id="e6518-135">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>

6. <span data-ttu-id="e6518-136">Im eingeblendeten Clientkonsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML-Hilfeseite für den ausgeführten Dienst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e6518-136">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="e6518-137">Sie können die HTML-Hilfeseite jederzeit anzeigen, indem sie den URI der Hilfeseite in einem Browser eingeben.</span><span class="sxs-lookup"><span data-stu-id="e6518-137">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>

7. <span data-ttu-id="e6518-138">Während das Beispiel ausgeführt wird, schreibt der Client den Status der aktuellen Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e6518-138">As the sample runs, the client writes the status of the current activity.</span></span>

8. <span data-ttu-id="e6518-139">Drücken Sie eine beliebige Taste, um die Clientkonsolenanwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e6518-139">Press any key to terminate the client console application.</span></span>

9. <span data-ttu-id="e6518-140">Drücken Sie UMSCHALT+F5, um das Debugging des Diensts zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e6518-140">Press SHIFT+F5 to stop debugging the service.</span></span>

10. <span data-ttu-id="e6518-141">Klicken Sie im Windows-Benachrichtigungsbereich mit der rechten Maustaste auf das ASP.NET Development Server-Symbol, **und wählen Sie**dann</span><span class="sxs-lookup"><span data-stu-id="e6518-141">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
