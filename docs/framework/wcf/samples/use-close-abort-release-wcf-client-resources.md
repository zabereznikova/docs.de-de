---
title: Freigeben von WCF-Clientressourcen mit „Close“ und „Abort“
description: Der Löschvorgang kann fehlschlagen und Ausnahmen auslösen, wenn das Netzwerk ausfällt. Dies kann zu unerwünschtem Verhalten führen. Verwenden Sie stattdessen schließen und Abbrechen, um Client Ressourcen freizugeben, wenn das Netzwerk nicht ausgeführt werden konnte.
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 38861252a470f71a6fa88554e289344e2918d710
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715334"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a><span data-ttu-id="c94d6-105">Releaseressourcen beim Ablegen von Netzwerkverbindungen sicher schließen und Abbrechen</span><span class="sxs-lookup"><span data-stu-id="c94d6-105">Close and Abort release resources safely when network connections have dropped</span></span>

<span data-ttu-id="c94d6-106">Dieses Beispiel veranschaulicht die Verwendung der Methoden `Close` und `Abort` zum Bereinigen von Ressourcen, wenn ein typisierter Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c94d6-106">This sample demonstrates using the `Close` and `Abort` methods to clean up resources when using a typed client.</span></span> <span data-ttu-id="c94d6-107">Die `using`-Anweisung verursacht Ausnahmen, wenn die Netzwerkverbindung nicht stabil ist.</span><span class="sxs-lookup"><span data-stu-id="c94d6-107">The `using` statement causes exceptions when the network connection is not robust.</span></span> <span data-ttu-id="c94d6-108">Dieses Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c94d6-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="c94d6-109">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="c94d6-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="c94d6-110">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c94d6-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="c94d6-111">In diesem Beispiel werden zwei häufige Probleme veranschaulicht, die beim Verwenden der C#-Anweisung "using" mit typisierten Clients auftreten. Außerdem wird Code bereitgestellt, mit dem die Bereinigung nach Ausnahmen korrekt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c94d6-111">This sample shows two of the common problems that occur when using the C# "using" statement with typed clients, as well as code that correctly cleans up after exceptions.</span></span>

<span data-ttu-id="c94d6-112">Die C#-Anweisung "using" führt zu einem Aufruf von `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="c94d6-112">The C# "using" statement results in a call to `Dispose`().</span></span> <span data-ttu-id="c94d6-113">Dies ist das Gleiche wie `Close`(). Dies kann zu Ausnahmen führen, wenn ein Netzwerkfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="c94d6-113">This is the same as `Close`(), which may throw exceptions when a network error occurs.</span></span> <span data-ttu-id="c94d6-114">Da der Aufruf von `Dispose`() implizit an der schließenden Klammer des "using"-Blocks erfolgt, wird diese Quelle für Ausnahmen beim Schreiben oder Lesen des Codes häufig nicht bemerkt.</span><span class="sxs-lookup"><span data-stu-id="c94d6-114">Because the call to `Dispose`() happens implicitly at the closing brace of the "using" block, this source of exceptions is likely to go unnoticed both by people writing the code and reading the code.</span></span> <span data-ttu-id="c94d6-115">Dies stellt eine potenzielle Quelle für Anwendungsfehler dar.</span><span class="sxs-lookup"><span data-stu-id="c94d6-115">This represents a potential source of application errors.</span></span>

<span data-ttu-id="c94d6-116">Das erste Problem (in der `DemonstrateProblemUsingCanThrow`-Methode dargestellt) liegt darin, dass die schließende Klammer eine Ausnahme auslöst und der Code nach der schließenden Klammer nicht ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="c94d6-116">The first problem, illustrated in the `DemonstrateProblemUsingCanThrow` method, is that the closing brace throws an exception and the code after the closing brace does not execute:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
} // <-- this line might throw
Console.WriteLine("Hope this code wasn't important, because it might not happen.");
```

<span data-ttu-id="c94d6-117">Selbst wenn nichts im using-Block eine Ausnahme auslöst oder alle Ausnahmen im using-Block abgefangen werden, wird `Console.WriteLine` möglicherweise nicht ausgeführt, da der implizite `Dispose`()-Aufruf an der schließenden Klammer eine Ausnahme auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="c94d6-117">Even if nothing inside the using block throws an exception or all exceptions inside the using block are caught, the `Console.WriteLine` might not happen because the implicit `Dispose`() call at the closing brace might throw an exception.</span></span>

<span data-ttu-id="c94d6-118">Das zweite Problem (in der `DemonstrateProblemUsingCanThrowAndMask`-Methode veranschaulicht) ist eine weitere Implikation der schließenden Klammer, die eine Ausnahme auslöst:</span><span class="sxs-lookup"><span data-stu-id="c94d6-118">The second problem, illustrated in the `DemonstrateProblemUsingCanThrowAndMask` method, is another implication of the closing brace throwing an exception:</span></span>

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
    throw new ApplicationException("Hope this exception was not important, because "+
                                   "it might be masked by the Close exception.");
} // <-- this line might throw an exception.
```

<span data-ttu-id="c94d6-119">Da `Dispose`() in einem "finally"-Block auftritt, tritt `ApplicationException` nur außerhalb des using-Blocks auf, wenn bei `Dispose`() ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="c94d6-119">Because the `Dispose`() occurs inside a "finally" block, the `ApplicationException` is never seen outside the using block if the `Dispose`() fails.</span></span> <span data-ttu-id="c94d6-120">Wenn der Code außen wissen muss, wann die `ApplicationException` auftritt, kann das "using"-Konstrukt zu Problemen führen, da diese Ausnahme maskiert wird.</span><span class="sxs-lookup"><span data-stu-id="c94d6-120">If the code outside must know about when the `ApplicationException` occurs, the "using" construct may cause problems by masking this exception.</span></span>

<span data-ttu-id="c94d6-121">Abschließend wird im Beispiel veranschaulicht, wie die Bereinigung ordnungsgemäß ausgeführt wird, nachdem Ausnahmen in `DemonstrateCleanupWithExceptions` aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="c94d6-121">Finally, the sample demonstrates how to clean up correctly when exceptions occur in `DemonstrateCleanupWithExceptions`.</span></span> <span data-ttu-id="c94d6-122">Dabei wird ein try/catch-Block verwendet, um Fehler zu melden und `Abort` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c94d6-122">This uses a try/catch block to report errors and call `Abort`.</span></span> <span data-ttu-id="c94d6-123">Weitere Informationen zum Abfangen von Ausnahmen von Client aufrufen finden Sie im Beispiel [erwartete Ausnahmen](../../../../docs/framework/wcf/samples/expected-exceptions.md) .</span><span class="sxs-lookup"><span data-stu-id="c94d6-123">See the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample for more details about catching exceptions from client calls.</span></span>

```csharp
try
{
    ...
    client.Close();
}
catch (CommunicationException e)
{
    ...
    client.Abort();
}
catch (TimeoutException e)
{
    ...
    client.Abort();
}
catch (Exception e)
{
    ...
    client.Abort();
    throw;
}
```

> [!NOTE]
> <span data-ttu-id="c94d6-124">Die using-Anweisung und ServiceHost: Viele selbst gehostete Anwendungen führen wenige andere Aktionen als das Hosten eines Diensts aus, und ServiceHost.Close löst selten Ausnahmen aus. In solchen Anwendungen kann die using-Anweisung mit ServiceHost daher sicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c94d6-124">The using statement and ServiceHost: Many self-hosting applications do little more than host a service, and ServiceHost.Close rarely throws an exception, so such applications can safely use the using statement with ServiceHost.</span></span> <span data-ttu-id="c94d6-125">Achten Sie jedoch darauf, dass ServiceHost.Close eine `CommunicationException` auslösen kann. Wenn die Anwendung daher nach dem Schließen von ServiceHost fortgesetzt wird, sollten Sie die Verwendung der using-Anweisung vermeiden und sich an das zuvor beschriebene Muster halten.</span><span class="sxs-lookup"><span data-stu-id="c94d6-125">However, be aware that ServiceHost.Close can throw a `CommunicationException`, so if your application continues after closing the ServiceHost, you should avoid the using statement and follow the pattern previously given.</span></span>

<span data-ttu-id="c94d6-126">Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c94d6-126">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>

<span data-ttu-id="c94d6-127">Im Clientprozess werden drei Szenarios ausgeführt, die jeweils versuchen, `Divide` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c94d6-127">The client process runs three scenarios, each of which attempts to call `Divide`.</span></span> <span data-ttu-id="c94d6-128">Im ersten Szenario wird veranschaulicht, dass Code aufgrund einer Ausnahme von `Dispose`() übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="c94d6-128">The first scenario demonstrates code being skipped because of an exception from `Dispose`().</span></span> <span data-ttu-id="c94d6-129">Im zweiten Szenario wird veranschaulicht, dass eine wichtige Ausnahme aufgrund einer Ausnahme von `Dispose`() maskiert wird.</span><span class="sxs-lookup"><span data-stu-id="c94d6-129">The second scenario demonstrates an important exception being masked because of an exception from `Dispose`().</span></span> <span data-ttu-id="c94d6-130">Das dritte Szenario zeigt die ordnungsgemäße Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="c94d6-130">The third scenario demonstrates correct clean up.</span></span>

<span data-ttu-id="c94d6-131">Die erwartete Ausgabe vom Clientprozess lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c94d6-131">The expected output from the client process is:</span></span>

```console
=
= Demonstrating problem:  closing brace of using statement can throw.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating cleanup with Exceptions.
=
Calling client.Add(0.0, 0.0);
        client.Add(0.0, 0.0); returned 0
Calling client.Divide(0.0, 0.0);
Got System.ServiceModel.CommunicationException from Divide.

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c94d6-132">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c94d6-132">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c94d6-133">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="c94d6-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c94d6-134">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c94d6-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="c94d6-135">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c94d6-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c94d6-136">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c94d6-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c94d6-137">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c94d6-137">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c94d6-138">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="c94d6-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c94d6-139">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c94d6-139">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`
