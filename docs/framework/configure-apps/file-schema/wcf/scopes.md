---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: eee6382c578648866045fd9b283454d9e0e76fcb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275023"
---
# <a name="scopes"></a><span data-ttu-id="c3f53-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="c3f53-101">\<scopes></span></span>
<span data-ttu-id="c3f53-102">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="c3f53-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="c3f53-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c3f53-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c3f53-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c3f53-104">\<behaviors></span></span>  
<span data-ttu-id="c3f53-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c3f53-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="c3f53-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c3f53-106">\<behavior></span></span>  
<span data-ttu-id="c3f53-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="c3f53-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="c3f53-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="c3f53-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3f53-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3f53-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3f53-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3f53-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c3f53-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3f53-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3f53-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3f53-112">Attributes</span></span>  
 <span data-ttu-id="c3f53-113">Keine</span><span class="sxs-lookup"><span data-stu-id="c3f53-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3f53-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3f53-114">Child Elements</span></span>  
  
|<span data-ttu-id="c3f53-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="c3f53-115">Attribute</span></span>|<span data-ttu-id="c3f53-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3f53-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="c3f53-117">\<add></span><span class="sxs-lookup"><span data-stu-id="c3f53-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="c3f53-118">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c3f53-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3f53-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3f53-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c3f53-120">Element</span><span class="sxs-lookup"><span data-stu-id="c3f53-120">Element</span></span>|<span data-ttu-id="c3f53-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3f53-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3f53-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="c3f53-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="c3f53-123">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="c3f53-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3f53-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3f53-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
