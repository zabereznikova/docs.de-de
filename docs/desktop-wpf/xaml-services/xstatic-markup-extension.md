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
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433265"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="eef89-102">x:Statische Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="eef89-102">x:Static Markup Extension</span></span>

<span data-ttu-id="eef89-103">Verweist auf jede statische Codeentität mit Nebenwert, die auf CLS-konform (Common Language Specification) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="eef89-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="eef89-104">Die statische Eigenschaft, auf die verwiesen wird, kann verwendet werden, um den Wert einer Eigenschaft in XAML bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eef89-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="eef89-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="eef89-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="eef89-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="eef89-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="eef89-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="eef89-107">Optional.</span></span> <span data-ttu-id="eef89-108">Ein Präfix, das auf einen zugeordneten, nicht standardmäßigen XAML-Namespace verweist.</span><span class="sxs-lookup"><span data-stu-id="eef89-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="eef89-109">`prefix`wird explizit in der Verwendung angezeigt, da Sie selten auf statische Eigenschaften verweisen, die aus einem standardmäßigen XAML-Namespace stammen.</span><span class="sxs-lookup"><span data-stu-id="eef89-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="eef89-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="eef89-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="eef89-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eef89-111">Required.</span></span> <span data-ttu-id="eef89-112">Der Name des Typs, der den gewünschten statischen Member definiert.</span><span class="sxs-lookup"><span data-stu-id="eef89-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="eef89-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eef89-113">Required.</span></span> <span data-ttu-id="eef89-114">Der Name des gewünschten statischen Wertelements (eine Konstante, eine statische Eigenschaft, ein Feld oder ein Enumerationswert).</span><span class="sxs-lookup"><span data-stu-id="eef89-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="eef89-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="eef89-115">Remarks</span></span>

<span data-ttu-id="eef89-116">Die Codeentität, auf die verwiesen wird, muss eine der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="eef89-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="eef89-117">Eine Konstante</span><span class="sxs-lookup"><span data-stu-id="eef89-117">A constant</span></span>
- <span data-ttu-id="eef89-118">Eine statische Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eef89-118">A static property</span></span>
- <span data-ttu-id="eef89-119">Ein Feld</span><span class="sxs-lookup"><span data-stu-id="eef89-119">A field</span></span>
- <span data-ttu-id="eef89-120">Ein Enumerationswert</span><span class="sxs-lookup"><span data-stu-id="eef89-120">An enumeration value</span></span>

<span data-ttu-id="eef89-121">Das Angeben einer anderen Codeentität, z. B. einer nicht statischen Eigenschaft, verursacht einen Kompilierungsfehler, wenn das XAML Markup kompiliert wird, oder eine XAML-Ausnahme für die Lastzeitanalyse.</span><span class="sxs-lookup"><span data-stu-id="eef89-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="eef89-122">Sie können `x:Static` Verweise auf statische Felder oder Eigenschaften erstellen, die nicht im Standard-XAML-Namespace für das aktuelle XAML-Dokument enthalten sind. Dies erfordert jedoch eine Präfixzuordnung.</span><span class="sxs-lookup"><span data-stu-id="eef89-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="eef89-123">XAML-Namespaces werden fast immer im Stammelement des XAML-Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="eef89-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="eef89-124">Die Suchvorgänge für statische Eigenschaften können von .NET XAML Services und seinen XAML-Readern und XAML-Writern ausgeführt werden, wenn sie mit dem standardmäßigen XAML-Schemakontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eef89-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="eef89-125">Dieser XAML-Schemakontext kann CLR-Reflektion verwenden, um die erforderlichen statischen Werte für die Objektdiagrammerstellung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eef89-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="eef89-126">Der `typeName` von Ihnen angegebene Name ist eigentlich ein XAML-Typname und kein CLR-Typname, obwohl diese im Wesentlichen derselbe Name sind, wenn sie den standardmäßigen XAML-Schemakontext verwenden oder alle vorhandenen CLAML-basierten XAML-implementierenden Frameworks verwenden.</span><span class="sxs-lookup"><span data-stu-id="eef89-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="eef89-127">Seien Sie vorsichtig, wenn Sie Verweise vornehmen, `x:Static` die nicht direkt der Typ des Werts einer Eigenschaft sind.</span><span class="sxs-lookup"><span data-stu-id="eef89-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="eef89-128">In der XAML-Verarbeitungssequenz rufen bereitgestellte Werte aus einer Markuperweiterung keine zusätzliche Wertkonvertierung auf.</span><span class="sxs-lookup"><span data-stu-id="eef89-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="eef89-129">Dies gilt auch `x:Static` dann, wenn Ihr Verweis eine Textzeichenfolge erstellt und eine Wertkonvertierung für Attributwerte basierend auf Textzeichenfolge nmöglich entweder für dieses bestimmte Element oder für Elementwerte des Rückgabetyps erfolgt.</span><span class="sxs-lookup"><span data-stu-id="eef89-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="eef89-130">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="eef89-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="eef89-131">Das Zeichenfolgentoken, das auf die `x:Static`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.StaticExtension.Member%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.StaticExtension>-Erweiterungsklasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="eef89-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="eef89-132">Es gibt zwei weitere XAML-Verwendungen, die technisch möglich sind.</span><span class="sxs-lookup"><span data-stu-id="eef89-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="eef89-133">Diese Verwendungen sind jedoch seltener, da sie unnötig ausführlich sind:</span><span class="sxs-lookup"><span data-stu-id="eef89-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="eef89-134">Objektelementsyntax.</span><span class="sxs-lookup"><span data-stu-id="eef89-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="eef89-135">Attributsyntax mit expliziter Member-Eigenschaft für Initialisierungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eef89-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="eef89-136">In der .NET XAML Services-Implementierung wird die Verarbeitung <xref:System.Windows.Markup.StaticExtension> für diese Markuperweiterung von der Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="eef89-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="eef89-137">`x:Static` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="eef89-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="eef89-138">Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in ihrer Attributsyntax, d. h. der Konvention, nach der ein XAML-Prozessor erkennt, dass eine Markuperweiterung einen Wert bereitstellen muss.</span><span class="sxs-lookup"><span data-stu-id="eef89-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="eef89-139">Weitere Informationen zur Markuperweiterungen finden Sie unter [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eef89-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="eef89-140">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="eef89-140">WPF Usage Notes</span></span>

<span data-ttu-id="eef89-141">Der standardmäßige XAML-Namespace, den Sie für die WPF-Programmierung verwenden, enthält nicht viele nützliche statische Eigenschaften, `{x:Static}` und die meisten nützlichen statischen Eigenschaften unterstützen z. B. Typkonverter, die die Verwendung ohne die Verwendung erleichtern.</span><span class="sxs-lookup"><span data-stu-id="eef89-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="eef89-142">Für statische Eigenschaften müssen Sie ein Präfix für einen XAML-Namespace zuordnen, wenn eine der folgenden Optionen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="eef89-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="eef89-143">Sie verweisen auf einen Typ, der in WPF vorhanden ist, aber nicht Teil`http://schemas.microsoft.com/winfx/2006/xaml/presentation`des standardmäßigen XAML-Namespace für WPF ( ) ist.</span><span class="sxs-lookup"><span data-stu-id="eef89-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="eef89-144">Dies ist ein ziemlich `x:Static`häufiges Szenario für die Verwendung von .</span><span class="sxs-lookup"><span data-stu-id="eef89-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="eef89-145">Sie können z. `x:Static` B. einen Verweis mit einer <xref:System> XAML-Namespacezuordnung zum CLR-Namespace und <xref:System.Environment> zur mscorlib-Assembly verwenden, um auf die statischen Eigenschaften der Klasse zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="eef89-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="eef89-146">Sie verweisen auf einen Typ aus einer benutzerdefinierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="eef89-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="eef89-147">Sie verweisen auf einen Typ, der in einer WPF-Assembly vorhanden ist, dieser Typ befindet sich jedoch in einem CLR-Namespace, der nicht als Teil des WPF-Standard-XAML-Namespace zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="eef89-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="eef89-148">Die Zuordnung von CLR-Namespaces zum Standardmäßigen XAML-Namespace für WPF wird durch Definitionen in den verschiedenen WPF-Assemblys durchgeführt (weitere Informationen zu diesem Konzept finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="eef89-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="eef89-149">Nicht zugeordnete CLR-Namespaces können vorhanden sein, wenn dieser CLR-Namespace hauptsächlich aus Klassendefinitionen <xref:System.Windows.Threading>besteht, die normalerweise nicht für XAML vorgesehen sind, z. B. .</span><span class="sxs-lookup"><span data-stu-id="eef89-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="eef89-150">Weitere Informationen zur Verwendung von Präfixen und XAML-Namespaces für WPF finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="eef89-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eef89-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eef89-151">See also</span></span>

- [<span data-ttu-id="eef89-152">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="eef89-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="eef89-153">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="eef89-153">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
