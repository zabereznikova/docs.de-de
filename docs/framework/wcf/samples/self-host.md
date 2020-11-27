---
title: Selbst gehostete Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
ms.openlocfilehash: f421e9e1fb33ca0f8a35025603d279c5629fb7ec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262592"
---
# <a name="self-host"></a><span data-ttu-id="e93d8-102">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="e93d8-102">Self-Host</span></span>

<span data-ttu-id="e93d8-103">In diesem Beispiel wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e93d8-103">This sample demonstrates how to implement a self-hosted service in a console application.</span></span> <span data-ttu-id="e93d8-104">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="e93d8-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="e93d8-105">Die Dienstkonfigurationsdatei wurde von "Web.config" in "App.config" umbenannt und so geändert, dass eine vom Host verwendete Basisadresse konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="e93d8-105">The service configuration file has been renamed from Web.config to App.config and modified to configure a base address, which the host uses.</span></span> <span data-ttu-id="e93d8-106">Der Quellcode für den Dienst wurde so geändert, dass eine statische `Main`-Funktion implementiert wird. Diese erstellt und öffnet einen Diensthost, der die konfigurierte Basisadresse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e93d8-106">The service source code has been modified to implement a static `Main` function that creates and opens a service host that provides the configured base address.</span></span> <span data-ttu-id="e93d8-107">Die Dienstimplementierung wurde geändert, sodass die Ausgabe für jeden Vorgang in der Konsole geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e93d8-107">The service implementation has been modified to write output to the console for each operation.</span></span> <span data-ttu-id="e93d8-108">Der Client ist unverändert geblieben, er wurde nur mit der richtigen Endpunktadresse des Diensts konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e93d8-108">The client has been unmodified, except for configuring the correct endpoint address of the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e93d8-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e93d8-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e93d8-110">Im Beispiel wird eine statische Hauptfunktion zum Erstellen eines <xref:System.ServiceModel.ServiceHost> für den gegebenen `CalculatorService`-Typ implementiert, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e93d8-110">The sample implements a static main function to create a <xref:System.ServiceModel.ServiceHost> for the given `CalculatorService` type, as shown in the following sample code.</span></span>  
  
```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 <span data-ttu-id="e93d8-111">Wenn ein Dienst in Internetinformationsdienste (IIS) oder Windows Process Activation Service (WAS) gehostet wird, wird die Basisadresse des Diensts von der Hostumgebung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e93d8-111">When a service is hosted in Internet Information Services (IIS) or Windows Process Activation Service (WAS), the base address of the service is provided by the hosting environment.</span></span> <span data-ttu-id="e93d8-112">Bei einem selbst gehosteten Dienst müssen Sie die Basisadresse selbst angeben.</span><span class="sxs-lookup"><span data-stu-id="e93d8-112">In the self-hosted case, you must specify the base address yourself.</span></span> <span data-ttu-id="e93d8-113">Dies erfolgt mit dem untergeordneten-Element, das untergeordnet ist, `add` [\<baseAddresses>](../../configure-apps/file-schema/wcf/baseaddresses.md) [\<host>](../../configure-apps/file-schema/wcf/host.md) [\<service>](../../configure-apps/file-schema/wcf/service.md) wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e93d8-113">This is done using the `add` element, child of [\<baseAddresses>](../../configure-apps/file-schema/wcf/baseaddresses.md), child of [\<host>](../../configure-apps/file-schema/wcf/host.md), child of [\<service>](../../configure-apps/file-schema/wcf/service.md) as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 <span data-ttu-id="e93d8-114">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e93d8-114">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="e93d8-115">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e93d8-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e93d8-116">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e93d8-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e93d8-117">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e93d8-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e93d8-118">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e93d8-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e93d8-119">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e93d8-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e93d8-120">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e93d8-120">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e93d8-121">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e93d8-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e93d8-122">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e93d8-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e93d8-123">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e93d8-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a><span data-ttu-id="e93d8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e93d8-124">See also</span></span>

- <span data-ttu-id="e93d8-125">[AppFabric-Hosting- und -Persistenzbeispiele](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e93d8-125">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
