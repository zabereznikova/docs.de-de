---
title: "StaticResource-Markuperweiterung | Microsoft Docs"
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
  - "StaticResource"
  - "StaticResourceExtension"
helpviewer_keywords: 
  - "StaticResource-Markuperweiterungen"
  - "XAML, StaticResource-Markuperweiterung"
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# StaticResource-Markuperweiterung
Stellt einen Wert für ein beliebiges [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Eigenschaftenattribut bereit, indem nach einem Verweis auf eine bereits definierte Ressource gesucht wird.  Das Suchverhalten für diese Ressource ist analog zur Suche während der Ladezeit, bei der nach Ressourcen gesucht wird, die vorher aus dem Markup der aktuellen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite und aus anderen Anwendungsquellen geladen wurden. Der Ressourcenwert wird als Eigenschaftswert in den Laufzeitobjekten generiert.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{StaticResource key}" .../>  
```  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`key`|Der Schlüssel für die angeforderte Ressource.  Dieser Schlüssel wurde ursprünglich vom [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) zugewiesen, falls im Markup eine Ressource erstellt wurde, oder er wurde als `key`\-Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName> bereitgestellt, wenn die Ressource im Code erstellt wurde.|  
  
## Hinweise  
  
> [!IMPORTANT]
>  Eine `StaticResource` darf nicht versuchen, einen Vorwärtsverweis auf eine Ressource einzurichten, die lexikalisch weiter innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei definiert ist.  Derartige Versuche werden nicht unterstützt, und auch wenn ein Verweis dieser Art nicht fehlschlägt, führen versuchte Vorwärtsverweise zur Ladezeit zu Leistungseinbußen, wenn die internen Hashtabellen durchsucht werden, die ein <xref:System.Windows.ResourceDictionary> darstellen.  Um die besten Ergebnisse zu erzielen, passen Sie die Zusammensetzung der Ressourcenwörterbücher so an, dass Vorwärtsverweise verhindert werden können.  Wenn Sie einen Vorwärtsverweis nicht vermeiden können, verwenden Sie stattdessen [DynamicResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 Der angegebene <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> sollte einer vorhandenen Ressource entsprechen, die auf einer Ebene der Seite, der Anwendung, der verfügbaren Steuerelementdesigns und externen Ressourcen oder der Systemressourcen durch ein [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) identifiziert wird.  Die Ressourcensuche wird in dieser Reihenfolge durchgeführt.  Weitere Informationen zum Verhalten bei der Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Bei einem Ressourcenschlüssel kann es sich um eine beliebige Zeichenfolge handeln, die unter [XamlName\-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md) definiert ist.  Bei einem Ressourcenschlüssel kann es sich auch um andere Objekttypen handeln, zum Beispiel einen <xref:System.Type>.  Ein <xref:System.Type>\-Schlüssel ist von wesentlicher Bedeutung dafür, wie Steuerelemente mithilfe von Designs und eines impliziten Designschlüssels formatiert werden können.  Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Die alternative Deklarationsmöglichkeit zum Verweisen auf eine Ressource ist eine [DynamicResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Das Zeichenfolgentoken, das auf die `StaticResource`\-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>\-Wert der zugrunde liegenden <xref:System.Windows.StaticResourceExtension>\-Erweiterungsklasse zugeordnet.  
  
 `StaticResource` kann in der Objektelementsyntax verwendet werden.  In diesem Fall muss der Wert für die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>\-Eigenschaft angegeben werden.  
  
 `StaticResource` kann zudem in einer ausführlichen Attributverwendung genutzt werden, die die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>\-Eigenschaft als Eigenschaft\/Wert\-Paar angibt:  
  
```  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.  Da für `StaticResource` nur eine \(erforderliche\) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessorimplementierung wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.StaticResourceExtension>\-Klasse definiert.  
  
 `StaticResource` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden die Zeichen { und } in der Attributsyntax. Dies ist die Konvention, anhand der ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)