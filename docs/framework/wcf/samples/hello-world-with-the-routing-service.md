---
title: Hello World mit dem Routingdienst
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: ae0615c8cf2fa33f3bb363f77c0d06440b6afc13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743707"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="03364-102">Hello World mit dem Routingdienst</span><span class="sxs-lookup"><span data-stu-id="03364-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="03364-103">In diesem Beispiel wird der Windows Communication Foundation (WCF)-Routing Dienst veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="03364-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="03364-104">Der Routing Dienst ist eine WCF-Komponente, mit der Sie ganz einfach einen Inhalts basierten Router in Ihre Anwendung integrieren können.</span><span class="sxs-lookup"><span data-stu-id="03364-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="03364-105">In diesem Beispiel wird das standardmäßige WCF-Rechner Beispiel für die Kommunikation über den Routing Dienst angepasst.</span><span class="sxs-lookup"><span data-stu-id="03364-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="03364-106">In diesem Beispiel ist der Rechnerclient so konfiguriert, dass er Nachrichten an einen vom Router verfügbar gemachten Endpunkt sendet.</span><span class="sxs-lookup"><span data-stu-id="03364-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="03364-107">Der Routingdienst ist so konfiguriert, dass er alle gesendeten Nachrichten akzeptiert und diese an einen Endpunkt weiterleitet, der dem Rechnerdienst entspricht.</span><span class="sxs-lookup"><span data-stu-id="03364-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="03364-108">Somit werden vom Client gesendete Nachrichten vom Router empfangen und zum eigentlichen Rechnerdienst umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="03364-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="03364-109">Nachrichten vom Rechnerdienst werden an den Router zurückgesendet, der sie dann zurück an den Rechnerclient übergibt.</span><span class="sxs-lookup"><span data-stu-id="03364-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="03364-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="03364-110">To use this sample</span></span>

1. <span data-ttu-id="03364-111">Öffnen Sie mit Visual Studio 2012 die Datei "helloroutingservice. sln".</span><span class="sxs-lookup"><span data-stu-id="03364-111">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2. <span data-ttu-id="03364-112">Drücken Sie F5 oder STRG+UMSCHALT+B.</span><span class="sxs-lookup"><span data-stu-id="03364-112">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03364-113">Wenn Sie F5 drücken, wird der Rechnerclient automatisch gestartet.</span><span class="sxs-lookup"><span data-stu-id="03364-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="03364-114">Wenn Sie STRG+UMSCHALT+B (Erstellen) drücken, müssen Sie die folgenden Anwendungen selbst starten.</span><span class="sxs-lookup"><span data-stu-id="03364-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1. <span data-ttu-id="03364-115">Rechnerclient (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="03364-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2. <span data-ttu-id="03364-116">Rechnerdienst (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="03364-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3. <span data-ttu-id="03364-117">Routingdienst (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="03364-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3. <span data-ttu-id="03364-118">Drücken Sie die EINGABETASTE, um den Client zu starten.</span><span class="sxs-lookup"><span data-stu-id="03364-118">Press ENTER to start the client.</span></span>

     <span data-ttu-id="03364-119">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03364-119">You should see the following output:</span></span>

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="03364-120">Konfigurierbar über Code oder App.Config</span><span class="sxs-lookup"><span data-stu-id="03364-120">Configurable via Code or App.Config</span></span>
 <span data-ttu-id="03364-121">Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert.</span><span class="sxs-lookup"><span data-stu-id="03364-121">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="03364-122">Sie können außerdem den Namen der Datei App.config ändern, damit er nicht erkannt wird, und die Auskommentierung des Methodenaufrufs von ConfigureRouterViaCode() aufheben.</span><span class="sxs-lookup"><span data-stu-id="03364-122">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="03364-123">Beide Methoden führen zum gleichen Routerverhalten.</span><span class="sxs-lookup"><span data-stu-id="03364-123">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="03364-124">Szenario</span><span class="sxs-lookup"><span data-stu-id="03364-124">Scenario</span></span>
 <span data-ttu-id="03364-125">In diesem Beispiel wird der Router in der Funktion als einfaches Nachrichtensystem veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="03364-125">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="03364-126">Der Routingdienst funktioniert als transparenter Proxyknoten, der so konfiguriert wurde, dass er Nachrichten direkt an einen vorkonfigurierten Satz von Zielendpunkten übergibt.</span><span class="sxs-lookup"><span data-stu-id="03364-126">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="03364-127">Reales Szenario</span><span class="sxs-lookup"><span data-stu-id="03364-127">Real World Scenario</span></span>
 <span data-ttu-id="03364-128">Contoso möchte mehr Flexibilität bei der Benennung, Adressierung, Konfiguration und Sicherheit der Dienste.</span><span class="sxs-lookup"><span data-stu-id="03364-128">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="03364-129">Aus diesem Grund wird ein einfaches Nachrichtensystem vor die Dienste gesetzt, das als öffentlicher Endpunkt fungiert.</span><span class="sxs-lookup"><span data-stu-id="03364-129">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="03364-130">So können zusätzliche Sicherheitsmaßnahmen vor den eigentlichen Diensten eingefügt werden, und skalierte Lösungen sowie die Dienstversionsverwaltung können später einfacher implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="03364-130">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03364-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="03364-131">The samples may already be installed on your computer.</span></span> <span data-ttu-id="03364-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="03364-132">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="03364-133">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="03364-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03364-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="03364-134">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="03364-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03364-135">See also</span></span>

- <span data-ttu-id="03364-136">[AppFabric-Hosting-und persistenzbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="03364-136">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
