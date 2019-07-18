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
ms.openlocfilehash: 90768a0c816e790138ba60bd24afee242e41e652
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860289"
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource-Markuperweiterung
Gibt einen Wert für alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschaftsattribut, das von bereit, um einen Verweis auf eine Ressource definiert werden. Das Suchverhalten für diese Ressource ist analog zur Laufzeit-Suche.  
  
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
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde ursprünglich zugewiesen, durch die [X: Key Directive](../../xaml-services/x-key-directive.md) , wenn eine Ressource, die im Markup erstellt wurde, oder es bereitgestellt wurde die `key` -Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> , wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `DynamicResource` erstellt während der erstmaligen Kompilierung einen temporären Ausdruck und Suche nach Ressourcen daher verzögert, bis der Wert für die angeforderte Ressource tatsächlich erforderlich ist, um ein Objekt zu erstellen ist. Dies kann potenziell sein, nach der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite wird geladen. Der Ressourcenwert basierend auf wichtige Suche für alle aktiven Ressourcenwörterbüchern aus dem aktuellen Seitenbereich befindet und für den Platzhalterausdruck aus der Kompilierung ersetzt wird.  
  
> [!IMPORTANT]
>  Im Hinblick auf haben Abhängigkeitseigenschaften eine `DynamicResource` Ausdruck ist identisch mit die Position der dynamischen Ressourcenverweis wird angewendet. Wenn Sie einen lokalen Wert einer Eigenschaft festlegen, die bisher ein `DynamicResource` Ausdruck als lokalen Wert, der `DynamicResource` vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Bestimmte eignen sich besonders für `DynamicResource` im Gegensatz zu einem [StaticResource-Markuperweiterung](staticresource-markup-extension.md). Finden Sie unter [XAML-Ressourcen](xaml-resources.md) für eine Diskussion über die Vorteile und die Auswirkungen auf die Leistung der `DynamicResource` und `StaticResource`.  
  
 Das angegebene <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> sollte entsprechen, eine vorhandene Ressource bestimmt, indem die [X: Key Directive](../../xaml-services/x-key-directive.md) auf einer bestimmten Ebene in Ihrer Seite, Anwendung, die verfügbaren Steuerelementdesigns und externe Ressourcen oder Systemressourcen, und die die Ressourcensuche wird in dieser Reihenfolge ausgeführt. Weitere Informationen zur Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources.md).  
  
 Ein Ressourcenschlüssel möglicherweise eine beliebige Zeichenfolge, die definiert, der [XamlName-Grammatik](../../xaml-services/xamlname-grammar.md). Ein Ressourcenschlüssel möglicherweise auch andere Objekttypen, z. B. eine <xref:System.Type>. Ein <xref:System.Type> Schlüssel ist wesentlich, wie Steuerelemente mithilfe von Designs formatiert werden können. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 APIs für die Suche nach Ressourcen-Werte, z. B. <xref:System.Windows.FrameworkElement.FindResource%2A>, befolgen Sie die Suchlogik der gleichen Ressource vom verwendete `DynamicResource`.  
  
 Die alternative deklaratives Mittel für die verweisen auf eine Ressource ist als eine [StaticResource-Markuperweiterung](staticresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `DynamicResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.DynamicResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `DynamicResource` kann in Objektelementsyntax verwendet werden. In diesem Fall geben Sie den Wert der <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> Eigenschaft ist erforderlich.  
  
 `DynamicResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `DynamicResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung wird die Handhabung dieser Markuperweiterung wird definiert, indem die <xref:System.Windows.DynamicResourceExtension> Klasse.  
  
 `DynamicResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](xaml-resources.md)
- [Ressourcen und Code](resources-and-code.md)
- [x:Key-Anweisung](../../xaml-services/x-key-directive.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [StaticResource-Markuperweiterung](staticresource-markup-extension.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
