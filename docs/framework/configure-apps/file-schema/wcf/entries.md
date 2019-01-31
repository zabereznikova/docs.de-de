---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 9c4c7fa4f778642d549deebce6e7476f4da13a0d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283685"
---
# <a name="entries"></a><span data-ttu-id="7ab7f-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="7ab7f-101">\<entries></span></span>
<span data-ttu-id="7ab7f-102">Ein Routingeintrag, der Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ab7f-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="7ab7f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7ab7f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="7ab7f-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="7ab7f-104">\<routing></span></span>  
<span data-ttu-id="7ab7f-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="7ab7f-105">\<routingTables></span></span>  
<span data-ttu-id="7ab7f-106">\<table></span><span class="sxs-lookup"><span data-stu-id="7ab7f-106">\<table></span></span>  
<span data-ttu-id="7ab7f-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="7ab7f-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab7f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ab7f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ab7f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ab7f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ab7f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ab7f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ab7f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ab7f-111">Attributes</span></span>  
 <span data-ttu-id="7ab7f-112">Keine</span><span class="sxs-lookup"><span data-stu-id="7ab7f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ab7f-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ab7f-113">Child Elements</span></span>  
  
|<span data-ttu-id="7ab7f-114">Element</span><span class="sxs-lookup"><span data-stu-id="7ab7f-114">Element</span></span>|<span data-ttu-id="7ab7f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ab7f-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ab7f-116">\<filters></span><span class="sxs-lookup"><span data-stu-id="7ab7f-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="7ab7f-117">Ordnet einem Clientendpunkt, der zuvor definiert wurde, einen Filter zu.</span><span class="sxs-lookup"><span data-stu-id="7ab7f-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="7ab7f-118">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="7ab7f-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ab7f-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ab7f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7ab7f-120">Element</span><span class="sxs-lookup"><span data-stu-id="7ab7f-120">Element</span></span>|<span data-ttu-id="7ab7f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ab7f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ab7f-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="7ab7f-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="7ab7f-123">Ein Konfigurationsabschnitt, der eine Routingtabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="7ab7f-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ab7f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ab7f-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
