---
title: '&lt;add&gt; von &lt;scopes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c720d99a5abee00eeb52f91586503e0a8a89027b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="70e4e-102">&lt;add&gt; von &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="70e4e-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="70e4e-103">Fügt einen benutzerdefinierten Bereichs-URI hinzu, der verwendet werden kann, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="70e4e-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="70e4e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="70e4e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="70e4e-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="70e4e-105">\<behaviors></span></span>  
<span data-ttu-id="70e4e-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="70e4e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="70e4e-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="70e4e-107">\<behavior></span></span>  
<span data-ttu-id="70e4e-108">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="70e4e-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="70e4e-109">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="70e4e-109">\<scopes></span></span>  
<span data-ttu-id="70e4e-110">\<add></span><span class="sxs-lookup"><span data-stu-id="70e4e-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e4e-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="70e4e-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70e4e-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="70e4e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="70e4e-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="70e4e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70e4e-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="70e4e-114">Attributes</span></span>  
  
|<span data-ttu-id="70e4e-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="70e4e-115">Attribute</span></span>|<span data-ttu-id="70e4e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70e4e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70e4e-117">Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="70e4e-117">scope</span></span>|<span data-ttu-id="70e4e-118">Ein URI, der Bereichsinformationen für den Endpunkt enthält, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="70e4e-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70e4e-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70e4e-119">Child Elements</span></span>  
 <span data-ttu-id="70e4e-120">Keine</span><span class="sxs-lookup"><span data-stu-id="70e4e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70e4e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70e4e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="70e4e-122">Element</span><span class="sxs-lookup"><span data-stu-id="70e4e-122">Element</span></span>|<span data-ttu-id="70e4e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70e4e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70e4e-124">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="70e4e-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="70e4e-125">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="70e4e-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70e4e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70e4e-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
