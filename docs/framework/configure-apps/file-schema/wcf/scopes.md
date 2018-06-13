---
title: '&lt;Bereiche&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 7e2dda0d0def4d1f90bf1b4dbf54f18983355222
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749620"
---
# <a name="ltscopesgt"></a><span data-ttu-id="ddf55-102">&lt;Bereiche&gt;</span><span class="sxs-lookup"><span data-stu-id="ddf55-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="ddf55-103">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="ddf55-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="ddf55-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ddf55-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ddf55-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ddf55-105">\<behaviors></span></span>  
<span data-ttu-id="ddf55-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ddf55-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ddf55-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="ddf55-107">\<behavior></span></span>  
<span data-ttu-id="ddf55-108">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ddf55-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="ddf55-109">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="ddf55-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf55-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddf55-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddf55-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ddf55-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ddf55-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ddf55-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddf55-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ddf55-113">Attributes</span></span>  
 <span data-ttu-id="ddf55-114">Keine</span><span class="sxs-lookup"><span data-stu-id="ddf55-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ddf55-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddf55-115">Child Elements</span></span>  
  
|<span data-ttu-id="ddf55-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="ddf55-116">Attribute</span></span>|<span data-ttu-id="ddf55-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddf55-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ddf55-118">\<add></span><span class="sxs-lookup"><span data-stu-id="ddf55-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="ddf55-119">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ddf55-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ddf55-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ddf55-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ddf55-121">Element</span><span class="sxs-lookup"><span data-stu-id="ddf55-121">Element</span></span>|<span data-ttu-id="ddf55-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddf55-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddf55-123">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ddf55-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="ddf55-124">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="ddf55-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ddf55-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddf55-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
