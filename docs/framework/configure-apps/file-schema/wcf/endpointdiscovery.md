---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 125baba917a49135aaa426df2cfa1a4dbe8ac1e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700909"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="15528-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="15528-101">\<endpointDiscovery></span></span>
<span data-ttu-id="15528-102">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="15528-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="15528-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="15528-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="15528-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="15528-104">\<behaviors></span></span>  
<span data-ttu-id="15528-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="15528-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="15528-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15528-106">\<behavior></span></span>  
<span data-ttu-id="15528-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="15528-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15528-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="15528-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15528-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15528-109">Attributes and Elements</span></span>  
 <span data-ttu-id="15528-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15528-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15528-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="15528-111">Attributes</span></span>  
  
|<span data-ttu-id="15528-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="15528-112">Attribute</span></span>|<span data-ttu-id="15528-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15528-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15528-114">enabled</span><span class="sxs-lookup"><span data-stu-id="15528-114">enabled</span></span>|<span data-ttu-id="15528-115">Ein boolescher Wert, der angibt, ob die ermittelbarkeit für diesen Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="15528-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="15528-116">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="15528-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15528-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15528-117">Child Elements</span></span>  
  
|<span data-ttu-id="15528-118">Element</span><span class="sxs-lookup"><span data-stu-id="15528-118">Element</span></span>|<span data-ttu-id="15528-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15528-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15528-120">\<scopes></span><span class="sxs-lookup"><span data-stu-id="15528-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="15528-121">Eine Auflistung von Bereichs-URIs für den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="15528-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="15528-122">Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="15528-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="15528-123">[\<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [von \<EndpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="15528-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="15528-124">Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15528-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="15528-125">\<types></span><span class="sxs-lookup"><span data-stu-id="15528-125">\<types></span></span>|<span data-ttu-id="15528-126">Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="15528-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15528-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15528-127">Parent Elements</span></span>  
  
|<span data-ttu-id="15528-128">Element</span><span class="sxs-lookup"><span data-stu-id="15528-128">Element</span></span>|<span data-ttu-id="15528-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15528-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15528-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15528-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="15528-131">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="15528-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="15528-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15528-132">Remarks</span></span>  
 <span data-ttu-id="15528-133">Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.</span><span class="sxs-lookup"><span data-stu-id="15528-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="15528-134">Darüber hinaus können Sie die [ \<Bereiche >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)untergeordnetes Element angeben benutzerdefinierter Bereichs-Uris, die verwendet werden kann, um Dienstendpunkte während der Abfrage filtern als auch die [ \<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) untergeordnetes Element, um benutzerdefinierte Metadaten anzugeben, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, ContractTypeName, BindingName, Scope und ListenURI) veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15528-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="15528-135">Dieses Konfigurationselement ist abhängig von der [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element, das der dienststeuerungs-Ebene für die Auffindbarkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="15528-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="15528-136">Dies bedeutet, dass die Einstellungen dieses Elements ignoriert werden, wenn [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) nicht in der Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="15528-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15528-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="15528-137">Example</span></span>  
 <span data-ttu-id="15528-138">Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="15528-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="15528-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15528-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
