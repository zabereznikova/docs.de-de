---
title: DynamicResource-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 579fae46a7c53a61b728d7526ef397eb371abb74
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141067"
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource-Markuperweiterung
Stellt einen Wert für jedes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschafts Attribut bereit, indem dieser Wert als Verweis auf eine definierte Ressource zurückgenommen wird. Das Suchverhalten für diese Ressource entspricht der Lauf Zeit Suche.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{DynamicResource key}" ... />  
```  
  
## <a name="xaml-property-element-usage"></a>Verwendung von XAML-Eigenschaftenelementen  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" ... />  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde anfänglich durch die [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) zugewiesen, wenn eine Ressource im Markup erstellt wurde, oder `key` wurde beim Aufrufen <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> von als Parameter bereitgestellt, wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein `DynamicResource` erstellt während der anfänglichen Kompilierung einen temporären Ausdruck und verzögert die Suche nach Ressourcen so lange, bis der angeforderte Ressourcen Wert tatsächlich erforderlich ist, um ein Objekt zu erstellen. Dies kann potenziell sein, nachdem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die Seite geladen wurde. Der Ressourcen Wert wird basierend auf der Schlüsselsuche nach allen aktiven Ressourcen Wörterbüchern gefunden, beginnend ab dem aktuellen Seitenbereich, und wird durch den Platzhalter Ausdruck aus der Kompilierung ersetzt.  
  
> [!IMPORTANT]
> Im Hinblick auf die Rangfolge der Abhängigkeits Eigenschaften entspricht ein `DynamicResource` -Ausdruck der Position, an der der dynamische Ressourcen Verweis angewendet wird. Wenn Sie einen lokalen Wert für eine Eigenschaft festlegen, die zuvor einen `DynamicResource` -Ausdruck als lokalen Wert enthielt, `DynamicResource` wird der vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Bestimmte Szenarien für den Ressourcen Zugriff sind besonders `DynamicResource` geeignet für anstelle einer [statikresource-Markup Erweiterung](staticresource-markup-extension.md). In den [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md) finden Sie eine Erläuterung zu den relativen Vorteilen und `DynamicResource` Leistungs `StaticResource`Auswirkungen von und.  
  
 Der angegebene <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> sollte einer vorhandenen Ressource entsprechen, die von der [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) auf einer bestimmten Ebene auf der Seite, Anwendung, den verfügbaren Steuerelementen und externen Ressourcen oder Systemressourcen bestimmt wird, und die Ressourcen Suche erfolgt in dieser Reihenfolge. Weitere Informationen zur Ressourcen Suche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Ein Ressourcen Schlüssel kann eine beliebige Zeichenfolge sein, die in der [XamlName-Grammatik](../../../desktop-wpf/xaml-services/xamlname-grammar.md)definiert ist. Ein Ressourcen Schlüssel kann auch andere Objekttypen sein, z <xref:System.Type>. b.. Ein <xref:System.Type> Schlüssel ist grundlegend für die Formatierung von Steuerelementen. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 APIs für die Suche nach Ressourcen Werten, wie z <xref:System.Windows.FrameworkElement.FindResource%2A>. b., folgen derselben Ressourcen Suchlogik, die `DynamicResource`von verwendet wird.  
  
 Die alternative deklarative Möglichkeit, auf eine Ressource zu verweisen, ist als [statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `DynamicResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.DynamicResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `DynamicResource`kann in der Objekt Element Syntax verwendet werden. In diesem Fall ist die Angabe des Werts der <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> -Eigenschaft erforderlich.  
  
 `DynamicResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" ... />  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `DynamicResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.DynamicResourceExtension> -Klasse definiert.  
  
 `DynamicResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ressourcen und Code](resources-and-code.md)
- [x:Key-Anweisung](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [StaticResource-Markuperweiterung](staticresource-markup-extension.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
