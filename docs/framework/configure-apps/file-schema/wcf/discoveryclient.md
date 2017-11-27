---
title: '&lt;discoveryClient&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0b7161c9e4564367348d1c94d469d6fa4a4b79b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="fc0ee-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="fc0ee-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="fc0ee-103">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="fc0ee-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="fc0ee-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fc0ee-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-105">\<bindings></span></span>  
<span data-ttu-id="fc0ee-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-106">\<customBinding></span></span>  
<span data-ttu-id="fc0ee-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-107">\<binding></span></span>  
<span data-ttu-id="fc0ee-108">\<DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc0ee-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc0ee-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String" >
  <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String" namespace="String" />
    <contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc0ee-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc0ee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fc0ee-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc0ee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc0ee-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc0ee-112">Attributes</span></span>  
  
|<span data-ttu-id="fc0ee-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fc0ee-113">Attribute</span></span>|<span data-ttu-id="fc0ee-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc0ee-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc0ee-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="fc0ee-115">discoveryEndpoint</span></span>|<span data-ttu-id="fc0ee-116">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fc0ee-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc0ee-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc0ee-117">Child Elements</span></span>  
  
|<span data-ttu-id="fc0ee-118">Element</span><span class="sxs-lookup"><span data-stu-id="fc0ee-118">Element</span></span>|<span data-ttu-id="fc0ee-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc0ee-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc0ee-120">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fc0ee-121">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fc0ee-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fc0ee-122">Kriterien können in Suchkriterien (was Sie suchen Dienste) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="fc0ee-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc0ee-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc0ee-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fc0ee-124">Element</span><span class="sxs-lookup"><span data-stu-id="fc0ee-124">Element</span></span>|<span data-ttu-id="fc0ee-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc0ee-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc0ee-126">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="fc0ee-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="fc0ee-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="fc0ee-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc0ee-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc0ee-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
