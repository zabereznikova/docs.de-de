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
ms.openlocfilehash: 5c0bb247bae525658d89d53f1672e57b87aba7bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646210"
---
# <a name="staticresource-markup-extension"></a>StaticResource-Markuperweiterung
Stellt einen Wert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für jedes Eigenschaftsattribut bereit, indem ein Verweis auf eine bereits definierte Ressource gesucht wird. Das Nachschlageverhalten für diese Ressource ist analog zur Ladezeitsuche, bei der nach Ressourcen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] gesucht wird, die zuvor aus dem Markup der aktuellen Seite geladen wurden, sowie nach anderen Anwendungsquellen, und diesen Ressourcenwert als Eigenschaftswert in den Laufzeitobjekten generiert.  
  
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
|`key`|Der Schlüssel für die angeforderte Ressource. Dieser Schlüssel wurde ursprünglich von der [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) zugewiesen, wenn eine `key` Ressource <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> in Markup erstellt wurde, oder als Parameter beim Aufruf angegeben wurde, wenn die Ressource im Code erstellt wurde.|  
  
## <a name="remarks"></a>Bemerkungen  
  
> [!IMPORTANT]
> A `StaticResource` darf nicht versuchen, einen Forward-Verweis auf eine Ressource [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zu erstellen, die in der Datei lexikalisch weiter definiert ist. Der Versuch, dies zu tun, wird nicht unterstützt, und selbst wenn ein solcher Verweis nicht fehlschlägt, wird <xref:System.Windows.ResourceDictionary> der Versuch des Vorwärtsverweises mit einer Belastungszeit-Leistungseinbußen beim Durchsuchen der internen Hashtabellen, die eine darstellen, mit sich gebracht. Um optimale Ergebnisse zu erzielen, passen Sie die Zusammensetzung Ihrer Ressourcenwörterbücher so an, dass Vorwärtsreferenzen vermieden werden können. Wenn Sie einen Forward-Verweis nicht vermeiden können, verwenden Sie stattdessen [DynamicResource Markup Extension.](dynamicresource-markup-extension.md)  
  
 Die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> angegebene Ressource sollte einer vorhandenen Ressource entsprechen, die auf einer bestimmten Ebene auf Ihrer Seite, Anwendung, den verfügbaren Steuerungsthemen und externen Ressourcen oder Systemressourcen mit einer [x:Key-Richtlinie](../../../desktop-wpf/xaml-services/xkey-directive.md) gekennzeichnet ist. Die Ressourcensuche erfolgt in dieser Reihenfolge. Weitere Informationen zum Ressourcensuchverhalten für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 Ein Ressourcenschlüssel kann eine beliebige Zeichenfolge sein, die in der [XamlName-Grammatik](../../../desktop-wpf/xaml-services/xamlname-grammar.md)definiert ist. Ein Ressourcenschlüssel kann auch andere Objekttypen <xref:System.Type>sein, z. B. eine . Ein <xref:System.Type> Schlüssel ist von grundlegender Bedeutung dafür, wie Steuerelemente durch Designs mithilfe eines impliziten Stilschlüssels formatiert werden können. Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md).  
  
 Die alternative deklarative Möglichkeit, auf eine Ressource zu verweisen, ist als [DynamicResource Markup Extension](dynamicresource-markup-extension.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `StaticResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.StaticResourceExtension>-Erweiterungsklasse zugeordnet.  
  
 `StaticResource`kann in der Objektelementsyntax verwendet werden. In diesem Fall ist die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> Angabe des Werts der Eigenschaft erforderlich.  
  
 `StaticResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `StaticResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Prozessorimplementierung wird die Verarbeitung für diese <xref:System.Windows.StaticResourceExtension> Markuperweiterung durch die Klasse definiert.  
  
 `StaticResource` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Ressourcen und Code](resources-and-code.md)
