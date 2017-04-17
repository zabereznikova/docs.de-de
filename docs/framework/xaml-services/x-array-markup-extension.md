---
title: "x:Array Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Array"
  - "xArray"
helpviewer_keywords: 
  - "x:Array [XAML Services]"
  - "XAML [XAML Services], x:Array markup extension"
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Array Markup Extension
Bietet allgemeine Unterstützung für Arrays von Objekten in XAML durch eine Markuperweiterung.  Diese Eigenschaft entspricht dem `x:ArrayExtension`\-XAML\-Type in \[MS\-XAML\].  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`typeName`|Der Name des Typs, den das `x:Array` enthält.  `typeName` wird möglicherweise \(und ist oft\) für einen XAML\-Namespace vorangestellt, der die XAML\-Typdefinitionen enthält.|  
|`arrayContents`|Der Elementeinhalt, der der systeminternen `ArrayExtension.Items`\-Eigenschaft zugewiesen wird.  In der Regel werden diese Elemente angegeben wie ein oder mehrere Objektelemente, die innerhalb der `x:Array`\-Starttags und \-Endtags enthalten sind.  Es wird erwartet, dass hier angegebene Objekte dem in `typeName` angegebenen XAML\-Typ zugeordnet werden können.|  
  
## Hinweise  
 `Type` ist ein erforderliches Attribut für alle `x:Array`\-Objektelemente.  Ein `Type`\-Parameterwert muss keine `x:Type`\-Markuperweiterung verwenden. Der Kurzname des Typs ist ein XAML\-Typ, der als Zeichenfolge angegeben werden kann.  
  
 In der Implementierung für .NET Framework\-XAML\-Dienste wird die Beziehung zwischen dem Eingabe\-XAML\-Typ und dem Ausgabe\-CLR <xref:System.Type> des erstellten Arrays durch den Dienstkontext für Markuperweiterungen beeinflusst.  Der Ausgabe\-<xref:System.Type> ist der <xref:System.Xaml.XamlType.UnderlyingType%2A> des Eingabe\-XAML\-Typs, nachdem die erforderlichen <xref:System.Xaml.XamlType> auf Grundlage des XAML\-Schemakontexts und des vom Kontext bereitgestellten <xref:System.Windows.Markup.IXamlTypeResolver>\-Diensts nachgeschlagen wurden.  
  
 Wenn er verarbeitet wird, wird dem Arrayinhalt `ArrayExtension.Items` systeminterne Eigenschaft zugewiesen.  In der <xref:System.Windows.Markup.ArrayExtension>\- Implementierung wird dies durch <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=fullName> dargestellt.  
  
 Bei der Implementierung von .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.Markup.ArrayExtension>\-Klasse definiert.  <xref:System.Windows.Markup.ArrayExtension> ist nicht versiegelt und kann als Basis für eine Markuperweiterung\-Implementierung für einen benutzerdefinierten Arraytyp verwendet werden.  
  
 `x:Array` ist mehr für die allgemeine Spracherweiterbarkeit in XAML bestimmt.  `x:Array` kann jedoch auch nützlich sein, um SAML\-Werte mit bestimmten Eigenschaften anzugeben, die als strukturierten Eigenschafteninhalt XAML\-unterstützte Auflistungen verwenden.  Sie könnten z. B. den Inhalt einer <xref:System.Collections.IEnumerable>\-Eigenschaft mit einer `x:Array`\-Verwendung angeben.  
  
 `x:Array` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  `x:Array` ist teilweise eine Ausnahme von dieser Regel, da `x:Array` keine alternative Attributwertbehandlung bereitstellt, sondern eine alternative Behandlung des inneren Textinhalts.  Dieses Verhalten ermöglicht es, dass Typen, die möglicherweise nicht durch ein vorhandenes Inhaltsmodell unterstützt werden, in ein Array gruppiert werden und später darauf in Code\-Behind verwiesen wird, indem auf das benannte Array zugegriffen wird. Sie können <xref:System.Array>\-Methoden aufrufen, um einzelne Arrayelemente abzurufen.  
  
 Alle Markuperweiterungen in XAML verwenden geschweifte Klammern \({,}`)` in der Attributsyntax. Dies ist die Konvention, durch die ein XAML\-Prozessor erkennt, dass der Attributwert von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen zu Markuperweiterungen finden Sie unter [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 In XAML 2009 wird `x:Array` als Sprachprimitive definiert, und nicht als Markuperweiterung.  Weitere Informationen finden Sie unter [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## Hinweise zur WPF\-Verwendung  
 Normalerweise handelt es sich bei den Objektelementen, die ein `x:Array` auffüllen, nicht um Elemente, die im [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]\-XML\-Namespace vorhanden sind. Außerdem erfordern diese Elemente eine Präfixzuordnung zu einem nicht standardmäßigen XAML\-Namespace.  
  
 Unten folgt z. B. ein einfaches Array mit zwei Zeichenfolgen, wobei das `sys`\-Präfix \(sowie `x`\) auf der Arrayebene definiert wird.  
  
 \[xaml\]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Bei benutzerdefinierten Typen, die als Arrayelemente verwendet werden, muss die Klasse auch die entsprechenden Anforderungen unterstützen, damit sie in XAML als Objektelemente instanziiert werden können.  Weitere Informationen finden Sie unter [XAML\- und benutzerdefinierte Klassen für WPF](../../../ocs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## Siehe auch  
 [Markuperweiterungen und WPF\-XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)