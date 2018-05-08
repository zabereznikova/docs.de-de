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
ms.openlocfilehash: 7c728b63c16d8f24c4ad68d07e6d174f510204ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xarray-markup-extension"></a>x:Array-Markuperweiterung
Bietet allgemeine Unterstützung für Arrays von Objekten in XAML durch eine Markuperweiterung. Dies entspricht der `x:ArrayExtension` XAML-Typ in [MS-XAML].  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`typeName`|Der Name des Typs, die Ihre `x:Array` enthält. `typeName` Möglicherweise hat (und häufig) als Präfix für einen XAML-Namespace, den XAML-Code enthält, Typdefinitionen.|  
|`arrayContents`|Die Elemente Inhalte, die systeminterne Funktion zugewiesen wird `ArrayExtension.Items` Eigenschaft. Normalerweise werden diese Elemente als eine oder mehrere Objektelemente enthaltenen angegeben die `x:Array` Start- und Endtags. Objekten angegeben hier voraussichtlich im angegebenen XAML-Typ zugeordnet werden `typeName`.|  
  
## <a name="remarks"></a>Hinweise  
 `Type` ist ein erforderliches Attribut für alle `x:Array` Objektelemente. Ein `Type` Parameterwert muss nicht mit einer `x:Type` Markuperweiterung; der kurze Name des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.  
  
 In der .NET Framework-XAML-Dienste-Implementierung, die die Beziehung zwischen der Verwendung von XAML-Typ der Eingabe und die Ausgabe CLR <xref:System.Type> der das erstellte Array von Dienstkontext für Markuperweiterungen beeinflusst wird. Die Ausgabe <xref:System.Type> ist die <xref:System.Xaml.XamlType.UnderlyingType%2A> von der Verwendung von XAML-Typ der Eingabe, nach der Suche nach den erforderlichen <xref:System.Xaml.XamlType> basierend auf XAML-Schemakontext und der <xref:System.Windows.Markup.IXamlTypeResolver> Dienst, der den Kontext bereitstellt.  
  
 Bei der Verarbeitung der Arrayinhalt zugewiesen sind die `ArrayExtension.Items` systeminterne-Eigenschaft. In der <xref:System.Windows.Markup.ArrayExtension> -Implementierung wird dies durch <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 In der .NET Framework-XAML-Dienste-Implementierung wird durch die Verarbeitung für diese Markuperweiterung definiert die <xref:System.Windows.Markup.ArrayExtension> Klasse. <xref:System.Windows.Markup.ArrayExtension> ist nicht versiegelt und kann als Grundlage für eine Markuperweiterungsimplementierung für einen benutzerdefinierten Arraytyp verwendet werden.  
  
 `x:Array` Weitere Sprache Erweiterbarkeit in XAML für allgemeine vorgesehen ist. Aber `x:Array` kann auch zum Angeben der Verwendung von XAML-Werte mancher Eigenschaften, die XAML unterstützt Auflistungen als ihren Inhalt strukturierte Eigenschaft akzeptieren nützlich sein. Beispielsweise können Sie angeben, den Inhalt des ein <xref:System.Collections.IEnumerable> Eigenschaft mit einer `x:Array` Verwendung.  
  
 `x:Array` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. `x:Array` ist teilweise eine Ausnahme von dieser Regel, da statt alternatives Attribut-Wert-Behandlung `x:Array` alternative Behandlung des inneren Textinhalts enthält. Dieses Verhalten ermöglicht die Typen, die von einer vorhandenen Inhaltsmodell in einem Array gruppiert werden und später im Code-Behind verwiesen wird, durch den Zugriff auf das benannte Array nicht unterstützt werden können. Sie können Aufrufen <xref:System.Array> Methoden, um einzelne Arrayelemente abzurufen.  
  
 Alle Markuperweiterungen in XAML verwenden Sie die geschweiften Klammern ({,} `)` in der Attributsyntax, also die Konvention, die mit dem ein XAML-Prozessor erkennt, dass eine Markuperweiterung den Attributwert verarbeiten muss. Weitere Informationen über Markuperweiterungen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In XAML 2009 `x:Array` als Sprachprimitive anstelle einer Markuperweiterung definiert ist. Weitere Informationen finden Sie unter [integrierte Typen für häufige XAML-Sprachprimitive](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 In der Regel die Objektelemente, die Auffüllen einer `x:Array` sind keine Elemente, die in der [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML-Namespace und erfordern eine/Präfix-Zuordnung zu einem nicht standardmäßigen XAML-Namespace.  
  
 Im folgenden ist beispielsweise ein einfaches Array von zwei Zeichenfolgen mit der `sys` Präfix (und auch `x`) auf der Ebene des Arrays definiert.  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Für benutzerdefinierte Typen, die als Elemente des Arrays verwendet werden, muss die Klasse auch die Anforderungen für die in XAML instanziiert wird, die als Objektelemente unterstützen. Weitere Informationen finden Sie unter [XAML und benutzerdefinierte Klassen für WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Markuperweiterungen und WPF-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Aus WPF zu System.Xaml migrierte Typen](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
