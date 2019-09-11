---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855278"
---
# <a name="entries"></a><span data-ttu-id="1abf8-101">\<Einträge ></span><span class="sxs-lookup"><span data-stu-id="1abf8-101">\<entries></span></span>
<span data-ttu-id="1abf8-102">Ein Routingeintrag, der Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1abf8-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="1abf8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1abf8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1abf8-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1abf8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1abf8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="1abf8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="1abf8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Filter Tables->** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="1abf8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="1abf8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filtertable->** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="1abf8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="1abf8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Einträge >**</span><span class="sxs-lookup"><span data-stu-id="1abf8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1abf8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1abf8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1abf8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1abf8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1abf8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1abf8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1abf8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="1abf8-112">Attributes</span></span>  
 <span data-ttu-id="1abf8-113">Keine</span><span class="sxs-lookup"><span data-stu-id="1abf8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1abf8-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1abf8-114">Child Elements</span></span>  
  
|<span data-ttu-id="1abf8-115">Element</span><span class="sxs-lookup"><span data-stu-id="1abf8-115">Element</span></span>|<span data-ttu-id="1abf8-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1abf8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1abf8-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="1abf8-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="1abf8-118">Ordnet einem Clientendpunkt, der zuvor definiert wurde, einen Filter zu.</span><span class="sxs-lookup"><span data-stu-id="1abf8-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="1abf8-119">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="1abf8-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1abf8-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1abf8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1abf8-121">Element</span><span class="sxs-lookup"><span data-stu-id="1abf8-121">Element</span></span>|<span data-ttu-id="1abf8-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1abf8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1abf8-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="1abf8-123">\<routing></span></span>](routing.md)|<span data-ttu-id="1abf8-124">Ein Konfigurationsabschnitt, der eine Routingtabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="1abf8-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1abf8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1abf8-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
