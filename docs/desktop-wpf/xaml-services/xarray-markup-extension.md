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
ms.openlocfilehash: b812939cbaa74576361de534c0d39ba45536cbcf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555171"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="b61ed-102">x:Array-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="b61ed-102">x:Array Markup Extension</span></span>

<span data-ttu-id="b61ed-103">Bietet allgemeine Unterstützung für Arrays von Objekten in XAML über eine Markup Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="b61ed-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="b61ed-104">Dies entspricht dem `x:ArrayExtension` XAML-Typ in [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="b61ed-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b61ed-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="b61ed-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="b61ed-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="b61ed-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="b61ed-107">Der Name des Typs, den Ihr `x:Array` enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="b61ed-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="b61ed-108">`typeName` kann (und oft) ein Präfix für einen XAML-Namespace sein, der die XAML-Typdefinitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="b61ed-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="b61ed-109">Der Inhalt der Elemente, der der intrinsischen `ArrayExtension.Items` Eigenschaft zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b61ed-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="b61ed-110">In der Regel werden diese Elemente als ein oder mehrere Objekt Elemente angegeben, die in den `x:Array` öffnenden und schließenden Tags enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b61ed-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="b61ed-111">Die hier angegebenen Objekte können dem in angegebenen XAML-Typ zugewiesen werden `typeName` .</span><span class="sxs-lookup"><span data-stu-id="b61ed-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b61ed-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b61ed-112">Remarks</span></span>

<span data-ttu-id="b61ed-113">`Type` ist ein erforderliches Attribut für alle `x:Array` Objekt Elemente.</span><span class="sxs-lookup"><span data-stu-id="b61ed-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="b61ed-114">Ein `Type` Parameterwert muss keine `x:Type` Markup Erweiterung verwenden. der Kurzname des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b61ed-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="b61ed-115">Bei der Implementierung der .net XAML-Dienste wird die Beziehung zwischen dem Eingabe-XAML-Typ und der Ausgabe-CLR <xref:System.Type> des erstellten Arrays durch den Dienst Kontext für Markup Erweiterungen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="b61ed-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="b61ed-116">Bei der Ausgabe <xref:System.Type> handelt es sich um den <xref:System.Xaml.XamlType.UnderlyingType%2A> des Eingabe-XAML-Typs, nachdem nach den erforderlichen Anforderungen <xref:System.Xaml.XamlType> basierend auf dem XAML-Schema Kontext und dem vom <xref:System.Windows.Markup.IXamlTypeResolver> Kontext bereitgestellten Dienst gesucht wurde.</span><span class="sxs-lookup"><span data-stu-id="b61ed-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="b61ed-117">Bei der Verarbeitung wird der Inhalt des Arrays der `ArrayExtension.Items` intrinsischen Eigenschaft zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b61ed-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="b61ed-118">In der- <xref:System.Windows.Markup.ArrayExtension> Implementierung wird dies durch dargestellt <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b61ed-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b61ed-119">In der .net XAML Services-Implementierung wird die Handhabung dieser Markup Erweiterung durch die- <xref:System.Windows.Markup.ArrayExtension> Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="b61ed-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="b61ed-120"><xref:System.Windows.Markup.ArrayExtension> ist nicht versiegelt und kann als Grundlage für eine Markup Erweiterungs Implementierung für einen benutzerdefinierten Arraytyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b61ed-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="b61ed-121">`x:Array` ist eher für die Erweiterbarkeit allgemeiner Sprachen in XAML vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b61ed-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="b61ed-122">`x:Array`Kann jedoch auch nützlich sein, um XAML-Werte bestimmter Eigenschaften anzugeben, die XAML-unterstützte Auflistungen als ihren strukturierten Eigenschafts Inhalt akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b61ed-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="b61ed-123">Beispielsweise können Sie den Inhalt einer <xref:System.Collections.IEnumerable> Eigenschaft mit einer `x:Array` Verwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="b61ed-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="b61ed-124">`x:Array` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="b61ed-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="b61ed-125">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b61ed-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="b61ed-126">`x:Array` ist teilweise eine Ausnahme von dieser Regel, da statt alternativer Attribut Wert Behandlung eine `x:Array` Alternative Verarbeitung des inneren Text Inhalts bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b61ed-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="b61ed-127">Dieses Verhalten ermöglicht es, dass Typen, die möglicherweise von einem vorhandenen Inhalts Modell nicht unterstützt werden, in ein Array gruppiert werden und später im Code Behind durch Zugriff auf das benannte Array referenziert werden. Sie können <xref:System.Array> Methoden zum Abrufen einzelner Array Elemente abrufen.</span><span class="sxs-lookup"><span data-stu-id="b61ed-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="b61ed-128">Alle Markup Erweiterungen in XAML verwenden die geschweiften Klammern ( {,} `)` in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass eine Markup Erweiterung den Attribut Wert verarbeiten muss.</span><span class="sxs-lookup"><span data-stu-id="b61ed-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="b61ed-129">Weitere Informationen zu Markup Erweiterungen im Allgemeinen finden Sie unter [Typkonverter und Markup Erweiterungen für XAML](type-converters-and-markup-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="b61ed-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="b61ed-130">In XAML 2009 `x:Array` ist als sprach primitiv anstelle einer Markup Erweiterung definiert.</span><span class="sxs-lookup"><span data-stu-id="b61ed-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="b61ed-131">Weitere Informationen finden Sie unter [integrierte Typen für häufige XAML-sprach primitive](types-for-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="b61ed-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="b61ed-132">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="b61ed-132">WPF Usage Notes</span></span>

<span data-ttu-id="b61ed-133">In der Regel sind die Objekt Elemente, die ein-Element auffüllen, `x:Array` keine Elemente, die im [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML-Namespace vorhanden sind, und erfordern eine Präfix Zuordnung zu einem nicht standardmäßigen XAML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="b61ed-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="b61ed-134">Folgendes ist beispielsweise ein einfaches Array von zwei Zeichen folgen, wobei das `sys` Präfix (und auch `x` ) auf der Ebene des Arrays definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b61ed-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="b61ed-135">Bei benutzerdefinierten Typen, die als Array Elemente verwendet werden, muss die-Klasse auch die Anforderungen für die instanziierte in XAML als Objekt Elemente unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b61ed-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="b61ed-136">Weitere Informationen finden Sie unter [XAML und benutzerdefinierte Klassen für WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span><span class="sxs-lookup"><span data-stu-id="b61ed-136">For more information, see [XAML and Custom Classes for WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).</span></span>

## <a name="see-also"></a><span data-ttu-id="b61ed-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b61ed-137">See also</span></span>

- [<span data-ttu-id="b61ed-138">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="b61ed-138">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [<span data-ttu-id="b61ed-139">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="b61ed-139">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
