---
title: <add> von <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850395"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="9eb01-102">\<Fügen Sie > \<von namespacetable hinzu ></span><span class="sxs-lookup"><span data-stu-id="9eb01-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="9eb01-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9eb01-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="9eb01-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9eb01-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9eb01-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9eb01-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9eb01-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="9eb01-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="9eb01-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namespacetable->** ](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="9eb01-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="9eb01-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="9eb01-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb01-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9eb01-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9eb01-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9eb01-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9eb01-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9eb01-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9eb01-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9eb01-112">Attributes</span></span>  
  
|<span data-ttu-id="9eb01-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9eb01-113">Attribute</span></span>|<span data-ttu-id="9eb01-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9eb01-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9eb01-115">namespace</span><span class="sxs-lookup"><span data-stu-id="9eb01-115">namespace</span></span>|<span data-ttu-id="9eb01-116">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="9eb01-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="9eb01-117">prefix</span><span class="sxs-lookup"><span data-stu-id="9eb01-117">prefix</span></span>|<span data-ttu-id="9eb01-118">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="9eb01-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9eb01-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9eb01-119">Child Elements</span></span>  
 <span data-ttu-id="9eb01-120">Keine</span><span class="sxs-lookup"><span data-stu-id="9eb01-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9eb01-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9eb01-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9eb01-122">Element</span><span class="sxs-lookup"><span data-stu-id="9eb01-122">Element</span></span>|<span data-ttu-id="9eb01-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9eb01-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9eb01-124">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="9eb01-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="9eb01-125">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9eb01-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9eb01-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eb01-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
