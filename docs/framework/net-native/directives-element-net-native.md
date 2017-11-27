---
title: '&lt;Richtlinien&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a55048ea5b2889da82b10ac2a51865d945635143
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="fcf83-102">&lt;Richtlinien&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="fcf83-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="fcf83-103">Das Stammelement in jeder Laufzeitdirektivendatei für [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf83-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="fcf83-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span><span class="sxs-lookup"><span data-stu-id="fcf83-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf83-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcf83-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="fcf83-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="fcf83-106">Attributes</span></span>  
  
|<span data-ttu-id="fcf83-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="fcf83-107">Attribute</span></span>|<span data-ttu-id="fcf83-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcf83-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="fcf83-109">Der XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="fcf83-109">The XML namespace.</span></span> <span data-ttu-id="fcf83-110">Der Wert ist immer **„http://schemas.microsoft.com/netfx/2013/01/metadata“**.</span><span class="sxs-lookup"><span data-stu-id="fcf83-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="fcf83-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fcf83-111">Child elements</span></span>  
  
|<span data-ttu-id="fcf83-112">Element</span><span class="sxs-lookup"><span data-stu-id="fcf83-112">Element</span></span>|<span data-ttu-id="fcf83-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcf83-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcf83-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="fcf83-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="fcf83-115">Dient als Container für anwendungsweite Typen und Typmember, dessen Metadaten für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fcf83-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="fcf83-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="fcf83-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="fcf83-117">Definiert die Assembly, deren untergeordneten Typen und Typmember Metadaten zur Laufzeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="fcf83-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcf83-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcf83-118">Remarks</span></span>  
 <span data-ttu-id="fcf83-119">Jede Laufzeitdirektivendatei darf nur ein `<Directives>`-Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="fcf83-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="fcf83-120">Das `<Directives>`-Element kann null oder ein [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Element sowie null, ein oder mehrere [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="fcf83-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf83-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcf83-121">See Also</span></span>  
 [<span data-ttu-id="fcf83-122">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="fcf83-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="fcf83-123">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="fcf83-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
