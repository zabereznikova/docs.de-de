---
title: '&lt;Richtlinien&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394445"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="a16f7-102">&lt;Richtlinien&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="a16f7-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="a16f7-103">Das Stammelement in jeder Laufzeitdirektivendatei für [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a16f7-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="a16f7-104">**\<Direktiven Xmlns = "http://schemas.microsoft.com/netfx/2013/01/metadata" >**</span><span class="sxs-lookup"><span data-stu-id="a16f7-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16f7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a16f7-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="a16f7-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="a16f7-106">Attributes</span></span>  
  
|<span data-ttu-id="a16f7-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="a16f7-107">Attribute</span></span>|<span data-ttu-id="a16f7-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a16f7-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="a16f7-109">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a16f7-109">The XML namespace.</span></span> <span data-ttu-id="a16f7-110">Der Wert ist immer **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span><span class="sxs-lookup"><span data-stu-id="a16f7-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="a16f7-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a16f7-111">Child elements</span></span>  
  
|<span data-ttu-id="a16f7-112">Element</span><span class="sxs-lookup"><span data-stu-id="a16f7-112">Element</span></span>|<span data-ttu-id="a16f7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a16f7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a16f7-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="a16f7-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="a16f7-115">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a16f7-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="a16f7-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="a16f7-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="a16f7-117">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="a16f7-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a16f7-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a16f7-118">Remarks</span></span>  
 <span data-ttu-id="a16f7-119">Jede Laufzeitdirektivendatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="a16f7-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="a16f7-120">Das `<Directives>`-Element kann null oder ein [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="a16f7-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16f7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a16f7-121">See Also</span></span>  
 [<span data-ttu-id="a16f7-122">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="a16f7-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="a16f7-123">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="a16f7-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
