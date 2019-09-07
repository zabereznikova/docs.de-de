---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398023"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="0013d-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="0013d-101">\<endpointDiscovery></span></span>
<span data-ttu-id="0013d-102">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="0013d-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="0013d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0013d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0013d-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0013d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0013d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0013d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0013d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0013d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="0013d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0013d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="0013d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<endpointdiscovery->**</span><span class="sxs-lookup"><span data-stu-id="0013d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0013d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0013d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0013d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0013d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0013d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0013d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0013d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0013d-112">Attributes</span></span>  
  
|<span data-ttu-id="0013d-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="0013d-113">Attribute</span></span>|<span data-ttu-id="0013d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0013d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0013d-115">aktiviert</span><span class="sxs-lookup"><span data-stu-id="0013d-115">enabled</span></span>|<span data-ttu-id="0013d-116">Ein boolescher Wert, der angibt, ob die Auffindbarkeit für diesen Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0013d-116">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="0013d-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0013d-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0013d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0013d-118">Child Elements</span></span>  
  
|<span data-ttu-id="0013d-119">Element</span><span class="sxs-lookup"><span data-stu-id="0013d-119">Element</span></span>|<span data-ttu-id="0013d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0013d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0013d-121">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="0013d-121">\<scopes></span></span>](scopes.md)|<span data-ttu-id="0013d-122">Eine Auflistung von Bereichs-URIs für den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="0013d-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="0013d-123">Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="0013d-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="0013d-124">Erweiterungen > [von \<endpointdiscovery >] [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="0013d-124">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="0013d-125">Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0013d-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="0013d-126">\<Typen ></span><span class="sxs-lookup"><span data-stu-id="0013d-126">\<types></span></span>|<span data-ttu-id="0013d-127">Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0013d-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0013d-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0013d-128">Parent Elements</span></span>  
  
|<span data-ttu-id="0013d-129">Element</span><span class="sxs-lookup"><span data-stu-id="0013d-129">Element</span></span>|<span data-ttu-id="0013d-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0013d-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0013d-131">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0013d-131">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0013d-132">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="0013d-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="0013d-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0013d-133">Remarks</span></span>  
 <span data-ttu-id="0013d-134">Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.</span><span class="sxs-lookup"><span data-stu-id="0013d-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="0013d-135">Außerdem können Sie die [ \<Bereiche >](scopes.md)untergeordneten Elements verwenden, um benutzerdefinierte Bereichs-URIs anzugeben, die verwendet werden können, um Dienst Endpunkte während der Abfrage zu filtern, sowie die [ \<Erweiterungen >](extensions.md) untergeordneten Elements, um benutzerdefinierte Elemente anzugeben. Metadaten, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, "Kontoname", "bindingName", "Scope" und "ListenUri") veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0013d-135">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="0013d-136">Dieses Konfigurationselement ist vom Service [ \<Discovery->](servicediscovery.md) Element abhängig, das die serviservimebene Kontrolle über die Auffindbarkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0013d-136">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="0013d-137">Dies bedeutet, dass die Einstellungen dieses Elements ignoriert werden, wenn [ \<Service Discovery >](servicediscovery.md) nicht in der Konfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0013d-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0013d-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0013d-138">Example</span></span>  
 <span data-ttu-id="0013d-139">Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0013d-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0013d-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0013d-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
