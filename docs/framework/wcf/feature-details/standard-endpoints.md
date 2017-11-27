---
title: Standardendpunkte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 755669b1305060efeb6af592867844b571b67020
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2017
---
# <a name="standard-endpoints"></a><span data-ttu-id="0d626-102">Standardendpunkte</span><span class="sxs-lookup"><span data-stu-id="0d626-102">Standard Endpoints</span></span>
<span data-ttu-id="0d626-103">Endpunkte werden definiert, indem eine Adresse, eine Bindung und ein Vertrag angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0d626-103">Endpoints are defined by specifying an address, a binding, and a contract.</span></span> <span data-ttu-id="0d626-104">Andere Parameter, die für einen Endpunkt festgelegt werden können, sind beispielsweise Verhaltenskonfigurationen, Header und Abhör-URIs.</span><span class="sxs-lookup"><span data-stu-id="0d626-104">Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs.</span></span>  <span data-ttu-id="0d626-105">Für bestimmte Typen von Endpunkten ändern sich diese Werte nicht.</span><span class="sxs-lookup"><span data-stu-id="0d626-105">For certain types of endpoints these values do not change.</span></span> <span data-ttu-id="0d626-106">Beispielsweise verwenden Metadatenaustausch-Endpunkte immer den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="0d626-106">For example, metadata exchange endpoints always use the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="0d626-107">Andere Endpunkte, z. B. <xref:System.ServiceModel.Description.WebHttpEndpoint>, erfordern immer ein angegebenes Endpunktverhalten.</span><span class="sxs-lookup"><span data-stu-id="0d626-107">Other endpoints, such as <xref:System.ServiceModel.Description.WebHttpEndpoint> always require a specified endpoint behavior.</span></span> <span data-ttu-id="0d626-108">Die Verwendbarkeit eines Endpunkts kann verbessert werden, indem für häufig verwendete Endpunkteigenschaften Endpunkte mit Standardwerten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d626-108">The usability of an endpoint can be improved by having endpoints with default values for commonly used endpoint properties.</span></span> <span data-ttu-id="0d626-109">Mithilfe von Standardendpunkten können Entwickler einen Endpunkt definieren, der über Standardwerte verfügt oder für den sich eine oder mehrere Endpunkteigenschaften nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0d626-109">Standard endpoints enable a developer to define an endpoint that has default values or where one or more endpoint’s properties does not change.</span></span>  <span data-ttu-id="0d626-110">Mit diesen Endpunkten können Sie einen solchen Endpunkt verwenden, ohne Informationen statischer Natur angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="0d626-110">These endpoints allow you to use such an endpoint without having to specify information of a static nature.</span></span> <span data-ttu-id="0d626-111">Standardendpunkte können für Infrastruktur- und Anwendungsendpunkte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d626-111">Standard endpoints can be used for infrastructure and application endpoints.</span></span>  
  
## <a name="infrastructure-endpoints"></a><span data-ttu-id="0d626-112">Infrastrukturendpunkte</span><span class="sxs-lookup"><span data-stu-id="0d626-112">Infrastructure Endpoints</span></span>  
 <span data-ttu-id="0d626-113">Es kann sein, dass ein Dienst Endpunkte verfügbar macht, für die einige Eigenschaften vom Dienstautor nicht explizit implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0d626-113">A service may expose endpoints with some of the properties not explicitly implemented by the service author.</span></span> <span data-ttu-id="0d626-114">Der Metadatenaustausch-Endpunkt macht z. B. den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag verfügbar. Als Dienstautor implementieren Sie diese Schnittstelle jedoch nicht, sondern sie wird von der WCF implementiert.</span><span class="sxs-lookup"><span data-stu-id="0d626-114">For example, the metadata exchange endpoint exposes the <xref:System.ServiceModel.Description.IMetadataExchange> contract but as a service author you do not implement that interface, it is implemented by WCF.</span></span> <span data-ttu-id="0d626-115">Solche Infrastrukturendpunkte haben Standardwerte für eine oder mehrere Endpunkteigenschaften, von denen einige ggf. unveränderbar sind.</span><span class="sxs-lookup"><span data-stu-id="0d626-115">Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable.</span></span> <span data-ttu-id="0d626-116">Die <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A>-Eigenschaft des Metadatenaustausch-Endpunkts muss <xref:System.ServiceModel.Description.IMetadataExchange> sein, während andere Eigenschaften wie die Bindung vom Entwickler angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="0d626-116">The <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> property of the metadata exchange endpoint must be <xref:System.ServiceModel.Description.IMetadataExchange>, while other properties like binding can be supplied by the developer.</span></span> <span data-ttu-id="0d626-117">Infrastrukturendpunkte werden identifiziert, indem die <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A>-Eigenschaft auf `true` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0d626-117">Infrastructure endpoints are identified by setting the <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> property to `true`.</span></span>  
  
## <a name="application-endpoints"></a><span data-ttu-id="0d626-118">Anwendungsendpunkte</span><span class="sxs-lookup"><span data-stu-id="0d626-118">Application Endpoints</span></span>  
 <span data-ttu-id="0d626-119">Anwendungsentwickler können eigene Standardendpunkte definieren, die Standardwerte für die Adresse, die Bindung oder den Vertrag angeben.</span><span class="sxs-lookup"><span data-stu-id="0d626-119">Application developers can define their own standard endpoints which specify default values for the address, binding, or contract.</span></span> <span data-ttu-id="0d626-120">Sie definieren einen Standardendpunkt, indem Sie eine Klasse von <xref:System.ServiceModel.Description.ServiceEndpoint> ableiten und die entsprechenden Endpunkteigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="0d626-120">You define a standard endpoint by deriving a class from <xref:System.ServiceModel.Description.ServiceEndpoint> and setting the appropriate endpoint properties.</span></span> <span data-ttu-id="0d626-121">Sie können Standardwerte für Eigenschaften bereitstellen, die geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="0d626-121">You can provide default values for properties that can be changed.</span></span> <span data-ttu-id="0d626-122">Einige andere Eigenschaften verfügen über statische Werte, die sich nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="0d626-122">Some other properties will have static values that cannot change.</span></span> <span data-ttu-id="0d626-123">Das folgende Beispiel zeigt, wie Sie einen Standardendpunkt implementieren.</span><span class="sxs-lookup"><span data-stu-id="0d626-123">The following example shows how to implement a standard endpoint.</span></span>  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  
    
    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  
    
    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }
    
    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 <span data-ttu-id="0d626-124">Um einen benutzerdefinierten Endpunkt in einer Konfigurationsdatei zu verwenden, müssen Sie eine Klasse von <xref:System.ServiceModel.Configuration.StandardEndpointElement> ableiten, eine Klasse von <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> ableiten und den neuen Standardendpunkt in der Datei "app.config" oder "machine.config" im Abschnitt mit den Erweiterungen registrieren.  Das <xref:System.ServiceModel.Configuration.StandardEndpointElement>-Objekt bietet Konfigurationsunterstützung für den Standardendpunkt. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0d626-124">To use a user-defined custom endpoint in a configuration file you must derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointElement>, derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>, and register the new standard endpoint in the extensions section in app.config or machine.config.  The <xref:System.ServiceModel.Configuration.StandardEndpointElement> provides configuration support for the standard endpoint, as shown in the following example.</span></span>  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 <span data-ttu-id="0d626-125">Die <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> bietet der Unterstützungstyp für die Sammlung, die unter der <`standardEndpoints`> Abschnitt in der Konfiguration für den Standardendpunkt.</span><span class="sxs-lookup"><span data-stu-id="0d626-125">The <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> provides the backing type for the collection that appears under the <`standardEndpoints`> section in the configuration for the standard endpoint.</span></span>  <span data-ttu-id="0d626-126">Im folgenden Beispiel wird die Implementierung dieser Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0d626-126">The following example shows how to implement this class.</span></span>  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

<span data-ttu-id="0d626-127">Im folgenden Beispiel wird gezeigt, wie Sie einen Standardendpunkt im Abschnitt für die Erweiterungen registrieren.</span><span class="sxs-lookup"><span data-stu-id="0d626-127">The following example shows how to register a standard endpoint in the extensions section.</span></span>

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
```  
  
## <a name="configuring-a-standard-endpoint"></a><span data-ttu-id="0d626-128">Konfigurieren eines Standardendpunkts</span><span class="sxs-lookup"><span data-stu-id="0d626-128">Configuring a Standard Endpoint</span></span>  
 <span data-ttu-id="0d626-129">Standardendpunkte können im Code oder in der Konfiguration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0d626-129">Standard endpoints can be added in code or in configuration.</span></span>  <span data-ttu-id="0d626-130">Um einen Standardendpunkt im Code hinzuzufügen, instanziieren Sie einfach den entsprechenden Standardendpunkttyp und fügen diesen dem Diensthost wie im folgenden Beispiel dargestellt hinzu:</span><span class="sxs-lookup"><span data-stu-id="0d626-130">To add a standard endpoint in code simply instantiate the appropriate standard endpoint type and add it to the service host as shown in the following example:</span></span>  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 <span data-ttu-id="0d626-131">Um einen Standardendpunkt in der Konfiguration hinzuzufügen, fügen Sie ein <`endpoint`>-Elements auf der <`service`> Element und alle erforderlichen Konfigurationseinstellungen in der <`standardEndpoints`> Element.</span><span class="sxs-lookup"><span data-stu-id="0d626-131">To add a standard endpoint in configuration, add an <`endpoint`> element to the <`service`> element and any needed configuration settings in the <`standardEndpoints`> element.</span></span> <span data-ttu-id="0d626-132">Im folgenden Beispiel wird gezeigt, wie Sie ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Objekt hinzufügen. Dabei handelt es sich um einen der Standardendpunkte, die im Lieferumfang von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="0d626-132">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, one of the standard endpoints that ships with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>    
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 <span data-ttu-id="0d626-133">Der Typ des Standardendpunkts wird angegeben, mit dem Kind-Attribut in der <`endpoint`> Element.</span><span class="sxs-lookup"><span data-stu-id="0d626-133">The type of standard endpoint is specified using the kind attribute in the <`endpoint`> element.</span></span> <span data-ttu-id="0d626-134">Der Endpunkt ist konfiguriert, in der <`standardEndpoints`> Element.</span><span class="sxs-lookup"><span data-stu-id="0d626-134">The endpoint is configured within the <`standardEndpoints`> element.</span></span> <span data-ttu-id="0d626-135">Im obigen Beispiel wird ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Endpunkt hinzugefügt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0d626-135">In the example above, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint is added and configured.</span></span> <span data-ttu-id="0d626-136">Der <`udpDiscoveryEndpoint`> Element enthält ein <`standardEndpoint`> festlegt, die die <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> Eigenschaft von der <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="0d626-136">The <`udpDiscoveryEndpoint`> element contains a <`standardEndpoint`> that sets the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> property of the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a><span data-ttu-id="0d626-137">Im Lieferumfang von .NET Framework enthaltene Standardendpunkte</span><span class="sxs-lookup"><span data-stu-id="0d626-137">Standard Endpoints Shipped with the .NET Framework</span></span>  
 <span data-ttu-id="0d626-138">In der folgenden Tabelle sind die im Lieferumfang von [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] enthaltenen Standardendpunkte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d626-138">The following table lists the standard endpoints shipped with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 `Mex Endpoint`  
 <span data-ttu-id="0d626-139">Ein Standardendpunkt, der verwendet wird, um Dienstmetadaten verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="0d626-139">A standard endpoint that is used to expose service metadata.</span></span>  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 <span data-ttu-id="0d626-140">Ein Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsmeldungen zu senden.</span><span class="sxs-lookup"><span data-stu-id="0d626-140">A standard endpoint that is used by services to send announcement messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 <span data-ttu-id="0d626-141">Ein Standardendpunkt, der von Diensten verwendet wird, um Suchmeldungen zu senden.</span><span class="sxs-lookup"><span data-stu-id="0d626-141">A standard endpoint that is used by services to send discovery messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 <span data-ttu-id="0d626-142">Ein Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="0d626-142">A standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 <span data-ttu-id="0d626-143">Ein Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsmeldungen über eine UDP-Bindung zu senden.</span><span class="sxs-lookup"><span data-stu-id="0d626-143">A standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <span data-ttu-id="0d626-144">Ein Standardendpunkt, der die WS-Suche verwendet, um zur Laufzeit dynamisch nach der Endpunktadresse zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0d626-144">A standard endpoint that uses WS-Discovery to find the endpoint address dynamically at runtime.</span></span>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 <span data-ttu-id="0d626-145">Ein Standardendpunkt für den Metadatenaustausch.</span><span class="sxs-lookup"><span data-stu-id="0d626-145">A standard endpoint for metadata exchange.</span></span>  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <span data-ttu-id="0d626-146">Ein Standardendpunkt mit einer <xref:System.ServiceModel.WebHttpBinding>-Bindung, die das <xref:System.ServiceModel.Description.WebHttpBehavior>-Verhalten automatisch hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0d626-146">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior</span></span>  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <span data-ttu-id="0d626-147">Ein Standardendpunkt mit einer <xref:System.ServiceModel.WebHttpBinding>-Bindung, die das <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>-Verhalten automatisch hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0d626-147">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior.</span></span>  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <span data-ttu-id="0d626-148">Ein Standardendpunkt mit einer <xref:System.ServiceModel.WebHttpBinding>-Bindung.</span><span class="sxs-lookup"><span data-stu-id="0d626-148">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 <span data-ttu-id="0d626-149">Ein Standardendpunkt, der es Ihnen ermöglicht, Steuerungsvorgänge für Workflowinstanzen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0d626-149">A standard endpoint that enables you to call control operations on workflow instances.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 <span data-ttu-id="0d626-150">Ein Standardendpunkt, der die Workflowerstellung und die Wiederaufnahme von Lesezeichen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0d626-150">A standard endpoint that supports workflow creation and bookmark resumption.</span></span>
