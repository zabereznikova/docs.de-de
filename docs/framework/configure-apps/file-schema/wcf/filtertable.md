---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925602"
---
# <a name="filtertable"></a><span data-ttu-id="df250-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="df250-101">\<filterTable></span></span>
<span data-ttu-id="df250-102">Stellt eine Routing Tabelle dar, die eine Liste von Filtern zum Auswerten von Nachrichten sowie den Client Endpunkt enthält, an den Nachrichten weitergeleitet werden sollen, wenn der Filter zu true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="df250-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="df250-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="df250-103">\<system.serviceModel></span></span>  
<span data-ttu-id="df250-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="df250-104">\<routing></span></span>  
<span data-ttu-id="df250-105">\<RoutingTables-></span><span class="sxs-lookup"><span data-stu-id="df250-105">\<routingTables></span></span>  
<span data-ttu-id="df250-106">\<Tabellen ></span><span class="sxs-lookup"><span data-stu-id="df250-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df250-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="df250-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df250-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="df250-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df250-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="df250-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df250-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="df250-110">Attributes</span></span>  
  
|<span data-ttu-id="df250-111">Element</span><span class="sxs-lookup"><span data-stu-id="df250-111">Element</span></span>|<span data-ttu-id="df250-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df250-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df250-113">Name</span><span class="sxs-lookup"><span data-stu-id="df250-113">name</span></span>|<span data-ttu-id="df250-114">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="df250-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df250-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df250-115">Child Elements</span></span>  
  
|<span data-ttu-id="df250-116">Element</span><span class="sxs-lookup"><span data-stu-id="df250-116">Element</span></span>|<span data-ttu-id="df250-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df250-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df250-118">\<filters></span><span class="sxs-lookup"><span data-stu-id="df250-118">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="df250-119">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="df250-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df250-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df250-120">Parent Elements</span></span>  
  
|<span data-ttu-id="df250-121">Element</span><span class="sxs-lookup"><span data-stu-id="df250-121">Element</span></span>|<span data-ttu-id="df250-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df250-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df250-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="df250-123">\<routing></span></span>](routing.md)|<span data-ttu-id="df250-124">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="df250-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df250-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df250-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
