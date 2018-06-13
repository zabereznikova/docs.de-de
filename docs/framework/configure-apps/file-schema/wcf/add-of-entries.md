---
title: '&lt;add&gt; von &lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: a6960c16c84c13d905f0993ee3cfc1cf67df07fc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744979"
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="12a63-102">&lt;add&gt; von &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="12a63-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="12a63-103">Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="12a63-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="12a63-104">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="12a63-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="12a63-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="12a63-105">\<system.serviceModel></span></span>  
<span data-ttu-id="12a63-106">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="12a63-106">\<routing></span></span>  
<span data-ttu-id="12a63-107">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="12a63-107">\<routingTables></span></span>  
<span data-ttu-id="12a63-108">\<Tabelle ></span><span class="sxs-lookup"><span data-stu-id="12a63-108">\<table></span></span>  
<span data-ttu-id="12a63-109">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="12a63-109">\<entries></span></span>  
<span data-ttu-id="12a63-110">\<add></span><span class="sxs-lookup"><span data-stu-id="12a63-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a63-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="12a63-111">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12a63-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12a63-112">Attributes and Elements</span></span>  
 <span data-ttu-id="12a63-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12a63-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12a63-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="12a63-114">Attributes</span></span>  
  
|<span data-ttu-id="12a63-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="12a63-115">Attribute</span></span>|<span data-ttu-id="12a63-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12a63-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12a63-117">backupList</span><span class="sxs-lookup"><span data-stu-id="12a63-117">backupList</span></span>|<span data-ttu-id="12a63-118">Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.</span><span class="sxs-lookup"><span data-stu-id="12a63-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="12a63-119">Endpunkt (endpoint)</span><span class="sxs-lookup"><span data-stu-id="12a63-119">endpoint</span></span>|<span data-ttu-id="12a63-120">Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="12a63-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="12a63-121">filterName</span><span class="sxs-lookup"><span data-stu-id="12a63-121">filterName</span></span>|<span data-ttu-id="12a63-122">Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.</span><span class="sxs-lookup"><span data-stu-id="12a63-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="12a63-123">priority</span><span class="sxs-lookup"><span data-stu-id="12a63-123">priority</span></span>|<span data-ttu-id="12a63-124">Eine ganze Zahl, die die Priorität dieses Eintrags angibt.</span><span class="sxs-lookup"><span data-stu-id="12a63-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="12a63-125">Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht.</span><span class="sxs-lookup"><span data-stu-id="12a63-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="12a63-126">Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="12a63-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="12a63-127">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="12a63-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12a63-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12a63-128">Child Elements</span></span>  
 <span data-ttu-id="12a63-129">Keine</span><span class="sxs-lookup"><span data-stu-id="12a63-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12a63-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12a63-130">Parent Elements</span></span>  
  
|<span data-ttu-id="12a63-131">Element</span><span class="sxs-lookup"><span data-stu-id="12a63-131">Element</span></span>|<span data-ttu-id="12a63-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12a63-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12a63-133">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="12a63-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="12a63-134">Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="12a63-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12a63-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12a63-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
