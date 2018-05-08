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
ms.openlocfilehash: 518a85c158c9a4472689d3c236b84278114cf3ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="staticresource-markup-extension"></a>StaticResource-Markuperweiterung
Stellt einen Wert für eine beliebige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschaftsattribut, das durch einen Verweis auf eine bereits definierte Ressource nachschlagen. Suchverhalten für diese Ressource ist analog zur Ladezeit Suche, bei der nach Ressourcen gesucht werden, die zuvor aus dem Markup des aktuellen geladen wurden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sowie andere Quellen für die Anwendung, und generiert dieses Ressourcenwert als der der Eigenschaftswert in der Laufzeit-Objekten.  
  
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
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde ursprünglich zugewiesen, durch die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) Wenn eine Ressource, die im Markup erstellt wurde, oder als bereitgestellt wurde die `key` -Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> , wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Ein `StaticResource` auf keinen Fall einen Vorwärtsverweis auf eine Ressource, die definiert wird, stellen lexikalisch weiter innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei. Versuch wird nicht unterstützt, und auch wenn Sie ein solchen Verweis nicht fehlschlägt, versucht, den vorwärts gerichteten Verweis entstehen durch eine Ladezeit zu Leistungseinbußen bei der internen Hashtabellen darstellt eine <xref:System.Windows.ResourceDictionary> durchsucht werden. Passen Sie für optimale Ergebnisse die Zusammensetzung der Ressourcenwörterbücher so, dass Vorwärtsverweisen vermieden werden können. Wenn Sie einen Vorwärtsverweis nicht vermeiden können, verwenden Sie [DynamicResource Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) stattdessen.  
  
 Das angegebene <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> sollte entsprechen, eine vorhandene Ressource, die mit identifiziert eine [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) auf einer bestimmten Ebene in der Seite, Anwendung, die verfügbare Steuerelementdesigns und externe Ressourcen oder Systemressourcen verfügbar sind. Die Ressourcensuche wird in dieser Reihenfolge. Weitere Informationen zum Verhalten bei der Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Ein Ressourcenschlüssel kann eine beliebige Zeichenfolge, die definiert, der [XamlName-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md). Ein Ressourcenschlüssel kann auch andere Objekttypen, z. B. eine <xref:System.Type>. Ein <xref:System.Type> Schlüssel ist grundlegend, wie Steuerelemente mithilfe von Designs über einen impliziten Schlüssel formatiert werden können. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Die alternative deklaratives Mittel für verweisen auf eine Ressource wird als eine [DynamicResource Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `StaticResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.StaticResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `StaticResource` kann in der Syntax der Object-Element verwendet werden. In diesem Fall geben Sie den Wert der <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> ist eine erforderliche Eigenschaft.  
  
 `StaticResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `StaticResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.StaticResourceExtension> Klasse.  
  
 `StaticResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Ressourcen und Code](../../../../docs/framework/wpf/advanced/resources-and-code.md)
