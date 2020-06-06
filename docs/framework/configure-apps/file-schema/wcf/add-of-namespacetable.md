---
title: <add> von <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850395"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="cd087-102">\<add> von \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="cd087-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="cd087-103">Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd087-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="cd087-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd087-104">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd087-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd087-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cd087-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd087-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd087-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd087-107">Attributes</span></span>  
  
|<span data-ttu-id="cd087-108">attribute</span><span class="sxs-lookup"><span data-stu-id="cd087-108">Attribute</span></span>|<span data-ttu-id="cd087-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd087-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd087-110">Namespace</span><span class="sxs-lookup"><span data-stu-id="cd087-110">namespace</span></span>|<span data-ttu-id="cd087-111">Eine Zeichenfolge, die den Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="cd087-111">A string containing the namespace.</span></span>|  
|<span data-ttu-id="cd087-112">prefix</span><span class="sxs-lookup"><span data-stu-id="cd087-112">prefix</span></span>|<span data-ttu-id="cd087-113">Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="cd087-113">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd087-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd087-114">Child Elements</span></span>  
 <span data-ttu-id="cd087-115">Keine</span><span class="sxs-lookup"><span data-stu-id="cd087-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd087-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd087-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cd087-117">Element</span><span class="sxs-lookup"><span data-stu-id="cd087-117">Element</span></span>|<span data-ttu-id="cd087-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd087-118">Description</span></span>|  
|-------------|-----------------|  
|[\<namespaceTable>](namespacetable.md)|<span data-ttu-id="cd087-119">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="cd087-119">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd087-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd087-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
