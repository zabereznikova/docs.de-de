---
title: Elemente der Laufzeitanweisung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3143c6b78749f3339e7e7195b551b5a5c31fad12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="45ddf-102">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="45ddf-102">Runtime Directive Elements</span></span>
<span data-ttu-id="45ddf-103">Das Dateiformat der Laufzeitanweisungen (rd.xml) unterstützt die folgenden Laufzeitanweisungselemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="45ddf-104">Eine hierarchische Darstellung finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="45ddf-104">See [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="45ddf-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="45ddf-105">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)  
 <span data-ttu-id="45ddf-106">Wendet die Laufzeitreflektionsrichtlinie auf alle von der Anwendung verwendeten Typen an und dient als Container für anwendungsweite Typen und Typmember, deren Metadaten für die Reflektion zur Laufzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="45ddf-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="45ddf-107">Dies ist ein untergeordnetes Element des [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)-Elements.</span><span class="sxs-lookup"><span data-stu-id="45ddf-107">This is a child of the [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="45ddf-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="45ddf-108">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 <span data-ttu-id="45ddf-109">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-109">Applies runnntime policy to all the types in an assembly.</span></span> <span data-ttu-id="45ddf-110">Dies ist ein untergeordnetes Element der [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)- und [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-110">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="45ddf-111">\<AttributeImplies></span></span>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 <span data-ttu-id="45ddf-112">Wenn die enthaltende [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)-Anweisung ein Attribut ist, wird eine Laufzeitrichtlinie auf Codeelemente angewendet, auf die dieses Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="45ddf-112">If its containing [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="45ddf-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="45ddf-113">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)  
 <span data-ttu-id="45ddf-114">Das Stammelement in jeder Laufzeitdirektivendatei für [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45ddf-114">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="45ddf-115">Die untergeordneten Elemente sind [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) und [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="45ddf-115">Its child elements are [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="45ddf-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="45ddf-116">\<Event></span></span>](../../../docs/framework/net-native/event-element-net-native.md)  
 <span data-ttu-id="45ddf-117">Wendet eine Laufzeitrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="45ddf-118">Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-118">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="45ddf-119">\<Field></span></span>](../../../docs/framework/net-native/field-element-net-native.md)  
 <span data-ttu-id="45ddf-120">Wendet eine Laufzeitrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="45ddf-121">Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-121">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="45ddf-122">\<GenericParameter></span></span>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 <span data-ttu-id="45ddf-123">Wendet eine Laufzeitrichtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="45ddf-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="45ddf-124">\<ImpliesType></span></span>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 <span data-ttu-id="45ddf-125">Wendet eine Laufzeitrichtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="45ddf-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="45ddf-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="45ddf-126">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)  
 <span data-ttu-id="45ddf-127">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="45ddf-128">Dies ist ein untergeordnetes Element der [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)- und [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-128">This is a child of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) and [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="45ddf-129">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 <span data-ttu-id="45ddf-130">Wendet eine Laufzeitrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="45ddf-131">Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-131">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="45ddf-132">\<MethodInstantiation></span></span>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 <span data-ttu-id="45ddf-133">Wendet eine Laufzeitrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="45ddf-134">Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-134">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="45ddf-135">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 <span data-ttu-id="45ddf-136">Wendet eine Laufzeitrichtlinie auf alle Typen in einem Namespace an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="45ddf-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="45ddf-137">\<Parameter></span></span>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 <span data-ttu-id="45ddf-138">Wendet eine Laufzeitrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="45ddf-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="45ddf-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="45ddf-139">\<Property></span></span>](../../../docs/framework/net-native/property-element-net-native.md)  
 <span data-ttu-id="45ddf-140">Wendet eine Laufzeitrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="45ddf-141">Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="45ddf-141">This is a child of the [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) and [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="45ddf-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="45ddf-142">\<Subtypes></span></span>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 <span data-ttu-id="45ddf-143">Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="45ddf-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="45ddf-144">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 <span data-ttu-id="45ddf-145">Wendet eine Laufzeitrichtlinie auf einen Typ an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="45ddf-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="45ddf-146">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 <span data-ttu-id="45ddf-147">Wendet eine Laufzeitrichtlinie auf einen konstruierten generischen Typ an.</span><span class="sxs-lookup"><span data-stu-id="45ddf-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="45ddf-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="45ddf-148">\<TypeParameter></span></span>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 <span data-ttu-id="45ddf-149">Wendet eine Laufzeitrichtlinie auf den Typ an, der durch ein <xref:System.Type>-Argument, das an eine Methode übergeben wird, dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="45ddf-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ddf-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45ddf-150">See Also</span></span>  
 [<span data-ttu-id="45ddf-151">„rd.xml“-Konfigurationsdateireferenz</span><span class="sxs-lookup"><span data-stu-id="45ddf-151">rd.xml Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
