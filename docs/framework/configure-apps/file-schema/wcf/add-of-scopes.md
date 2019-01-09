---
title: '&lt;add&gt; von &lt;scopes&gt;'
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: e2bf649259d6ccb0e55428ab3619fe561d051ff7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146235"
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="8ebb6-102">&lt;add&gt; von &lt;scopes&gt;</span><span class="sxs-lookup"><span data-stu-id="8ebb6-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="8ebb6-103">Fügt einen benutzerdefinierten Bereichs-URI hinzu, der verwendet werden kann, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="8ebb6-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="8ebb6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8ebb6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8ebb6-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8ebb6-105">\<behaviors></span></span>  
<span data-ttu-id="8ebb6-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8ebb6-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8ebb6-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8ebb6-107">\<behavior></span></span>  
<span data-ttu-id="8ebb6-108">\<EndpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="8ebb6-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="8ebb6-109">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="8ebb6-109">\<scopes></span></span>  
<span data-ttu-id="8ebb6-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8ebb6-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebb6-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ebb6-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ebb6-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8ebb6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8ebb6-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ebb6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ebb6-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="8ebb6-114">Attributes</span></span>  
  
|<span data-ttu-id="8ebb6-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="8ebb6-115">Attribute</span></span>|<span data-ttu-id="8ebb6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ebb6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ebb6-117">Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="8ebb6-117">scope</span></span>|<span data-ttu-id="8ebb6-118">Ein URI, der Bereichsinformationen für den Endpunkt enthält, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8ebb6-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ebb6-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ebb6-119">Child Elements</span></span>  
 <span data-ttu-id="8ebb6-120">Keine</span><span class="sxs-lookup"><span data-stu-id="8ebb6-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ebb6-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8ebb6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8ebb6-122">Element</span><span class="sxs-lookup"><span data-stu-id="8ebb6-122">Element</span></span>|<span data-ttu-id="8ebb6-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ebb6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ebb6-124">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="8ebb6-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="8ebb6-125">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="8ebb6-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ebb6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ebb6-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
