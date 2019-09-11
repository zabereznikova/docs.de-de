---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855194"
---
# <a name="filtertable"></a><span data-ttu-id="04860-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="04860-101">\<filterTable></span></span>
<span data-ttu-id="04860-102">Stellt eine Routing Tabelle dar, die eine Liste von Filtern zum Auswerten von Nachrichten sowie den Client Endpunkt enthält, an den Nachrichten weitergeleitet werden sollen, wenn der Filter zu true ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="04860-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="04860-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="04860-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="04860-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="04860-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="04860-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="04860-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="04860-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Filter Tables->** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="04860-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="04860-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filtertable->**</span><span class="sxs-lookup"><span data-stu-id="04860-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04860-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="04860-108">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04860-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="04860-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04860-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="04860-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04860-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="04860-111">Attributes</span></span>  
  
|<span data-ttu-id="04860-112">Element</span><span class="sxs-lookup"><span data-stu-id="04860-112">Element</span></span>|<span data-ttu-id="04860-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04860-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04860-114">NAME</span><span class="sxs-lookup"><span data-stu-id="04860-114">name</span></span>|<span data-ttu-id="04860-115">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="04860-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04860-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04860-116">Child Elements</span></span>  
  
|<span data-ttu-id="04860-117">Element</span><span class="sxs-lookup"><span data-stu-id="04860-117">Element</span></span>|<span data-ttu-id="04860-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04860-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04860-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="04860-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="04860-120">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="04860-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04860-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="04860-121">Parent Elements</span></span>  
  
|<span data-ttu-id="04860-122">Element</span><span class="sxs-lookup"><span data-stu-id="04860-122">Element</span></span>|<span data-ttu-id="04860-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04860-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04860-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="04860-124">\<routing></span></span>](routing.md)|<span data-ttu-id="04860-125">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="04860-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04860-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04860-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
