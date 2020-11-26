---
title: Unidirektional
ms.date: 03/30/2017
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
ms.openlocfilehash: 7732b63cccb98ac54d99a0430dbaf0c8abfdaaa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245041"
---
# <a name="one-way"></a><span data-ttu-id="efa77-102">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="efa77-102">One-Way</span></span>

<span data-ttu-id="efa77-103">In diesem Beispiel wird ein Dienstvertrag mit unidirektionalen Dienstvorgängen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="efa77-103">This sample demonstrates a service contact with one-way service operations.</span></span> <span data-ttu-id="efa77-104">Der Client wartet nicht darauf, dass Dienstvorgänge abgeschlossen sind, wie es bei bidirektionalen Dienstvorgängen der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="efa77-104">The client does not wait for service operations to complete as is the case with two-way service operations.</span></span> <span data-ttu-id="efa77-105">Dieses Beispiel basiert auf den ersten [Schritten und verwendet die](getting-started-sample.md) - `wsHttpBinding` Bindung.</span><span class="sxs-lookup"><span data-stu-id="efa77-105">This sample is based on the [Getting Started](getting-started-sample.md) and uses the `wsHttpBinding` binding.</span></span> <span data-ttu-id="efa77-106">Der Dienst ist in diesem Beispiel eine selbst gehostete Konsolenanwendung, sodass Sie den Dienst beobachten können, der Nachrichten empfängt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="efa77-106">The service in this sample is a self-hosted console application to enable you to observe the service that receives and processes requests.</span></span> <span data-ttu-id="efa77-107">Der Client ist auch eine Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="efa77-107">The client is also a console application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efa77-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="efa77-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="efa77-109">Wenn Sie einen unidirektionalen Dienstvertrag erstellen möchten, wenden Sie die <xref:System.ServiceModel.OperationContractAttribute>-Klasse auf alle Vorgänge an, und legen Sie <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> auf `true` fest, wie im folgenden Beispielcode dargestellt:</span><span class="sxs-lookup"><span data-stu-id="efa77-109">To create a one-way service contract, define your service contract, apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, and set <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> to `true` as shown in the following sample code:</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="efa77-110">Um zu veranschaulichen, dass der Client nicht auf das Abschließen von Dienstvorgängen wartet, implementiert der Dienstcode in diesem Beispiel eine Verzögerung von fünf Sekunden, wie im folgenden Beispielcode dargestellt:</span><span class="sxs-lookup"><span data-stu-id="efa77-110">To demonstrate that the client does not wait for the service operations to complete, the service code in this sample implements a five-second delay, as shown in the following sample code:</span></span>  
  
```csharp
// This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="efa77-111">Wenn der Client den Dienst aufruft, wird der Aufruf zurückgegeben, ohne auf das Abschließen des Dienstvorgangs zu warten.</span><span class="sxs-lookup"><span data-stu-id="efa77-111">When the client calls the service, the call returns without waiting for the service operation to complete.</span></span>  
  
 <span data-ttu-id="efa77-112">Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="efa77-112">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="efa77-113">Sie können sehen, wie der Dienst Nachrichten vom Client empfängt.</span><span class="sxs-lookup"><span data-stu-id="efa77-113">You can see the service receive messages from the client.</span></span> <span data-ttu-id="efa77-114">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="efa77-114">Press ENTER in each console window to shut down both the service and the client.</span></span>  
  
 <span data-ttu-id="efa77-115">Der Client wird vor dem Dienst beendet und veranschaulicht damit, dass ein Client nicht auf das Abschließen unidirektionaler Dienstvorgänge warten muss.</span><span class="sxs-lookup"><span data-stu-id="efa77-115">The client finishes ahead of the service, demonstrating that a client does not wait for one-way service operations to complete.</span></span> <span data-ttu-id="efa77-116">Die Clientausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="efa77-116">The client output is as follows:</span></span>  
  
```console  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="efa77-117">Die folgende Dienstausgabe wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="efa77-117">The following service output is shown:</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
> <span data-ttu-id="efa77-118">HTTP ist per Definition ein Anforderungs-/Antwortprotokoll: wenn eine Anforderung gestellt wird, wird eine Antwort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="efa77-118">HTTP is, by definition, a request/response protocol; when a request is made, a response is returned.</span></span> <span data-ttu-id="efa77-119">Dies gilt sogar für einen unidirektionalen Dienstvorgang, der über HTTP verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="efa77-119">This is true even for a one-way service operation that is exposed over HTTP.</span></span> <span data-ttu-id="efa77-120">Wenn der Vorgang aufgerufen wird, gibt der Dienst den HTTP-Statuscode 202 zurück, bevor der Dienstvorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="efa77-120">When the operation is called, the service returns an HTTP status code of 202 before the service operation has executed.</span></span> <span data-ttu-id="efa77-121">Dieser Statuscode bedeutet, dass die Anforderung zur Verarbeitung akzeptiert, die Verarbeitung jedoch noch nicht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="efa77-121">This status code means that the request has been accepted for processing, but the processing has not yet been completed.</span></span> <span data-ttu-id="efa77-122">Der den Vorgang aufrufende Client wird so lange blockiert, bis er die 202-Antwort vom Dienst empfängt.</span><span class="sxs-lookup"><span data-stu-id="efa77-122">The client that called the operation blocks until it receives the 202 response from the service.</span></span> <span data-ttu-id="efa77-123">Dadurch kann es zu unerwartetem Verhalten kommen, wenn mehrere unidirektionale Nachrichten mithilfe einer Bindung gesendet werden, die für die Verwendung von Sitzungen konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="efa77-123">This can cause some unexpected behavior when multiple one-way messages are sent using a binding that is configured to use sessions.</span></span> <span data-ttu-id="efa77-124">Die in diesem Beispiel verwendete `wsHttpBinding`-Bindung wird so konfiguriert, dass standardmäßig Sitzungen verwendet werden, um einen Sicherheitskontext herzustellen.</span><span class="sxs-lookup"><span data-stu-id="efa77-124">The `wsHttpBinding` binding used in this sample is configured to use sessions by default to establish a security context.</span></span> <span data-ttu-id="efa77-125">Standardmäßig treffen Nachrichten in einer Sitzung in der Reihenfolge ihres Versands ein.</span><span class="sxs-lookup"><span data-stu-id="efa77-125">By default, messages in a session are guaranteed to arrive in the order in which they are sent.</span></span> <span data-ttu-id="efa77-126">Aus diesem Grund wird die zweite Nachricht in einer Sitzung beim Senden erst nach dem Verarbeiten der ersten Nachricht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="efa77-126">Because of this, when the second message in a session is sent, it is not processed until the first message has been processed.</span></span> <span data-ttu-id="efa77-127">Das führt dazu, dass der Client erst dann die 202-Antwort für eine Nachricht empfängt, wenn die Verarbeitung der vorhergehenden Nachricht abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="efa77-127">The result of this is that the client does not receive the 202 response for a message until the processing of the previous message has been completed.</span></span> <span data-ttu-id="efa77-128">Der Client scheint daher bei jedem nachfolgenden Vorgangsaufruf zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="efa77-128">The client therefore appears to block on each subsequent operation call.</span></span> <span data-ttu-id="efa77-129">Um dieses Verhalten zu vermeiden, wird in diesem Beispiel die Laufzeit so konfiguriert, dass Nachrichten gleichzeitig an unterschiedliche Instanzen zur Verarbeitung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="efa77-129">To avoid this behavior, this sample configures the runtime to dispatch messages concurrently to distinct instances for processing.</span></span> <span data-ttu-id="efa77-130">Im Beispiel wird <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> auf `PerCall` festgelegt, sodass jede Nachricht von einer anderen Instanz verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="efa77-130">The sample sets <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> to `PerCall` so that each message can be processed by a different instance.</span></span> <span data-ttu-id="efa77-131"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> ist auf `Multiple` festgelegt, damit mehrere Threads gleichzeitig Nachrichten senden können.</span><span class="sxs-lookup"><span data-stu-id="efa77-131"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to `Multiple` to allow more than one thread to dispatch messages at a time.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="efa77-132">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="efa77-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="efa77-133">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="efa77-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="efa77-134">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="efa77-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="efa77-135">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="efa77-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efa77-136">Starten Sie den Dienst vor dem Client, und beenden Sie den Client vor dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="efa77-136">Run the service before you run the client and shut down the client before shutting down the service.</span></span> <span data-ttu-id="efa77-137">Dadurch wird eine Clientausnahme vermieden, wenn der Client die Sicherheitssitzung nicht ordnungsgemäß beenden kann, da der Dienst nicht mehr vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="efa77-137">This avoids a client exception when the client cannot close the security session cleanly because the service is gone.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="efa77-138">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="efa77-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="efa77-139">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="efa77-139">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="efa77-140">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efa77-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="efa77-141">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="efa77-141">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
