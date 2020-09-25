---
title: <add> von <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7d055d4933f1ad625d6842f91a140f668c05c64e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204995"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="ca756-102">\<add> von \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="ca756-102">\<add> of \<namespaceTable></span></span>

<span data-ttu-id="ca756-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca756-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ca756-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca756-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca756-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ca756-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ca756-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca756-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca756-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="ca756-107">Attributes</span></span>  
  
|<span data-ttu-id="ca756-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ca756-108">Attribute</span></span>|<span data-ttu-id="ca756-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ca756-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca756-110">Namespace</span><span class="sxs-lookup"><span data-stu-id="ca756-110">namespace</span></span>|<span data-ttu-id="ca756-111">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="ca756-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="ca756-112">prefix</span><span class="sxs-lookup"><span data-stu-id="ca756-112">prefix</span></span>|<span data-ttu-id="ca756-113">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="ca756-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca756-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca756-114">Child Elements</span></span>  

 <span data-ttu-id="ca756-115">Keine</span><span class="sxs-lookup"><span data-stu-id="ca756-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca756-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ca756-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ca756-117">Element</span><span class="sxs-lookup"><span data-stu-id="ca756-117">Element</span></span>|<span data-ttu-id="ca756-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca756-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="ca756-119">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ca756-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca756-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca756-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
