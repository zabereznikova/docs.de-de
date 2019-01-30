---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: a54386de369a11a1958e4d81ab01f053a0bc5b36
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55253976"
---
# <a name="filtertables"></a><span data-ttu-id="9dabb-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="9dabb-101">\<filterTables></span></span>
<span data-ttu-id="9dabb-102">Stellt einen Konfigurationsabschnitt zum Definieren von Routingtabellen dar, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthalten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9dabb-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="9dabb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9dabb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9dabb-104">\<routing></span><span class="sxs-lookup"><span data-stu-id="9dabb-104">\<routing></span></span>  
<span data-ttu-id="9dabb-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="9dabb-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dabb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dabb-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9dabb-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9dabb-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9dabb-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9dabb-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9dabb-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9dabb-109">Attributes</span></span>  
 <span data-ttu-id="9dabb-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9dabb-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9dabb-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9dabb-111">Child Elements</span></span>  
  
|<span data-ttu-id="9dabb-112">Element</span><span class="sxs-lookup"><span data-stu-id="9dabb-112">Element</span></span>|<span data-ttu-id="9dabb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dabb-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9dabb-114">\<filters></span><span class="sxs-lookup"><span data-stu-id="9dabb-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="9dabb-115">Eine Routingtabelle, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9dabb-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9dabb-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9dabb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9dabb-117">Element</span><span class="sxs-lookup"><span data-stu-id="9dabb-117">Element</span></span>|<span data-ttu-id="9dabb-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dabb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9dabb-119">\<routing></span><span class="sxs-lookup"><span data-stu-id="9dabb-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="9dabb-120">Ein Konfigurationsabschnitt, der Routingfilter und Routingtabellen enthält.</span><span class="sxs-lookup"><span data-stu-id="9dabb-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9dabb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dabb-121">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
