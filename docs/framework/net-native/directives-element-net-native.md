---
title: <Directives>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: abe2e7221e0afb984a6178b12fabc36ea24deb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128470"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="cc963-102">\<-Direktiven > Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="cc963-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="cc963-103">Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.</span><span class="sxs-lookup"><span data-stu-id="cc963-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="cc963-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc963-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="cc963-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc963-105">Attributes</span></span>  
  
|<span data-ttu-id="cc963-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="cc963-106">Attribute</span></span>|<span data-ttu-id="cc963-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc963-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="cc963-108">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="cc963-108">The XML namespace.</span></span> <span data-ttu-id="cc963-109">Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .</span><span class="sxs-lookup"><span data-stu-id="cc963-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="cc963-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc963-110">Child elements</span></span>  
  
|<span data-ttu-id="cc963-111">Element</span><span class="sxs-lookup"><span data-stu-id="cc963-111">Element</span></span>|<span data-ttu-id="cc963-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc963-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc963-113">\<Anwendung></span><span class="sxs-lookup"><span data-stu-id="cc963-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="cc963-114">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cc963-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="cc963-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="cc963-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="cc963-116">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="cc963-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc963-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc963-117">Remarks</span></span>  
 <span data-ttu-id="cc963-118">Jede Laufzeitanweisungsdatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="cc963-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="cc963-119">Das `<Directives>`-Element kann null oder ein [\<Application>](application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](library-element-net-native.md)-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="cc963-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc963-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc963-120">See also</span></span>

- [<span data-ttu-id="cc963-121">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="cc963-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="cc963-122">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="cc963-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
