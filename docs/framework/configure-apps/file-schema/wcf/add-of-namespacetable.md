---
title: '&lt;add&gt; von &lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: ef4f1c46a0ee3b94e5548b752e4e0a6a759fd45b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149513"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="62f0f-102">&lt;add&gt; von &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="62f0f-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="62f0f-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="62f0f-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="62f0f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62f0f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="62f0f-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="62f0f-105">\<routing></span></span>  
<span data-ttu-id="62f0f-106">\<NamespaceTable ></span><span class="sxs-lookup"><span data-stu-id="62f0f-106">\<namespaceTable></span></span>  
<span data-ttu-id="62f0f-107">\<add></span><span class="sxs-lookup"><span data-stu-id="62f0f-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f0f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="62f0f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62f0f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62f0f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="62f0f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62f0f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62f0f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="62f0f-111">Attributes</span></span>  
  
|<span data-ttu-id="62f0f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="62f0f-112">Attribute</span></span>|<span data-ttu-id="62f0f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62f0f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62f0f-114">namespace</span><span class="sxs-lookup"><span data-stu-id="62f0f-114">namespace</span></span>|<span data-ttu-id="62f0f-115">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="62f0f-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="62f0f-116">prefix</span><span class="sxs-lookup"><span data-stu-id="62f0f-116">prefix</span></span>|<span data-ttu-id="62f0f-117">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="62f0f-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62f0f-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62f0f-118">Child Elements</span></span>  
 <span data-ttu-id="62f0f-119">Keine</span><span class="sxs-lookup"><span data-stu-id="62f0f-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62f0f-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62f0f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="62f0f-121">Element</span><span class="sxs-lookup"><span data-stu-id="62f0f-121">Element</span></span>|<span data-ttu-id="62f0f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62f0f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62f0f-123">\<NamespaceTable ></span><span class="sxs-lookup"><span data-stu-id="62f0f-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="62f0f-124">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="62f0f-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62f0f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62f0f-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
