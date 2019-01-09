---
title: '&lt;add&gt; von &lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 5a61aefd92390eefb95d1f3e39236e53fa264990
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151501"
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="695af-102">&lt;add&gt; von &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="695af-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="695af-103">Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="695af-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="695af-104">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="695af-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="695af-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="695af-105">\<system.serviceModel></span></span>  
<span data-ttu-id="695af-106">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="695af-106">\<routing></span></span>  
<span data-ttu-id="695af-107">\<FilterTables ></span><span class="sxs-lookup"><span data-stu-id="695af-107">\<filterTables></span></span>  
<span data-ttu-id="695af-108">\<FilterTable ></span><span class="sxs-lookup"><span data-stu-id="695af-108">\<filterTable></span></span>  
<span data-ttu-id="695af-109">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="695af-109">\<entries></span></span>  
<span data-ttu-id="695af-110">\<add></span><span class="sxs-lookup"><span data-stu-id="695af-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="695af-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="695af-111">Syntax</span></span>  
  
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
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="695af-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="695af-112">Attributes and Elements</span></span>  
 <span data-ttu-id="695af-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="695af-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="695af-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="695af-114">Attributes</span></span>  
  
|<span data-ttu-id="695af-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="695af-115">Attribute</span></span>|<span data-ttu-id="695af-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="695af-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="695af-117">backupList</span><span class="sxs-lookup"><span data-stu-id="695af-117">backupList</span></span>|<span data-ttu-id="695af-118">Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.</span><span class="sxs-lookup"><span data-stu-id="695af-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="695af-119">Endpunkt (endpoint)</span><span class="sxs-lookup"><span data-stu-id="695af-119">endpoint</span></span>|<span data-ttu-id="695af-120">Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="695af-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="695af-121">filterName</span><span class="sxs-lookup"><span data-stu-id="695af-121">filterName</span></span>|<span data-ttu-id="695af-122">Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.</span><span class="sxs-lookup"><span data-stu-id="695af-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="695af-123">priority</span><span class="sxs-lookup"><span data-stu-id="695af-123">priority</span></span>|<span data-ttu-id="695af-124">Eine ganze Zahl, die die Priorität dieses Eintrags angibt.</span><span class="sxs-lookup"><span data-stu-id="695af-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="695af-125">Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht.</span><span class="sxs-lookup"><span data-stu-id="695af-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="695af-126">Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="695af-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="695af-127">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="695af-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="695af-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="695af-128">Child Elements</span></span>  
 <span data-ttu-id="695af-129">Keine</span><span class="sxs-lookup"><span data-stu-id="695af-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="695af-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="695af-130">Parent Elements</span></span>  
  
|<span data-ttu-id="695af-131">Element</span><span class="sxs-lookup"><span data-stu-id="695af-131">Element</span></span>|<span data-ttu-id="695af-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="695af-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="695af-133">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="695af-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="695af-134">Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="695af-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="695af-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="695af-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
