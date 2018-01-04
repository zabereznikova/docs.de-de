---
title: Dynamische Neukonfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbf286891211da0e35274ff59f3bee69ebf3c9bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="ac188-102">Dynamische Neukonfiguration</span><span class="sxs-lookup"><span data-stu-id="ac188-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="ac188-103">In diesem Beispiel wird der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Routingdienst veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ac188-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="ac188-104">Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="ac188-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="ac188-105">In diesem Beispiel wird das standardmäßige [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Rechnerbeispiel für die Kommunikation über den Routingdienst angepasst.</span><span class="sxs-lookup"><span data-stu-id="ac188-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="ac188-106">In diesem Beispiel wird gezeigt, wie der Routingdienst während der Laufzeit dynamisch neu konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac188-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac188-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ac188-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ac188-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ac188-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac188-109">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ac188-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac188-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ac188-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="ac188-111">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="ac188-111">Sample Details</span></span>  
 <span data-ttu-id="ac188-112">Damit der Routingdienst während der Laufzeit dynamisch neu konfiguriert werden kann, wird in diesem Beispiel alle fünf Sekunden ein Timer ausgelöst, mit dem ein neues <xref:System.ServiceModel.Routing.RoutingConfiguration>-Objekt erstellt und angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac188-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="ac188-113">Diese Konfiguration verweist entweder auf den reguläre Rechnerendpunkt oder auf den Rundungsrechnerendpunkt.</span><span class="sxs-lookup"><span data-stu-id="ac188-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="ac188-114">Die Meldungen der Rechnerclientanwendung werden von einem der beiden Dienste zurückgegeben, abhängig davon, auf welchem Dienst der Routingdienst für das Routing zu der jeweiligen Zeit konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ac188-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="ac188-115">Es wird die Funktion des Routingdiensts zur dynamischen Neukonfiguration über ein benutzerdefiniertes Verhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac188-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="ac188-116">Mit diesem benutzerdefinierten Verhalten wird eine Diensterweiterung angefügt, die einen einfachen Threadtimer enthält. Der Timer wird alle fünf Sekunden ausgelöst und verursacht damit einen Rückruf zur `UpdateRules`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ac188-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="ac188-117">Mit dem Rückruf wird die neue Routingkonfiguration erstellt und übernommen.</span><span class="sxs-lookup"><span data-stu-id="ac188-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="ac188-118">In einer tatsächlichen Bereitstellung würde dieser Rückruf wahrscheinlich als Ergebnis eines anderen Ereignistyps (z. B. einer SQL-Ereignisbenachrichtigung oder einer WS-Discovery-Ankündigung) erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ac188-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ac188-119">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac188-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="ac188-120">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] DynamicReconfiguration.sln.</span><span class="sxs-lookup"><span data-stu-id="ac188-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="ac188-121">So öffnen **Projektmappen-Explorer**wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="ac188-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="ac188-122">Drücken Sie **F5** oder **STRG + UMSCHALT + B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac188-122">Press **F5** or **CTRL+SHIFT+B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="ac188-123">Wenn Sie möchten, um die erforderlichen Projekte automatisch gestartet, wenn Sie durch Drücken **F5**mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ac188-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="ac188-124">Wählen Sie die **Startprojekt** Knoten unter **allgemeine Eigenschaften** im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="ac188-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="ac188-125">Wählen Sie die **mehrere Startprojekte** Optionsfeld aus, und legen Sie alle Projekte haben die **starten** Aktion.</span><span class="sxs-lookup"><span data-stu-id="ac188-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="ac188-126">Wenn Sie das Projekt mit erstellen **STRG + UMSCHALT + B**, müssen Sie die folgenden Anwendungen starten:</span><span class="sxs-lookup"><span data-stu-id="ac188-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="ac188-127">Rechnerclient (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="ac188-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="ac188-128">Rechnerdienst (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="ac188-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="ac188-129">Routingrechnerdienst (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="ac188-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="ac188-130">Routingdienst (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="ac188-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="ac188-131">Drücken Sie im Konsolenfenster des Rechnerclients die EINGABETASTE, um den Client zu starten und die Rechnerdienstvorgänge aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ac188-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="ac188-132">Der Routingdienst leitet abwechselnd Meldungen an den Rundungsrechner und den regulären Rechner, da die Routingkonfiguration sich alle fünf Sekunden ändert.</span><span class="sxs-lookup"><span data-stu-id="ac188-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="ac188-133">Abhängig davon, an welchen Endpunkt der Routingdienst Meldungen laut Konfiguration senden soll, ist die Ausgabe im Clientkonsolenfenster jeweils unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="ac188-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="ac188-134">Drücken Sie mindestens fünf Sekunden lang wiederholt die EINGABETASTE, und achten Sie auf die Änderung der Ergebnisse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="ac188-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="ac188-135">Die zurückgegebene Ausgabe, wenn der Routerdienst zum Routen von Meldungen an den Rundungsrechnerdienst konfiguriert ist, sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="ac188-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="ac188-136">Die zurückgegebene Ausgabe, wenn der Routingdienst zum Routen von Meldungen an den regulären Rechnerdienst konfiguriert ist, sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="ac188-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="ac188-137">Vom Rechnerdienst und der Rundungsrechnerdienst wird außerdem ein Protokoll der Vorgänge gedruckt, die in den jeweiligen Konsolenfenstern aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ac188-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="ac188-138">Klicken Sie im Konsolenfenster Clients geben Sie "Beenden", und drücken Sie EINGABETASTE zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ac188-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="ac188-139">Drücken Sie die EINGABETASTE in den Dienstkonsolenfenstern, um die Dienste zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ac188-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="ac188-140">Szenario</span><span class="sxs-lookup"><span data-stu-id="ac188-140">Scenario</span></span>  
 <span data-ttu-id="ac188-141">In diesem Beispiel wird der Router als inhaltsbasierter Router dargestellt, der ermöglicht, dass mehrere Typen oder Implementierungen von Diensten über einen Endpunkt verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ac188-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="ac188-142">Reales Szenario</span><span class="sxs-lookup"><span data-stu-id="ac188-142">Real World Scenario</span></span>  
 <span data-ttu-id="ac188-143">Contoso möchte sämtliche Dienste virtualisieren, um nur einen Endpunkt öffentlich verfügbar zu machen, über den Zugriff auf mehrere verschiedene Dienste gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="ac188-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="ac188-144">In diesem Fall werden die inhaltsbasierten Routingfunktionen des Routingdiensts verwendet, um zu bestimmen, wohin die eingehenden Anforderungen gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ac188-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac188-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac188-145">See Also</span></span>  
 [<span data-ttu-id="ac188-146">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="ac188-146">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
