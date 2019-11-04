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
ms.openlocfilehash: a04e1569f77fed73a480fda3d63cabf6dbc30664
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460511"
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource-Markuperweiterung
Stellt einen Wert für ein beliebiges [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschafts Attribut bereit, indem dieser Wert als Verweis auf eine definierte Ressource festgelegt wird. Das Suchverhalten für diese Ressource entspricht der Lauf Zeit Suche.  
  
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
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde anfänglich durch die [x:Key-Direktive](../../xaml-services/x-key-directive.md) zugewiesen, wenn eine Ressource im Markup erstellt wurde, oder wurde beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> als `key` Parameter bereitgestellt, wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `DynamicResource` erstellt während der anfänglichen Kompilierung einen temporären Ausdruck und verzögert die Suche nach Ressourcen so lange, bis der angeforderte Ressourcen Wert tatsächlich benötigt wird, um ein Objekt zu erstellen. Dies kann möglicherweise darauf liegen, dass die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite geladen wurde. Der Ressourcen Wert wird basierend auf der Schlüsselsuche nach allen aktiven Ressourcen Wörterbüchern gefunden, beginnend ab dem aktuellen Seitenbereich, und wird durch den Platzhalter Ausdruck aus der Kompilierung ersetzt.  
  
> [!IMPORTANT]
> Im Hinblick auf die Rangfolge der Abhängigkeits Eigenschaften entspricht ein `DynamicResource` Ausdruck der Position, an der der dynamische Ressourcen Verweis angewendet wird. Wenn Sie einen lokalen Wert für eine Eigenschaft festgelegt haben, für die zuvor ein `DynamicResource` Ausdruck als lokaler Wert festgelegt wurde, wird der `DynamicResource` vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Bestimmte Ressourcen Zugriffs Szenarien eignen sich besonders für `DynamicResource` im Gegensatz zu einer [statikresource-Markup Erweiterung](staticresource-markup-extension.md). In den [XAML-Ressourcen](xaml-resources.md) finden Sie eine Erläuterung zu den relativen Vorteilen und Leistungs Auswirkungen von `DynamicResource` und `StaticResource`.  
  
 Der angegebene <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> sollte einer vorhandenen Ressource entsprechen, die von der [x:Key-Direktive](../../xaml-services/x-key-directive.md) auf einer bestimmten Ebene auf der Seite, Anwendung, den verfügbaren Steuerelement Designs und externen Ressourcen oder Systemressourcen bestimmt wird, und die Ressourcen Suche erfolgt in Diese Reihenfolge. Weitere Informationen zur Ressourcen Suche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources.md).  
  
 Ein Ressourcen Schlüssel kann eine beliebige Zeichenfolge sein, die in der [XamlName-Grammatik](../../xaml-services/xamlname-grammar.md)definiert ist. Ein Ressourcen Schlüssel kann auch andere Objekttypen sein, z. b. ein <xref:System.Type>. Ein <xref:System.Type> Schlüssel ist grundlegend für die Formatierung von Steuerelementen. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 APIs für die Suche nach Ressourcen Werten, wie z. b. <xref:System.Windows.FrameworkElement.FindResource%2A>, folgen derselben Ressourcen Suchlogik, die von `DynamicResource`verwendet wird.  
  
 Die alternative deklarative Möglichkeit, auf eine Ressource zu verweisen, ist als [statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `DynamicResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.DynamicResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `DynamicResource` können in der Objekt Element Syntax verwendet werden. In diesem Fall muss der Wert der <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Eigenschaft angegeben werden.  
  
 `DynamicResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `DynamicResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der Implementierung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessors wird die Behandlung dieser Markup Erweiterung durch die <xref:System.Windows.DynamicResourceExtension>-Klasse definiert.  
  
 `DynamicResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](xaml-resources.md)
- [Ressourcen und Code](resources-and-code.md)
- [x:Key-Anweisung](../../xaml-services/x-key-directive.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [StaticResource-Markuperweiterung](staticresource-markup-extension.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
