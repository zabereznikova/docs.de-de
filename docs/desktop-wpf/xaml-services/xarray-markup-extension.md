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
# <a name="xarray-markup-extension"></a>x:Array-Markuperweiterung

Bietet allgemeine Unterstützung für Arrays von Objekten in XAML über eine Markuperweiterung. Dies entspricht `x:ArrayExtension` dem XAML-Typ in [MS-XAML].

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`typeName`|Der Name des Typs, den Sie `x:Array` enthalten. `typeName`kann für einen XAML-Namespace, der die XAML-Typdefinitionen enthält, vorangestellt sein (und häufig ist).|
|`arrayContents`|Der Elementinhalt, der der `ArrayExtension.Items` systeminternen Eigenschaft zugewiesen ist. In der Regel werden diese Elemente als ein `x:Array` oder mehrere Objektelemente angegeben, die in den öffnenden und schließenden Tags enthalten sind. Die hier angegebenen Objekte können voraussichtlich dem in `typeName`angegebenen XAML-Typ zugewiesen werden.|

## <a name="remarks"></a>Bemerkungen

`Type`ist ein erforderliches `x:Array` Attribut für alle Objektelemente. Ein `Type` Parameterwert muss keine `x:Type` Markuperweiterung verwenden. Der Kurzname des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.

In der .NET XAML Services-Implementierung wird die Beziehung zwischen <xref:System.Type> dem Eingabe-XAML-Typ und der Ausgabe-CLR des erstellten Arrays vom Dienstkontext für Markuperweiterungen beeinflusst. Die <xref:System.Type> Ausgabe <xref:System.Xaml.XamlType.UnderlyingType%2A> ist die des Eingabe-XAML-Typs, nachdem der erforderliche <xref:System.Xaml.XamlType> <xref:System.Windows.Markup.IXamlTypeResolver> XAML-Schemakontext und der Dienst, den der Kontext bereitstellt, nachgesucht wurde.

Bei der Verarbeitung werden die `ArrayExtension.Items` Arrayinhalte der intrinsischen Eigenschaft zugewiesen. In <xref:System.Windows.Markup.ArrayExtension> der Implementierung wird <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>dies durch dargestellt.

In der .NET XAML Services-Implementierung wird die Verarbeitung <xref:System.Windows.Markup.ArrayExtension> für diese Markuperweiterung von der Klasse definiert. <xref:System.Windows.Markup.ArrayExtension>ist nicht versiegelt und könnte als Grundlage für eine Markuperweiterungsimplementierung für einen benutzerdefinierten Arraytyp verwendet werden.

`x:Array`ist eher für die allgemeine Spracherweiterbarkeit in XAML vorgesehen. Es `x:Array` kann jedoch auch nützlich sein, um XAML-Werte bestimmter Eigenschaften anzugeben, die XAML-unterstützte Auflistungen als strukturierten Eigenschafteninhalt verwenden. Sie können z. B. <xref:System.Collections.IEnumerable> den Inhalt `x:Array` einer Eigenschaft mit einer Verwendung angeben.

`x:Array` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. `x:Array`ist teilweise eine Ausnahme von dieser Regel, da `x:Array` anstelle einer alternativen Attributwertbehandlung eine alternative Behandlung des inneren Textinhalts vorgesehen ist. Dieses Verhalten ermöglicht es Typen, die möglicherweise nicht von einem vorhandenen Inhaltsmodell unterstützt werden, in ein Array gruppiert und später im CodeBehind referenziert zu werden, indem auf das benannte Array zugreift. Sie können <xref:System.Array> Methoden aufrufen, um einzelne Arrayelemente abzurufen.

Alle Markuperweiterungen in XAML{,} `)` verwenden die geschweiften Klammern (in ihrer Attributsyntax, d. h. der Konvention, nach der ein XAML-Prozessor erkennt, dass eine Markuperweiterung den Attributwert verarbeiten muss. Weitere Informationen zu Markuperweiterungen im Allgemeinen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions.md).

In XAML 2009 `x:Array` wird er als Sprachprimitive anstelle einer Markuperweiterung definiert. Weitere Informationen finden Sie unter [Integrierte Typen für allgemeine XAML-Sprachprimitive](types-for-primitives.md).

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

In der Regel sind die `x:Array` Objektelemente, die ein [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] auffüllen, keine Elemente, die im XAML-Namespace vorhanden sind und eine Präfixzuordnung zu einem nicht standardmäßigen XAML-Namespace erfordern.

Im Folgenden ist z. B. ein einfaches `sys` Array aus `x`zwei Zeichenfolgen, wobei das Präfix (und auch ) auf der Ebene des Arrays definiert ist.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

Bei benutzerdefinierten Typen, die als Arrayelemente verwendet werden, muss die Klasse auch die Anforderungen für die Instanziiertung in XAML als Objektelemente unterstützen. Weitere Informationen finden Sie unter [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).

## <a name="see-also"></a>Weitere Informationen

- [Markuperweiterungen und WPF-XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Aus WPF zu System.Xaml migrierte Typen](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
