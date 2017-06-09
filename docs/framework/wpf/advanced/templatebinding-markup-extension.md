---
title: "TemplateBinding-Markuperweiterung | Microsoft Docs"
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
  - "TemplateBinding"
  - "TemplateBindingExtension"
helpviewer_keywords: 
  - "TemplateBinding-Markuperweiterungen"
  - "XAML, TemplateBinding-Markuperweiterung"
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# TemplateBinding-Markuperweiterung
Verknüpft den Wert einer Eigenschaft in einer Steuerelementvorlage so, dass er der Wert einer anderen Eigenschaft des Steuerelements mit Vorlagen ist.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## Verwendung von XAML\-Attributen \(für Setter\-Eigenschaft in Vorlage oder Stil\)  
  
```  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=fullName> der Eigenschaft, der in der Setter\-Syntax festgelegt wird.|  
|`sourceProperty`|Eine weitere Abhängigkeitseigenschaft für den auf Vorlagen basierenden Typ, die durch ihren <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=fullName> angegeben wird.<br /><br /> – oder –<br /><br /> Ein Eigenschaftenname in Punktnotation, der durch einen anderen Typ als den auf Vorlagen basierenden Zieltyp definiert wird.  Hierbei handelt es sich eigentlich um einen <xref:System.Windows.PropertyPath>.  Siehe [XAML\-Syntax von PropertyPath](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## Hinweise  
 Eine `TemplateBinding` ist die optimierte Form einer [Bindung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) für Vorlagenszenarios, die einer mit `{Binding RelativeSource={RelativeSource TemplatedParent}}` erstellten `Binding` entspricht.  Eine `TemplateBinding` ist immer eine unidirektionale Bindung, auch wenn die betroffenen Eigenschaften standardmäßig bidirektionale Bindungen sind.  Beide betroffenen Eigenschaften müssen Abhängigkeitseigenschaften sein.  
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) ist eine weitere Markuperweiterung, die gelegentlich in Verbindung mit oder anstelle von `TemplateBinding` verwendet wird, um eine relative Eigenschaftenbindung in einer Vorlage auszuführen.  
  
 Die Beschreibung des Konzepts von Steuerelementvorlagen wird in diesem Thema nicht behandelt. Weitere Informationen finden Sie unter [Steuerelementformate und \-vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Das Zeichenfolgentoken, das auf die `TemplateBinding`\-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.TemplateBindingExtension.Property%2A>\-Wert der zugrunde liegenden <xref:System.Windows.TemplateBindingExtension>\-Erweiterungsklasse zugeordnet.  
  
 Die Objektelementsyntax ist zwar möglich, wird jedoch nicht gezeigt, da sie keine realistische Anwendung hat.  `TemplateBinding` wird verwendet, um Werte mithilfe von ausgewerteten Ausdrücken innerhalb von Settern zu füllen. Die Verwendung der Objektelementsyntax für `TemplateBinding` zum Füllen der `<Setter.Property>`\-Eigenschaftenelementsyntax ist unnötig ausführlich.  
  
 `TemplateBinding` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.TemplateBindingExtension.Property%2A>\-Eigenschaft als Eigenschaft\=Wert\-Paar angibt:  
  
```  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.  Da für `TemplateBinding` nur eine \(erforderliche\) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-XAML\-Prozessorimplementierung wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.TemplateBindingExtension>\-Klasse definiert.  
  
 `TemplateBinding` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in XAML verwenden die Zeichen `{` und `}` in der Attributsyntax. Dies ist die Konvention, durch die ein XAML\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [RelativeSource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)   
 [Bindung als Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)