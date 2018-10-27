---
title: Standard-Dienstverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, defaults
- Default Service Behavior Sample [Windows Communication Foundation]
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
ms.openlocfilehash: 2c49c28d99bb3d300fd4589a088b2f086bdfd45d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184477"
---
# <a name="default-service-behavior"></a><span data-ttu-id="57bd7-102">Standard-Dienstverhalten</span><span class="sxs-lookup"><span data-stu-id="57bd7-102">Default Service Behavior</span></span>
<span data-ttu-id="57bd7-103">In diesem Beispiel wird veranschaulicht, wie Einstellungen für das Dienstverhalten konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="57bd7-103">This sample demonstrates how service behavior settings can be configured.</span></span> <span data-ttu-id="57bd7-104">Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert die `ICalculator` Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="57bd7-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="57bd7-105">In diesem Beispiel werden explizit Dienstverhaltensweisen und Vorgangsverhaltensweisen mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut bzw. dem <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut definiert.</span><span class="sxs-lookup"><span data-stu-id="57bd7-105">This sample explicitly defines service behaviors and operation behaviors using the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes.</span></span> <span data-ttu-id="57bd7-106">Sie können Verhaltensweisen in Konfigurationsdateien oder imperativ im Code konfigurieren, wie dieses Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="57bd7-106">You can configure behaviors in configuration files or imperatively in code (as this sample demonstrates).</span></span>  
  
 <span data-ttu-id="57bd7-107">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="57bd7-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57bd7-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="57bd7-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="57bd7-109">Die Dienstklasse gibt Verhaltensweisen mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute> und dem <xref:System.ServiceModel.OperationBehaviorAttribute> an, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="57bd7-109">The service class specifies behaviors with the <xref:System.ServiceModel.ServiceBehaviorAttribute> and the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following code sample.</span></span> <span data-ttu-id="57bd7-110">Alle angegebenen Werte sind Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="57bd7-110">All values specified are the defaults.</span></span>  
  
```csharp
[ServiceBehavior(  
    AutomaticSessionShutdown=true,  
    ConcurrencyMode=ConcurrencyMode.Single,  
    InstanceContextMode=InstanceContextMode.PerSession,  
    IncludeExceptionDetailInFaults=false,  
    UseSynchronizationContext=true,  
    ValidateMustUnderstand=true)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(  
        TransactionAutoComplete=true,  
        TransactionScopeRequired=false,  
        Impersonation=ImpersonationOption.NotAllowed)]  
    public double Add(double n1, double n2)  
    {  
        System.Threading.Thread.Sleep(1600);  
        return n1 + n2;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="57bd7-111">Dienstverhaltensweisen werden mit dem <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="57bd7-111">Service behaviors are specified with the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span> <span data-ttu-id="57bd7-112">In der folgenden Tabelle werden einige dieser Verhaltensweisen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="57bd7-112">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="57bd7-113">Dienstverhalten</span><span class="sxs-lookup"><span data-stu-id="57bd7-113">Service behavior</span></span>|<span data-ttu-id="57bd7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57bd7-114">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|<span data-ttu-id="57bd7-115">Fährt eine Sitzung auf Anforderung des Clients automatisch herunter.</span><span class="sxs-lookup"><span data-stu-id="57bd7-115">Automatically shuts down a session at the client's request.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|<span data-ttu-id="57bd7-116">Gibt den Parallelitätsmodus für jede Dienstinstanz an.</span><span class="sxs-lookup"><span data-stu-id="57bd7-116">Specifies the concurrency mode for each service instance.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|<span data-ttu-id="57bd7-117">Gibt den Instanzkontextmodus an.</span><span class="sxs-lookup"><span data-stu-id="57bd7-117">Specifies the instance context mode.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|<span data-ttu-id="57bd7-118">Bestimmt, ob der bereitgestellte Synchronisierungskontext (falls festgelegt) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="57bd7-118">Determines whether to use the provided synchronization context, if one is set.</span></span> <span data-ttu-id="57bd7-119">Verwenden Sie dies, wenn Sie kontrollieren möchten, ob in Windows Forms-Anwendungen ein `WindowsFormsSynchronizationContext` verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="57bd7-119">Use this when you want to control whether to use a `WindowsFormsSynchronizationContext` in Windows Forms applications.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|<span data-ttu-id="57bd7-120">Bestimmt, ob allgemeine unbehandelte Ausführungsausnahmen in eine `Fault<string>` konvertiert und als Fehlermeldung gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="57bd7-120">Determines whether general unhandled execution exceptions are to be converted into a `Fault<string>` and sent as a fault message.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|<span data-ttu-id="57bd7-121">Gibt die Isolierungsebene für Transaktionen an.</span><span class="sxs-lookup"><span data-stu-id="57bd7-121">Specifies the isolation level for transactions.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|<span data-ttu-id="57bd7-122">Legt fest, ob unerwartete Nachrichtenheader eine Fehlerbedingung auslösen.</span><span class="sxs-lookup"><span data-stu-id="57bd7-122">Determines whether unexpected message headers cause an error condition.</span></span>|  
  
 <span data-ttu-id="57bd7-123">Vorgangsverhaltensweisen werden mit dem <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="57bd7-123">Operation behaviors are specified by using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="57bd7-124">In der folgenden Tabelle werden einige dieser Verhaltensweisen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="57bd7-124">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="57bd7-125">Vorgangsverhalten</span><span class="sxs-lookup"><span data-stu-id="57bd7-125">Operation Behavior</span></span>|<span data-ttu-id="57bd7-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57bd7-126">Description</span></span>|  
|------------------------|-----------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|<span data-ttu-id="57bd7-127">Bestimmt, ob bei Abschluss eines Dienstvorgangs ein Commit für die aktuelle Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57bd7-127">Determines whether service operation completion commits the current transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|<span data-ttu-id="57bd7-128">Bestimmt, ob sich der Dienstvorgang in einem Clienttransaktionsfluss einträgt.</span><span class="sxs-lookup"><span data-stu-id="57bd7-128">Determines whether the service operation enlists in a client-flowed transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|<span data-ttu-id="57bd7-129">Bestimmt, ob der Dienstvorgang die Identität des Aufrufers annimmt.</span><span class="sxs-lookup"><span data-stu-id="57bd7-129">Determines whether the service operation impersonates the caller's identity.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|<span data-ttu-id="57bd7-130">Bestimmt, ob Dienstinstanzen zu Beginn oder am Ende des Dienstvorgangsaufrufs wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57bd7-130">Determines whether service instances are recycled at the start or end of the service operation call.</span></span>|  
  
 <span data-ttu-id="57bd7-131">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57bd7-131">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="57bd7-132">Die Verzögerung zwischen den Aufrufen resultiert von den in den Dienstvorgängen vorgenommenen Aufrufen von `System.Threading.Thread.Sleep()`.</span><span class="sxs-lookup"><span data-stu-id="57bd7-132">The delay between the calls is the result of the calls to `System.Threading.Thread.Sleep()` made in the service operations.</span></span> <span data-ttu-id="57bd7-133">Diese Verhaltensweisen werden in den restlichen Verhaltensbeispielen ausführlicher erklärt.</span><span class="sxs-lookup"><span data-stu-id="57bd7-133">The rest of the behavior samples explain these behaviors in more detail.</span></span> <span data-ttu-id="57bd7-134">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="57bd7-134">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="57bd7-135">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="57bd7-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="57bd7-136">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="57bd7-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="57bd7-137">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="57bd7-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="57bd7-138">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="57bd7-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57bd7-139">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="57bd7-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="57bd7-140">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="57bd7-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="57bd7-141">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="57bd7-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="57bd7-142">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="57bd7-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
  
## <a name="see-also"></a><span data-ttu-id="57bd7-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57bd7-143">See Also</span></span>
