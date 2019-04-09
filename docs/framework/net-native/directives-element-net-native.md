---
title: <Directives> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cfc9dc5c8122f9b1b1696cedcd5d9a8ceead403
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100222"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="24301-102">\<Directives > (Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="24301-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="24301-103">Das Stammelement in jeder laufzeitanweisungsdatei für .NET Native.</span><span class="sxs-lookup"><span data-stu-id="24301-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="24301-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24301-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="24301-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="24301-105">Attributes</span></span>  
  
|<span data-ttu-id="24301-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="24301-106">Attribute</span></span>|<span data-ttu-id="24301-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24301-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="24301-108">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="24301-108">The XML namespace.</span></span> <span data-ttu-id="24301-109">Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="24301-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="24301-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24301-110">Child elements</span></span>  
  
|<span data-ttu-id="24301-111">Element</span><span class="sxs-lookup"><span data-stu-id="24301-111">Element</span></span>|<span data-ttu-id="24301-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24301-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24301-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="24301-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="24301-114">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="24301-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="24301-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="24301-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="24301-116">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="24301-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24301-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24301-117">Remarks</span></span>  
 <span data-ttu-id="24301-118">Jede Laufzeitanweisungsdatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="24301-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="24301-119">Das `<Directives>`-Element kann null oder ein [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="24301-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24301-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24301-120">See also</span></span>

- [<span data-ttu-id="24301-121">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="24301-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="24301-122">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="24301-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
