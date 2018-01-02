---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8cf87cc74c7bb5d495584407c803dacc7b94f195
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="30e31-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="30e31-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="30e31-103">Stellt eine Routingtabelle, die enthält eine Liste der Filter für Nachrichten und zum Weiterleiten von Nachrichten an den Clientendpunkt zu ermitteln, ob der Filter auf "true" ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="30e31-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="30e31-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="30e31-104">\<system.serviceModel></span></span>  
<span data-ttu-id="30e31-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="30e31-105">\<routing></span></span>  
<span data-ttu-id="30e31-106">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="30e31-106">\<routingTables></span></span>  
<span data-ttu-id="30e31-107">\<Tabelle ></span><span class="sxs-lookup"><span data-stu-id="30e31-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e31-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="30e31-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="30e31-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30e31-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30e31-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30e31-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30e31-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="30e31-111">Attributes</span></span>  
  
|<span data-ttu-id="30e31-112">Element</span><span class="sxs-lookup"><span data-stu-id="30e31-112">Element</span></span>|<span data-ttu-id="30e31-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e31-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30e31-114">Name</span><span class="sxs-lookup"><span data-stu-id="30e31-114">name</span></span>|<span data-ttu-id="30e31-115">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="30e31-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30e31-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30e31-116">Child Elements</span></span>  
  
|<span data-ttu-id="30e31-117">Element</span><span class="sxs-lookup"><span data-stu-id="30e31-117">Element</span></span>|<span data-ttu-id="30e31-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e31-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30e31-119">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="30e31-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="30e31-120">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="30e31-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30e31-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30e31-121">Parent Elements</span></span>  
  
|<span data-ttu-id="30e31-122">Element</span><span class="sxs-lookup"><span data-stu-id="30e31-122">Element</span></span>|<span data-ttu-id="30e31-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30e31-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30e31-124">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="30e31-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="30e31-125">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="30e31-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30e31-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30e31-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
