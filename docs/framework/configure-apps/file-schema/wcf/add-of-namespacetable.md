---
title: <add> von <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e65b66170465a8b3bb60754feebb7730b959d9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089717"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="fe61c-102">\<Hinzufügen > der \<NamespaceTable ></span><span class="sxs-lookup"><span data-stu-id="fe61c-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="fe61c-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe61c-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="fe61c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fe61c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fe61c-105">\<routing></span><span class="sxs-lookup"><span data-stu-id="fe61c-105">\<routing></span></span>  
<span data-ttu-id="fe61c-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="fe61c-106">\<namespaceTable></span></span>  
<span data-ttu-id="fe61c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fe61c-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe61c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe61c-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe61c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe61c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fe61c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe61c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe61c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe61c-111">Attributes</span></span>  
  
|<span data-ttu-id="fe61c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="fe61c-112">Attribute</span></span>|<span data-ttu-id="fe61c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe61c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe61c-114">namespace</span><span class="sxs-lookup"><span data-stu-id="fe61c-114">namespace</span></span>|<span data-ttu-id="fe61c-115">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="fe61c-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="fe61c-116">prefix</span><span class="sxs-lookup"><span data-stu-id="fe61c-116">prefix</span></span>|<span data-ttu-id="fe61c-117">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="fe61c-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe61c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe61c-118">Child Elements</span></span>  
 <span data-ttu-id="fe61c-119">Keine</span><span class="sxs-lookup"><span data-stu-id="fe61c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe61c-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe61c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fe61c-121">Element</span><span class="sxs-lookup"><span data-stu-id="fe61c-121">Element</span></span>|<span data-ttu-id="fe61c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe61c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe61c-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="fe61c-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="fe61c-124">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fe61c-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe61c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe61c-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
