---
title: '&lt;Richtlinien&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8921d2841f9a7b4228ae3b8735d7047453f71bcb
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178495"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="62fec-102">&lt;Richtlinien&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="62fec-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="62fec-103">Das Stammelement in jeder laufzeitanweisungsdatei für .NET Native.</span><span class="sxs-lookup"><span data-stu-id="62fec-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="62fec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62fec-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="62fec-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="62fec-105">Attributes</span></span>  
  
|<span data-ttu-id="62fec-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="62fec-106">Attribute</span></span>|<span data-ttu-id="62fec-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62fec-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="62fec-108">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="62fec-108">The XML namespace.</span></span> <span data-ttu-id="62fec-109">Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="62fec-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="62fec-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62fec-110">Child elements</span></span>  
  
|<span data-ttu-id="62fec-111">Element</span><span class="sxs-lookup"><span data-stu-id="62fec-111">Element</span></span>|<span data-ttu-id="62fec-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62fec-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62fec-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="62fec-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="62fec-114">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="62fec-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="62fec-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="62fec-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="62fec-116">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="62fec-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62fec-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62fec-117">Remarks</span></span>  
 <span data-ttu-id="62fec-118">Jede Laufzeitdirektivendatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="62fec-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="62fec-119">Das `<Directives>`-Element kann null oder ein [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="62fec-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fec-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62fec-120">See Also</span></span>  
 [<span data-ttu-id="62fec-121">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="62fec-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="62fec-122">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="62fec-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
