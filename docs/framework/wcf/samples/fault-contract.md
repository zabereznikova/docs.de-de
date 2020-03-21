---
title: Fehlervertrag
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: c8e93f73d150132c9d6750b81ba2ade944808d40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183667"
---
# <a name="fault-contract"></a><span data-ttu-id="57fa2-102">Fehlervertrag</span><span class="sxs-lookup"><span data-stu-id="57fa2-102">Fault Contract</span></span>
<span data-ttu-id="57fa2-103">Im Fehlervertragsbeispiel wird veranschaulicht, wie Fehlerinformationen von einem Dienst zu einem Client übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="57fa2-103">The Fault Contract sample demonstrates how to communicate error information from a service to a client.</span></span> <span data-ttu-id="57fa2-104">Das Beispiel basiert auf den [Ersten Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), wobei dem Dienst zusätzlicher Code hinzugefügt wird, um eine interne Ausnahme in einen Fehler zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="57fa2-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="57fa2-105">Der Client versucht, eine Division durch 0 (null) auszuführen, um einen Fehlerzustand beim Dienst zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="57fa2-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57fa2-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="57fa2-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="57fa2-107">Der Rechnervertrag wurde geändert, um ein <xref:System.ServiceModel.FaultContractAttribute> einzuschließen, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="57fa2-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="57fa2-108">Das <xref:System.ServiceModel.FaultContractAttribute>-Attribut gibt an, dass der `Divide`-Vorgang möglicherweise einen Fehler vom Typ `MathFault` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="57fa2-108">The <xref:System.ServiceModel.FaultContractAttribute> attribute indicates that the `Divide` operation may return a fault of type `MathFault`.</span></span> <span data-ttu-id="57fa2-109">Ein Fehler kann von jedem Typ sein, der serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="57fa2-109">A fault can be of any type that can be serialized.</span></span> <span data-ttu-id="57fa2-110">In diesem Fall ist der `MathFault` ein Datenvertrag, wie im Folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="57fa2-110">In this case, the `MathFault` is a data contract, as follows:</span></span>  
  
```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
```  
  
 <span data-ttu-id="57fa2-111">Die `Divide`-Methode löst eine <xref:System.ServiceModel.FaultException%601>-Ausnahme aus, wenn eine Ausnahme durch Division durch 0 (null) auftritt, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="57fa2-111">The `Divide` method throws a <xref:System.ServiceModel.FaultException%601> exception when a divide by zero exception occurs as shown in the following sample code.</span></span> <span data-ttu-id="57fa2-112">Diese Ausnahme führt dazu, dass ein Fehler an den Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="57fa2-112">This exception results in a fault being sent to the client.</span></span>  
  
```csharp
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 <span data-ttu-id="57fa2-113">Der Clientcode erzwingt einen Fehler, indem eine Division durch 0 (null) angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="57fa2-113">The client code forces an error by requesting a division by zero.</span></span> <span data-ttu-id="57fa2-114">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57fa2-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="57fa2-115">Sie sehen, dass die Division durch 0 (null) als Fehler gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="57fa2-115">You see the division by zero being reported as a fault.</span></span> <span data-ttu-id="57fa2-116">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="57fa2-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="57fa2-117">Der Client fängt hierzu die entsprechende `FaultException<MathFault>`-Ausnahme ab:</span><span class="sxs-lookup"><span data-stu-id="57fa2-117">The client does this by catching the appropriate `FaultException<MathFault>` exception:</span></span>  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="57fa2-118">In der Standardeinstellung werden Details zu unerwarteten Ausnahmen nicht an den Client gesendet, damit verhindert wird, dass Informationen zur Dienstimplementierung die sichere Begrenzung des Diensts verlassen.</span><span class="sxs-lookup"><span data-stu-id="57fa2-118">By default, the details of unexpected exceptions are not sent to the client to prevent details of the service implementation from escaping the secure boundary of the service.</span></span> <span data-ttu-id="57fa2-119">`FaultContract` stellt eine Möglichkeit bereit, um Fehler in einem Vertrag so zu beschreiben und bestimmte Arten von Ausnahmen so zu kennzeichnen, dass sie für die Übertragung an den Client geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="57fa2-119">`FaultContract` provides a way to describe faults in a contract and mark certain types of exceptions as appropriate for transmission to the client.</span></span> <span data-ttu-id="57fa2-120">`FaultException<T>` stellt einen Laufzeitmechanismus zum Senden von Fehlern an den Consumer bereit.</span><span class="sxs-lookup"><span data-stu-id="57fa2-120">`FaultException<T>` provides the run-time mechanism for sending faults to consumers.</span></span>  
  
 <span data-ttu-id="57fa2-121">Es ist jedoch hilfreich, die internen Details eines Dienstfehlers beim Debuggen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="57fa2-121">However, it is useful to see the internal details of a service failure when debugging.</span></span> <span data-ttu-id="57fa2-122">Zum Deaktivieren des oben beschriebenen sicheren Verhaltens können Sie angeben, dass die Details zu allen unbehandelten Ausnahmen auf dem Server in den Fehler eingeschlossen werden sollen, der an den Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="57fa2-122">To turn off the secure behavior previously described, you can indicate that the details of every unhandled exception on the server should be included in the fault that is sent to the client.</span></span> <span data-ttu-id="57fa2-123">Dies wird durch Festlegen von <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> auf `true` erreicht.</span><span class="sxs-lookup"><span data-stu-id="57fa2-123">This is accomplished by setting <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> to `true`.</span></span> <span data-ttu-id="57fa2-124">Sie können dies im Code festlegen oder in der Konfiguration, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="57fa2-124">You can either set it in code, or in configuration as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="57fa2-125">Darüber hinaus muss das Verhalten dem Dienst `behaviorConfiguration` zugeordnet werden, indem das Attribut des Dienstes in der Konfigurationsdatei auf "CalculatorServiceBehavior" gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="57fa2-125">Further, the behavior must be associated with the service by setting the `behaviorConfiguration` attribute of the service in the configuration file to "CalculatorServiceBehavior".</span></span>  
  
 <span data-ttu-id="57fa2-126">Damit solche Fehler auf dem Client abgefangen werden, muss die nicht generische <xref:System.ServiceModel.FaultException> abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="57fa2-126">To catch such faults on the client, the non-generic <xref:System.ServiceModel.FaultException> must be caught.</span></span>  
  
 <span data-ttu-id="57fa2-127">Dieses Verhalten sollte nur für Debuggingzwecke verwendet und nie in der Produktion aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="57fa2-127">This behavior should only be used for debugging purposes and should never be enabled in production.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="57fa2-128">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="57fa2-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="57fa2-129">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="57fa2-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="57fa2-130">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="57fa2-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="57fa2-131">Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="57fa2-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="57fa2-132">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="57fa2-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="57fa2-133">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="57fa2-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="57fa2-134">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="57fa2-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="57fa2-135">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="57fa2-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  
