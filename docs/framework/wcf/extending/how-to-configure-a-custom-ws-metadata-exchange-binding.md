---
title: 'Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 6459e3f0cf0ab72af8027bd6802a0e7aa574aece
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635784"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="53107-102">Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung</span><span class="sxs-lookup"><span data-stu-id="53107-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>

<span data-ttu-id="53107-103">In diesem Artikel wird erläutert, wie Sie eine benutzerdefinierte WS-Metadata-Austauschbindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="53107-103">This article explains how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="53107-104">Windows Communication Foundation (WCF) enthält vier systemdefinierte Metadatenbindungen, Sie können Metadaten jedoch mit einer beliebigen Bindung veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="53107-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="53107-105">In diesem Artikel erfahren Sie, `wsHttpBinding`wie Sie Metadaten mit der veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="53107-105">This article shows you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="53107-106">Diese Bindung ermöglicht es Ihnen, Metadaten auf eine sichere Weise verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="53107-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="53107-107">Der Code in diesem Artikel basiert auf der [Ersten Schritte](../samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="53107-107">The code in this article is based on the [Getting Started](../samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="53107-108">Verwenden einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="53107-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="53107-109">Fügen Sie in der Konfigurationsdatei des Dienstes ein Dienstverhalten hinzu, das das `serviceMetadata`-Tag enthält:</span><span class="sxs-lookup"><span data-stu-id="53107-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="53107-110">Fügen Sie dem Dienst-Tag ein `behaviorConfiguration`-Attribut hinzu, das auf dieses neue Verhalten verweist:</span><span class="sxs-lookup"><span data-stu-id="53107-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. <span data-ttu-id="53107-111">Fügen Sie einen Metadatenendpunkt hinzu, der MEX als Adresse, `wsHttpBinding` als Bindung und <xref:System.ServiceModel.Description.IMetadataExchange> als Vertrag angibt:</span><span class="sxs-lookup"><span data-stu-id="53107-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="53107-112">Um zu überprüfen, ob der Metadatenaustauschendpunkt ordnungsgemäß funktioniert, fügen Sie der Clientkonfigurationsdatei ein Endpunkt-Tag hinzu:</span><span class="sxs-lookup"><span data-stu-id="53107-112">To verify the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="53107-113">Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie ihre <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:</span><span class="sxs-lookup"><span data-stu-id="53107-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="53107-114">Konfigurieren durch Code</span><span class="sxs-lookup"><span data-stu-id="53107-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="53107-115">Erstellen Sie eine <xref:System.ServiceModel.WSHttpBinding>-Bindungsinstanz:</span><span class="sxs-lookup"><span data-stu-id="53107-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="53107-116">Erstellen Sie eine <xref:System.ServiceModel.ServiceHost>-Instanz:</span><span class="sxs-lookup"><span data-stu-id="53107-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="53107-117">Fügen Sie einen Dienstendpunkt hinzu, und fügen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz hinzu:</span><span class="sxs-lookup"><span data-stu-id="53107-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="53107-118">Fügen Sie einen Metadatenaustausch-Endpunkt hinzu, der die zuvor erstellte <xref:System.ServiceModel.WSHttpBinding> angibt:</span><span class="sxs-lookup"><span data-stu-id="53107-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="53107-119">Fügen Sie ein Endpunkt-Tag in der Client-Konfigurationsdatei hinzu, um zu überprüfen, ob der Metadatenaustausch-Endpunkt ordnungsgemäß funktioniert:</span><span class="sxs-lookup"><span data-stu-id="53107-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="53107-120">Erstellen Sie in der Main()-Methode des Clients eine neue <xref:System.ServiceModel.Description.MetadataExchangeClient>-Instanz, legen Sie die <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A>-Eigenschaft auf `true` fest, rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf, und durchlaufen Sie dann die Auflistung zurückgegebener Metadaten:</span><span class="sxs-lookup"><span data-stu-id="53107-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="53107-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53107-121">See also</span></span>

- [<span data-ttu-id="53107-122">Metadatenveröffentlichungsverhalten</span><span class="sxs-lookup"><span data-stu-id="53107-122">Metadata Publishing Behavior</span></span>](../samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="53107-123">Metadaten abrufen</span><span class="sxs-lookup"><span data-stu-id="53107-123">Retrieve Metadata</span></span>](../samples/retrieve-metadata.md)
- [<span data-ttu-id="53107-124">Metadaten</span><span class="sxs-lookup"><span data-stu-id="53107-124">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="53107-125">Veröffentlichen von Metadaten</span><span class="sxs-lookup"><span data-stu-id="53107-125">Publishing Metadata</span></span>](../feature-details/publishing-metadata.md)
- [<span data-ttu-id="53107-126">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="53107-126">Publishing Metadata Endpoints</span></span>](../publishing-metadata-endpoints.md)
