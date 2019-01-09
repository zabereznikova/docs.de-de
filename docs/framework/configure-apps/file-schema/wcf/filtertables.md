---
title: '&lt;filterTables&gt;'
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: 2b537619a276f32c50576561aea03b5fbbb58e7d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147784"
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="05d40-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="05d40-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="05d40-103">Stellt einen Konfigurationsabschnitt zum Definieren von Routingtabellen dar, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthalten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="05d40-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="05d40-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="05d40-104">\<system.serviceModel></span></span>  
<span data-ttu-id="05d40-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="05d40-105">\<routing></span></span>  
<span data-ttu-id="05d40-106">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="05d40-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d40-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="05d40-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05d40-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05d40-108">Attributes and Elements</span></span>  
 <span data-ttu-id="05d40-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05d40-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05d40-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="05d40-110">Attributes</span></span>  
 <span data-ttu-id="05d40-111">Keine</span><span class="sxs-lookup"><span data-stu-id="05d40-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05d40-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05d40-112">Child Elements</span></span>  
  
|<span data-ttu-id="05d40-113">Element</span><span class="sxs-lookup"><span data-stu-id="05d40-113">Element</span></span>|<span data-ttu-id="05d40-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05d40-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05d40-115">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="05d40-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="05d40-116">Eine Routingtabelle, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="05d40-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05d40-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05d40-117">Parent Elements</span></span>  
  
|<span data-ttu-id="05d40-118">Element</span><span class="sxs-lookup"><span data-stu-id="05d40-118">Element</span></span>|<span data-ttu-id="05d40-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05d40-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05d40-120">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="05d40-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="05d40-121">Ein Konfigurationsabschnitt, der Routingfilter und Routingtabellen enthält.</span><span class="sxs-lookup"><span data-stu-id="05d40-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05d40-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05d40-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
