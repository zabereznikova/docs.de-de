---
title: '&lt;Einträge&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltentriesgt"></a><span data-ttu-id="3ce9e-102">&lt;Einträge&gt;</span><span class="sxs-lookup"><span data-stu-id="3ce9e-102">&lt;entries&gt;</span></span>
<span data-ttu-id="3ce9e-103">Ein Routingeintrag, der Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ce9e-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="3ce9e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3ce9e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3ce9e-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="3ce9e-105">\<routing></span></span>  
<span data-ttu-id="3ce9e-106">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="3ce9e-106">\<routingTables></span></span>  
<span data-ttu-id="3ce9e-107">\<Tabelle ></span><span class="sxs-lookup"><span data-stu-id="3ce9e-107">\<table></span></span>  
<span data-ttu-id="3ce9e-108">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="3ce9e-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce9e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ce9e-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3ce9e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3ce9e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ce9e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3ce9e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ce9e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3ce9e-112">Attributes</span></span>  
 <span data-ttu-id="3ce9e-113">Keine</span><span class="sxs-lookup"><span data-stu-id="3ce9e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3ce9e-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ce9e-114">Child Elements</span></span>  
  
|<span data-ttu-id="3ce9e-115">Element</span><span class="sxs-lookup"><span data-stu-id="3ce9e-115">Element</span></span>|<span data-ttu-id="3ce9e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ce9e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ce9e-117">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="3ce9e-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="3ce9e-118">Ordnet einem Clientendpunkt, der zuvor definiert wurde, einen Filter zu.</span><span class="sxs-lookup"><span data-stu-id="3ce9e-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="3ce9e-119">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="3ce9e-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ce9e-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3ce9e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3ce9e-121">Element</span><span class="sxs-lookup"><span data-stu-id="3ce9e-121">Element</span></span>|<span data-ttu-id="3ce9e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ce9e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ce9e-123">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="3ce9e-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="3ce9e-124">Ein Konfigurationsabschnitt, der eine Routingtabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="3ce9e-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ce9e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ce9e-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
