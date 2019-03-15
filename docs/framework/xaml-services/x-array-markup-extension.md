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
|`typeName`|Der Name des Typs, die Ihre `x:Array` enthält. `typeName` möglicherweise (und häufig ist) mit dem Präfix für einen XAML-Namespace, die XAML enthält, Typdefinitionen.|  
|`arrayContents`|Den Elementeinhalt, die die systeminterne Funktion zugewiesen wird `ArrayExtension.Items` Eigenschaft. Diese Elemente werden in der Regel angegeben, als eine oder mehrere Object-Elemente, die innerhalb der `x:Array` Start- und Endtags. Hier sollen in den angegebenen XAML-Typ zugewiesen werden Objekte des angegebenen `typeName`.|  
  
## <a name="remarks"></a>Hinweise  
 `Type` ist ein erforderliches Attribut für alle `x:Array` Objektelemente. Ein `Type` Parameterwert muss nicht mit einer `x:Type` Markuperweiterung, die kurze Name des Typs ist ein XAML-Typ, der als Zeichenfolge angegeben werden kann.  
  
 In der Implementierung von .NET Framework-XAML-Dienste, die Beziehung zwischen der Eingabe-XAML-Typ und die Ausgabe CLR <xref:System.Type> der das erstellte Array wird durch den Dienstkontext für Markuperweiterungen beeinflusst. Die Ausgabe <xref:System.Type> ist der <xref:System.Xaml.XamlType.UnderlyingType%2A> des eingegebenen XAML-Typs, nach der Suche der erforderlichen <xref:System.Xaml.XamlType> basierend auf XAML-Schemakontext und der <xref:System.Windows.Markup.IXamlTypeResolver> Dienst, der den Kontext bereitstellt.  
  
 Bei der Verarbeitung den Inhalt des Arrays zugewiesen sind die `ArrayExtension.Items` systeminterne Eigenschaft. In der <xref:System.Windows.Markup.ArrayExtension> -Implementierung wird dies durch <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 In der .NET Framework-XAML-Dienste-Implementierung, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.ArrayExtension> Klasse. <xref:System.Windows.Markup.ArrayExtension> ist nicht versiegelt und kann als Grundlage für eine Markuperweiterungsimplementierung für einen benutzerdefinierten Arraytyp verwendet werden.  
  
 `x:Array` Weitere für die allgemeine spracherweiterbarkeit in XAML vorgesehen ist. Aber `x:Array` kann auch nützlich für die Angabe von XAML-Werte, der bestimmte Eigenschaften, die XAML-Unterstützung von Auflistungen als Eigenschaft der strukturierten Inhalt Nutzen sein. Sie könnten z. B. Angeben des Inhalts ein <xref:System.Collections.IEnumerable> Eigenschaft mit dem ein `x:Array` Nutzung.  
  
 `x:Array` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. `x:Array` ist teilweise eine Ausnahme von dieser Regel, da statt alternatives Attribut-Wert-Behandlung, `x:Array` alternative Behandlung von seinen inneren Text-Inhalt enthält. Dieses Verhalten ermöglicht die Typen, die von einem vorhandenen Content-Modell in einem Array gruppiert werden und später im Code-Behind verweist, auf das benannte Array nicht unterstützt werden können; Rufen Sie <xref:System.Array> Methoden zum Abrufen der einzelnen Arrayelemente.  
  
 Alle Markuperweiterungen in XAML verwenden Sie die geschweiften Klammern ({,} `)` in der Attributsyntax, d.h. die Konvention, die mit dem erkennt ein XAML-Prozessor, der den Wert des Attributs eine Markuperweiterung verarbeitet werden muss. Weitere Informationen über Markuperweiterungen im Allgemeinen finden Sie unter [Typkonverter und Markuperweiterungen für XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 In XAML 2009 `x:Array` als Sprachprimitive eine Markuperweiterung definiert ist. Weitere Informationen finden Sie unter [integrierte Typen für häufige XAML-Sprachprimitive](built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
 In der Regel der Object-Elemente, die Werte ein `x:Array` sind keine Elemente, die in vorhanden sind die [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML-Namespace und eine Präfix-Zuordnung zu einem nicht standardmäßigen XAML-Namespace erfordern.  
  
 Folgendes ist beispielsweise ein einfaches Array von zwei Zeichenfolgen mit den `sys` Präfix (und auch `x`) auf der Ebene des Arrays definiert.  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Für benutzerdefinierte Typen, die als Elemente des Arrays verwendet werden, muss die Klasse auch die Anforderungen für die in XAML instanziiert wird, die als Object-Elemente unterstützen. Weitere Informationen finden Sie unter [XAML und benutzerdefinierte Klassen für WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>Siehe auch
- [Markuperweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Aus WPF zu System.Xaml migrierte Typen](types-migrated-from-wpf-to-system-xaml.md)
