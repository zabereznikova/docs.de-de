---
title: Elemente der Laufzeitanweisung
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 062f13ad92f37bb7ae29ed34dcf88f99f98e7612
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049269"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="c50f4-102">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="c50f4-102">Runtime Directive Elements</span></span>
<span data-ttu-id="c50f4-103">Das Dateiformat der Laufzeitanweisungen (rd.xml) unterstützt die folgenden Laufzeitanweisungselemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="c50f4-104">Eine hierarchische Darstellung finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c50f4-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="c50f4-105">\<Application></span><span class="sxs-lookup"><span data-stu-id="c50f4-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="c50f4-106">Wendet die Laufzeitreflektionsrichtlinie auf alle von der Anwendung verwendeten Typen an und dient als Container für anwendungsweite Typen und Typmember, deren Metadaten für die Reflektion zur Laufzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c50f4-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="c50f4-107">Dies ist ein untergeordnetes Element des [\<Directives>](directives-element-net-native.md)-Elements.</span><span class="sxs-lookup"><span data-stu-id="c50f4-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="c50f4-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="c50f4-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="c50f4-109">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="c50f4-110">Dies ist ein untergeordnetes Element der [\<Application>](application-element-net-native.md)- und [\<Library>](library-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="c50f4-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="c50f4-112">Wenn die enthaltende [\<Type>](type-element-net-native.md)-Anweisung ein Attribut ist, wird eine Laufzeitrichtlinie auf Codeelemente angewendet, auf die dieses Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c50f4-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="c50f4-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="c50f4-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="c50f4-114">Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.</span><span class="sxs-lookup"><span data-stu-id="c50f4-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="c50f4-115">Die untergeordneten Elemente sind [\<Application>](application-element-net-native.md) und [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="c50f4-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="c50f4-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="c50f4-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="c50f4-117">Wendet eine Laufzeitrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="c50f4-118">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="c50f4-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="c50f4-120">Wendet eine Laufzeitrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="c50f4-121">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="c50f4-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="c50f4-123">Wendet eine Laufzeitrichtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="c50f4-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="c50f4-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="c50f4-125">Wendet eine Laufzeitrichtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c50f4-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="c50f4-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="c50f4-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="c50f4-127">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="c50f4-128">Dies ist ein untergeordnetes Element der [\<Application>](application-element-net-native.md)- und [\<Library>](library-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="c50f4-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="c50f4-130">Wendet eine Laufzeitrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="c50f4-131">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="c50f4-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="c50f4-133">Wendet eine Laufzeitrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="c50f4-134">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="c50f4-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="c50f4-136">Wendet eine Laufzeitrichtlinie auf alle Typen in einem Namespace an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="c50f4-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="c50f4-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="c50f4-138">Wendet eine Laufzeitrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c50f4-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="c50f4-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="c50f4-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="c50f4-140">Wendet eine Laufzeitrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="c50f4-141">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c50f4-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="c50f4-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="c50f4-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="c50f4-143">Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="c50f4-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="c50f4-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="c50f4-145">Wendet eine Laufzeitrichtlinie auf einen Typ an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="c50f4-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="c50f4-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="c50f4-147">Wendet eine Laufzeitrichtlinie auf einen konstruierten generischen Typ an.</span><span class="sxs-lookup"><span data-stu-id="c50f4-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="c50f4-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="c50f4-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="c50f4-149">Wendet eine Laufzeitrichtlinie auf den Typ an, der durch ein <xref:System.Type>-Argument, das an eine Methode übergeben wird, dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c50f4-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50f4-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c50f4-150">See also</span></span>

- [<span data-ttu-id="c50f4-151">„rd.xml“-Konfigurationsdateireferenz</span><span class="sxs-lookup"><span data-stu-id="c50f4-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
