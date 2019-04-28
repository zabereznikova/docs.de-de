---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 5561cf61cef2258ec61bd32770538add1c69f5c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704205"
---
# <a name="entries"></a><span data-ttu-id="313d4-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="313d4-101">\<entries></span></span>
<span data-ttu-id="313d4-102">Ein Routingeintrag, der Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="313d4-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="313d4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="313d4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="313d4-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="313d4-104">\<routing></span></span>  
<span data-ttu-id="313d4-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="313d4-105">\<routingTables></span></span>  
<span data-ttu-id="313d4-106">\<table></span><span class="sxs-lookup"><span data-stu-id="313d4-106">\<table></span></span>  
<span data-ttu-id="313d4-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="313d4-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="313d4-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="313d4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="313d4-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="313d4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="313d4-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="313d4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="313d4-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="313d4-111">Attributes</span></span>  
 <span data-ttu-id="313d4-112">Keine</span><span class="sxs-lookup"><span data-stu-id="313d4-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="313d4-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="313d4-113">Child Elements</span></span>  
  
|<span data-ttu-id="313d4-114">Element</span><span class="sxs-lookup"><span data-stu-id="313d4-114">Element</span></span>|<span data-ttu-id="313d4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="313d4-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="313d4-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="313d4-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="313d4-117">Ordnet einem Clientendpunkt, der zuvor definiert wurde, einen Filter zu.</span><span class="sxs-lookup"><span data-stu-id="313d4-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="313d4-118">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="313d4-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="313d4-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="313d4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="313d4-120">Element</span><span class="sxs-lookup"><span data-stu-id="313d4-120">Element</span></span>|<span data-ttu-id="313d4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="313d4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="313d4-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="313d4-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="313d4-123">Ein Konfigurationsabschnitt, der eine Routingtabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="313d4-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="313d4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="313d4-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
