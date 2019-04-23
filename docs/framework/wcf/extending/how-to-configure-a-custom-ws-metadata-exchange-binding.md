---
title: 'Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 51681e258e6a21b3a7ae604d1c0ef65d320bfb4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311876"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="e9cc3-102">Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung</span><span class="sxs-lookup"><span data-stu-id="e9cc3-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>
<span data-ttu-id="e9cc3-103">In diesem Thema wird erläutert, wie Sie eine benutzerdefinierte WS-Metadatenaustausch-Bindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e9cc3-103">This topic will explain how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="e9cc3-104">Windows Communication Foundation (WCF) enthält vier vom System definierte metadatenbindungen, aber Sie können Metadaten mit jeder gewünschten Bindung veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e9cc3-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="e9cc3-105">In diesem Thema wird beschrieben, wie Metadaten mit der `wsHttpBinding` veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="e9cc3-105">This topic will show you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="e9cc3-106">Diese Bindung ermöglicht es Ihnen, Metadaten auf eine sichere Weise verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e9cc3-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="e9cc3-107">Der Code in diesem Artikel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e9cc3-107">The code in this article is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="e9cc3-108">Verwenden einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e9cc3-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="e9cc3-109">Fügen Sie in der Konfigurationsdatei des Dienstes ein Dienstverhalten hinzu, das das `serviceMetadata`-Tag enthält:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="e9cc3-110">Fügen Sie dem Dienst-Tag ein `behaviorConfiguration`-Attribut hinzu, das auf dieses neue Verhalten verweist:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3. <span data-ttu-id="e9cc3-111">Fügen Sie einen Metadatenendpunkt hinzu, der MEX als Adresse, `wsHttpBinding` als Bindung und <xref:System.ServiceModel.Description.IMetadataExchange> als Vertrag angibt:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="e9cc3-112">Fügen Sie ein Endpunkt-Tag in der Client-Konfigurationsdatei hinzu, um zu überprüfen, ob der Metadatenaustausch-Endpunkt ordnungsgemäß funktioniert:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-112">To verify the metadata exchange endpoint is working correctly add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="e9cc3-113">Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie ihre <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="e9cc3-114">Konfigurieren durch Code</span><span class="sxs-lookup"><span data-stu-id="e9cc3-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="e9cc3-115">Erstellen Sie eine <xref:System.ServiceModel.WSHttpBinding>-Bindungsinstanz:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="e9cc3-116">Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="e9cc3-117">Fügen Sie einen Dienstendpunkt hinzu, und fügen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz hinzu:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="e9cc3-118">Fügen Sie einen Metadatenaustausch-Endpunkt hinzu, der die zuvor erstellte <xref:System.ServiceModel.WSHttpBinding> angibt:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="e9cc3-119">Fügen Sie ein Endpunkt-Tag in der Client-Konfigurationsdatei hinzu, um zu überprüfen, ob der Metadatenaustausch-Endpunkt ordnungsgemäß funktioniert:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="e9cc3-120">Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie die <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:</span><span class="sxs-lookup"><span data-stu-id="e9cc3-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e9cc3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9cc3-121">See also</span></span>

- [<span data-ttu-id="e9cc3-122">Metadatenveröffentlichungsverhalten</span><span class="sxs-lookup"><span data-stu-id="e9cc3-122">Metadata Publishing Behavior</span></span>](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="e9cc3-123">Metadaten abrufen</span><span class="sxs-lookup"><span data-stu-id="e9cc3-123">Retrieve Metadata</span></span>](../../../../docs/framework/wcf/samples/retrieve-metadata.md)
- [<span data-ttu-id="e9cc3-124">Metadaten</span><span class="sxs-lookup"><span data-stu-id="e9cc3-124">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="e9cc3-125">Veröffentlichen von Metadaten</span><span class="sxs-lookup"><span data-stu-id="e9cc3-125">Publishing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)
- [<span data-ttu-id="e9cc3-126">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="e9cc3-126">Publishing Metadata Endpoints</span></span>](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
