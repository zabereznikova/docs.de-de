---
title: <add> von <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850511"
---
# <a name="add-of-entries"></a><span data-ttu-id="0a75c-102">\<Fügen Sie > \<von Einträgen hinzu ></span><span class="sxs-lookup"><span data-stu-id="0a75c-102">\<add> of \<entries></span></span>
<span data-ttu-id="0a75c-103">Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="0a75c-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="0a75c-104">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="0a75c-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="0a75c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a75c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a75c-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0a75c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0a75c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="0a75c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="0a75c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Filter Tables->** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="0a75c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="0a75c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filtertable->** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="0a75c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="0a75c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Einträge >** ](entries.md)</span><span class="sxs-lookup"><span data-stu-id="0a75c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="0a75c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="0a75c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a75c-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a75c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a75c-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a75c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0a75c-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a75c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a75c-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a75c-115">Attributes</span></span>  
  
|<span data-ttu-id="0a75c-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="0a75c-116">Attribute</span></span>|<span data-ttu-id="0a75c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a75c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a75c-118">backupList</span><span class="sxs-lookup"><span data-stu-id="0a75c-118">backupList</span></span>|<span data-ttu-id="0a75c-119">Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.</span><span class="sxs-lookup"><span data-stu-id="0a75c-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="0a75c-120">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0a75c-120">endpoint</span></span>|<span data-ttu-id="0a75c-121">Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0a75c-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="0a75c-122">filterName</span><span class="sxs-lookup"><span data-stu-id="0a75c-122">filterName</span></span>|<span data-ttu-id="0a75c-123">Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.</span><span class="sxs-lookup"><span data-stu-id="0a75c-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="0a75c-124">priority</span><span class="sxs-lookup"><span data-stu-id="0a75c-124">priority</span></span>|<span data-ttu-id="0a75c-125">Eine ganze Zahl, die die Priorität dieses Eintrags angibt.</span><span class="sxs-lookup"><span data-stu-id="0a75c-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="0a75c-126">Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht.</span><span class="sxs-lookup"><span data-stu-id="0a75c-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="0a75c-127">Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0a75c-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="0a75c-128">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="0a75c-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a75c-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a75c-129">Child Elements</span></span>  
 <span data-ttu-id="0a75c-130">Keine</span><span class="sxs-lookup"><span data-stu-id="0a75c-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a75c-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a75c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0a75c-132">Element</span><span class="sxs-lookup"><span data-stu-id="0a75c-132">Element</span></span>|<span data-ttu-id="0a75c-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a75c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a75c-134">\<routing></span><span class="sxs-lookup"><span data-stu-id="0a75c-134">\<routing></span></span>](routing.md)|<span data-ttu-id="0a75c-135">Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="0a75c-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a75c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a75c-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
