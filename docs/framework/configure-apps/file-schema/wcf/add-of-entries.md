---
title: <add> von <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850511"
---
# <a name="add-of-entries"></a><span data-ttu-id="b8ae4-102">\<add> von \<entries></span><span class="sxs-lookup"><span data-stu-id="b8ae4-102">\<add> of \<entries></span></span>
<span data-ttu-id="b8ae4-103">Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="b8ae4-104">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-104">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="b8ae4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8ae4-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8ae4-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b8ae4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b8ae4-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8ae4-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b8ae4-108">Attributes</span></span>  
  
|<span data-ttu-id="b8ae4-109">attribute</span><span class="sxs-lookup"><span data-stu-id="b8ae4-109">Attribute</span></span>|<span data-ttu-id="b8ae4-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b8ae4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8ae4-111">backupList</span><span class="sxs-lookup"><span data-stu-id="b8ae4-111">backupList</span></span>|<span data-ttu-id="b8ae4-112">Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-112">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="b8ae4-113">endpoint</span><span class="sxs-lookup"><span data-stu-id="b8ae4-113">endpoint</span></span>|<span data-ttu-id="b8ae4-114">Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-114">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="b8ae4-115">filterName</span><span class="sxs-lookup"><span data-stu-id="b8ae4-115">filterName</span></span>|<span data-ttu-id="b8ae4-116">Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-116">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="b8ae4-117">priority</span><span class="sxs-lookup"><span data-stu-id="b8ae4-117">priority</span></span>|<span data-ttu-id="b8ae4-118">Eine ganze Zahl, die die Priorität dieses Eintrags angibt.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-118">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="b8ae4-119">Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-119">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="b8ae4-120">Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-120">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="b8ae4-121">Dieser Wert ist optional.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-121">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8ae4-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8ae4-122">Child Elements</span></span>  
 <span data-ttu-id="b8ae4-123">Keine</span><span class="sxs-lookup"><span data-stu-id="b8ae4-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8ae4-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8ae4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b8ae4-125">Element</span><span class="sxs-lookup"><span data-stu-id="b8ae4-125">Element</span></span>|<span data-ttu-id="b8ae4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8ae4-126">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="b8ae4-127">Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.</span><span class="sxs-lookup"><span data-stu-id="b8ae4-127">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b8ae4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8ae4-128">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
