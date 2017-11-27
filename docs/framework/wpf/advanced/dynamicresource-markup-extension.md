---
title: DynamicResource-Markuperweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c80d975e756fab449c254b9e1d8d1bc99a25652e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource-Markuperweiterung
Stellt einen Wert für eine beliebige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Property-Attribut von bereit, um einen Verweis auf eine Ressource definiert werden. Suchverhalten für diese Ressource ist analog zur Laufzeit-Suche.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>Verwendung von XAML-Eigenschaftenelementen  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde ursprünglich zugewiesen, durch die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) Wenn eine Ressource, die im Markup erstellt wurde, oder als bereitgestellt wurde die `key` -Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> , wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `DynamicResource` erstellt einen temporären Ausdruck bei der ersten Kompilierung und somit Suche nach Ressourcen verzögern, bis der Wert für die angeforderte Ressource tatsächlich erforderlich, um ein Objekt zu erstellen ist. Dies kann möglicherweise nach der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite wird geladen. Der Ressourcenwert wird basierend auf für alle aktiven Ressourcenverzeichnis, beginnend mit der aktuellen Seitenbereich gefunden werden und für den Platzhalterausdruck von der Kompilierung ersetzt wird.  
  
> [!IMPORTANT]
>  Im Hinblick auf Vorrangs einer Abhängigkeitseigenschaft eine `DynamicResource` Ausdruck entspricht der Position der dynamischen Ressourcenverweis wird angewendet. Wenn Sie einen lokalen Wert für eine Eigenschaft festlegen, die zuvor bereits profitierten eine `DynamicResource` Ausdruck als den lokalen Wert der `DynamicResource` wird vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Bestimmte Szenarien der Ressource eignen sich besonders für `DynamicResource` im Gegensatz zu einer [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). Finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) Nähere Informationen über die relativen Vorteile und Leistungseinbußen bei der `DynamicResource` und `StaticResource`.  
  
 Das angegebene <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> sollte entsprechen, eine vorhandene Ressource bestimmt, indem die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) auf einer bestimmten Ebene in der Seite, Anwendung, die verfügbare Steuerelementdesigns und externe Ressourcen oder Systemressourcen, und die der Ressourcensuche erfolgt in dieser Reihenfolge. Weitere Informationen zur Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ein Ressourcenschlüssel möglicherweise auf eine beliebige Zeichenfolge, die definiert, der [XamlName-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md). Ein Ressourcenschlüssel möglicherweise auch andere Objekttypen, z. B. eine <xref:System.Type>. Ein <xref:System.Type> Schlüssel ist grundlegend, wie Steuerelemente mithilfe von Designs formatiert werden können. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]für die Suche nach Ressourcenwerten z. B. <xref:System.Windows.FrameworkElement.FindResource%2A>, befolgen Sie die gleiche Logik Ressourcensuche vom verwendete `DynamicResource`.  
  
 Die alternative deklaratives Mittel für verweisen auf eine Ressource wird als eine [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `DynamicResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.DynamicResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `DynamicResource`kann in der Syntax der Object-Element verwendet werden. In diesem Fall geben Sie den Wert der <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> ist eine erforderliche Eigenschaft.  
  
 `DynamicResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `DynamicResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.DynamicResourceExtension> Klasse.  
  
 `DynamicResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [x:Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
