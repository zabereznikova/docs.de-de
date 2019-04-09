---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: a5ea10601732021af578c17d4f5c5ab69c98f17a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128426"
---
# <a name="discoveryclient"></a><span data-ttu-id="ba17c-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="ba17c-101">\<discoveryClient></span></span>
<span data-ttu-id="ba17c-102">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="ba17c-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="ba17c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ba17c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ba17c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ba17c-104">\<bindings></span></span>  
<span data-ttu-id="ba17c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ba17c-105">\<customBinding></span></span>  
<span data-ttu-id="ba17c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba17c-106">\<binding></span></span>  
<span data-ttu-id="ba17c-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="ba17c-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba17c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba17c-108">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba17c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba17c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba17c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba17c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba17c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba17c-111">Attributes</span></span>  
  
|<span data-ttu-id="ba17c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba17c-112">Attribute</span></span>|<span data-ttu-id="ba17c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba17c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba17c-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="ba17c-114">discoveryEndpoint</span></span>|<span data-ttu-id="ba17c-115">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ba17c-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba17c-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba17c-116">Child Elements</span></span>  
  
|<span data-ttu-id="ba17c-117">Element</span><span class="sxs-lookup"><span data-stu-id="ba17c-117">Element</span></span>|<span data-ttu-id="ba17c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba17c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba17c-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ba17c-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="ba17c-120">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba17c-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="ba17c-121">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden, für die) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="ba17c-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba17c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba17c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ba17c-123">Element</span><span class="sxs-lookup"><span data-stu-id="ba17c-123">Element</span></span>|<span data-ttu-id="ba17c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba17c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba17c-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="ba17c-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ba17c-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ba17c-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba17c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba17c-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
