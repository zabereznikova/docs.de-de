---
title: Sitzung
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: e364b539e355f669037983813f9e6d1e0371da1f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715088"
---
# <a name="session"></a><span data-ttu-id="01cdc-102">Sitzung</span><span class="sxs-lookup"><span data-stu-id="01cdc-102">Session</span></span>
<span data-ttu-id="01cdc-103">Das Sitzungsbeispiel führt vor, wie ein Vertrag implementiert wird, der eine Sitzung erfordert.</span><span class="sxs-lookup"><span data-stu-id="01cdc-103">The Session sample demonstrates how to implement a contract that requires a session.</span></span> <span data-ttu-id="01cdc-104">Eine Sitzung bietet den Kontext zum Ausführen mehrerer Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="01cdc-104">A session provides context for performing multiple operations.</span></span> <span data-ttu-id="01cdc-105">Dadurch wird ermöglicht, dass ein Dienst einer bestimmten Sitzung einen Zustand zuordnen kann, sodass nachfolgende Vorgänge den Zustand eines vorherigen Vorgangs verwenden können.</span><span class="sxs-lookup"><span data-stu-id="01cdc-105">This allows a service to associate state with a given session, such that subsequent operations can use the state of a previous operation.</span></span> <span data-ttu-id="01cdc-106">Dieses Beispiel basiert auf den ersten Schritten, durch die ein Rechner Dienst [implementiert wird.](../../../../docs/framework/wcf/samples/getting-started-sample.md)</span><span class="sxs-lookup"><span data-stu-id="01cdc-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="01cdc-107">Der `ICalculator`-Vertrag wurde so geändert, dass eine Reihe von arithmetischen Operationen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="01cdc-107">The `ICalculator` contract has been modified to allow a set of arithmetic operations to be performed, while keeping a running result.</span></span> <span data-ttu-id="01cdc-108">Diese Funktion wird vom `ICalculatorSession`-Vertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="01cdc-108">This functionality is defined by the `ICalculatorSession` contract.</span></span> <span data-ttu-id="01cdc-109">Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst den Status für einen Client bei.</span><span class="sxs-lookup"><span data-stu-id="01cdc-109">The service maintains the state for a client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="01cdc-110">Der Client kann das aktuelle Ergebnis abrufen, indem er `Result()` aufruft, und es auf Null löschen, indem er `Clear()` aufruft.</span><span class="sxs-lookup"><span data-stu-id="01cdc-110">The client can retrieve the current result by calling `Result()` and clear the result to zero by calling `Clear()`.</span></span>  
  
 <span data-ttu-id="01cdc-111">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="01cdc-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01cdc-112">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="01cdc-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="01cdc-113">Durch Festlegen von <xref:System.ServiceModel.SessionMode> des Vertrags auf `Required` wird sichergestellt, dass – wenn der Vertrag über eine bestimmte Bindung verfügbar gemacht wird – die Bindung Sitzungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01cdc-113">Setting the <xref:System.ServiceModel.SessionMode> of the contract to `Required` ensures that when the contract is exposed over a particular binding, the binding supports sessions.</span></span> <span data-ttu-id="01cdc-114">Wenn Sitzungen von der Bindung nicht unterstützt werden, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="01cdc-114">If the binding does not support sessions an exception is thrown.</span></span> <span data-ttu-id="01cdc-115">Die `ICalculatorSession`-Schnittstelle wird so definiert, dass ein oder mehrere Vorgänge aufgerufen werden können, die ein aktuelles Ergebnis ändern (siehe folgender Beispielcode).</span><span class="sxs-lookup"><span data-stu-id="01cdc-115">The `ICalculatorSession` interface is defined such that one or more operations can be called, which modifies a running result, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="01cdc-116">Der Dienst verwendet einen <xref:System.ServiceModel.InstanceContextMode> von <xref:System.ServiceModel.InstanceContextMode.PerSession>, um an jede eingehende Sitzung einen bestimmten Dienstinstanzkontext zu binden.</span><span class="sxs-lookup"><span data-stu-id="01cdc-116">The service uses a <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession> to bind a given service instance context to each incoming session.</span></span> <span data-ttu-id="01cdc-117">Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jede Sitzung in einer lokalen Membervariablen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="01cdc-117">This allows the service to maintain the running result for each session in a local member variable.</span></span>  
  
```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 <span data-ttu-id="01cdc-118">Beim Ausführen des Beispiels nimmt der Client mehrere Anforderungen am Server vor und fordert das Ergebnis ab, das dann im Clientkonsolenfenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="01cdc-118">When you run the sample, the client makes several requests to the server and requests the result, which it then displays in the client console window.</span></span> <span data-ttu-id="01cdc-119">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="01cdc-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="01cdc-120">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="01cdc-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="01cdc-121">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="01cdc-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="01cdc-122">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="01cdc-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="01cdc-123">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="01cdc-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="01cdc-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="01cdc-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="01cdc-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="01cdc-125">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="01cdc-126">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="01cdc-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01cdc-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="01cdc-127">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
