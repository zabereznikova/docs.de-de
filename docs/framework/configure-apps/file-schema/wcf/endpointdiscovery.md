---
title: '&lt;endpointDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a997ddffa2267cdeb9e54bb98d4122db254104d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltendpointdiscoverygt"></a><span data-ttu-id="8fc23-102">&lt;endpointDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="8fc23-102">&lt;endpointDiscovery&gt;</span></span>
<span data-ttu-id="8fc23-103">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="8fc23-103">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="8fc23-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8fc23-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8fc23-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8fc23-105">\<behaviors></span></span>  
<span data-ttu-id="8fc23-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8fc23-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8fc23-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8fc23-107">\<behavior></span></span>  
<span data-ttu-id="8fc23-108">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="8fc23-108">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc23-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fc23-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fc23-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8fc23-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8fc23-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fc23-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fc23-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8fc23-112">Attributes</span></span>  
  
|<span data-ttu-id="8fc23-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8fc23-113">Attribute</span></span>|<span data-ttu-id="8fc23-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fc23-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8fc23-115">enabled</span><span class="sxs-lookup"><span data-stu-id="8fc23-115">enabled</span></span>|<span data-ttu-id="8fc23-116">Ein boolescher Wert, der angibt, ob die Ermittelbarkeit für diesen Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8fc23-116">A Boolean value that that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="8fc23-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="8fc23-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fc23-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fc23-118">Child Elements</span></span>  
  
|<span data-ttu-id="8fc23-119">Element</span><span class="sxs-lookup"><span data-stu-id="8fc23-119">Element</span></span>|<span data-ttu-id="8fc23-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fc23-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fc23-121">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="8fc23-121">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="8fc23-122">Eine Auflistung von Bereichs-URIs für den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="8fc23-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="8fc23-123">Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8fc23-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="8fc23-124">[\<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [von \<EndpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="8fc23-124">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="8fc23-125">Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fc23-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="8fc23-126">\<Typen ></span><span class="sxs-lookup"><span data-stu-id="8fc23-126">\<types></span></span>|<span data-ttu-id="8fc23-127">Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8fc23-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8fc23-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fc23-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8fc23-129">Element</span><span class="sxs-lookup"><span data-stu-id="8fc23-129">Element</span></span>|<span data-ttu-id="8fc23-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fc23-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fc23-131">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8fc23-131">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8fc23-132">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="8fc23-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="8fc23-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fc23-133">Remarks</span></span>  
 <span data-ttu-id="8fc23-134">Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.</span><span class="sxs-lookup"><span data-stu-id="8fc23-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="8fc23-135">Darüber hinaus können Sie die [ \<Bereiche >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)untergeordnetes Element angeben benutzerdefinierter Bereichs-Uris, die verwendet werden kann, um Dienstendpunkte während der Abfrage filtern als auch die [ \<Extensions >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) untergeordnetes Element, um benutzerdefinierte Metadaten anzugeben, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, ContractTypeName, BindingName, Bereich und ListenURI) veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fc23-135">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="8fc23-136">Dieses Konfigurationselement ist abhängig von der [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element, das die Service Level Control Steuerbarkeit der bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8fc23-136">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="8fc23-137">Dies bedeutet, dass die Einstellungen für dieses Element ignoriert werden, wenn [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) nicht in der Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8fc23-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fc23-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fc23-138">Example</span></span>  
 <span data-ttu-id="8fc23-139">Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fc23-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="8fc23-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fc23-140">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
