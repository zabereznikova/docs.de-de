---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f790e294b832f43a595d0636c60a8a67da5ad56a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147888"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="e60dd-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="e60dd-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="e60dd-103">Stellt eine Routingtabelle, die enthält eine Liste der Filter Nachrichten und Weiterleiten von Nachrichten an den Clientendpunkt zu ermitteln, ob der Filter auf "true" ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e60dd-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="e60dd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e60dd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e60dd-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="e60dd-105">\<routing></span></span>  
<span data-ttu-id="e60dd-106">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="e60dd-106">\<routingTables></span></span>  
<span data-ttu-id="e60dd-107">\<Tabelle ></span><span class="sxs-lookup"><span data-stu-id="e60dd-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e60dd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e60dd-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e60dd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e60dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e60dd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e60dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e60dd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e60dd-111">Attributes</span></span>  
  
|<span data-ttu-id="e60dd-112">Element</span><span class="sxs-lookup"><span data-stu-id="e60dd-112">Element</span></span>|<span data-ttu-id="e60dd-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e60dd-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e60dd-114">Name</span><span class="sxs-lookup"><span data-stu-id="e60dd-114">name</span></span>|<span data-ttu-id="e60dd-115">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="e60dd-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e60dd-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e60dd-116">Child Elements</span></span>  
  
|<span data-ttu-id="e60dd-117">Element</span><span class="sxs-lookup"><span data-stu-id="e60dd-117">Element</span></span>|<span data-ttu-id="e60dd-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e60dd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e60dd-119">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="e60dd-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="e60dd-120">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e60dd-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e60dd-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e60dd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e60dd-122">Element</span><span class="sxs-lookup"><span data-stu-id="e60dd-122">Element</span></span>|<span data-ttu-id="e60dd-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e60dd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e60dd-124">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="e60dd-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e60dd-125">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="e60dd-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e60dd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e60dd-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
