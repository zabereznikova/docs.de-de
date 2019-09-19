---
title: <Directives>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ec9a09e2fc03adbfcff0d7e69489e37da6e4a5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049884"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="238bb-102">\<Direktiven > Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="238bb-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="238bb-103">Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.</span><span class="sxs-lookup"><span data-stu-id="238bb-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="238bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="238bb-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="238bb-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="238bb-105">Attributes</span></span>  
  
|<span data-ttu-id="238bb-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="238bb-106">Attribute</span></span>|<span data-ttu-id="238bb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="238bb-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="238bb-108">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="238bb-108">The XML namespace.</span></span> <span data-ttu-id="238bb-109">Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .</span><span class="sxs-lookup"><span data-stu-id="238bb-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="238bb-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="238bb-110">Child elements</span></span>  
  
|<span data-ttu-id="238bb-111">Element</span><span class="sxs-lookup"><span data-stu-id="238bb-111">Element</span></span>|<span data-ttu-id="238bb-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="238bb-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="238bb-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="238bb-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="238bb-114">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="238bb-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="238bb-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="238bb-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="238bb-116">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="238bb-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="238bb-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="238bb-117">Remarks</span></span>  
 <span data-ttu-id="238bb-118">Jede Laufzeitanweisungsdatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="238bb-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="238bb-119">Das `<Directives>`-Element kann null oder ein [\<Application>](application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](library-element-net-native.md)-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="238bb-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238bb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="238bb-120">See also</span></span>

- [<span data-ttu-id="238bb-121">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="238bb-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="238bb-122">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="238bb-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
