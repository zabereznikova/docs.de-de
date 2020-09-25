---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 621c742e3bb06ce91fa5a6b8951351295f73df9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185807"
---
# \<endpointDiscovery>

<span data-ttu-id="b44a0-101">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="b44a0-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="b44a0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b44a0-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b44a0-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b44a0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b44a0-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b44a0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b44a0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b44a0-105">Attributes</span></span>  
  
|<span data-ttu-id="b44a0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b44a0-106">Attribute</span></span>|<span data-ttu-id="b44a0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b44a0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b44a0-108">enabled</span><span class="sxs-lookup"><span data-stu-id="b44a0-108">enabled</span></span>|<span data-ttu-id="b44a0-109">Ein boolescher Wert, der angibt, ob die Auffindbarkeit für diesen Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b44a0-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="b44a0-110">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="b44a0-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b44a0-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b44a0-111">Child Elements</span></span>  
  
|<span data-ttu-id="b44a0-112">Element</span><span class="sxs-lookup"><span data-stu-id="b44a0-112">Element</span></span>|<span data-ttu-id="b44a0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b44a0-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="b44a0-114">Eine Auflistung von Bereichs-URIs für den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="b44a0-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="b44a0-115">Einem Endpunkt können mehrere Bereichs-URIs zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b44a0-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="b44a0-116">[\<extensions>](extensions.md) [von \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="b44a0-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="b44a0-117">Eine Auflistung von XML-Elementen, die Ihnen ermöglicht, benutzerdefinierte Metadaten anzugeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b44a0-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="b44a0-118">Eine Auflistung von Schnittstellen, nach denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b44a0-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b44a0-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b44a0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b44a0-120">Element</span><span class="sxs-lookup"><span data-stu-id="b44a0-120">Element</span></span>|<span data-ttu-id="b44a0-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b44a0-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="b44a0-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="b44a0-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="b44a0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b44a0-123">Remarks</span></span>  

 <span data-ttu-id="b44a0-124">Bei Hinzufügung zur Verhaltenskonfiguration des Endpunkts und bei Festlegen des `enabled`-Attributs auf `true` aktiviert dieses Konfigurationselement seine Ermittelbarkeit.</span><span class="sxs-lookup"><span data-stu-id="b44a0-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="b44a0-125">Außerdem können Sie mit dem untergeordneten- [\<scopes>](scopes.md) Element benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienst Endpunkte während der Abfrage zu filtern. Außerdem können Sie das untergeordnete-Element verwenden, um [\<extensions>](extensions.md) benutzerdefinierte Metadaten anzugeben, die zusammen mit den standardmäßigen sichtbaren Metadaten (EPR, Kontextname, bindingName, Scope und ListenUri) veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b44a0-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="b44a0-126">Dieses Konfigurationselement ist von dem [\<serviceDiscovery>](servicediscovery.md) Element abhängig, das die Dienst Ebene der Auffindbarkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b44a0-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="b44a0-127">Dies bedeutet, dass die Einstellungen dieses Elements ignoriert werden, wenn [\<serviceDiscovery>](servicediscovery.md) in der Konfiguration nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b44a0-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b44a0-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b44a0-128">Example</span></span>  

 <span data-ttu-id="b44a0-129">Im folgenden Konfigurationsbeispiel werden Filterbereiche und Erweiterungsmetadaten angegeben, die für einen Endpunkt veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b44a0-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b44a0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b44a0-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
