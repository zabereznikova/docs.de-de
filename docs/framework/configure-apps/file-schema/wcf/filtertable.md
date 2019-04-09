---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 4e5c7d56e35afe3001f4c70064adbfef7702c720
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229276"
---
# <a name="filtertable"></a><span data-ttu-id="3d54f-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="3d54f-101">\<filterTable></span></span>
<span data-ttu-id="3d54f-102">Stellt eine Routingtabelle, die enthält eine Liste der Filter Nachrichten und Weiterleiten von Nachrichten an den Clientendpunkt zu ermitteln, ob der Filter auf "true" ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="3d54f-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="3d54f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3d54f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="3d54f-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="3d54f-104">\<routing></span></span>  
<span data-ttu-id="3d54f-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="3d54f-105">\<routingTables></span></span>  
<span data-ttu-id="3d54f-106">\<table></span><span class="sxs-lookup"><span data-stu-id="3d54f-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d54f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d54f-107">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d54f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3d54f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3d54f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d54f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d54f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d54f-110">Attributes</span></span>  
  
|<span data-ttu-id="3d54f-111">Element</span><span class="sxs-lookup"><span data-stu-id="3d54f-111">Element</span></span>|<span data-ttu-id="3d54f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d54f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d54f-113">Name</span><span class="sxs-lookup"><span data-stu-id="3d54f-113">name</span></span>|<span data-ttu-id="3d54f-114">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="3d54f-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d54f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d54f-115">Child Elements</span></span>  
  
|<span data-ttu-id="3d54f-116">Element</span><span class="sxs-lookup"><span data-stu-id="3d54f-116">Element</span></span>|<span data-ttu-id="3d54f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d54f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d54f-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="3d54f-118">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="3d54f-119">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d54f-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d54f-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d54f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3d54f-121">Element</span><span class="sxs-lookup"><span data-stu-id="3d54f-121">Element</span></span>|<span data-ttu-id="3d54f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d54f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d54f-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="3d54f-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="3d54f-124">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="3d54f-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d54f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d54f-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
