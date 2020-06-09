---
title: Metadaten abrufen
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 4763686485dfe97844fad78cf0bb279113c0ce08
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594607"
---
# <a name="retrieve-metadata"></a><span data-ttu-id="28fe3-102">Metadaten abrufen</span><span class="sxs-lookup"><span data-stu-id="28fe3-102">Retrieve Metadata</span></span>
<span data-ttu-id="28fe3-103">Dieses Beispiel veranschaulicht, wie ein Client implementiert werden kann, der Metadaten dynamisch von einem Dienst abruft, um einen Endpunkt für die Kommunikation auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="28fe3-103">This sample demonstrates how to implement a client that dynamically retrieves metadata from a service to choose an endpoint with which to communicate.</span></span> <span data-ttu-id="28fe3-104">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="28fe3-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="28fe3-105">Der Dienst wurde so geändert, dass zwei Endpunkte verfügbar gemacht werden – ein Endpunkt an der Basisadresse mit der `basicHttpBinding` -Bindung und ein sicherer Endpunkt unter {*BaseAddress*}/Secure, der die- `wsHttpBinding` Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="28fe3-105">The service has been modified to expose two endpoints—an endpoint at the base address using the `basicHttpBinding` binding, and a secure endpoint at {*baseaddress*}/secure using the `wsHttpBinding` binding.</span></span> <span data-ttu-id="28fe3-106">Anstatt den Client mit den Endpunktadressen und -bindungen zu konfigurieren, ruft der Client mithilfe der Klasse  <xref:System.ServiceModel.Description.MetadataExchangeClient> dynamisch die Metadaten für den Dienst ab und importiert sie danach als <xref:System.ServiceModel.Description.ServiceEndpointCollection> mithilfe der <xref:System.ServiceModel.Description.WsdlImporter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="28fe3-106">Instead of configuring the client with the endpoint addresses and bindings, the client dynamically retrieves the metadata for the service using the <xref:System.ServiceModel.Description.MetadataExchangeClient> class and then imports the metadata as a <xref:System.ServiceModel.Description.ServiceEndpointCollection> using the <xref:System.ServiceModel.Description.WsdlImporter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28fe3-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="28fe3-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="28fe3-108">Die Clientanwendung verwendet die importierte <xref:System.ServiceModel.Description.ServiceEndpointCollection>, um Clients für die Kommunikation mit dem Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="28fe3-108">The client application uses the imported <xref:System.ServiceModel.Description.ServiceEndpointCollection> to create clients to communicate with the service.</span></span> <span data-ttu-id="28fe3-109">Die Clientanwendung durchläuft jeden empfangenen Endpunkt und kommuniziert mit jedem Endpunkt, der den `ICalculator`-Vertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="28fe3-109">The client application iterates through each retrieved endpoint and communicates with each endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="28fe3-110">Die geeignete Adresse und Bindung werden zusammen mit dem empfangenen Endpunkt bereitgestellt, sodass der Client für die Kommunikation mit den einzelnen Endpunkten konfiguriert wird, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="28fe3-110">The appropriate address and binding are provided with the retrieved endpoint, so that the client is configured to communicate with each endpoint, as shown in the following sample code.</span></span>  
  
```csharp
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 <span data-ttu-id="28fe3-111">Das Clientkonsolenfenster zeigt die an jeden Endpunkt gesendeten Vorgänge an (unter Angabe von Adresspfad und Bindungsnamen).</span><span class="sxs-lookup"><span data-stu-id="28fe3-111">The client console window displays the operations sent to each of the endpoints, displaying the address path and binding name.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="28fe3-112">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="28fe3-112">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="28fe3-113">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="28fe3-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="28fe3-114">Um die c#-, C++-oder Visual Basic .NET-Edition der Projekt Mappe zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="28fe3-114">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="28fe3-115">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="28fe3-115">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="28fe3-116">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="28fe3-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="28fe3-117">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="28fe3-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="28fe3-118">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28fe3-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="28fe3-119">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="28fe3-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  
