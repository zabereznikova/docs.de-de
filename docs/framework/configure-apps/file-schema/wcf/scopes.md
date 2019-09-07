---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399933"
---
# <a name="scopes"></a><span data-ttu-id="aacb3-101">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="aacb3-101">\<scopes></span></span>
<span data-ttu-id="aacb3-102">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="aacb3-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="aacb3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aacb3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aacb3-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aacb3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aacb3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aacb3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="aacb3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aacb3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="aacb3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aacb3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="aacb3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointdiscovery->** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="aacb3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="aacb3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bereiche >**</span><span class="sxs-lookup"><span data-stu-id="aacb3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aacb3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="aacb3-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aacb3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aacb3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aacb3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aacb3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aacb3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="aacb3-113">Attributes</span></span>  
 <span data-ttu-id="aacb3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="aacb3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aacb3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aacb3-115">Child Elements</span></span>  
  
|<span data-ttu-id="aacb3-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="aacb3-116">Attribute</span></span>|<span data-ttu-id="aacb3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aacb3-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="aacb3-118">\<add></span><span class="sxs-lookup"><span data-stu-id="aacb3-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="aacb3-119">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="aacb3-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aacb3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aacb3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="aacb3-121">Element</span><span class="sxs-lookup"><span data-stu-id="aacb3-121">Element</span></span>|<span data-ttu-id="aacb3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aacb3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aacb3-123">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="aacb3-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="aacb3-124">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="aacb3-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aacb3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aacb3-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
