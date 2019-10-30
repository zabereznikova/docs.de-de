---
title: Elemente der Laufzeitanweisung
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128169"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="1c6f2-102">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="1c6f2-102">Runtime Directive Elements</span></span>
<span data-ttu-id="1c6f2-103">Das Dateiformat der Laufzeitanweisungen (rd.xml) unterstützt die folgenden Laufzeitanweisungselemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="1c6f2-104">Eine hierarchische Darstellung finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="1c6f2-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [<span data-ttu-id="1c6f2-105">\<Anwendung></span><span class="sxs-lookup"><span data-stu-id="1c6f2-105">\<Application></span></span>](application-element-net-native.md)  
 <span data-ttu-id="1c6f2-106">Wendet die Laufzeitreflektionsrichtlinie auf alle von der Anwendung verwendeten Typen an und dient als Container für anwendungsweite Typen und Typmember, deren Metadaten für die Reflektion zur Laufzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-106">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="1c6f2-107">Dies ist ein untergeordnetes Element des [\<Directives>](directives-element-net-native.md)-Elements.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-107">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [<span data-ttu-id="1c6f2-108">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="1c6f2-108">\<Assembly></span></span>](assembly-element-net-native.md)  
 <span data-ttu-id="1c6f2-109">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-109">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="1c6f2-110">Dies ist ein untergeordnetes Element der [\<Application>](application-element-net-native.md)- und [\<Library>](library-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-110">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-111">\<AttributeImplies></span><span class="sxs-lookup"><span data-stu-id="1c6f2-111">\<AttributeImplies></span></span>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="1c6f2-112">Wenn die enthaltende [\<Type>](type-element-net-native.md)-Anweisung ein Attribut ist, wird eine Laufzeitrichtlinie auf Codeelemente angewendet, auf die dieses Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-112">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [<span data-ttu-id="1c6f2-113">\<Directives></span><span class="sxs-lookup"><span data-stu-id="1c6f2-113">\<Directives></span></span>](directives-element-net-native.md)  
 <span data-ttu-id="1c6f2-114">Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-114">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="1c6f2-115">Die untergeordneten Elemente sind [\<Application>](application-element-net-native.md) und [\<Library>](library-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="1c6f2-115">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [<span data-ttu-id="1c6f2-116">\<Event></span><span class="sxs-lookup"><span data-stu-id="1c6f2-116">\<Event></span></span>](event-element-net-native.md)  
 <span data-ttu-id="1c6f2-117">Wendet eine Laufzeitrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-117">Applies runtime policy to an event.</span></span> <span data-ttu-id="1c6f2-118">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-118">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-119">\<Field></span><span class="sxs-lookup"><span data-stu-id="1c6f2-119">\<Field></span></span>](field-element-net-native.md)  
 <span data-ttu-id="1c6f2-120">Wendet eine Laufzeitrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-120">Applies runtime policy to a field.</span></span> <span data-ttu-id="1c6f2-121">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-122">\<GenericParameter></span><span class="sxs-lookup"><span data-stu-id="1c6f2-122">\<GenericParameter></span></span>](genericparameter-element-net-native.md)  
 <span data-ttu-id="1c6f2-123">Wendet eine Laufzeitrichtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-123">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [<span data-ttu-id="1c6f2-124">\<ImpliesType></span><span class="sxs-lookup"><span data-stu-id="1c6f2-124">\<ImpliesType></span></span>](impliestype-element-net-native.md)  
 <span data-ttu-id="1c6f2-125">Wendet eine Laufzeitrichtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-125">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [<span data-ttu-id="1c6f2-126">\<Library></span><span class="sxs-lookup"><span data-stu-id="1c6f2-126">\<Library></span></span>](library-element-net-native.md)  
 <span data-ttu-id="1c6f2-127">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-127">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="1c6f2-128">Dies ist ein untergeordnetes Element der [\<Application>](application-element-net-native.md)- und [\<Library>](library-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-128">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-129">\<Method></span><span class="sxs-lookup"><span data-stu-id="1c6f2-129">\<Method></span></span>](method-element-net-native.md)  
 <span data-ttu-id="1c6f2-130">Wendet eine Laufzeitrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-130">Applies runtime policy to a method.</span></span> <span data-ttu-id="1c6f2-131">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-131">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-132">\<MethodInstantiation></span><span class="sxs-lookup"><span data-stu-id="1c6f2-132">\<MethodInstantiation></span></span>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="1c6f2-133">Wendet eine Laufzeitrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-133">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="1c6f2-134">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-134">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-135">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="1c6f2-135">\<Namespace></span></span>](namespace-element-net-native.md)  
 <span data-ttu-id="1c6f2-136">Wendet eine Laufzeitrichtlinie auf alle Typen in einem Namespace an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-136">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [<span data-ttu-id="1c6f2-137">\<Parameter></span><span class="sxs-lookup"><span data-stu-id="1c6f2-137">\<Parameter></span></span>](parameter-element-net-native.md)  
 <span data-ttu-id="1c6f2-138">Wendet eine Laufzeitrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-138">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [<span data-ttu-id="1c6f2-139">\<Property></span><span class="sxs-lookup"><span data-stu-id="1c6f2-139">\<Property></span></span>](property-element-net-native.md)  
 <span data-ttu-id="1c6f2-140">Wendet eine Laufzeitrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-140">Applies runtime policy to a property.</span></span> <span data-ttu-id="1c6f2-141">Dies ist ein untergeordnetes Element der [\<Type>](type-element-net-native.md)- und [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-141">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [<span data-ttu-id="1c6f2-142">\<Subtypes></span><span class="sxs-lookup"><span data-stu-id="1c6f2-142">\<Subtypes></span></span>](subtypes-element-net-native.md)  
 <span data-ttu-id="1c6f2-143">Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-143">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [<span data-ttu-id="1c6f2-144">\<Type></span><span class="sxs-lookup"><span data-stu-id="1c6f2-144">\<Type></span></span>](type-element-net-native.md)  
 <span data-ttu-id="1c6f2-145">Wendet eine Laufzeitrichtlinie auf einen Typ an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-145">Applies runtime policy to a type.</span></span>  
  
 [<span data-ttu-id="1c6f2-146">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="1c6f2-146">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="1c6f2-147">Wendet eine Laufzeitrichtlinie auf einen konstruierten generischen Typ an.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-147">Applies runtime policy to a constructed generic type.</span></span>  
  
 [<span data-ttu-id="1c6f2-148">\<TypeParameter></span><span class="sxs-lookup"><span data-stu-id="1c6f2-148">\<TypeParameter></span></span>](typeparameter-element-net-native.md)  
 <span data-ttu-id="1c6f2-149">Wendet eine Laufzeitrichtlinie auf den Typ an, der durch ein <xref:System.Type>-Argument, das an eine Methode übergeben wird, dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1c6f2-149">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6f2-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c6f2-150">See also</span></span>

- [<span data-ttu-id="1c6f2-151">„rd.xml“-Konfigurationsdateireferenz</span><span class="sxs-lookup"><span data-stu-id="1c6f2-151">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
