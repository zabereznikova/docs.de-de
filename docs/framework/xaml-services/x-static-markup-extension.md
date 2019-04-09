---
title: x:Statische Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: eb0c34f259220a0326238b27ab43efd3078b0bcc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207083"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="d6350-102">x:Statische Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="d6350-102">x:Static Markup Extension</span></span>
<span data-ttu-id="d6350-103">Verweist auf alle statischen by-Value-Codeentitäten, die in definiert ist eine [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– konforme Speicherung.</span><span class="sxs-lookup"><span data-stu-id="d6350-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="d6350-104">Die statische Eigenschaft, die auf die verwiesen wird kann verwendet werden, um den Wert einer Eigenschaft in XAML bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6350-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d6350-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="d6350-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d6350-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="d6350-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="d6350-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d6350-107">Optional.</span></span> <span data-ttu-id="d6350-108">Ein Präfix, das mit einem zugeordneten, nicht standardmäßigen XAML-Namespace verweist.</span><span class="sxs-lookup"><span data-stu-id="d6350-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> `prefix` <span data-ttu-id="d6350-109">wird explizit in der Verwendung angezeigt werden, da Sie selten Eigenschaften für statische verweisen, die von einem Standard-XAML-Namespace enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d6350-109">is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="d6350-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="d6350-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="d6350-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6350-111">Required.</span></span> <span data-ttu-id="d6350-112">Der Name des Typs, der den gewünschten statischen Member definiert.</span><span class="sxs-lookup"><span data-stu-id="d6350-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="d6350-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6350-113">Required.</span></span> <span data-ttu-id="d6350-114">Der Name des Members gewünschten statischen Wert (eine Konstante, eine statische Eigenschaft, eines Felds oder eines Enumerationswerts).</span><span class="sxs-lookup"><span data-stu-id="d6350-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6350-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6350-115">Remarks</span></span>  

<span data-ttu-id="d6350-116">Die Codeentität, die auf die verwiesen wird, muss eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="d6350-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="d6350-117">Eine Konstante</span><span class="sxs-lookup"><span data-stu-id="d6350-117">A constant</span></span>  
-   <span data-ttu-id="d6350-118">Eine statische Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d6350-118">A static property</span></span>  
-   <span data-ttu-id="d6350-119">Ein Feld</span><span class="sxs-lookup"><span data-stu-id="d6350-119">A field</span></span>  
-   <span data-ttu-id="d6350-120">Ein Enumerationswert</span><span class="sxs-lookup"><span data-stu-id="d6350-120">An enumeration value</span></span>

<span data-ttu-id="d6350-121">Angeben einer beliebigen anderen Codeentität, z. B. eine nicht statische Eigenschaft bewirkt, dass einen Fehler während der Kompilierung ist die XAML-Markup kompiliert und eine XAML-Ladezeit-Analyseausnahme.</span><span class="sxs-lookup"><span data-stu-id="d6350-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="d6350-122">Möglich `x:Static` Verweise auf statische Felder oder Eigenschaften, die nicht in der XAML-Standardnamespace für das aktuelle XAML-Dokument; dies erfordert jedoch eine Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="d6350-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="d6350-123">XAML-Namespaces werden fast immer für das Stammelement des XAML-Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="d6350-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="d6350-124">Wenn sie mit der Standard-XAML-Schemakontext ausgeführt werden, können die Suchvorgänge für statische Eigenschaften von .NET Framework-XAML-Dienste und die XAML-Readern und XAML-Writer, ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6350-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="d6350-125">Dieser XAML-Schemakontext können CLR-Reflektion Graph objekterstellung notwendigen statische Werte bereit.</span><span class="sxs-lookup"><span data-stu-id="d6350-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="d6350-126">Die `typeName` Sie angeben, ist tatsächlich ein XAML Typname, keine CLR-Typnamen, auch diese sind im Wesentlichen den gleichen Namen bei Verwendung den Standard-XAML-Schemakontext, oder wenn Sie alle vorhandenen CLR-basierten XAML-implementierungsframeworks verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6350-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="d6350-127">Vorsichtig, wenn Sie stellen `x:Static` Verweise, die nicht direkt der Typ des Werts einer Eigenschaft sind.</span><span class="sxs-lookup"><span data-stu-id="d6350-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="d6350-128">In der XAML Verarbeitungssequenz, Werte von einer Markuperweiterung bereitgestellt werden nicht aufrufen, zusätzliche wertkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="d6350-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="d6350-129">Dies gilt auch, wenn Ihre `x:Static` Verweis erstellt eine Zeichenfolge, und eine wertkonvertierung für Attributwerte, die basierend auf Textzeichenfolge in der Regel tritt auf, für die dieses bestimmte Element oder für alle Memberwerte des Rückgabetyps.</span><span class="sxs-lookup"><span data-stu-id="d6350-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="d6350-130">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="d6350-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="d6350-131">Das Zeichenfolgentoken, das auf die `x:Static`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>-Erweiterungsklasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d6350-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="d6350-132">Es gibt zwei anderen XAML-Verwendungen, die technisch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="d6350-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="d6350-133">Allerdings sind diese Verwendungen seltener auf, da sie unnötig ausführlich sind:</span><span class="sxs-lookup"><span data-stu-id="d6350-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1.  <span data-ttu-id="d6350-134">Die Objektelementsyntax.</span><span class="sxs-lookup"><span data-stu-id="d6350-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2.  <span data-ttu-id="d6350-135">Attribut-Syntax mit expliziter Member-Eigenschaft für die Initialisierungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="d6350-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="d6350-136">In der .NET Framework-XAML-Dienste-Implementierung, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.StaticExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d6350-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

`x:Static` <span data-ttu-id="d6350-137">ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="d6350-137">is a markup extension.</span></span> <span data-ttu-id="d6350-138">Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax, dies ist die Konvention mit dem ein XAML-Prozessor erkennt, dass eine Markuperweiterung einen Wert angeben, muss.</span><span class="sxs-lookup"><span data-stu-id="d6350-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="d6350-139">Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6350-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d6350-140">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="d6350-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="d6350-141">Der XAML-Standardnamespace, die Sie für WPF-Programmierung verwenden enthält viele nützliche statische Eigenschaften nicht, und die meisten nützlich statische Eigenschaften Unterstützung wie z. B. Typkonverter, die die Verwendung ohne erleichtern `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="d6350-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="d6350-142">Für statische Eigenschaften müssen Sie ein Präfix für einen XAML-Namespace zuordnen, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="d6350-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="d6350-143">Sie verweisen auf einen Typ, die in WPF vorhanden ist, aber ist nicht Teil der XAML-Standardnamespace für WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="d6350-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="d6350-144">Dies ist ein gängiges Szenario für die Verwendung von `x:Static`.</span><span class="sxs-lookup"><span data-stu-id="d6350-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="d6350-145">Können z. B. eine `x:Static` Verweis auf eine XAML-Namespace-Zuordnung zu den <xref:System> CLR-Namespace und Mscorlib-Assembly um die statischen Eigenschaften der verweisen die <xref:System.Environment> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d6350-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="d6350-146">Sie sind auf einen Typ aus einer benutzerdefinierten Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="d6350-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="d6350-147">Sie verweisen auf einen Typ, der in einer WPF-Assembly vorhanden ist, aber innerhalb eines CLR-Namespace ist, die nicht als Teil der WPF-XAML-Standardnamespace zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="d6350-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="d6350-148">Die Zuordnung von CLR-Namespaces in der XAML-Standardnamespace für WPF von Definitionen in den verschiedenen WPF-Assemblys ausgeführt wird (Weitere Informationen zu diesem Konzept, finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="d6350-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="d6350-149">Nicht zugeordnete CLR-Namespaces können vorhanden sein, wenn der CLR-Namespace besteht hauptsächlich aus Klassendefinitionen, die nicht in der Regel für XAML, wie z. B. <xref:System.Windows.Threading>.</span><span class="sxs-lookup"><span data-stu-id="d6350-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="d6350-150">Weitere Informationen zur Verwendung von Präfixen und Namespaces von XAML für WPF finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d6350-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6350-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6350-151">See also</span></span>

- [<span data-ttu-id="d6350-152">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="d6350-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="d6350-153">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="d6350-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
