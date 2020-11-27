---
title: Elemente der Laufzeitanweisung
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: 96bce89c02ad17d1b30eda66237f69a15123dcd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250800"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="35551-102">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="35551-102">Runtime Directive Elements</span></span>

<span data-ttu-id="35551-103">Das Dateiformat der Laufzeitanweisungen (rd.xml) unterstützt die folgenden Laufzeitanweisungselemente.</span><span class="sxs-lookup"><span data-stu-id="35551-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="35551-104">Eine hierarchische Darstellung finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="35551-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [\<Application>](application-element-net-native.md)  
 <span data-ttu-id="35551-105">Wendet die Laufzeitreflektionsrichtlinie auf alle von der Anwendung verwendeten Typen an und dient als Container für anwendungsweite Typen und Typmember, deren Metadaten für die Reflektion zur Laufzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35551-105">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="35551-106">Dies ist ein untergeordnetes Element des- [\<Directives>](directives-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-106">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [\<Assembly>](assembly-element-net-native.md)  
 <span data-ttu-id="35551-107">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="35551-107">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="35551-108">Dies ist ein untergeordnetes [\<Application>](application-element-net-native.md) Element des-Elements und des- [\<Library>](library-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-108">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="35551-109">Wenn die enthaltende [\<Type>](type-element-net-native.md) Direktive ein Attribut ist, wendet eine Lauf Zeit Richtlinie auf Code Elemente an, auf die dieses Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="35551-109">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [\<Directives>](directives-element-net-native.md)  
 <span data-ttu-id="35551-110">Das Stamm Element in jeder laufzeitdirektivendatei für .net Native.</span><span class="sxs-lookup"><span data-stu-id="35551-110">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="35551-111">Die untergeordneten Elemente sind [\<Application>](application-element-net-native.md) und [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="35551-111">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [\<Event>](event-element-net-native.md)  
 <span data-ttu-id="35551-112">Wendet eine Laufzeitrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="35551-112">Applies runtime policy to an event.</span></span> <span data-ttu-id="35551-113">Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-113">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Field>](field-element-net-native.md)  
 <span data-ttu-id="35551-114">Wendet eine Laufzeitrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="35551-114">Applies runtime policy to a field.</span></span> <span data-ttu-id="35551-115">Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-115">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 <span data-ttu-id="35551-116">Wendet eine Laufzeitrichtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="35551-116">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 <span data-ttu-id="35551-117">Wendet eine Laufzeitrichtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="35551-117">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [\<Library>](library-element-net-native.md)  
 <span data-ttu-id="35551-118">Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="35551-118">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="35551-119">Dies ist ein untergeordnetes [\<Application>](application-element-net-native.md) Element des-Elements und des- [\<Library>](library-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-119">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<Method>](method-element-net-native.md)  
 <span data-ttu-id="35551-120">Wendet eine Laufzeitrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="35551-120">Applies runtime policy to a method.</span></span> <span data-ttu-id="35551-121">Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="35551-122">Wendet eine Laufzeitrichtlinie auf eine konstruierte generische Methode an.</span><span class="sxs-lookup"><span data-stu-id="35551-122">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="35551-123">Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-123">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Namespace>](namespace-element-net-native.md)  
 <span data-ttu-id="35551-124">Wendet eine Laufzeitrichtlinie auf alle Typen in einem Namespace an.</span><span class="sxs-lookup"><span data-stu-id="35551-124">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [\<Parameter>](parameter-element-net-native.md)  
 <span data-ttu-id="35551-125">Wendet eine Laufzeitrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="35551-125">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [\<Property>](property-element-net-native.md)  
 <span data-ttu-id="35551-126">Wendet eine Laufzeitrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="35551-126">Applies runtime policy to a property.</span></span> <span data-ttu-id="35551-127">Dies ist ein untergeordnetes [\<Type>](type-element-net-native.md) Element des-Elements und des- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="35551-127">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 <span data-ttu-id="35551-128">Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.</span><span class="sxs-lookup"><span data-stu-id="35551-128">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [\<Type>](type-element-net-native.md)  
 <span data-ttu-id="35551-129">Wendet eine Laufzeitrichtlinie auf einen Typ an.</span><span class="sxs-lookup"><span data-stu-id="35551-129">Applies runtime policy to a type.</span></span>  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="35551-130">Wendet eine Laufzeitrichtlinie auf einen konstruierten generischen Typ an.</span><span class="sxs-lookup"><span data-stu-id="35551-130">Applies runtime policy to a constructed generic type.</span></span>  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 <span data-ttu-id="35551-131">Wendet eine Laufzeitrichtlinie auf den Typ an, der durch ein <xref:System.Type>-Argument, das an eine Methode übergeben wird, dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="35551-131">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35551-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35551-132">See also</span></span>

- [<span data-ttu-id="35551-133">„rd.xml“-Konfigurationsdateireferenz</span><span class="sxs-lookup"><span data-stu-id="35551-133">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
