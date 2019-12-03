---
title: Zuverlässige WS-Sitzung
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: 1b1878b5e3d04968ae13527a594bb2520891c6e5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714607"
---
# <a name="ws-reliable-session"></a><span data-ttu-id="82bd5-102">Zuverlässige WS-Sitzung</span><span class="sxs-lookup"><span data-stu-id="82bd5-102">WS Reliable Session</span></span>
<span data-ttu-id="82bd5-103">Dieses Beispiel veranschaulicht die Verwendung von zuverlässigen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="82bd5-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="82bd5-104">Zuverlässige Sitzungen bieten Unterstützung für zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="82bd5-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="82bd5-105">Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen vorgenommen, wie Prüfung der Nachrichtenreihenfolge beim Eingang.</span><span class="sxs-lookup"><span data-stu-id="82bd5-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="82bd5-106">Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht.</span><span class="sxs-lookup"><span data-stu-id="82bd5-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="82bd5-107">Im Beispiel werden Sitzungen zum Aufrechterhalten des Clientstatus implementiert und eine Zustellungszusicherungen anhand der Nachrichtenreihenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82bd5-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="82bd5-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="82bd5-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="82bd5-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="82bd5-109">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="82bd5-110">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="82bd5-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82bd5-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="82bd5-111">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="82bd5-112">Dieses Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="82bd5-112">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="82bd5-113">Die Funktionen für zuverlässige Sitzungen sind in den Anwendungskonfigurationsdateien für Client und Dienst aktiviert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="82bd5-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="82bd5-114">In diesem Beispiel wird der Dienst in Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="82bd5-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82bd5-115">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="82bd5-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="82bd5-116">Im Beispiel wird `wsHttpBinding` verwendet.</span><span class="sxs-lookup"><span data-stu-id="82bd5-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="82bd5-117">Die Bindung wird in den Konfigurationsdateien sowohl für den Client als auch für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="82bd5-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="82bd5-118">Der Bindungstyp wird im `binding`-Attribut des Endpunktelements angegeben (siehe folgende Beispielkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="82bd5-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="82bd5-119">Der Endpunkt enthält ein `bindingConfiguration`-Attribut, das auf die Bindungskonfiguration namens „Binding1“ verweist.</span><span class="sxs-lookup"><span data-stu-id="82bd5-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="82bd5-120">Die Bindungs Konfiguration ermöglicht zuverlässige Sitzungen, indem das `enabled`-Attribut des [\<ReliableSession->](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) auf `true`festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="82bd5-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="82bd5-121">Zustellungszusicherungen für geordnete Sitzungen werden gesteuert, indem das geordnete Attribut auf `true` oder `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="82bd5-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="82bd5-122">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="82bd5-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="82bd5-123">Die Dienstimplementierungsklasse implementiert eine <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanziierung, um eine separate Klasseninstanz für jeden Client beizubehalten, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="82bd5-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="82bd5-124">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82bd5-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="82bd5-125">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="82bd5-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82bd5-126">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="82bd5-126">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="82bd5-127">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="82bd5-127">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="82bd5-128">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="82bd5-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="82bd5-129">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="82bd5-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="82bd5-130">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="82bd5-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
