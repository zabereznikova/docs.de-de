---
title: Erwartete Ausnahmen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28af4a374d7ff474cf313aad711a3062f56263c9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="expected-exceptions"></a><span data-ttu-id="fe422-102">Erwartete Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="fe422-102">Expected Exceptions</span></span>
<span data-ttu-id="fe422-103">Dieses Beispiel zeigt, wie erwartete Ausnahmen beim Verwenden eines typisierten Clients abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fe422-103">This sample demonstrates how to catch expected exceptions when using a typed client.</span></span> <span data-ttu-id="fe422-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , implementiert einen rechnerdienst.</span><span class="sxs-lookup"><span data-stu-id="fe422-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="fe422-105">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="fe422-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe422-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="fe422-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fe422-107">Dieses Beispiel zeigt das Abfangen und Behandeln von erwarteten Ausnahmen beider Typen, die korrekte Programme verarbeiten müssen: `TimeoutException` und `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="fe422-107">This sample demonstrates catching and handling the two expected exception types that correct programs must handle: `TimeoutException` and `CommunicationException`.</span></span>  
  
 <span data-ttu-id="fe422-108">Ausnahmen, die aus Kommunikationsmethoden in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client ausgelöst werden, sind entweder erwartet oder unerwartet.</span><span class="sxs-lookup"><span data-stu-id="fe422-108">Exceptions that are thrown from communication methods on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client are either expected or unexpected.</span></span> <span data-ttu-id="fe422-109">Unerwartete Ausnahmen umfassen katastrophale Fehler (wie `OutOfMemoryException`) und Programmierfehler (wie `ArgumentNullException` oder `InvalidOperationException`).</span><span class="sxs-lookup"><span data-stu-id="fe422-109">Unexpected exceptions include catastrophic failures like `OutOfMemoryException` and programming errors like `ArgumentNullException` or `InvalidOperationException`.</span></span> <span data-ttu-id="fe422-110">Meist gibt es keinen praktikablen Weg im Umgang mit unerwarteten Fehlern, daher sollten sie beim Aufruf einer Kommunikationsmethode aus dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client meist auch gar nicht abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fe422-110">Typically there is no useful way to handle unexpected errors, so typically you should not catch them when calling a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client communication method.</span></span>  
  
 <span data-ttu-id="fe422-111">Zu den erwarteten Ausnahmen aus Kommunikationsmethoden in einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client gehören `TimeoutException`, `CommunicationException` und jede von `CommunicationException` abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="fe422-111">Expected exceptions from communication methods on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client include `TimeoutException`, `CommunicationException`, and any derived class of `CommunicationException`.</span></span> <span data-ttu-id="fe422-112">Sie zeigen an, dass während der Kommunikation ein Problem aufgetreten ist, das sicher behandelt werden kann, indem der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client abgebrochen und ein Kommunikationsfehler gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="fe422-112">These indicate a problem during communication that can be safely handled by aborting the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and reporting a communication failure.</span></span> <span data-ttu-id="fe422-113">Da diese Fehler durch externe Faktoren in jeder Anwendung verursacht werden können, müssen ordnungsgemäße Anwendungen diese Ausnahmen abfangen und wiederherstellen, wenn sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="fe422-113">Because external factors can cause these errors in any application, correct applications must catch these exceptions and recover when they occur.</span></span>  
  
 <span data-ttu-id="fe422-114">Es gibt verschiedene von `CommunicationException` abgeleitete Klassen, die ein Client auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="fe422-114">There are several derived classes of `CommunicationException` that a client can throw.</span></span> <span data-ttu-id="fe422-115">In manchen Fällen fangen Anwendungen auch einige von ihnen ab, um eine bestimmte Verarbeitung auszuführen, während sie andere Ausnahmen als `CommunicationException` behandeln lassen.</span><span class="sxs-lookup"><span data-stu-id="fe422-115">In some cases, applications also catch some of these to do special handling, but let the others be handled as a `CommunicationException`.</span></span> <span data-ttu-id="fe422-116">Dies kann durchgeführt werden, indem zuerst Ausnahmen bestimmter Typen und dann `CommunicationException` in einer späteren Abfangklausel abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fe422-116">This can be accomplished by catching the more specific exception type first and then catching `CommunicationException` in a later catch-clause.</span></span>  
  
 <span data-ttu-id="fe422-117">Code, der eine Clientkommunikationsmethode aufruft, muss `TimeoutException` und `CommunicationException` abfangen.</span><span class="sxs-lookup"><span data-stu-id="fe422-117">Code that calls a client communication method must catch the `TimeoutException` and `CommunicationException`.</span></span> <span data-ttu-id="fe422-118">Eine Möglichkeit zum Umgang mit solchen Fehlern wäre, den Client abzubrechen und den Kommunikationsfehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="fe422-118">One way to handle such errors is to abort the client and report the communication failure.</span></span>  
  
```csharp   
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="fe422-119">Wenn eine erwartete Ausnahme auftritt, kann der Client anschließend noch verwendbar oder nicht mehr verwendbar sein.</span><span class="sxs-lookup"><span data-stu-id="fe422-119">If an expected exception occurs, the client may or may not be usable afterwards.</span></span> <span data-ttu-id="fe422-120">Um zu bestimmen, ob der Client immer noch verwendbar ist, überprüfen Sie, dass die `State`-Eigenschaft `CommunicationState`.Opened ist.</span><span class="sxs-lookup"><span data-stu-id="fe422-120">To determine if the client is still usable, check that the `State` property is `CommunicationState`.Opened.</span></span> <span data-ttu-id="fe422-121">Wenn der Client immer noch geöffnet ist, dann ist er auch noch verwendbar.</span><span class="sxs-lookup"><span data-stu-id="fe422-121">If it is still opened, then it is still usable.</span></span> <span data-ttu-id="fe422-122">Andernfalls sollten Sie den Client abbrechen und alle Verweise auf ihn freigeben.</span><span class="sxs-lookup"><span data-stu-id="fe422-122">Otherwise you should abort the client and release all references to it.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fe422-123">Manchmal lässt sich beobachten, dass Clients mit einer Sitzung nach einer Ausnahme nicht mehr verwendbar sind, während Clients ohne eine Sitzung auch nach Auftreten einer Ausnahme oftmals noch verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fe422-123">You may observe that clients that have a session are often no longer usable after an exception, and clients that do not have a session are often still usable after an exception.</span></span> <span data-ttu-id="fe422-124">Da es jedoch für keinen der beiden Fälle eine Garantie gibt, sollte die Anwendung &#150; falls der Client nach einer Ausnahme weiter verwendet werden soll &#150; mithilfe der `State`-Eigenschaft überprüfen, ob der Client weiterhin geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="fe422-124">However, neither of these is guaranteed, so if you want to try to continue using the client after an exception your application should check the `State` property to verify the client is still opened.</span></span>  
  
 <span data-ttu-id="fe422-125">Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe422-125">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="fe422-126">Der Clientprozess führt zwei Szenarios aus, die beide versuchen, `Add` und anschließend `Divide` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fe422-126">The client process runs two scenarios, each of which attempts to call `Add` followed by `Divide`.</span></span> <span data-ttu-id="fe422-127">Das erste Szenario simuliert ein Netzwerkproblem, indem der Client vor dem Aufruf von `Divide` abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="fe422-127">The first scenario simulates a network issue by aborting the client before making the call to `Divide`.</span></span> <span data-ttu-id="fe422-128">Das zweite Szenario verursacht einen Timeout-Zustand, indem ein so kurzes Timeout festgelegt wird, dass die Methode nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe422-128">The second scenario causes a timeout condition by setting the timeout too short for the method to complete.</span></span> <span data-ttu-id="fe422-129">Die erwartete Ausgabe vom Clientprozess lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fe422-129">The expected output from the client process is:</span></span>  
  
```  
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fe422-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fe422-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fe422-131">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fe422-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fe422-132">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fe422-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="fe422-133">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fe422-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe422-134">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fe422-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe422-135">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fe422-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fe422-136">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="fe422-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe422-137">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe422-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
  
## <a name="see-also"></a><span data-ttu-id="fe422-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe422-138">See Also</span></span>
