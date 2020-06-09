---
title: Erwartete Ausnahmen
ms.date: 03/30/2017
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
ms.openlocfilehash: d8e3c024eb69fe22ec27f3e3697bc4fc7b4ee121
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600528"
---
# <a name="expected-exceptions"></a><span data-ttu-id="93fb5-102">Erwartete Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="93fb5-102">Expected Exceptions</span></span>
<span data-ttu-id="93fb5-103">Dieses Beispiel zeigt, wie erwartete Ausnahmen beim Verwenden eines typisierten Clients abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="93fb5-103">This sample demonstrates how to catch expected exceptions when using a typed client.</span></span> <span data-ttu-id="93fb5-104">Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="93fb5-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="93fb5-105">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="93fb5-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93fb5-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="93fb5-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="93fb5-107">Dieses Beispiel zeigt das Abfangen und Behandeln von erwarteten Ausnahmen beider Typen, die korrekte Programme verarbeiten müssen: `TimeoutException` und `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="93fb5-107">This sample demonstrates catching and handling the two expected exception types that correct programs must handle: `TimeoutException` and `CommunicationException`.</span></span>  
  
 <span data-ttu-id="93fb5-108">Ausnahmen, die von Kommunikationsmethoden auf einem Windows Communication Foundation (WCF)-Client ausgelöst werden, sind entweder erwartungsgemäß oder unerwartet.</span><span class="sxs-lookup"><span data-stu-id="93fb5-108">Exceptions that are thrown from communication methods on a Windows Communication Foundation (WCF) client are either expected or unexpected.</span></span> <span data-ttu-id="93fb5-109">Unerwartete Ausnahmen umfassen katastrophale Fehler (wie `OutOfMemoryException`) und Programmierfehler (wie `ArgumentNullException` oder `InvalidOperationException`).</span><span class="sxs-lookup"><span data-stu-id="93fb5-109">Unexpected exceptions include catastrophic failures like `OutOfMemoryException` and programming errors like `ArgumentNullException` or `InvalidOperationException`.</span></span> <span data-ttu-id="93fb5-110">In der Regel gibt es keine nützliche Methode, um unerwartete Fehler zu behandeln. in der Regel sollten Sie Sie beim Aufrufen einer WCF-Client Kommunikationsmethode nicht abfangen.</span><span class="sxs-lookup"><span data-stu-id="93fb5-110">Typically there is no useful way to handle unexpected errors, so typically you should not catch them when calling a WCF client communication method.</span></span>  
  
 <span data-ttu-id="93fb5-111">Zu den erwarteten Ausnahmen von Kommunikationsmethoden auf einem WCF-Client zählen `TimeoutException` , `CommunicationException` und eine beliebige abgeleitete Klasse von `CommunicationException` .</span><span class="sxs-lookup"><span data-stu-id="93fb5-111">Expected exceptions from communication methods on a WCF client include `TimeoutException`, `CommunicationException`, and any derived class of `CommunicationException`.</span></span> <span data-ttu-id="93fb5-112">Diese weisen auf ein Problem während der Kommunikation hin, das sicher verarbeitet werden kann, indem der WCF-Client abgebrochen und ein Kommunikationsfehler gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="93fb5-112">These indicate a problem during communication that can be safely handled by aborting the WCF client and reporting a communication failure.</span></span> <span data-ttu-id="93fb5-113">Da diese Fehler durch externe Faktoren in jeder Anwendung verursacht werden können, müssen ordnungsgemäße Anwendungen diese Ausnahmen abfangen und wiederherstellen, wenn sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="93fb5-113">Because external factors can cause these errors in any application, correct applications must catch these exceptions and recover when they occur.</span></span>  
  
 <span data-ttu-id="93fb5-114">Es gibt verschiedene von `CommunicationException` abgeleitete Klassen, die ein Client auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="93fb5-114">There are several derived classes of `CommunicationException` that a client can throw.</span></span> <span data-ttu-id="93fb5-115">In manchen Fällen fangen Anwendungen auch einige von ihnen ab, um eine bestimmte Verarbeitung auszuführen, während sie andere Ausnahmen als `CommunicationException` behandeln lassen.</span><span class="sxs-lookup"><span data-stu-id="93fb5-115">In some cases, applications also catch some of these to do special handling, but let the others be handled as a `CommunicationException`.</span></span> <span data-ttu-id="93fb5-116">Dies kann durchgeführt werden, indem zuerst Ausnahmen bestimmter Typen und dann `CommunicationException` in einer späteren Abfangklausel abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="93fb5-116">This can be accomplished by catching the more specific exception type first and then catching `CommunicationException` in a later catch-clause.</span></span>  
  
 <span data-ttu-id="93fb5-117">Code, der eine Clientkommunikationsmethode aufruft, muss `TimeoutException` und `CommunicationException` abfangen.</span><span class="sxs-lookup"><span data-stu-id="93fb5-117">Code that calls a client communication method must catch the `TimeoutException` and `CommunicationException`.</span></span> <span data-ttu-id="93fb5-118">Eine Möglichkeit zum Umgang mit solchen Fehlern wäre, den Client abzubrechen und den Kommunikationsfehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="93fb5-118">One way to handle such errors is to abort the client and report the communication failure.</span></span>  
  
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
  
 <span data-ttu-id="93fb5-119">Wenn eine erwartete Ausnahme auftritt, kann der Client anschließend noch verwendbar oder nicht mehr verwendbar sein.</span><span class="sxs-lookup"><span data-stu-id="93fb5-119">If an expected exception occurs, the client may or may not be usable afterwards.</span></span> <span data-ttu-id="93fb5-120">Um zu bestimmen, ob der Client immer noch verwendbar ist, überprüfen Sie, dass die `State`-Eigenschaft `CommunicationState`.Opened ist.</span><span class="sxs-lookup"><span data-stu-id="93fb5-120">To determine if the client is still usable, check that the `State` property is `CommunicationState`.Opened.</span></span> <span data-ttu-id="93fb5-121">Wenn der Client immer noch geöffnet ist, dann ist er auch noch verwendbar.</span><span class="sxs-lookup"><span data-stu-id="93fb5-121">If it is still opened, then it is still usable.</span></span> <span data-ttu-id="93fb5-122">Andernfalls sollten Sie den Client abbrechen und alle Verweise auf ihn freigeben.</span><span class="sxs-lookup"><span data-stu-id="93fb5-122">Otherwise you should abort the client and release all references to it.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="93fb5-123">Manchmal lässt sich beobachten, dass Clients mit einer Sitzung nach einer Ausnahme nicht mehr verwendbar sind, während Clients ohne eine Sitzung auch nach Auftreten einer Ausnahme oftmals noch verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="93fb5-123">You may observe that clients that have a session are often no longer usable after an exception, and clients that do not have a session are often still usable after an exception.</span></span> <span data-ttu-id="93fb5-124">Da es jedoch für keinen der beiden Fälle eine Garantie gibt, sollte die Anwendung &#150; falls der Client nach einer Ausnahme weiter verwendet werden soll &#150; mithilfe der `State`-Eigenschaft überprüfen, ob der Client weiterhin geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="93fb5-124">However, neither of these is guaranteed, so if you want to try to continue using the client after an exception your application should check the `State` property to verify the client is still opened.</span></span>  
  
 <span data-ttu-id="93fb5-125">Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93fb5-125">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="93fb5-126">Der Clientprozess führt zwei Szenarios aus, die beide versuchen, `Add` und anschließend `Divide` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="93fb5-126">The client process runs two scenarios, each of which attempts to call `Add` followed by `Divide`.</span></span> <span data-ttu-id="93fb5-127">Das erste Szenario simuliert ein Netzwerkproblem, indem der Client vor dem Aufruf von `Divide` abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="93fb5-127">The first scenario simulates a network issue by aborting the client before making the call to `Divide`.</span></span> <span data-ttu-id="93fb5-128">Das zweite Szenario verursacht einen Timeout-Zustand, indem ein so kurzes Timeout festgelegt wird, dass die Methode nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="93fb5-128">The second scenario causes a timeout condition by setting the timeout too short for the method to complete.</span></span> <span data-ttu-id="93fb5-129">Die erwartete Ausgabe vom Clientprozess lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="93fb5-129">The expected output from the client process is:</span></span>  
  
```output
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="93fb5-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="93fb5-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="93fb5-131">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="93fb5-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="93fb5-132">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="93fb5-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="93fb5-133">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="93fb5-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="93fb5-134">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="93fb5-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="93fb5-135">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="93fb5-135">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="93fb5-136">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93fb5-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="93fb5-137">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="93fb5-137">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
