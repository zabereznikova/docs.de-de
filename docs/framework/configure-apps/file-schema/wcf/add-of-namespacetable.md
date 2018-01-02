---
title: '&lt;add&gt; von &lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 394657abcebb42192fb7a8b57b0402bcacf37693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="4df2e-102">&lt;add&gt; von &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="4df2e-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="4df2e-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4df2e-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="4df2e-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4df2e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4df2e-105">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="4df2e-105">\<routing></span></span>  
<span data-ttu-id="4df2e-106">\<NamespaceTable ></span><span class="sxs-lookup"><span data-stu-id="4df2e-106">\<namespaceTable></span></span>  
<span data-ttu-id="4df2e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="4df2e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4df2e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="4df2e-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4df2e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4df2e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4df2e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4df2e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4df2e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="4df2e-111">Attributes</span></span>  
  
|<span data-ttu-id="4df2e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="4df2e-112">Attribute</span></span>|<span data-ttu-id="4df2e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4df2e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4df2e-114">namespace</span><span class="sxs-lookup"><span data-stu-id="4df2e-114">namespace</span></span>|<span data-ttu-id="4df2e-115">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="4df2e-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="4df2e-116">prefix</span><span class="sxs-lookup"><span data-stu-id="4df2e-116">prefix</span></span>|<span data-ttu-id="4df2e-117">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="4df2e-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4df2e-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4df2e-118">Child Elements</span></span>  
 <span data-ttu-id="4df2e-119">Keine</span><span class="sxs-lookup"><span data-stu-id="4df2e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4df2e-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4df2e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4df2e-121">Element</span><span class="sxs-lookup"><span data-stu-id="4df2e-121">Element</span></span>|<span data-ttu-id="4df2e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4df2e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4df2e-123">\<NamespaceTable ></span><span class="sxs-lookup"><span data-stu-id="4df2e-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="4df2e-124">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4df2e-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4df2e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4df2e-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
