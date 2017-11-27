---
title: '&lt;add&gt; von &lt;entries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62236c604cd91c2dfe4b92cfaac4004fc18d439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="54f76-102">&lt;add&gt; von &lt;entries&gt;</span><span class="sxs-lookup"><span data-stu-id="54f76-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="54f76-103">Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="54f76-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="54f76-104">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="54f76-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="54f76-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="54f76-105">\<system.serviceModel></span></span>  
<span data-ttu-id="54f76-106">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="54f76-106">\<routing></span></span>  
<span data-ttu-id="54f76-107">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="54f76-107">\<routingTables></span></span>  
<span data-ttu-id="54f76-108">\<Tabelle ></span><span class="sxs-lookup"><span data-stu-id="54f76-108">\<table></span></span>  
<span data-ttu-id="54f76-109">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="54f76-109">\<entries></span></span>  
<span data-ttu-id="54f76-110">\<add></span><span class="sxs-lookup"><span data-stu-id="54f76-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f76-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="54f76-111">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54f76-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54f76-112">Attributes and Elements</span></span>  
 <span data-ttu-id="54f76-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54f76-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54f76-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="54f76-114">Attributes</span></span>  
  
|<span data-ttu-id="54f76-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="54f76-115">Attribute</span></span>|<span data-ttu-id="54f76-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54f76-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54f76-117">backupList</span><span class="sxs-lookup"><span data-stu-id="54f76-117">backupList</span></span>|<span data-ttu-id="54f76-118">Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.</span><span class="sxs-lookup"><span data-stu-id="54f76-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="54f76-119">Endpunkt (endpoint)</span><span class="sxs-lookup"><span data-stu-id="54f76-119">endpoint</span></span>|<span data-ttu-id="54f76-120">Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="54f76-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="54f76-121">filterName</span><span class="sxs-lookup"><span data-stu-id="54f76-121">filterName</span></span>|<span data-ttu-id="54f76-122">Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.</span><span class="sxs-lookup"><span data-stu-id="54f76-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="54f76-123">priority</span><span class="sxs-lookup"><span data-stu-id="54f76-123">priority</span></span>|<span data-ttu-id="54f76-124">Eine ganze Zahl, die die Priorität dieses Eintrags angibt.</span><span class="sxs-lookup"><span data-stu-id="54f76-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="54f76-125">Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht.</span><span class="sxs-lookup"><span data-stu-id="54f76-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="54f76-126">Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="54f76-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="54f76-127">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="54f76-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54f76-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54f76-128">Child Elements</span></span>  
 <span data-ttu-id="54f76-129">Keine</span><span class="sxs-lookup"><span data-stu-id="54f76-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54f76-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54f76-130">Parent Elements</span></span>  
  
|<span data-ttu-id="54f76-131">Element</span><span class="sxs-lookup"><span data-stu-id="54f76-131">Element</span></span>|<span data-ttu-id="54f76-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54f76-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54f76-133">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="54f76-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="54f76-134">Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="54f76-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54f76-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54f76-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
