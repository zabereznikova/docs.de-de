---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 610ba29ec98f4b1f2a9b1db3542bcb3aefb46457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925654"
---
# <a name="entries"></a><span data-ttu-id="8a382-101">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="8a382-101">\<entries></span></span>
<span data-ttu-id="8a382-102">Ein Routingeintrag, der Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a382-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="8a382-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8a382-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8a382-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="8a382-104">\<routing></span></span>  
<span data-ttu-id="8a382-105">\<RoutingTables-></span><span class="sxs-lookup"><span data-stu-id="8a382-105">\<routingTables></span></span>  
<span data-ttu-id="8a382-106">\<Tabellen ></span><span class="sxs-lookup"><span data-stu-id="8a382-106">\<table></span></span>  
<span data-ttu-id="8a382-107">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="8a382-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a382-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a382-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a382-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8a382-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8a382-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a382-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a382-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8a382-111">Attributes</span></span>  
 <span data-ttu-id="8a382-112">Keine</span><span class="sxs-lookup"><span data-stu-id="8a382-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8a382-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a382-113">Child Elements</span></span>  
  
|<span data-ttu-id="8a382-114">Element</span><span class="sxs-lookup"><span data-stu-id="8a382-114">Element</span></span>|<span data-ttu-id="8a382-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a382-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a382-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="8a382-116">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="8a382-117">Ordnet einem Clientendpunkt, der zuvor definiert wurde, einen Filter zu.</span><span class="sxs-lookup"><span data-stu-id="8a382-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="8a382-118">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="8a382-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a382-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a382-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8a382-120">Element</span><span class="sxs-lookup"><span data-stu-id="8a382-120">Element</span></span>|<span data-ttu-id="8a382-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a382-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a382-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="8a382-122">\<routing></span></span>](routing.md)|<span data-ttu-id="8a382-123">Ein Konfigurationsabschnitt, der eine Routingtabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="8a382-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a382-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a382-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
