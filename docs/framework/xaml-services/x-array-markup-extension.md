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
ms.openlocfilehash: 4d528039245e2720f78e8817e1752d88ca94e6e0
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58047886"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="5f835-102">x:Array-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="5f835-102">x:Array Markup Extension</span></span>
<span data-ttu-id="5f835-103">Bietet allgemeine Unterstützung für Arrays von Objekten in XAML durch eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="5f835-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="5f835-104">Dies entspricht der `x:ArrayExtension` XAML-Typ in [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="5f835-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="5f835-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="5f835-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5f835-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="5f835-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="5f835-107">Der Name des Typs, die Ihre `x:Array` enthält.</span><span class="sxs-lookup"><span data-stu-id="5f835-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="5f835-108">`typeName` möglicherweise (und häufig ist) mit dem Präfix für einen XAML-Namespace, die XAML enthält, Typdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="5f835-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="5f835-109">Den Elementeinhalt, die die systeminterne Funktion zugewiesen wird `ArrayExtension.Items` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5f835-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="5f835-110">Diese Elemente werden in der Regel angegeben, als eine oder mehrere Object-Elemente, die innerhalb der `x:Array` Start- und Endtags.</span><span class="sxs-lookup"><span data-stu-id="5f835-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="5f835-111">Hier sollen in den angegebenen XAML-Typ zugewiesen werden Objekte des angegebenen `typeName`.</span><span class="sxs-lookup"><span data-stu-id="5f835-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f835-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f835-112">Remarks</span></span>  
 <span data-ttu-id="5f835-113">`Type` ist ein erforderliches Attribut für alle `x:Array` Objektelemente.</span><span class="sxs-lookup"><span data-stu-id="5f835-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="5f835-114">Ein `Type` Parameterwert muss nicht mit einer `x:Type` Markuperweiterung, die kurze Name des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f835-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="5f835-115">In der Implementierung von .NET Framework-XAML-Dienste, die Beziehung zwischen der Eingabe-XAML-Typ und die Ausgabe CLR <xref:System.Type> der das erstellte Array wird durch den Dienstkontext für Markuperweiterungen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="5f835-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="5f835-116">Die Ausgabe <xref:System.Type> ist der <xref:System.Xaml.XamlType.UnderlyingType%2A> des eingegebenen XAML-Typs, nach der Suche der erforderlichen <xref:System.Xaml.XamlType> basierend auf XAML-Schemakontext und der <xref:System.Windows.Markup.IXamlTypeResolver> Dienst, der den Kontext bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5f835-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="5f835-117">Bei der Verarbeitung den Inhalt des Arrays zugewiesen sind die `ArrayExtension.Items` systeminterne Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5f835-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="5f835-118">In der <xref:System.Windows.Markup.ArrayExtension> -Implementierung wird dies durch <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f835-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5f835-119">In der .NET Framework-XAML-Dienste-Implementierung, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.ArrayExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="5f835-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="5f835-120"><xref:System.Windows.Markup.ArrayExtension> ist nicht versiegelt und kann als Grundlage für eine Markuperweiterungsimplementierung für einen benutzerdefinierten Arraytyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5f835-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 <span data-ttu-id="5f835-121">`x:Array` Weitere für die allgemeine spracherweiterbarkeit in XAML vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="5f835-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="5f835-122">Aber `x:Array` kann auch nützlich für die Angabe von XAML-Werte, der bestimmte Eigenschaften, die XAML-Unterstützung von Auflistungen als Eigenschaft der strukturierten Inhalt Nutzen sein.</span><span class="sxs-lookup"><span data-stu-id="5f835-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="5f835-123">Sie könnten z. B. Angeben des Inhalts ein <xref:System.Collections.IEnumerable> Eigenschaft mit dem ein `x:Array` Nutzung.</span><span class="sxs-lookup"><span data-stu-id="5f835-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 <span data-ttu-id="5f835-124">`x:Array` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="5f835-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="5f835-125">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f835-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="5f835-126">`x:Array` ist teilweise eine Ausnahme von dieser Regel, da statt alternatives Attribut-Wert-Behandlung, `x:Array` alternative Behandlung von seinen inneren Text-Inhalt enthält.</span><span class="sxs-lookup"><span data-stu-id="5f835-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="5f835-127">Dieses Verhalten ermöglicht die Typen, die von einem vorhandenen Content-Modell in einem Array gruppiert werden und später im Code-Behind verweist, auf das benannte Array nicht unterstützt werden können; Rufen Sie <xref:System.Array> Methoden zum Abrufen der einzelnen Arrayelemente.</span><span class="sxs-lookup"><span data-stu-id="5f835-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="5f835-128">Alle Markuperweiterungen in XAML verwenden Sie die geschweiften Klammern ({,} `)` in der Attributsyntax, d.h. die Konvention, die mit dem erkennt ein XAML-Prozessor, der den Wert des Attributs eine Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5f835-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="5f835-129">Weitere Informationen über Markuperweiterungen im Allgemeinen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="5f835-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="5f835-130">In XAML 2009 `x:Array` als Sprachprimitive eine Markuperweiterung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5f835-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="5f835-131">Weitere Informationen finden Sie unter [integrierte Typen für häufige XAML-Sprachprimitive](built-in-types-for-common-xaml-language-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="5f835-131">For more information, see [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="5f835-132">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="5f835-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="5f835-133">In der Regel der Object-Elemente, die Werte ein `x:Array` sind keine Elemente, die in vorhanden sind die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML-Namespace und eine Präfix-Zuordnung zu einem nicht standardmäßigen XAML-Namespace erfordern.</span><span class="sxs-lookup"><span data-stu-id="5f835-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="5f835-134">Folgendes ist beispielsweise ein einfaches Array von zwei Zeichenfolgen mit den `sys` Präfix (und auch `x`) auf der Ebene des Arrays definiert.</span><span class="sxs-lookup"><span data-stu-id="5f835-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="5f835-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="5f835-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="5f835-136">Für benutzerdefinierte Typen, die als Elemente des Arrays verwendet werden, muss die Klasse auch die Anforderungen für die in XAML instanziiert wird, die als Object-Elemente unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5f835-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="5f835-137">Weitere Informationen finden Sie unter [XAML und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="5f835-137">For more information, see [XAML and Custom Classes for WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f835-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f835-138">See also</span></span>
- [<span data-ttu-id="5f835-139">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="5f835-139">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="5f835-140">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="5f835-140">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
