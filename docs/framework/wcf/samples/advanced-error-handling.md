---
title: Erweiterte Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 72fb9885408759f5781501b548f81625d258d13c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423431"
---
# <a name="advanced-error-handling"></a><span data-ttu-id="e8c2b-102">Erweiterte Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="e8c2b-102">Advanced Error Handling</span></span>
<span data-ttu-id="e8c2b-103">Diesem Beispiel wird der Windows Communication Foundation (WCF)-Routingdienst veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="e8c2b-104">Der Routingdienst ist eine WCF-Komponente, die es einfach macht, ein inhaltsbasierten Routers in Ihre Anwendung einbinden.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="e8c2b-105">In diesem Beispiel wird gezeigt, wie der Routingdienst eine intelligente Fehlerwiederherstellung mit Transaktionen und anderen komplexen Messagingkonzepten (z. B. Multicasting) ausführt.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-105">This sample shows how the routing service intelligently recovers from errors, using transactions and other more complex messaging concepts such as multicasting.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8c2b-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e8c2b-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e8c2b-108">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e8c2b-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a><span data-ttu-id="e8c2b-110">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="e8c2b-110">Sample Details</span></span>  
 <span data-ttu-id="e8c2b-111">In diesem Beispiel wird der Routingdienst konfiguriert, um eine Nachricht aus einer MSMQ-Warteschlange zu lesen und die Nachricht per Multicast an zwei Warteschlangenlisten zu senden.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-111">In this sample, the routing service is configured to read a message from an MSMQ queue and multicast this message to two lists of queues.</span></span> <span data-ttu-id="e8c2b-112">Eine Liste wird für Dienstwarteschlangen verwendet, die andere für Protokollwarteschlangen.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-112">One list is used for service queues and another is used for logging queues.</span></span>  
  
 <span data-ttu-id="e8c2b-113">Da die MSMQ-Bindung, die der Routingdienst laut Konfiguration verwenden soll, normalerweise die Verwendung von Transaktionen unterstützt, stellt der Routingdienst sicher, dass die Meldung transaktionsfähig ist und von mindestens einer Warteschlange in jeder Liste empfangen wurde. Erst dann wird eine Meldung an die eingehende Warteschlange (`InQ`) gesendet, dass die Nachricht erfolgreich geroutet wurde.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-113">Because, by default, the MSMQ binding that the routing service is configured to use supports the use of transactions, the routing service makes sure that the message is transactional and received by at least one queue in each list before reporting to the Inbound Queue (`InQ`) that the message was successfully routed.</span></span> <span data-ttu-id="e8c2b-114">Wenn deshalb beide Dienstwarteschlangen oder beide Protokollwarteschlangen nicht verfügbar sind, meldet der Routingdienst, dass die Nachricht nicht geroutet werden konnte und die eingehende Warteschlange eine Aktion ausführen sollte.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-114">Thus, in the case where both of the service queues or both of the logging queues are unavailable, the routing service reports that the message could not be routed and the inbound queue should take some action.</span></span> <span data-ttu-id="e8c2b-115">Diese Aktion besteht darin, dass die Nachricht in die Systemwarteschlange für unzustellbare Meldungen verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-115">This action consists of moving the message to the system dead letter queue.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e8c2b-116">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8c2b-116">To use this sample</span></span>  
  
1.  > [!IMPORTANT]
    >  <span data-ttu-id="e8c2b-117">Installieren Sie MSMQ, bevor Sie dieses Beispiel ausführen.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-117">Install MSMQ before running this sample.</span></span> <span data-ttu-id="e8c2b-118">Wenn MSMQ nicht installiert ist, wird beim Ausführen des Beispiels eine Ausnahmemeldung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-118">If MSMQ is not installed, an exception message is returned when running the sample.</span></span> <span data-ttu-id="e8c2b-119">Anweisungen zum Installieren von MSMQ finden Sie unter [Installieren von Message Queuing (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span><span class="sxs-lookup"><span data-stu-id="e8c2b-119">Instructions for installing MSMQ can be found at [Installing Message Queuing (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).</span></span>  
  
     <span data-ttu-id="e8c2b-120">Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] AdvancedErrorHandling.sln.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedErrorHandling.sln.</span></span>  
  
2.  <span data-ttu-id="e8c2b-121">Drücken Sie **F5** oder **STRG + UMSCHALT + B** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-121">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="e8c2b-122">Wenn Sie die Anwendung mit STRT+UMSCHALT+B erstellen, müssen Sie die Anwendung mit ./RoutingService/bin/debug/RoutingService.exe starten.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-122">If you build the application with CTRL+SHIFT+B, you must start the application at ./RoutingService/bin/debug/RoutingService.exe.</span></span>  
  
3.  <span data-ttu-id="e8c2b-123">Drücken Sie die EINGABETASTE im Konsolenfenster, um den Client zu starten.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-123">In the console window, press ENTER to start the client.</span></span>  
  
4.  <span data-ttu-id="e8c2b-124">Der Client gibt für jeden Fall eine andere Statistik zu den Warteschlangen zurück.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-124">The client returns different statistics about the queues for each case.</span></span>  
  
    1.  <span data-ttu-id="e8c2b-125">Folgende Ausgabe wird in Fall 1 zurückgegeben (keine Fehler).</span><span class="sxs-lookup"><span data-stu-id="e8c2b-125">The following is the output returned for case 1 (no failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  <span data-ttu-id="e8c2b-126">Folgende Ausgabe wird in Fall 3 zurückgegeben (Fehler beim primären Dienst und der Protokollierungswarteschlange).</span><span class="sxs-lookup"><span data-stu-id="e8c2b-126">The following is the output returned for case 3 (primary service and logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  <span data-ttu-id="e8c2b-127">Folgende Ausgabe wird in Fall 4 zurückgegeben (Fehler bei der primären Dienstwarteschlange und bei der primären und Sicherungsprotokollierungswarteschlange).</span><span class="sxs-lookup"><span data-stu-id="e8c2b-127">The following is the output returned for case 4 (primary service queue and primary and backup logging queue failures).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  <span data-ttu-id="e8c2b-128">Folgende Ausgabe wird in Fall 2 zurückgegeben (Fehler bei der primären Dienstwarteschlange).</span><span class="sxs-lookup"><span data-stu-id="e8c2b-128">The following is the output returned for case 2 (primary service queue failure).</span></span>  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="e8c2b-129">Konfigurierbar über Code oder App.config</span><span class="sxs-lookup"><span data-stu-id="e8c2b-129">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="e8c2b-130">Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-130">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="e8c2b-131">Sie können auch den Namen der Datei RoutingService\App.config ändern, damit diese nicht erkannt wird, und den Wert des `configDriven`-Felds in RoutingService\Program.cs auf `false` festlegen, um die im Code definierte Konfiguration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-131">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and change the value of the `configDriven` field in RoutingService\Program.cs to `false` to use the configuration defined in the code.</span></span> <span data-ttu-id="e8c2b-132">Beide Methoden führen zum gleichen Routerverhalten.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-132">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="e8c2b-133">Szenario</span><span class="sxs-lookup"><span data-stu-id="e8c2b-133">Scenario</span></span>  
 <span data-ttu-id="e8c2b-134">In diesem Beispiel wird gezeigt, dass der Routingdienst erweiterte Messagingfunktionen behandeln kann, z. B. Transaktions- und Empfangskontext, und dass es diese Funktionen als Bestandteil der ordnungsgemäßen Behandlung von Fehlerszenarien verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-134">This sample demonstrates that the routing service can handle advanced messaging capabilities, such as transactions and receive context, and that it can utilize these capabilities as a part of correctly handling error scenarios.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="e8c2b-135">Reales Szenario</span><span class="sxs-lookup"><span data-stu-id="e8c2b-135">Real World Scenario</span></span>  
 <span data-ttu-id="e8c2b-136">Contoso möchte transaktionale Empfangsprozesse über den Routingdienst verwenden, um sicherzustellen, dass alle erforderlichen Dienste die Informationen auch beim Auftreten von Fehlern empfangen.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-136">Contoso wants to utilize transactional receives through the routing service to ensure that all necessary services receive information even during error conditions.</span></span> <span data-ttu-id="e8c2b-137">Außerdem sollen Fehler richtig und automatisch behandelt und Fehler gemeldet werden, falls eine Nachricht auch dann nicht zugestellt werden kann, wenn die Fehlerbehandlungslogik verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-137">Furthermore, they would like errors to be handled correctly and automatically and failures to be reported in the case that a message is undeliverable even when error handling logic is utilized.</span></span> <span data-ttu-id="e8c2b-138">Zu diesem Zweck wird der Routingdienst so konfiguriert, dass erwartungsgemäß ein Failover zu bestimmten Endpunkten ausgeführt wird. Der Routingdienst behandelt ggf. Fehlersituationen einschließlich Erstellung, Abschluss und Rollback/Abbrechen von Transaktionen/Empfangskontexten.</span><span class="sxs-lookup"><span data-stu-id="e8c2b-138">For this purpose, they configure the routing service to fail over to specific endpoints as expected and the routing service handles the error situations, which includes the creation, completion, and rollback/aborting of transactions/receive contexts as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c2b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8c2b-139">See Also</span></span>  
 [<span data-ttu-id="e8c2b-140">AppFabric-Hosting- und-persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="e8c2b-140">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
