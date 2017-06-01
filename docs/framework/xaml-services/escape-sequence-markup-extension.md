---
title: "{} Escape Sequence / Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "{}"
helpviewer_keywords: 
  - "XAML [XAML Services], quotation mark (")"
  - "{} escape sequence [XAML Services]"
  - "XAML [XAML Services], {} escape sequence"
  - "XAML [XAML Services], escape sequence"
  - "quotation mark (") [XAML Services]"
  - "escape sequence [XAML Services]"
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: 21
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
---
# {} Escape Sequence / Markup Extension
Stellt die XAML\-Escapesequenz für Attributwerte bereit.  Durch die Escapesequenz können die nachfolgenden Werte im Attribut als Literal interpretiert werden.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{} literalValue" .../>  
```  
  
## Verwendung von XAML\-Eigenschaftenelementen  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|**literalValue**|Das Zeichenfolgenliteral, das der Escapesequenz folgt.  In der Regel enthält diese Zeichenfolge eine öffnende oder schließende Klammer \({ oder }\).|  
  
## Hinweise  
 Die Escapesequenz \({}\) wird verwendet, damit ein öffnende geschweifte Klammer \({\) Literalzeichen in XAML verwendet werden kann.  
  
 XAML\-Reader verwenden in der Regel die öffnende geschweifte Klammer \({\), um den Einstiegspunkt einer Markuperweiterung anzugeben. Sie überprüfen jedoch zuerst das nächste Zeichen, um zu bestimmen, ob es eine schließende geschweifte Klammer \(}\) ist.  Nur wenn die beiden geschweiften Klammern \({}\) aufeinander folgen, werden sie als Escapesequenz betrachtet.  
  
 Wenn die Escape\-Sequenz gefunden wird, sollte der XAML\-Reader die restliche Zeichenfolge als Zeichenfolge verarbeiten.  Wenn jedoch die Escapesequenz für einen Member übernommen wird, der über einen Typkonverter verfügt, ist es möglich, dass die Zeichenfolge die Typkonvertierung durchläuft, wenn sie von einem XAML\-Writer interpretiert wird.  
  
 Die Escapesequenz ist keine Markuperweiterung und wird nicht von einer Klasse unterstützt.  Dies ist jedoch eine Konvention, die XAML\-Reader \(einschließlich benutzerdefinierter XAML\-Reader\) beachten müssen.  
  
 Ein Anführungszeichen \("\) kann nicht als Escapesequenz auf diese Weise verwendet werden.  Wenn Sie ein Anführungszeichen als Eigenschaftswert für eine Nicht\-Inhaltseigenschaft festlegen müssen, verwenden Sie die Syntax des Eigenschaftenelements und platzieren das Anführungszeichen als Zeichenfolge innerhalb des Eigenschaftenelements oder verwenden eine XML\-Zeichenentität.  Bei einer Inhaltseigenschaft kann das Anführungszeichen der ganze Inhalt sein.  
  
 Die Escapesequenz \({}\) ist oft erforderlich, wenn Sie an einer Position, an der XAML\-Markuperweiterungen auftreten können, einen XML\-Typ angeben, der einen Namespacequalifizierer beinhalten muss.  Dies umfasst auch den Anfang eines XAML\-Attributwerts und wird in einer Markuperweiterung sofort nach einem Gleichheitszeichen \(\=\) eingefügt.  Das folgende Beispiel zeigt Escapesequenzen für einen XML\-Namespace am Anfang eines XAML\-Attributwerts.  
  
 [!code-xml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## Siehe auch  
 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)   
 [XML Character Entities and XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)