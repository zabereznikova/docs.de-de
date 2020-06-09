---
title: Parallelität
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
ms.openlocfilehash: 393c8a79cb60a33203b41a0778176a4d78a9b6ee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585310"
---
# <a name="concurrency"></a><span data-ttu-id="b0905-102">Parallelität</span><span class="sxs-lookup"><span data-stu-id="b0905-102">Concurrency</span></span>
<span data-ttu-id="b0905-103">Das Parallelitätsbeispiel veranschaulicht die Verwendung des <xref:System.ServiceModel.ServiceBehaviorAttribute> mit der <xref:System.ServiceModel.ConcurrencyMode>-Enumeration, die steuert, ob eine Instanz eines Diensts Nachrichten sequenziell oder parallel verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b0905-103">The Concurrency sample demonstrates using the <xref:System.ServiceModel.ServiceBehaviorAttribute> with the <xref:System.ServiceModel.ConcurrencyMode> enumeration, which controls whether an instance of a service processes messages sequentially or concurrently.</span></span> <span data-ttu-id="b0905-104">Das Beispiel basiert auf den ersten [Schritten, die](getting-started-sample.md)den `ICalculator` Dienstvertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="b0905-104">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="b0905-105">Dieses Beispiel definiert einen neuen Vertrag, `ICalculatorConcurrency`, der von `ICalculator` erbt und zwei zusätzliche Vorgänge für die Überwachung des Status der Dienstparallelität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b0905-105">This sample defines a new contract, `ICalculatorConcurrency`, which inherits from `ICalculator`, providing two additional operations for inspecting the state of the service concurrency.</span></span> <span data-ttu-id="b0905-106">Indem Sie die Einstellung für die Parallelität ändern, können Sie Änderungen im Verhalten beobachten, wenn Sie den Client ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0905-106">By altering the concurrency setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="b0905-107">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="b0905-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0905-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="b0905-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b0905-109">Es stehen drei Parallelitätsmodi zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b0905-109">There are three concurrency modes available:</span></span>  
  
- <span data-ttu-id="b0905-110">`Single`: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b0905-110">`Single`: Each service instance processes one message at a time.</span></span> <span data-ttu-id="b0905-111">Dies ist der Standardparallelitätsmodus.</span><span class="sxs-lookup"><span data-stu-id="b0905-111">This is the default concurrency mode.</span></span>  
  
- <span data-ttu-id="b0905-112">`Multiple`: Jede Dienstinstanz verarbeitet mehrere Nachrichten gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="b0905-112">`Multiple`: Each service instance processes multiple messages concurrently.</span></span> <span data-ttu-id="b0905-113">Für diesen Parallelitätsmodus muss die Dienstimplementierung threadsicher sein.</span><span class="sxs-lookup"><span data-stu-id="b0905-113">The service implementation must be thread-safe to use this concurrency mode.</span></span>  
  
- <span data-ttu-id="b0905-114">`Reentrant`: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht, akzeptiert jedoch eintrittsvariante Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="b0905-114">`Reentrant`: Each service instance processes one message at a time, but accepts reentrant calls.</span></span> <span data-ttu-id="b0905-115">Der Dienst akzeptiert diese Aufrufe nur, wenn er aufruft. Das reentrant-Beispiel wird im Beispiel "" von " [".](concurrencymode-reentrant.md)</span><span class="sxs-lookup"><span data-stu-id="b0905-115">The service only accepts these calls when it is calling out. Reentrant is demonstrated in the [ConcurrencyMode.Reentrant](concurrencymode-reentrant.md) sample.</span></span>  
  
 <span data-ttu-id="b0905-116">Die Parallelität steht mit dem Instanziierungsmodus in Beziehung.</span><span class="sxs-lookup"><span data-stu-id="b0905-116">The use of concurrency is related to the instancing mode.</span></span> <span data-ttu-id="b0905-117">In der <xref:System.ServiceModel.InstanceContextMode.PerCall>-Instanziierung ist Parallelität nicht relevant, da jede Nachricht von einer neuen Dienstinstanz verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b0905-117">In <xref:System.ServiceModel.InstanceContextMode.PerCall> instancing, concurrency is not relevant, because each message is processed by a new service instance.</span></span> <span data-ttu-id="b0905-118">In der <xref:System.ServiceModel.InstanceContextMode.Single>-Instanziierung ist entweder die <xref:System.ServiceModel.ConcurrencyMode.Single>- oder die <xref:System.ServiceModel.ConcurrencyMode.Multiple>-Parallelität relevant, je nachdem, ob die einzelne Instanz Nachrichten sequenziell oder parallel verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b0905-118">In <xref:System.ServiceModel.InstanceContextMode.Single> instancing, either <xref:System.ServiceModel.ConcurrencyMode.Single> or <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency is relevant, depending on whether the single instance processes messages sequentially or concurrently.</span></span> <span data-ttu-id="b0905-119">In der <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanziierung sind möglicherweise alle Parallelitätsmodi relevant.</span><span class="sxs-lookup"><span data-stu-id="b0905-119">In <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing, any of the concurrency modes may be relevant.</span></span>  
  
 <span data-ttu-id="b0905-120">Die Dienstklasse gibt das Parallelitätsverhalten mit dem `[ServiceBehavior(ConcurrencyMode=<setting>)]`-Attribut an, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b0905-120">The service class specifies concurrency behavior with the `[ServiceBehavior(ConcurrencyMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="b0905-121">Durch wechselndes Auskommentieren der Zeilen können Sie mit den Parallelitätsmodi `Single` und `Multiple` experimentieren.</span><span class="sxs-lookup"><span data-stu-id="b0905-121">By changing which lines are commented out, you can experiment with the `Single` and `Multiple` concurrency modes.</span></span> <span data-ttu-id="b0905-122">Denken Sie daran, den Dienst nach dem Ändern des Parallelitätsmodus neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0905-122">Remember to rebuild the service after changing the concurrency mode.</span></span>  
  
```csharp
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 <span data-ttu-id="b0905-123">Im Beispiel wird standardmäßig die <xref:System.ServiceModel.ConcurrencyMode.Multiple>-Parallelität mit der <xref:System.ServiceModel.InstanceContextMode.Single>-Instanziierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0905-123">The sample uses <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency with <xref:System.ServiceModel.InstanceContextMode.Single> instancing by default.</span></span> <span data-ttu-id="b0905-124">Der Clientcode wurde geändert, um einen asynchronen Proxy zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0905-124">The client code has been modified to use an asynchronous proxy.</span></span> <span data-ttu-id="b0905-125">Auf diese Weise kann der Client mehrere Aufrufe an den Dienst ausführen, ohne zwischen den Aufrufen auf eine Antwort zu warten.</span><span class="sxs-lookup"><span data-stu-id="b0905-125">This allows the client to make multiple calls to the service without waiting for a response between each call.</span></span> <span data-ttu-id="b0905-126">Sie können das unterschiedliche Verhalten des Dienstparallelitätsmodus beobachten.</span><span class="sxs-lookup"><span data-stu-id="b0905-126">You can observe the difference in behavior of the service concurrency mode.</span></span>  
  
 <span data-ttu-id="b0905-127">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0905-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b0905-128">Der vom Dienst ausgeführte Parallelitätsmodus wird angezeigt, jeder Vorgang wird aufgerufen, und anschließend wird die Anzahl der Vorgänge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0905-128">The concurrency mode that the service is running under is displayed, each operation is called, and then the operation count is displayed.</span></span> <span data-ttu-id="b0905-129">Beachten Sie, dass die Ergebnisse in einer anderen Reihenfolge als in der zurückgeben werden, in der sie aufgerufen wurden, wenn der Parallelitätsmodus `Multiple` ist, da der Dienst mehrere Nachrichten gleichzeitig verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b0905-129">Notice that when the concurrency mode is `Multiple`, the results are returned in a different order than how they were called, because the service processes multiple messages concurrently.</span></span> <span data-ttu-id="b0905-130">Wenn der Parallelitätsmodus zu `Single` geändert wird, werden die Ergebnisse in der Reihenfolge zurückgegeben, in der sie aufgerufen wurden, da alle Nachrichten sequenziell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b0905-130">By changing the concurrency mode to `Single`, the results are returned in the order they were called, because the service processes each message sequentially.</span></span> <span data-ttu-id="b0905-131">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b0905-131">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0905-132">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="b0905-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b0905-133">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="b0905-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b0905-134">Wenn Sie "Svcutil. exe" verwenden, um den Proxy Client zu generieren, stellen Sie sicher, dass Sie die `/async` Option einschließen.</span><span class="sxs-lookup"><span data-stu-id="b0905-134">If you use Svcutil.exe to generate the proxy client, ensure that you include the `/async` option.</span></span>  
  
3. <span data-ttu-id="b0905-135">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b0905-135">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="b0905-136">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b0905-136">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b0905-137">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b0905-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0905-138">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b0905-138">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b0905-139">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0905-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0905-140">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b0905-140">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
