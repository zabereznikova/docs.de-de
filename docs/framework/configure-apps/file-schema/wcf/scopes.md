---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213076"
---
# <a name="scopes"></a><span data-ttu-id="707a7-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="707a7-101">\<scopes></span></span>
<span data-ttu-id="707a7-102">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="707a7-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="707a7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="707a7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="707a7-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="707a7-104">\<behaviors></span></span>  
<span data-ttu-id="707a7-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="707a7-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="707a7-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="707a7-106">\<behavior></span></span>  
<span data-ttu-id="707a7-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="707a7-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="707a7-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="707a7-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707a7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="707a7-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="707a7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="707a7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="707a7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="707a7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="707a7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="707a7-112">Attributes</span></span>  
 <span data-ttu-id="707a7-113">Keine</span><span class="sxs-lookup"><span data-stu-id="707a7-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="707a7-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="707a7-114">Child Elements</span></span>  
  
|<span data-ttu-id="707a7-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="707a7-115">Attribute</span></span>|<span data-ttu-id="707a7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="707a7-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="707a7-117">\<add></span><span class="sxs-lookup"><span data-stu-id="707a7-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="707a7-118">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="707a7-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="707a7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="707a7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="707a7-120">Element</span><span class="sxs-lookup"><span data-stu-id="707a7-120">Element</span></span>|<span data-ttu-id="707a7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="707a7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="707a7-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="707a7-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="707a7-123">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="707a7-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="707a7-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="707a7-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
