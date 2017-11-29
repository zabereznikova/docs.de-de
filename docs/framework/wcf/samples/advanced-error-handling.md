---
title: Erweiterte Fehlerbehandlung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77034a1948b7fc6dd383c9bdb5456917c6082687
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-error-handling"></a><span data-ttu-id="2c4f3-102">Erweiterte Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="2c4f3-102">Advanced Error Handling</span></span>
<span data-ttu-id="2c4f3-103">In diesem Beispiel wird der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Routingdienst veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-103">This sample demonstrates the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="2c4f3-104">Der Routingdienst ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponente, die das Integrieren eines inhaltsbasierten Routers in die Anwendung vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="2c4f3-105">In diesem Beispiel wird gezeigt, wie der Routingdienst eine intelligente Fehlerwiederherstellung mit Transaktionen und anderen komplexen Messagingkonzepten (z. B. Multicasting) ausführt.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c4f3-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2c4f3-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2c4f3-108">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2c4f3-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="2c4f3-110">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="2c4f3-110">Sample Details</span></span>  
 <span data-ttu-id="2c4f3-111">In diesem Beispiel wird der Routingdienst konfiguriert, um eine Nachricht aus einer MSMQ-Warteschlange zu lesen und die Nachricht per Multicast an zwei Warteschlangenlisten zu senden.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="2c4f3-112">Eine Liste wird für Dienstwarteschlangen verwendet, die andere für Protokollwarteschlangen.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="2c4f3-113">Da die MSMQ-Bindung, die der Routingdienst laut Konfiguration verwenden soll, normalerweise die Verwendung von Transaktionen unterstützt, stellt der Routingdienst sicher, dass die Meldung transaktionsfähig ist und von mindestens einer Warteschlange in jeder Liste empfangen wurde. Erst dann wird eine Meldung an die eingehende Warteschlange (`InQ`) gesendet, dass die Nachricht erfolgreich geroutet wurde.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="2c4f3-114">Wenn deshalb beide Dienstwarteschlangen oder beide Protokollwarteschlangen nicht verfügbar sind, meldet der Routingdienst, dass die Nachricht nicht geroutet werden konnte und die eingehende Warteschlange eine Aktion ausführen sollte.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="2c4f3-115">Diese Aktion besteht darin, dass die Nachricht in die Systemwarteschlange für unzustellbare Meldungen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2c4f3-116">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c4f3-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="2c4f3-117">Installieren Sie MSMQ, bevor Sie dieses Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="2c4f3-118">Wenn MSMQ nicht installiert ist, wird beim Ausführen des Beispiels eine Ausnahmemeldung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="2c4f3-119">Anweisungen zum Installieren von MSMQ finden Sie unter [Installieren von Message Queuing (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).</span><span class="sxs-lookup"><span data-stu-id="2c4f3-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="2c4f3-120">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] AdvancedErrorHandling.sln.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="2c4f3-121">Drücken Sie **F5** oder **STRG + UMSCHALT + B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c4f3-121">Press **F5** or **CTRL+SHIFT+B** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
    1.  <span data-ttu-id="2c4f3-122">Wenn Sie die Anwendung mit STRT+UMSCHALT+B erstellen, müssen Sie die Anwendung mit ./RoutingService/bin/debug/RoutingService.exe starten.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="2c4f3-123">Drücken Sie die EINGABETASTE im Konsolenfenster, um den Client zu starten.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="2c4f3-124">Der Client gibt für jeden Fall eine andere Statistik zu den Warteschlangen zurück.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="2c4f3-125">Folgende Ausgabe wird in Fall 1 zurückgegeben (keine Fehler).</span><span class="sxs-lookup"><span data-stu-id="2c4f3-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="2c4f3-126">Folgende Ausgabe wird in Fall 3 zurückgegeben (Fehler beim primären Dienst und der Protokollierungswarteschlange).</span><span class="sxs-lookup"><span data-stu-id="2c4f3-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="2c4f3-127">Folgende Ausgabe wird in Fall 4 zurückgegeben (Fehler bei der primären Dienstwarteschlange und bei der primären und Sicherungsprotokollierungswarteschlange).</span><span class="sxs-lookup"><span data-stu-id="2c4f3-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="2c4f3-128">Folgende Ausgabe wird in Fall 2 zurückgegeben (Fehler bei der primären Dienstwarteschlange).</span><span class="sxs-lookup"><span data-stu-id="2c4f3-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="2c4f3-129">Konfigurierbar über Code oder App.config</span><span class="sxs-lookup"><span data-stu-id="2c4f3-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="2c4f3-130">Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="2c4f3-131">Sie können auch den Namen der Datei RoutingService\App.config ändern, damit diese nicht erkannt wird, und den Wert des `configDriven`-Felds in RoutingService\Program.cs auf `false` festlegen, um die im Code definierte Konfiguration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="2c4f3-132">Beide Methoden führen zum gleichen Routerverhalten.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="2c4f3-133">Szenario</span><span class="sxs-lookup"><span data-stu-id="2c4f3-133">Scenario</span></span>  
 <span data-ttu-id="2c4f3-134">In diesem Beispiel wird gezeigt, dass der Routingdienst erweiterte Messagingfunktionen behandeln kann, z. B. Transaktions- und Empfangskontext, und dass es diese Funktionen als Bestandteil der ordnungsgemäßen Behandlung von Fehlerszenarien verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="2c4f3-135">Reales Szenario</span><span class="sxs-lookup"><span data-stu-id="2c4f3-135">Real World Scenario</span></span>  
 <span data-ttu-id="2c4f3-136">Contoso möchte transaktionale Empfangsprozesse über den Routingdienst verwenden, um sicherzustellen, dass alle erforderlichen Dienste die Informationen auch beim Auftreten von Fehlern empfangen.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="2c4f3-137">Außerdem sollen Fehler richtig und automatisch behandelt und Fehler gemeldet werden, falls eine Nachricht auch dann nicht zugestellt werden kann, wenn die Fehlerbehandlungslogik verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="2c4f3-138">Zu diesem Zweck wird der Routingdienst so konfiguriert, dass erwartungsgemäß ein Failover zu bestimmten Endpunkten ausgeführt wird. Der Routingdienst behandelt ggf. Fehlersituationen einschließlich Erstellung, Abschluss und Rollback/Abbrechen von Transaktionen/Empfangskontexten.</span><span class="sxs-lookup"><span data-stu-id="2c4f3-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4f3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c4f3-139">See Also</span></span>  
 [<span data-ttu-id="2c4f3-140">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="2c4f3-140">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
