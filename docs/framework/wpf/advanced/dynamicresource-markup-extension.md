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
ms.openlocfilehash: 5ccda8ba8f41a30e0ce1c832a6d3176b7fb8e8c2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646258"
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource-Markuperweiterung
Stellt einen Wert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für jedes Eigenschaftsattribut bereit, indem dieser Wert als Verweis auf eine definierte Ressource zurückgeschoben wird. Das Nachsuchverhalten für diese Ressource ist analog zur Laufzeitsuche.  
  
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
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde ursprünglich von der [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) zugewiesen, wenn eine `key` Ressource <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> in Markup erstellt wurde, oder als Parameter beim Aufruf angegeben wurde, wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Bemerkungen  
 A `DynamicResource` erstellt während der ersten Kompilierung einen temporären Ausdruck und verschiebt somit die Suche nach Ressourcen, bis der angeforderte Ressourcenwert tatsächlich zum Erstellen eines Objekts erforderlich ist. Dies kann möglicherweise [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Grund sein, nachdem die Seite geladen wurde. Der Ressourcenwert wird basierend auf der Schlüsselsuche für alle aktiven Ressourcenwörterbücher ab dem aktuellen Seitenbereich gefunden und durch den Platzhalterausdruck aus der Kompilierung ersetzt.  
  
> [!IMPORTANT]
> In Bezug auf die `DynamicResource` Priorität der Abhängigkeitseigenschaft entspricht ein Ausdruck der Position, an der der dynamische Ressourcenverweis angewendet wird. Wenn Sie einen lokalen Wert für eine `DynamicResource` Eigenschaft festlegen, die `DynamicResource` zuvor einen Ausdruck als lokalen Wert hatte, wird der vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Bestimmte Ressourcenzugriffsszenarien eignen `DynamicResource` sich im Gegensatz zu einer [StaticResource Markup Extension](staticresource-markup-extension.md)besonders gut. Eine [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) Diskussion über die relativen Vorteile und Leistungsauswirkungen `DynamicResource` `StaticResource`von und .  
  
 Die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> angegebene Ressource sollte einer vorhandenen Ressource entsprechen, die durch die [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) auf einer bestimmten Ebene in Ihrer Seite, Anwendung, den verfügbaren Steuerelementthemen und externen Ressourcen oder Systemressourcen bestimmt wird, und die Ressourcensuche erfolgt in dieser Reihenfolge. Weitere Informationen zur Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Ein Ressourcenschlüssel kann eine beliebige Zeichenfolge sein, die in der [XamlName-Grammatik](../../../desktop-wpf/xaml-services/xamlname-grammar.md)definiert ist. Ein Ressourcenschlüssel kann auch andere Objekttypen <xref:System.Type>sein, z. B. eine . Ein <xref:System.Type> Schlüssel ist von grundlegender Bedeutung, wie Steuerelemente nach Themen gestaltet werden können. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 APIs für die Suche nach <xref:System.Windows.FrameworkElement.FindResource%2A>Ressourcenwerten, z. B. , `DynamicResource`folgen der gleichen Ressourcensuchlogik wie von .  
  
 Die alternative deklarative Möglichkeit, auf eine Ressource zu verweisen, ist als [StaticResource Markup Extension](staticresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `DynamicResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.DynamicResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `DynamicResource`kann in der Objektelementsyntax verwendet werden. In diesem Fall ist die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> Angabe des Werts der Eigenschaft erforderlich.  
  
 `DynamicResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `DynamicResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Prozessorimplementierung wird die Verarbeitung für diese <xref:System.Windows.DynamicResourceExtension> Markuperweiterung durch die Klasse definiert.  
  
 `DynamicResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ressourcen und Code](resources-and-code.md)
- [x:Key-Anweisung](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [StaticResource-Markuperweiterung](staticresource-markup-extension.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
