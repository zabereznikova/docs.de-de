---
title: '&lt;Bereiche&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b35696cbecb0badf397d6d48e7c97aae3d0232e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltscopesgt"></a><span data-ttu-id="c28c6-102">&lt;Bereiche&gt;</span><span class="sxs-lookup"><span data-stu-id="c28c6-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="c28c6-103">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="c28c6-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="c28c6-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c28c6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c28c6-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="c28c6-105">\<behaviors></span></span>  
<span data-ttu-id="c28c6-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c28c6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c28c6-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="c28c6-107">\<behavior></span></span>  
<span data-ttu-id="c28c6-108">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="c28c6-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="c28c6-109">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="c28c6-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c28c6-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c28c6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c28c6-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c28c6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c28c6-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c28c6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c28c6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c28c6-113">Attributes</span></span>  
 <span data-ttu-id="c28c6-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="c28c6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c28c6-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c28c6-115">Child Elements</span></span>  
  
|<span data-ttu-id="c28c6-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="c28c6-116">Attribute</span></span>|<span data-ttu-id="c28c6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c28c6-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="c28c6-118">\<add></span><span class="sxs-lookup"><span data-stu-id="c28c6-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="c28c6-119">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c28c6-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c28c6-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c28c6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c28c6-121">Element</span><span class="sxs-lookup"><span data-stu-id="c28c6-121">Element</span></span>|<span data-ttu-id="c28c6-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c28c6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c28c6-123">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="c28c6-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="c28c6-124">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="c28c6-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c28c6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c28c6-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
