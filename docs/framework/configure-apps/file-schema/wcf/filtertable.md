---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 7bdc76ba7a8e2927b93fa0207f48cc569279482f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747410"
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="43a9d-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="43a9d-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="43a9d-103">Stellt eine Routingtabelle, die enthält eine Liste der Filter für Nachrichten und zum Weiterleiten von Nachrichten an den Clientendpunkt zu ermitteln, ob der Filter auf "true" ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="43a9d-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="43a9d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="43a9d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="43a9d-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="43a9d-105">\<routing></span></span>  
<span data-ttu-id="43a9d-106">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="43a9d-106">\<routingTables></span></span>  
<span data-ttu-id="43a9d-107">\<Tabelle ></span><span class="sxs-lookup"><span data-stu-id="43a9d-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a9d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="43a9d-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="43a9d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="43a9d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="43a9d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43a9d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43a9d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="43a9d-111">Attributes</span></span>  
  
|<span data-ttu-id="43a9d-112">Element</span><span class="sxs-lookup"><span data-stu-id="43a9d-112">Element</span></span>|<span data-ttu-id="43a9d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43a9d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43a9d-114">Name</span><span class="sxs-lookup"><span data-stu-id="43a9d-114">name</span></span>|<span data-ttu-id="43a9d-115">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="43a9d-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43a9d-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43a9d-116">Child Elements</span></span>  
  
|<span data-ttu-id="43a9d-117">Element</span><span class="sxs-lookup"><span data-stu-id="43a9d-117">Element</span></span>|<span data-ttu-id="43a9d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43a9d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43a9d-119">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="43a9d-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="43a9d-120">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="43a9d-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43a9d-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="43a9d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="43a9d-122">Element</span><span class="sxs-lookup"><span data-stu-id="43a9d-122">Element</span></span>|<span data-ttu-id="43a9d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43a9d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43a9d-124">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="43a9d-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="43a9d-125">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="43a9d-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43a9d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43a9d-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
