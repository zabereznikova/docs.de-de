---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 5cb64c54067ba695f67d86c0026db77ebbe7d5ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919047"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="2cea3-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="2cea3-101">\<endpointDiscovery></span></span>
<span data-ttu-id="2cea3-102">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="2cea3-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="2cea3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2cea3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2cea3-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2cea3-104">\<behaviors></span></span>  
<span data-ttu-id="2cea3-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2cea3-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="2cea3-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2cea3-106">\<behavior></span></span>  
<span data-ttu-id="2cea3-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="2cea3-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cea3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cea3-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cea3-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cea3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2cea3-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cea3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cea3-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cea3-111">Attributes</span></span>  
  
|<span data-ttu-id="2cea3-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2cea3-112">Attribute</span></span>|<span data-ttu-id="2cea3-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cea3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cea3-114">aktiviert</span><span class="sxs-lookup"><span data-stu-id="2cea3-114">enabled</span></span>|<span data-ttu-id="2cea3-115">Ein boolescher Wert, der angibt, ob die Auffindbarkeit für diesen Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2cea3-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="2cea3-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="2cea3-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cea3-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cea3-117">Child Elements</span></span>  
  
|<span data-ttu-id="2cea3-118">Element</span><span class="sxs-lookup"><span data-stu-id="2cea3-118">Element</span></span>|<span data-ttu-id="2cea3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cea3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cea3-120">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="2cea3-120">\<scopes></span></span>](scopes.md)|<span data-ttu-id="2cea3-121">Eine Auflistung von Bereichs-URIs für den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="2cea3-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="2cea3-122">Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="2cea3-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="2cea3-123">Erweiterungen > [von \<endpointdiscovery >] [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="2cea3-123">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="2cea3-124">Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2cea3-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="2cea3-125">\<Typen ></span><span class="sxs-lookup"><span data-stu-id="2cea3-125">\<types></span></span>|<span data-ttu-id="2cea3-126">Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2cea3-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cea3-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cea3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2cea3-128">Element</span><span class="sxs-lookup"><span data-stu-id="2cea3-128">Element</span></span>|<span data-ttu-id="2cea3-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cea3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cea3-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2cea3-130">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2cea3-131">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2cea3-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="2cea3-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cea3-132">Remarks</span></span>  
 <span data-ttu-id="2cea3-133">Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.</span><span class="sxs-lookup"><span data-stu-id="2cea3-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="2cea3-134">Außerdem können Sie die [ \<Bereiche >](scopes.md)untergeordneten Elements verwenden, um benutzerdefinierte Bereichs-URIs anzugeben, die verwendet werden können, um Dienst Endpunkte während der Abfrage zu filtern, sowie die [ \<Erweiterungen >](extensions.md) untergeordneten Elements, um benutzerdefinierte Elemente anzugeben. Metadaten, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, "Kontoname", "bindingName", "Scope" und "ListenUri") veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2cea3-134">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="2cea3-135">Dieses Konfigurationselement ist vom Service [ \<Discovery->](servicediscovery.md) Element abhängig, das die serviservimebene Kontrolle über die Auffindbarkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2cea3-135">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="2cea3-136">Dies bedeutet, dass die Einstellungen dieses Elements ignoriert werden, wenn [ \<Service Discovery >](servicediscovery.md) nicht in der Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2cea3-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cea3-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cea3-137">Example</span></span>  
 <span data-ttu-id="2cea3-138">Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2cea3-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="2cea3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cea3-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
