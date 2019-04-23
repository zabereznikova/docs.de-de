---
title: <add> von <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187083"
---
# <a name="add-of-scopes"></a><span data-ttu-id="53f03-102">\<Hinzufügen > der \<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="53f03-102">\<add> of \<scopes></span></span>
<span data-ttu-id="53f03-103">Fügt einen benutzerdefinierten Bereichs-URI hinzu, der verwendet werden kann, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="53f03-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="53f03-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="53f03-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="53f03-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="53f03-105">\<behaviors></span></span>  
<span data-ttu-id="53f03-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="53f03-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="53f03-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="53f03-107">\<behavior></span></span>  
<span data-ttu-id="53f03-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="53f03-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="53f03-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="53f03-109">\<scopes></span></span>  
<span data-ttu-id="53f03-110">\<add></span><span class="sxs-lookup"><span data-stu-id="53f03-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f03-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="53f03-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53f03-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53f03-112">Attributes and Elements</span></span>  
 <span data-ttu-id="53f03-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53f03-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53f03-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="53f03-114">Attributes</span></span>  
  
|<span data-ttu-id="53f03-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="53f03-115">Attribute</span></span>|<span data-ttu-id="53f03-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53f03-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53f03-117">Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="53f03-117">scope</span></span>|<span data-ttu-id="53f03-118">Ein URI, der Bereichsinformationen für den Endpunkt enthält, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="53f03-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53f03-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53f03-119">Child Elements</span></span>  
 <span data-ttu-id="53f03-120">Keine</span><span class="sxs-lookup"><span data-stu-id="53f03-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53f03-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53f03-121">Parent Elements</span></span>  
  
|<span data-ttu-id="53f03-122">Element</span><span class="sxs-lookup"><span data-stu-id="53f03-122">Element</span></span>|<span data-ttu-id="53f03-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53f03-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53f03-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="53f03-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="53f03-125">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="53f03-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53f03-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53f03-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
