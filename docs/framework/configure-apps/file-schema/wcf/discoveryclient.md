---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: f9d7e3a4957d2a8f30724f0bfc04e58a57fc5f7d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919270"
---
# <a name="discoveryclient"></a><span data-ttu-id="4b652-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="4b652-101">\<discoveryClient></span></span>
<span data-ttu-id="4b652-102">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="4b652-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="4b652-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4b652-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4b652-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4b652-104">\<bindings></span></span>  
<span data-ttu-id="4b652-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4b652-105">\<customBinding></span></span>  
<span data-ttu-id="4b652-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b652-106">\<binding></span></span>  
<span data-ttu-id="4b652-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="4b652-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b652-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b652-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b652-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b652-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4b652-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b652-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b652-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b652-111">Attributes</span></span>  
  
|<span data-ttu-id="4b652-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4b652-112">Attribute</span></span>|<span data-ttu-id="4b652-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b652-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b652-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="4b652-114">discoveryEndpoint</span></span>|<span data-ttu-id="4b652-115">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b652-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b652-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b652-116">Child Elements</span></span>  
  
|<span data-ttu-id="4b652-117">Element</span><span class="sxs-lookup"><span data-stu-id="4b652-117">Element</span></span>|<span data-ttu-id="4b652-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b652-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b652-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="4b652-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="4b652-120">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b652-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="4b652-121">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="4b652-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b652-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b652-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4b652-123">Element</span><span class="sxs-lookup"><span data-stu-id="4b652-123">Element</span></span>|<span data-ttu-id="4b652-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b652-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b652-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b652-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4b652-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="4b652-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b652-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b652-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
