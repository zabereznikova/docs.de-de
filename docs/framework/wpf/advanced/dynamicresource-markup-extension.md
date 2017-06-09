---
title: "DynamicResource-Markuperweiterung | Microsoft Docs"
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
  - "DynamicResource"
  - "DynamicResourceExtension"
helpviewer_keywords: 
  - "DynamicResource-Markuperweiterungen"
  - "XAML, DynamicResource-Markuperweiterung"
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# DynamicResource-Markuperweiterung
Stellt einen Wert für ein beliebiges [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Eigenschaftenattribut bereit, indem dieser Wert als Verweis für eine definierte Ressource festgelegt wird.  Das Suchverhalten für diese Ressource ist analog zur Suche während der Laufzeit.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{DynamicResource key}" .../>  
```  
  
## Verwendung von XAML\-Eigenschaftenelementen  
  
```  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`key`|Der Schlüssel für die angeforderte Ressource.  Dieser Schlüssel wurde ursprünglich vom [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) zugewiesen, falls im Markup eine Ressource erstellt wurde, oder er wurde als `key`\-Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName> bereitgestellt, wenn die Ressource im Code erstellt wurde.|  
  
## Hinweise  
 Eine `DynamicResource` erstellt während der erstmaligen Kompilierung einen temporären Ausdruck und schiebt daher die Suche nach Ressourcen auf, bis der angeforderte Ressourcenwert tatsächlich erforderlich ist, um ein Objekt zu erstellen.  Dies kann zum Beispiel erfolgen, nachdem die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Seite geladen wurde.  Der Ressourcenwert wird basierend auf einer Schlüsselsuche in allen aktiven Ressourcenwörterbüchern gefunden. Dabei wird mit dem aktuellen Seitenumfang begonnen, und der Ressourcenwert wird dann gegen den Platzhalterausdruck der Kompilierung ausgetauscht.  
  
> [!IMPORTANT]
>  Hinsichtlich des Vorrangs einer Abhängigkeitseigenschaft entspricht ein `DynamicResource`\-Ausdruck der Position, an der der Verweis auf die dynamische Ressource angewendet wird.  Wenn Sie einen lokalen Wert für eine Eigenschaft festlegen, die vorher als lokalen Wert einen `DynamicResource`\-Ausdruck aufwies, wird `DynamicResource` vollständig entfernt.  Ausführliche Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Bestimmte Ressourcenzugriffsszenarios eignen sich besonders für `DynamicResource`, im Gegensatz zu [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Informationen zu den relativen Vorteilen und Leistungsaspekten von `DynamicResource` und `StaticResource` finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Der angegebene <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> sollte einer vorhandenen Ressource entsprechen, die mithilfe von [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) auf einer Ebene der Seite, der Anwendung, der verfügbaren Steuerelementdesigns oder der externen Ressourcen bzw. Systemressourcen festgelegt wird. Die Ressourcensuche wird in dieser Reihenfolge durchgeführt.  Weitere Informationen zur Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ein Ressourcenschlüssel kann eine beliebige Zeichenfolge sein, die in der [XamlName\-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md) definiert ist.  Bei einem Ressourcenschlüssel kann es sich auch um andere Objekttypen handeln, z. B. einen <xref:System.Type>.  Ein <xref:System.Type>\-Schlüssel ist von wesentlicher Bedeutung dafür, wie Steuerelemente mithilfe von Designs formatiert werden können.  Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Bei [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zum Suchen nach Ressourcenwerten, z. B. <xref:System.Windows.FrameworkElement.FindResource%2A>, wird dieselbe Logik für Ressourcensuchen wie bei `DynamicResource` verwendet.  
  
 Die alternative Deklarationsmöglichkeit zum Verweisen auf eine Ressource ist eine [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Das Zeichenfolgentoken, das auf die `DynamicResource`\-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>\-Wert der zugrunde liegenden <xref:System.Windows.DynamicResourceExtension>\-Erweiterungsklasse zugeordnet.  
  
 `DynamicResource` kann in der Objektelementsyntax verwendet werden.  In diesem Fall muss der Wert für die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>\-Eigenschaft angegeben werden.  
  
 `DynamicResource` kann zudem in einer ausführlichen Attributverwendung genutzt werden, die die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>\-Eigenschaft als Eigenschaft\-Wert\-Paar angibt:  
  
```  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.  Da für `DynamicResource` nur eine Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessorimplementierung wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.DynamicResourceExtension>\-Klasse definiert.  
  
 `DynamicResource` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden die Zeichen { und } in der Attributsyntax. Dies ist die Konvention, anhand der ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)   
 [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)