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
ms.openlocfilehash: 8319e451268152e95326c02027157db72df631b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125145"
---
# <a name="staticresource-markup-extension"></a>StaticResource-Markuperweiterung
Gibt einen Wert für alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschaftsattribut, das durch einen Verweis auf einen bereits definierten Ressource überprüfen. Das Suchverhalten für diese Ressource ist analog zur Ladezeit-Suche, der nach Ressourcen gesucht werden, die zuvor aus dem Markup des aktuellen geladen wurden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sowie andere Anwendungsquellen, und diesen Ressourcenwert generiert die der Eigenschaftswert in den Laufzeit-Objekten.  
  
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
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde ursprünglich zugewiesen, durch die [X: Key Directive](../../xaml-services/x-key-directive.md) , wenn eine Ressource, die im Markup erstellt wurde, oder es bereitgestellt wurde die `key` -Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> , wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Ein `StaticResource` dürfen nicht versuchen, einen Vorwärtsverweis auf eine Ressource, die definiert wird, stellen lexikalisch weiter innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei. Dies dennoch versuchen, wird nicht unterstützt, und auch wenn Sie ein solchen Verweis nicht fehlschlägt, versucht, den vorwärts gerichteten Verweis fallen eine Ladezeit zu Leistungseinbußen bei der internen Hashtabellen darstellt eine <xref:System.Windows.ResourceDictionary> durchsucht werden. Passen Sie für optimale Ergebnisse die Zusammensetzung der Ressourcenwörterbücher, Vorwärtsverweise vermieden werden können. Wenn Sie einen Vorwärtsverweis nicht vermeiden können, verwenden Sie [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md) stattdessen.  
  
 Das angegebene <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> sollte entsprechen, eine vorhandene Ressource identifiziert, die mit einem [X: Key Directive](../../xaml-services/x-key-directive.md) auf einer bestimmten Ebene in Ihrer Seite, Anwendung, die verfügbaren Steuerelementdesigns und externe Ressourcen oder Systemressourcen. Die Ressourcensuche wird in dieser Reihenfolge. Weitere Informationen zum Verhalten bei der Suche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](xaml-resources.md).  
  
 Ein Ressourcenschlüssel kann eine beliebige Zeichenfolge, die in definierten werden die [XamlName-Grammatik](../../xaml-services/xamlname-grammar.md). Ein Ressourcenschlüssel kann auch sein andere Objekttypen, z. B. eine <xref:System.Type>. Ein <xref:System.Type> Schlüssel ist wesentlich, wie Steuerelemente mithilfe von Designs und einer impliziten formatiert werden können. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 Die alternative deklaratives Mittel für die verweisen auf eine Ressource ist als eine [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `StaticResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.StaticResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `StaticResource` kann in Objektelementsyntax verwendet werden. In diesem Fall geben Sie den Wert der <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> Eigenschaft ist erforderlich.  
  
 `StaticResource` kann auch verwendet werden, in einer ausführlichen Attributverwendung, der angibt, die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> Eigenschaft als Eigenschaft = Wert-Paar:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `StaticResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung wird die Handhabung dieser Markuperweiterung wird definiert, indem die <xref:System.Windows.StaticResourceExtension> Klasse.  
  
 `StaticResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [XAML-Ressourcen](xaml-resources.md)
- [Ressourcen und Code](resources-and-code.md)
