---
title: <Directives>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 0c6ebb8954e80f3f6dc6733f0e9d76094477689b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84202382"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="be1fc-102">\<Directives>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="be1fc-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="be1fc-103">Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.</span><span class="sxs-lookup"><span data-stu-id="be1fc-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="be1fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be1fc-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="be1fc-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="be1fc-105">Attributes</span></span>  
  
|<span data-ttu-id="be1fc-106">attribute</span><span class="sxs-lookup"><span data-stu-id="be1fc-106">Attribute</span></span>|<span data-ttu-id="be1fc-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="be1fc-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="be1fc-108">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="be1fc-108">The XML namespace.</span></span> <span data-ttu-id="be1fc-109">Der Wert ist immer `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="be1fc-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="be1fc-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="be1fc-110">Child elements</span></span>  
  
|<span data-ttu-id="be1fc-111">Element</span><span class="sxs-lookup"><span data-stu-id="be1fc-111">Element</span></span>|<span data-ttu-id="be1fc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be1fc-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="be1fc-113">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="be1fc-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="be1fc-114">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="be1fc-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be1fc-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="be1fc-115">Remarks</span></span>  
 <span data-ttu-id="be1fc-116">Jede Laufzeitanweisungsdatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="be1fc-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="be1fc-117">Das `<Directives>` -Element kann NULL oder ein [\<Application>](application-element-net-native.md) -Element und NULL, ein oder mehrere- [\<Library>](library-element-net-native.md) Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="be1fc-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1fc-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be1fc-118">See also</span></span>

- [<span data-ttu-id="be1fc-119">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="be1fc-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="be1fc-120">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="be1fc-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
