---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75e06b0258f2e4f65d441c25b5081cf7a6627518
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="94788-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="94788-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="94788-103">Stellt einen Konfigurationsabschnitt zum Definieren von Routingtabellen dar, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthalten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="94788-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="94788-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="94788-104">\<system.serviceModel></span></span>  
<span data-ttu-id="94788-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="94788-105">\<routing></span></span>  
<span data-ttu-id="94788-106">\<RoutingTables ></span><span class="sxs-lookup"><span data-stu-id="94788-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94788-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="94788-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="94788-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="94788-108">Attributes and Elements</span></span>  
 <span data-ttu-id="94788-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="94788-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94788-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="94788-110">Attributes</span></span>  
 <span data-ttu-id="94788-111">Keine.</span><span class="sxs-lookup"><span data-stu-id="94788-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="94788-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94788-112">Child Elements</span></span>  
  
|<span data-ttu-id="94788-113">Element</span><span class="sxs-lookup"><span data-stu-id="94788-113">Element</span></span>|<span data-ttu-id="94788-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94788-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94788-115">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="94788-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="94788-116">Eine Routingtabelle, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="94788-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94788-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="94788-117">Parent Elements</span></span>  
  
|<span data-ttu-id="94788-118">Element</span><span class="sxs-lookup"><span data-stu-id="94788-118">Element</span></span>|<span data-ttu-id="94788-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94788-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94788-120">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="94788-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="94788-121">Ein Konfigurationsabschnitt, der Routingfilter und Routingtabellen enthält.</span><span class="sxs-lookup"><span data-stu-id="94788-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94788-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94788-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
