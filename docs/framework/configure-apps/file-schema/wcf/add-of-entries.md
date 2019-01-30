---
title: <add> von <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 7267b8719987ecd25bcca78a7897a0d4172a42ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264569"
---
# <a name="add-of-entries"></a><span data-ttu-id="38f1d-102">\<Hinzufügen > der \<Einträge ></span><span class="sxs-lookup"><span data-stu-id="38f1d-102">\<add> of \<entries></span></span>
<span data-ttu-id="38f1d-103">Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="38f1d-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="38f1d-104">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="38f1d-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="38f1d-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="38f1d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="38f1d-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="38f1d-106">\<routing></span></span>  
<span data-ttu-id="38f1d-107">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="38f1d-107">\<filterTables></span></span>  
<span data-ttu-id="38f1d-108">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="38f1d-108">\<filterTable></span></span>  
<span data-ttu-id="38f1d-109">\<entries></span><span class="sxs-lookup"><span data-stu-id="38f1d-109">\<entries></span></span>  
<span data-ttu-id="38f1d-110">\<add></span><span class="sxs-lookup"><span data-stu-id="38f1d-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f1d-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="38f1d-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38f1d-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="38f1d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="38f1d-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38f1d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38f1d-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="38f1d-114">Attributes</span></span>  
  
|<span data-ttu-id="38f1d-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="38f1d-115">Attribute</span></span>|<span data-ttu-id="38f1d-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38f1d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38f1d-117">backupList</span><span class="sxs-lookup"><span data-stu-id="38f1d-117">backupList</span></span>|<span data-ttu-id="38f1d-118">Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.</span><span class="sxs-lookup"><span data-stu-id="38f1d-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="38f1d-119">Endpunkt (endpoint)</span><span class="sxs-lookup"><span data-stu-id="38f1d-119">endpoint</span></span>|<span data-ttu-id="38f1d-120">Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="38f1d-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="38f1d-121">filterName</span><span class="sxs-lookup"><span data-stu-id="38f1d-121">filterName</span></span>|<span data-ttu-id="38f1d-122">Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.</span><span class="sxs-lookup"><span data-stu-id="38f1d-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="38f1d-123">priority</span><span class="sxs-lookup"><span data-stu-id="38f1d-123">priority</span></span>|<span data-ttu-id="38f1d-124">Eine ganze Zahl, die die Priorität dieses Eintrags angibt.</span><span class="sxs-lookup"><span data-stu-id="38f1d-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="38f1d-125">Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht.</span><span class="sxs-lookup"><span data-stu-id="38f1d-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="38f1d-126">Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="38f1d-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="38f1d-127">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="38f1d-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38f1d-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38f1d-128">Child Elements</span></span>  
 <span data-ttu-id="38f1d-129">Keine</span><span class="sxs-lookup"><span data-stu-id="38f1d-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38f1d-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38f1d-130">Parent Elements</span></span>  
  
|<span data-ttu-id="38f1d-131">Element</span><span class="sxs-lookup"><span data-stu-id="38f1d-131">Element</span></span>|<span data-ttu-id="38f1d-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38f1d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38f1d-133">\<routing></span><span class="sxs-lookup"><span data-stu-id="38f1d-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="38f1d-134">Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="38f1d-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38f1d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38f1d-135">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
