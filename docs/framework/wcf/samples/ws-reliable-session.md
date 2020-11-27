---
title: Zuverlässige WS-Sitzung
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: cf3e206724636113646c478407e61dc1c775b620
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267194"
---
# <a name="ws-reliable-session"></a><span data-ttu-id="e3573-102">Zuverlässige WS-Sitzung</span><span class="sxs-lookup"><span data-stu-id="e3573-102">WS Reliable Session</span></span>

<span data-ttu-id="e3573-103">Dieses Beispiel veranschaulicht die Verwendung von zuverlässigen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="e3573-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="e3573-104">Zuverlässige Sitzungen bieten Unterstützung für zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="e3573-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="e3573-105">Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen vorgenommen, wie Prüfung der Nachrichtenreihenfolge beim Eingang.</span><span class="sxs-lookup"><span data-stu-id="e3573-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="e3573-106">Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht.</span><span class="sxs-lookup"><span data-stu-id="e3573-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="e3573-107">Im Beispiel werden Sitzungen zum Aufrechterhalten des Clientstatus implementiert und eine Zustellungszusicherungen anhand der Nachrichtenreihenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e3573-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e3573-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e3573-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e3573-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e3573-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e3573-110">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3573-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e3573-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3573-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="e3573-112">Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e3573-112">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="e3573-113">Die Funktionen für zuverlässige Sitzungen sind in den Anwendungskonfigurationsdateien für Client und Dienst aktiviert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e3573-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="e3573-114">In diesem Beispiel wird der Dienst in Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="e3573-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3573-115">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e3573-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e3573-116">Im Beispiel wird `wsHttpBinding` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3573-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="e3573-117">Die Bindung wird in den Konfigurationsdateien sowohl für den Client als auch für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="e3573-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="e3573-118">Der Bindungstyp wird im `binding`-Attribut des Endpunktelements angegeben (siehe folgende Beispielkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="e3573-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="e3573-119">Der Endpunkt enthält ein `bindingConfiguration`-Attribut, das auf die Bindungskonfiguration namens „Binding1“ verweist.</span><span class="sxs-lookup"><span data-stu-id="e3573-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="e3573-120">Die Bindungs Konfiguration ermöglicht zuverlässige Sitzungen, indem das- `enabled` Attribut des auf festgelegt wird [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) `true` .</span><span class="sxs-lookup"><span data-stu-id="e3573-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="e3573-121">Zustellungszusicherungen für geordnete Sitzungen werden gesteuert, indem das geordnete Attribut auf `true` oder `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e3573-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="e3573-122">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="e3573-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="e3573-123">Die Dienstimplementierungsklasse implementiert eine <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanziierung, um eine separate Klasseninstanz für jeden Client beizubehalten, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e3573-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="e3573-124">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3573-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e3573-125">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e3573-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e3573-126">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e3573-126">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e3573-127">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="e3573-127">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="e3573-128">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e3573-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="e3573-129">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e3573-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="e3573-130">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3573-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
