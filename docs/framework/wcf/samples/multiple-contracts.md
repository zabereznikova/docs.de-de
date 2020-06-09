---
title: Mehrere Verträge
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: e8451c49395a1dad55c5afca419f47a8e856b61f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602504"
---
# <a name="multiple-contracts"></a><span data-ttu-id="12081-102">Mehrere Verträge</span><span class="sxs-lookup"><span data-stu-id="12081-102">Multiple Contracts</span></span>
<span data-ttu-id="12081-103">Das Beispiel zu mehreren Verträgen zeigt, wie mehr als ein Vertrag für einen Dienst implementiert wird und wie Endpunkte zur Kommunikation mit den einzelnen implementierten Verträgen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="12081-103">The Multiple Contracts sample demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span> <span data-ttu-id="12081-104">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="12081-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="12081-105">Der Dienst wurde so geändert, dass zwei Verträge definiert sind – der `ICalculator`-Vertrag und der `ICalculatorSession`-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="12081-105">The service has been modified to define two contracts, the `ICalculator` contract and the `ICalculatorSession` contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12081-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="12081-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="12081-107">Die Dienstklasse implementiert sowohl den `ICalculator`-Vertrag als auch den `ICalculatorSession`-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="12081-107">The service class implements both the `ICalculator` and `ICalculatorSession` contracts.</span></span> <span data-ttu-id="12081-108">Da für einen der Verträge eine Sitzung erforderlich ist, verwendet der Dienst den <xref:System.ServiceModel.InstanceContextMode.PerSession>-Instanzmodus, um den Status während der Lebensdauer der Sitzung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="12081-108">Because one of the contracts requires a session, the service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the state over the lifetime of the session.</span></span>  
  
 <span data-ttu-id="12081-109">Die Dienstkonfiguration wurde so geändert, dass nun zwei Endpunkte definiert sind, um jeden der beiden Verträge zugänglich zu machen.</span><span class="sxs-lookup"><span data-stu-id="12081-109">The service configuration has been modified to define two endpoints to expose each contract.</span></span> <span data-ttu-id="12081-110">Der `ICalculator`-Endpunkt wird an der Basisadresse mit einer `basicHttpBinding` verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="12081-110">The `ICalculator` endpoint is exposed at the base address using a `basicHttpBinding`.</span></span> <span data-ttu-id="12081-111">Der `ICalculatorSession`-Endpunkt wird an der Basisadresse/in der Sitzung mit einer `wsHttpBinding` verfügbar gemacht, wobei für das `bindingConfiguration`-Attribut `BindingWithSession` festgelegt ist, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="12081-111">The `ICalculatorSession` endpoint is exposed at the baseaddress/session using a `wsHttpBinding` with the `bindingConfiguration` attribute set to `BindingWithSession`, as shown in the following sample configuration.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="12081-112">Der generierte Clientcode enthält nun eine Clientklasse für den ursprünglichen `ICalculator`-Vertrag und für den neuen `ICalculatorSession`-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="12081-112">The generated client code now includes a client class for both the original `ICalculator` contract and the new `ICalculatorSession` contract.</span></span> <span data-ttu-id="12081-113">Die Clientkonfiguration und der Code wurden geändert, um mit jedem Vertrag am entsprechenden Dienstendpunkt zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="12081-113">The client configuration and code have been modified to communicate with each contract at the appropriate service endpoint.</span></span>  
  
 <span data-ttu-id="12081-114">Der Client ist eine Konsolen-Windows-Anwendung (.exe).</span><span class="sxs-lookup"><span data-stu-id="12081-114">The client is a console windows application (.exe).</span></span> <span data-ttu-id="12081-115">Der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="12081-115">The service is hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="12081-116">Das Clientkonsolenfenster zeigt die an jeden Endpunkt gesendeten Vorgänge an (zuerst den Basisendpunkt, dann den sicheren Endpunkt).</span><span class="sxs-lookup"><span data-stu-id="12081-116">The client console window displays the operations sent to each of the endpoints, first the basic endpoint, followed by the secure endpoint.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="12081-117">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="12081-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="12081-118">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="12081-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="12081-119">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="12081-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="12081-120">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="12081-120">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="12081-121">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="12081-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="12081-122">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="12081-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="12081-123">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12081-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="12081-124">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="12081-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
