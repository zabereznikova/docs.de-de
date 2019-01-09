---
title: '&lt;Bereiche&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 7afab700c2d9eb91ffe57bfefaf5864782a0af5f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145327"
---
# <a name="ltscopesgt"></a><span data-ttu-id="22c7e-102">&lt;Bereiche&gt;</span><span class="sxs-lookup"><span data-stu-id="22c7e-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="22c7e-103">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="22c7e-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="22c7e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="22c7e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="22c7e-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="22c7e-105">\<behaviors></span></span>  
<span data-ttu-id="22c7e-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="22c7e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="22c7e-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="22c7e-107">\<behavior></span></span>  
<span data-ttu-id="22c7e-108">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="22c7e-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="22c7e-109">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="22c7e-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c7e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="22c7e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22c7e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="22c7e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22c7e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="22c7e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22c7e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="22c7e-113">Attributes</span></span>  
 <span data-ttu-id="22c7e-114">Keine</span><span class="sxs-lookup"><span data-stu-id="22c7e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22c7e-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22c7e-115">Child Elements</span></span>  
  
|<span data-ttu-id="22c7e-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="22c7e-116">Attribute</span></span>|<span data-ttu-id="22c7e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22c7e-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="22c7e-118">\<add></span><span class="sxs-lookup"><span data-stu-id="22c7e-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="22c7e-119">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="22c7e-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22c7e-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22c7e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="22c7e-121">Element</span><span class="sxs-lookup"><span data-stu-id="22c7e-121">Element</span></span>|<span data-ttu-id="22c7e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22c7e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22c7e-123">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="22c7e-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="22c7e-124">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="22c7e-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22c7e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22c7e-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
