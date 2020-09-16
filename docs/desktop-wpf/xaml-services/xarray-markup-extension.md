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
# <a name="xarray-markup-extension"></a>x:Array-Markuperweiterung

Bietet allgemeine Unterstützung für Arrays von Objekten in XAML über eine Markup Erweiterung. Dies entspricht dem `x:ArrayExtension` XAML-Typ in [MS-XAML].

## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a>XAML-Werte

|||
|-|-|
|`typeName`|Der Name des Typs, den Ihr `x:Array` enthalten soll. `typeName` kann (und oft) ein Präfix für einen XAML-Namespace sein, der die XAML-Typdefinitionen enthält.|
|`arrayContents`|Der Inhalt der Elemente, der der intrinsischen `ArrayExtension.Items` Eigenschaft zugewiesen ist. In der Regel werden diese Elemente als ein oder mehrere Objekt Elemente angegeben, die in den `x:Array` öffnenden und schließenden Tags enthalten sind. Die hier angegebenen Objekte können dem in angegebenen XAML-Typ zugewiesen werden `typeName` .|

## <a name="remarks"></a>Hinweise

`Type` ist ein erforderliches Attribut für alle `x:Array` Objekt Elemente. Ein `Type` Parameterwert muss keine `x:Type` Markup Erweiterung verwenden. der Kurzname des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.

Bei der Implementierung der .net XAML-Dienste wird die Beziehung zwischen dem Eingabe-XAML-Typ und der Ausgabe-CLR <xref:System.Type> des erstellten Arrays durch den Dienst Kontext für Markup Erweiterungen beeinflusst. Bei der Ausgabe <xref:System.Type> handelt es sich um den <xref:System.Xaml.XamlType.UnderlyingType%2A> des Eingabe-XAML-Typs, nachdem nach den erforderlichen Anforderungen <xref:System.Xaml.XamlType> basierend auf dem XAML-Schema Kontext und dem vom <xref:System.Windows.Markup.IXamlTypeResolver> Kontext bereitgestellten Dienst gesucht wurde.

Bei der Verarbeitung wird der Inhalt des Arrays der `ArrayExtension.Items` intrinsischen Eigenschaft zugewiesen. In der- <xref:System.Windows.Markup.ArrayExtension> Implementierung wird dies durch dargestellt <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType> .

In der .net XAML Services-Implementierung wird die Handhabung dieser Markup Erweiterung durch die- <xref:System.Windows.Markup.ArrayExtension> Klasse definiert. <xref:System.Windows.Markup.ArrayExtension> ist nicht versiegelt und kann als Grundlage für eine Markup Erweiterungs Implementierung für einen benutzerdefinierten Arraytyp verwendet werden.

`x:Array` ist eher für die Erweiterbarkeit allgemeiner Sprachen in XAML vorgesehen. `x:Array`Kann jedoch auch nützlich sein, um XAML-Werte bestimmter Eigenschaften anzugeben, die XAML-unterstützte Auflistungen als ihren strukturierten Eigenschafts Inhalt akzeptieren. Beispielsweise können Sie den Inhalt einer <xref:System.Collections.IEnumerable> Eigenschaft mit einer `x:Array` Verwendung angeben.

`x:Array` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. `x:Array` ist teilweise eine Ausnahme von dieser Regel, da statt alternativer Attribut Wert Behandlung eine `x:Array` Alternative Verarbeitung des inneren Text Inhalts bereitstellt. Dieses Verhalten ermöglicht es, dass Typen, die möglicherweise von einem vorhandenen Inhalts Modell nicht unterstützt werden, in ein Array gruppiert werden und später im Code Behind durch Zugriff auf das benannte Array referenziert werden. Sie können <xref:System.Array> Methoden zum Abrufen einzelner Array Elemente abrufen.

Alle Markup Erweiterungen in XAML verwenden die geschweiften Klammern ( {,} `)` in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass eine Markup Erweiterung den Attribut Wert verarbeiten muss. Weitere Informationen zu Markup Erweiterungen im Allgemeinen finden Sie unter [Typkonverter und Markup Erweiterungen für XAML](type-converters-and-markup-extensions.md).

In XAML 2009 `x:Array` ist als sprach primitiv anstelle einer Markup Erweiterung definiert. Weitere Informationen finden Sie unter [integrierte Typen für häufige XAML-sprach primitive](types-for-primitives.md).

## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung

In der Regel sind die Objekt Elemente, die ein-Element auffüllen, `x:Array` keine Elemente, die im [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML-Namespace vorhanden sind, und erfordern eine Präfix Zuordnung zu einem nicht standardmäßigen XAML-Namespace.

Folgendes ist beispielsweise ein einfaches Array von zwei Zeichen folgen, wobei das `sys` Präfix (und auch `x` ) auf der Ebene des Arrays definiert ist.

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

Bei benutzerdefinierten Typen, die als Array Elemente verwendet werden, muss die-Klasse auch die Anforderungen für die instanziierte in XAML als Objekt Elemente unterstützen. Weitere Informationen finden Sie unter [XAML und benutzerdefinierte Klassen für WPF](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf).

## <a name="see-also"></a>Siehe auch

- [Markuperweiterungen und WPF-XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
- [Aus WPF zu System.Xaml migrierte Typen](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
