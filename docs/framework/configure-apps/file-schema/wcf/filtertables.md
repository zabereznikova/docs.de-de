---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855196"
---
# <a name="filtertables"></a><span data-ttu-id="4ea2f-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="4ea2f-101">\<filterTables></span></span>
<span data-ttu-id="4ea2f-102">Stellt einen Konfigurationsabschnitt zum Definieren von Routingtabellen dar, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthalten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="4ea2f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ea2f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ea2f-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ea2f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ea2f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="4ea2f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="4ea2f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Filter Tables->**</span><span class="sxs-lookup"><span data-stu-id="4ea2f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea2f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ea2f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ea2f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4ea2f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4ea2f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ea2f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4ea2f-110">Attributes</span></span>  
 <span data-ttu-id="4ea2f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4ea2f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4ea2f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ea2f-112">Child Elements</span></span>  
  
|<span data-ttu-id="4ea2f-113">Element</span><span class="sxs-lookup"><span data-stu-id="4ea2f-113">Element</span></span>|<span data-ttu-id="4ea2f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ea2f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ea2f-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="4ea2f-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="4ea2f-116">Eine Routingtabelle, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ea2f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4ea2f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4ea2f-118">Element</span><span class="sxs-lookup"><span data-stu-id="4ea2f-118">Element</span></span>|<span data-ttu-id="4ea2f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ea2f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ea2f-120">\<routing></span><span class="sxs-lookup"><span data-stu-id="4ea2f-120">\<routing></span></span>](routing.md)|<span data-ttu-id="4ea2f-121">Ein Konfigurationsabschnitt, der Routingfilter und Routingtabellen enthält.</span><span class="sxs-lookup"><span data-stu-id="4ea2f-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ea2f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ea2f-122">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
