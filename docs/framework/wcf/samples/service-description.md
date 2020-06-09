---
title: Dienstbeschreibung
ms.date: 03/30/2017
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
ms.openlocfilehash: 467d8437ec6b3383974b1faf2a96aacb1524771a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596577"
---
# <a name="service-description"></a><span data-ttu-id="31c82-102">Dienstbeschreibung</span><span class="sxs-lookup"><span data-stu-id="31c82-102">Service Description</span></span>
<span data-ttu-id="31c82-103">Im Beispiel "Dienstbeschreibung" wird veranschaulicht, wie ein Dienst seine Dienstbeschreibungsinformationen zur Laufzeit abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="31c82-103">The Service Description sample demonstrates how a service can retrieve its service description information at runtime.</span></span> <span data-ttu-id="31c82-104">Das Beispiel basiert auf den ersten Schritten mit einem zusätzlichen Dienst Vorgang, der definiert [wird, um](getting-started-sample.md)beschreibende Informationen über den Dienst zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="31c82-104">The sample is based on the [Getting Started](getting-started-sample.md), with an additional service operation defined to return descriptive information about the service.</span></span> <span data-ttu-id="31c82-105">Die zurückgegebenen Informationen enthalten die Basisadressen und Endpunkte für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="31c82-105">The information that is returned lists the base addresses and endpoints for the service.</span></span> <span data-ttu-id="31c82-106">Der Dienst stellt diese Informationen mithilfe der Klassen <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> und <xref:System.ServiceModel.Description.ServiceDescription> bereit.</span><span class="sxs-lookup"><span data-stu-id="31c82-106">The service provides this information using the <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost>, and <xref:System.ServiceModel.Description.ServiceDescription> classes.</span></span>  
  
 <span data-ttu-id="31c82-107">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="31c82-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31c82-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="31c82-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="31c82-109">Dieses Beispiel enthält eine geänderte Version des Rechnervertrags mit der Bezeichnung `IServiceDescriptionCalculator`.</span><span class="sxs-lookup"><span data-stu-id="31c82-109">This sample has a modified version of the calculator contract called `IServiceDescriptionCalculator`.</span></span> <span data-ttu-id="31c82-110">Der Vertrag definiert einen zusätzlichen Dienstvorgang mit der Bezeichnung `GetServiceDescriptionInfo`, über den eine mehrzeilige Zeichenfolge an den Client zurückgegeben wird, die die Basisadressen oder die Adressen und Dienstendpunkte oder die Endpunkte für den Dienst beschreibt.</span><span class="sxs-lookup"><span data-stu-id="31c82-110">The contract defines an additional service operation named `GetServiceDescriptionInfo` that returns a multi-line string to the client that describes the base address or addresses and service endpoint or endpoints for the service.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 <span data-ttu-id="31c82-111">Im Implementierungscode für `GetServiceDescriptionInfo` wird <xref:System.ServiceModel.Description.ServiceDescription> verwendet, um die Dienstendpunkte aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="31c82-111">The implementation code for `GetServiceDescriptionInfo` uses the <xref:System.ServiceModel.Description.ServiceDescription> to list the service endpoints.</span></span> <span data-ttu-id="31c82-112">Da Dienstendpunkte relative Adressen haben können, werden zuerst die Basisadressen für den Dienst aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="31c82-112">Because service endpoints can have relative addresses, it first lists the base addresses for the service.</span></span> <span data-ttu-id="31c82-113">Der Code ruft seinen Vorgangskontext mithilfe von <xref:System.ServiceModel.OperationContext.Current%2A> ab, um all diese Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="31c82-113">To get all of this information, the code obtains its operation context using <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="31c82-114">Der <xref:System.ServiceModel.ServiceHost> und sein <xref:System.ServiceModel.Description.ServiceDescription>-Objekt werden aus dem Vorgangskontext abgerufen.</span><span class="sxs-lookup"><span data-stu-id="31c82-114">The <xref:System.ServiceModel.ServiceHost> and its <xref:System.ServiceModel.Description.ServiceDescription> object are retrieved from the operation context.</span></span> <span data-ttu-id="31c82-115">Um die Basisendpunkte für den Dienst aufzulisten, durchläuft der Code die Auflistung mit <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> des Diensthosts.</span><span class="sxs-lookup"><span data-stu-id="31c82-115">To list the base endpoints for the service, the code iterates through the service host's <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> collection.</span></span> <span data-ttu-id="31c82-116">Um die Dienstendpunkte für den Dienst aufzulisten, durchläuft der Code die Auflistung mit Endpunkten in der Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="31c82-116">To list the service endpoints for the service, the code iterates through the service description's endpoints collection.</span></span>  
  
```csharp
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 <span data-ttu-id="31c82-117">Bei der Ausführung des Beispiels werden die Rechnervorgänge und dann die vom `GetServiceDescriptionInfo`-Vorgang zurückgegebenen Dienstinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31c82-117">When you run the sample, you see the calculator operations and then the service information returned by the `GetServiceDescriptionInfo` operation.</span></span> <span data-ttu-id="31c82-118">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31c82-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="31c82-119">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="31c82-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="31c82-120">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="31c82-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="31c82-121">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="31c82-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="31c82-122">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="31c82-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="31c82-123">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="31c82-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="31c82-124">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="31c82-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="31c82-125">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31c82-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="31c82-126">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="31c82-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
