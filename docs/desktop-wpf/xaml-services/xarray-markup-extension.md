---
title: x:Array-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433283"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="45c6f-102">x:Array-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="45c6f-102">x:Array Markup Extension</span></span>

<span data-ttu-id="45c6f-103">Bietet allgemeine Unterstützung für Arrays von Objekten in XAML über eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="45c6f-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="45c6f-104">Dies entspricht `x:ArrayExtension` dem XAML-Typ in [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="45c6f-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="45c6f-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="45c6f-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="45c6f-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="45c6f-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="45c6f-107">Der Name des Typs, den Sie `x:Array` enthalten.</span><span class="sxs-lookup"><span data-stu-id="45c6f-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="45c6f-108">`typeName`kann für einen XAML-Namespace, der die XAML-Typdefinitionen enthält, vorangestellt sein (und häufig ist).</span><span class="sxs-lookup"><span data-stu-id="45c6f-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="45c6f-109">Der Elementinhalt, der der `ArrayExtension.Items` systeminternen Eigenschaft zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="45c6f-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="45c6f-110">In der Regel werden diese Elemente als ein `x:Array` oder mehrere Objektelemente angegeben, die in den öffnenden und schließenden Tags enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="45c6f-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="45c6f-111">Die hier angegebenen Objekte können voraussichtlich dem in `typeName`angegebenen XAML-Typ zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="45c6f-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45c6f-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45c6f-112">Remarks</span></span>

<span data-ttu-id="45c6f-113">`Type`ist ein erforderliches `x:Array` Attribut für alle Objektelemente.</span><span class="sxs-lookup"><span data-stu-id="45c6f-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="45c6f-114">Ein `Type` Parameterwert muss keine `x:Type` Markuperweiterung verwenden. Der Kurzname des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="45c6f-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="45c6f-115">In der .NET XAML Services-Implementierung wird die Beziehung zwischen <xref:System.Type> dem Eingabe-XAML-Typ und der Ausgabe-CLR des erstellten Arrays vom Dienstkontext für Markuperweiterungen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="45c6f-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="45c6f-116">Die <xref:System.Type> Ausgabe <xref:System.Xaml.XamlType.UnderlyingType%2A> ist die des Eingabe-XAML-Typs, nachdem der erforderliche <xref:System.Xaml.XamlType> <xref:System.Windows.Markup.IXamlTypeResolver> XAML-Schemakontext und der Dienst, den der Kontext bereitstellt, nachgesucht wurde.</span><span class="sxs-lookup"><span data-stu-id="45c6f-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="45c6f-117">Bei der Verarbeitung werden die `ArrayExtension.Items` Arrayinhalte der intrinsischen Eigenschaft zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="45c6f-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="45c6f-118">In <xref:System.Windows.Markup.ArrayExtension> der Implementierung wird <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>dies durch dargestellt.</span><span class="sxs-lookup"><span data-stu-id="45c6f-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="45c6f-119">In der .NET XAML Services-Implementierung wird die Verarbeitung <xref:System.Windows.Markup.ArrayExtension> für diese Markuperweiterung von der Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="45c6f-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="45c6f-120"><xref:System.Windows.Markup.ArrayExtension>ist nicht versiegelt und könnte als Grundlage für eine Markuperweiterungsimplementierung für einen benutzerdefinierten Arraytyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45c6f-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="45c6f-121">`x:Array`ist eher für die allgemeine Spracherweiterbarkeit in XAML vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="45c6f-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="45c6f-122">Es `x:Array` kann jedoch auch nützlich sein, um XAML-Werte bestimmter Eigenschaften anzugeben, die XAML-unterstützte Auflistungen als strukturierten Eigenschafteninhalt verwenden.</span><span class="sxs-lookup"><span data-stu-id="45c6f-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="45c6f-123">Sie können z. B. <xref:System.Collections.IEnumerable> den Inhalt `x:Array` einer Eigenschaft mit einer Verwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="45c6f-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="45c6f-124">`x:Array` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="45c6f-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="45c6f-125">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="45c6f-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="45c6f-126">`x:Array`ist teilweise eine Ausnahme von dieser Regel, da `x:Array` anstelle einer alternativen Attributwertbehandlung eine alternative Behandlung des inneren Textinhalts vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="45c6f-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="45c6f-127">Dieses Verhalten ermöglicht es Typen, die möglicherweise nicht von einem vorhandenen Inhaltsmodell unterstützt werden, in ein Array gruppiert und später im CodeBehind referenziert zu werden, indem auf das benannte Array zugreift. Sie können <xref:System.Array> Methoden aufrufen, um einzelne Arrayelemente abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45c6f-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="45c6f-128">Alle Markuperweiterungen in XAML{,} `)` verwenden die geschweiften Klammern (in ihrer Attributsyntax, d. h. der Konvention, nach der ein XAML-Prozessor erkennt, dass eine Markuperweiterung den Attributwert verarbeiten muss.</span><span class="sxs-lookup"><span data-stu-id="45c6f-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="45c6f-129">Weitere Informationen zu Markuperweiterungen im Allgemeinen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="45c6f-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="45c6f-130">In XAML 2009 `x:Array` wird er als Sprachprimitive anstelle einer Markuperweiterung definiert.</span><span class="sxs-lookup"><span data-stu-id="45c6f-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="45c6f-131">Weitere Informationen finden Sie unter [Integrierte Typen für allgemeine XAML-Sprachprimitive](types-for-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="45c6f-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="45c6f-132">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="45c6f-132">WPF Usage Notes</span></span>

<span data-ttu-id="45c6f-133">In der Regel sind die `x:Array` Objektelemente, die ein [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] auffüllen, keine Elemente, die im XAML-Namespace vorhanden sind und eine Präfixzuordnung zu einem nicht standardmäßigen XAML-Namespace erfordern.</span><span class="sxs-lookup"><span data-stu-id="45c6f-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="45c6f-134">Im Folgenden ist z. B. ein einfaches `sys` Array aus `x`zwei Zeichenfolgen, wobei das Präfix (und auch ) auf der Ebene des Arrays definiert ist.</span><span class="sxs-lookup"><span data-stu-id="45c6f-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="45c6f-135">Bei benutzerdefinierten Typen, die als Arrayelemente verwendet werden, muss die Klasse auch die Anforderungen für die Instanziiertung in XAML als Objektelemente unterstützen.</span><span class="sxs-lookup"><span data-stu-id="45c6f-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="45c6f-136">Weitere Informationen finden Sie unter [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="45c6f-136">For more information, see [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45c6f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45c6f-137">See also</span></span>

- [<span data-ttu-id="45c6f-138">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="45c6f-138">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="45c6f-139">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="45c6f-139">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
