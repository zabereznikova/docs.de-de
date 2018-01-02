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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c9cbdb61152a5315aaf919e3a3c58d9329449e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="f31b7-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="f31b7-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="f31b7-103">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="f31b7-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="f31b7-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f31b7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f31b7-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="f31b7-105">\<bindings></span></span>  
<span data-ttu-id="f31b7-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="f31b7-106">\<customBinding></span></span>  
<span data-ttu-id="f31b7-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="f31b7-107">\<binding></span></span>  
<span data-ttu-id="f31b7-108">\<DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="f31b7-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f31b7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f31b7-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f31b7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f31b7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f31b7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f31b7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f31b7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f31b7-112">Attributes</span></span>  
  
|<span data-ttu-id="f31b7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f31b7-113">Attribute</span></span>|<span data-ttu-id="f31b7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f31b7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f31b7-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="f31b7-115">discoveryEndpoint</span></span>|<span data-ttu-id="f31b7-116">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f31b7-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f31b7-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f31b7-117">Child Elements</span></span>  
  
|<span data-ttu-id="f31b7-118">Element</span><span class="sxs-lookup"><span data-stu-id="f31b7-118">Element</span></span>|<span data-ttu-id="f31b7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f31b7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f31b7-120">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="f31b7-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="f31b7-121">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f31b7-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="f31b7-122">Kriterien können in Suchkriterien (was Sie suchen Dienste) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="f31b7-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f31b7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f31b7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f31b7-124">Element</span><span class="sxs-lookup"><span data-stu-id="f31b7-124">Element</span></span>|<span data-ttu-id="f31b7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f31b7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f31b7-126">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="f31b7-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f31b7-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="f31b7-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f31b7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f31b7-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
