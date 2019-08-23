---
title: StaticResource-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 7392be182aedeeebe6b7092f9868c1fabfaafcb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963463"
---
# <a name="staticresource-markup-extension"></a>StaticResource-Markuperweiterung
Stellt einen Wert für ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beliebiges Eigenschafts Attribut bereit, indem ein Verweis auf eine bereits definierte Ressource gesucht wird. Das Suchverhalten für diese Ressource entspricht der Lade Zeit Suche, bei der nach Ressourcen gesucht wird, die zuvor aus dem Markup der aktuellen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Seite sowie aus anderen Anwendungs Quellen geladen wurden, und generiert den Ressourcen Wert als Eigenschafts Wert in den Lauf Zeit Objekten.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde anfänglich durch die [x:Key-Direktive](../../xaml-services/x-key-directive.md) zugewiesen, wenn eine Ressource im Markup erstellt wurde, oder `key` wurde beim Aufrufen <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> von als Parameter bereitgestellt, wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
> Ein `StaticResource` darf nicht versuchen, einen vorwärts Verweis auf eine Ressource zu erstellen, die lexikalisch weiter unten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Datei definiert ist. Der Versuch, dies zu tun, wird nicht unterstützt, und auch wenn ein solcher Verweis nicht fehlschlägt, wird beim Versuch, den vorwärts Verweis zu verwenden, eine Leistungs Einbuße <xref:System.Windows.ResourceDictionary> bei der Ladezeit verursacht, wenn die internen Hash Tabellen, die eine darstellen Um optimale Ergebnisse zu erzielen, passen Sie die Komposition ihrer Ressourcen Wörterbücher so an, dass vorwärts Verweise vermieden werden können. Wenn Sie keinen vorwärts Verweis vermeiden können, verwenden Sie stattdessen die [dynamikresource-Markup Erweiterung](dynamicresource-markup-extension.md) .  
  
 Der angegebene <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> sollte einer vorhandenen Ressource entsprechen, die mit einer [x:Key-Direktive](../../xaml-services/x-key-directive.md) auf einer bestimmten Ebene auf der Seite, Anwendung, den verfügbaren Steuerelementen und externen Ressourcen oder Systemressourcen identifiziert wird. Die Ressourcen Suche erfolgt in dieser Reihenfolge. Weitere Informationen zum Verhalten der Ressourcen Suche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources.md).  
  
 Ein Ressourcen Schlüssel kann eine beliebige Zeichenfolge sein, die in der [XamlName-Grammatik](../../xaml-services/xamlname-grammar.md)definiert ist. Ein Ressourcen Schlüssel kann auch andere Objekttypen sein, z <xref:System.Type>. b. Ein <xref:System.Type> Schlüssel ist von grundlegender Bedeutung für das Formatieren von Steuerelementen mithilfe eines impliziten Stil Schlüssels. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 Die alternative deklarative Methode zum Verweisen auf eine Ressource ist eine [dynamikresource-Markup Erweiterung](dynamicresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `StaticResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.StaticResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `StaticResource`kann in der Objekt Element Syntax verwendet werden. In diesem Fall ist die Angabe des Werts <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> der-Eigenschaft erforderlich.  
  
 `StaticResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `StaticResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.StaticResourceExtension> -Klasse definiert.  
  
 `StaticResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [XAML-Ressourcen](xaml-resources.md)
- [Ressourcen und Code](resources-and-code.md)
