---
title: "x:Null Markup Extension | Microsoft Docs"
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
  - "NullExtension"
  - "x:NullExtension"
  - "x:Null"
  - "Null"
  - "xNull"
helpviewer_keywords: 
  - "Null markup extension in XAML [XAML Services]"
  - "x:Null markup extension [XAML Services]"
  - "XAML [XAML Services], x:Null markup extension"
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Null Markup Extension
Gibt `null` als Wert für einen XAML\-Member an.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{x:Null}" .../>  
```  
  
## Hinweise  
 Das Schlüsselwort für einen NULL\-Verweis in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] ist NULL.  Das [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]\-Schlüsselwort für einen NULL\-Verweis ist `Nothing`, aber Sie verwenden immer `{x:Null}` in XAML, unabhängig davon, welche Code\-Behind\-Sprache dem XAML zugeordnet ist.  
  
 Für die `x:Null`\-Markuperweiterung gibt es keine festlegbaren Eigenschaften.  
  
 Eine NULL\-Verwendung wird häufig der XAML\-Memberbereitstellung eines <xref:System.Nullable%601>\-Werts in CLR zugeordnet.  
  
 Die `x:Null`\-Markuperweiterung verwendet wie alle XAML\-Markuperweiterungen die geschweiften Klammern \(`{,}`\), um Attributwerte mit Escapezeichen zu versehen, damit sie nicht als Literale oder Ereignishandlerverweise behandelt werden.  Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Eine Objektelementsyntax `<x:Null />` ist technisch möglich, wird aber selten verwendet, da die `x:Null`\-Markuperweiterung nicht über eine Positionsparameter oder Konstruktionsargumente verfügt.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 In .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung durch die Klasse <xref:System.Windows.Markup.NullExtension> definiert.  
  
## Hinweise zur WPF\-Verwendung  
 Beachten Sie, dass `null` nicht unbedingt der anfängliche nicht festgelegte Wert einer Verweistyp\-Abhängigkeitseigenschaft ist.  Der ursprüngliche Standardwert kann sich für jede Abhängigkeitseigenschaft ändern und auf eigenschaftenspezifischen Metadaten basieren.  Viele Abhängigkeitseigenschaften akzeptieren `null` nicht als über Markup oder Code festgelegten Wert aufgrund ihrer Validierungsrückrufimplementierung.  Weitere Informationen zu Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../ocs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.DependencyProperty.UnsetValue>   
 [Übersicht über XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)