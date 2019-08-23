---
title: <add> von <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e2a2e26099f2d31116e4a89297fc1ac984c480d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920081"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="1a567-102">\<Fügen Sie > \<von namespacetable hinzu ></span><span class="sxs-lookup"><span data-stu-id="1a567-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="1a567-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1a567-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="1a567-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1a567-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1a567-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="1a567-105">\<routing></span></span>  
<span data-ttu-id="1a567-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="1a567-106">\<namespaceTable></span></span>  
<span data-ttu-id="1a567-107">\<add></span><span class="sxs-lookup"><span data-stu-id="1a567-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a567-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a567-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a567-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1a567-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1a567-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a567-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a567-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="1a567-111">Attributes</span></span>  
  
|<span data-ttu-id="1a567-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="1a567-112">Attribute</span></span>|<span data-ttu-id="1a567-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a567-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a567-114">namespace</span><span class="sxs-lookup"><span data-stu-id="1a567-114">namespace</span></span>|<span data-ttu-id="1a567-115">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="1a567-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="1a567-116">prefix</span><span class="sxs-lookup"><span data-stu-id="1a567-116">prefix</span></span>|<span data-ttu-id="1a567-117">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="1a567-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a567-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a567-118">Child Elements</span></span>  
 <span data-ttu-id="1a567-119">Keine</span><span class="sxs-lookup"><span data-stu-id="1a567-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a567-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a567-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1a567-121">Element</span><span class="sxs-lookup"><span data-stu-id="1a567-121">Element</span></span>|<span data-ttu-id="1a567-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a567-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a567-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="1a567-123">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="1a567-124">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1a567-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a567-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a567-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
