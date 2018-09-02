---
title: TemplateBinding-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: 7c076172424baab4553a277baab2faca634c1e87
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474193"
---
# <a name="templatebinding-markup-extension"></a>TemplateBinding-Markuperweiterung
Verknüpft den Wert einer Eigenschaft in einer Steuerelementvorlage so, dass er der Wert einer anderen Eigenschaft des Steuerelements mit Vorlagen ist.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>Verwendung von XAML-Attributen (für Setter-Eigenschaft in Vorlage oder Stil)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> der Eigenschaft, der in der Setter-Syntax festgelegt wird.|  
|`sourceProperty`|Eine weitere Abhängigkeitseigenschaft für den auf Vorlagen basierenden Typ, die durch ihren <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> angegeben wird.<br /><br /> - oder -<br /><br /> Ein Eigenschaftenname in Punktnotation, der durch einen anderen Typ als den auf Vorlagen basierenden Zieltyp definiert wird. Hierbei handelt es sich eigentlich um einen <xref:System.Windows.PropertyPath>. Finden Sie unter ["PropertyPath"-XAML-Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Hinweise  
 Ein `TemplateBinding` ist eine optimierte Form der eine [Bindung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) für Vorlagenszenarios, analog zu einem `Binding` mit erstellt `{Binding RelativeSource={RelativeSource TemplatedParent}}`. Eine `TemplateBinding` ist immer eine unidirektionale Bindung, auch wenn die betroffenen Eigenschaften standardmäßig bidirektionale Bindungen sind. Beide betroffenen Eigenschaften müssen Abhängigkeitseigenschaften sein. Um zu erreichen bidirektionale Bindung an einem vorlagenbasierten übergeordneten Element stattdessen die folgende bindungsanweisung `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`. 
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) ist eine weitere Markuperweiterung, die manchmal in Verbindung mit oder anstelle von dient `TemplateBinding` um relative eigenschaftenbindung in einer Vorlage auszuführen.  
  
 Beschreiben von Steuerelementvorlagen als ein Konzept ist hier nicht behandelt; Weitere Informationen finden Sie unter [Steuerelementformate und-Vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `TemplateBinding`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.TemplateBindingExtension.Property%2A>-Wert der zugrunde liegenden <xref:System.Windows.TemplateBindingExtension>-Erweiterungsklasse zugeordnet.  
  
 Die Objektelementsyntax ist zwar möglich, wird jedoch nicht gezeigt, da sie keine realistische Anwendung hat. `TemplateBinding` wird verwendet, um Werte mithilfe von ausgewerteten Ausdrücken innerhalb von Settern zu füllen. Die Verwendung der Objektelementsyntax für `TemplateBinding` zum Füllen der `<Setter.Property>`-Eigenschaftenelementsyntax ist unnötig ausführlich.  
  
 `TemplateBinding` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.TemplateBindingExtension.Property%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `TemplateBinding` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-prozessorimplementierung wird die Handhabung dieser Markuperweiterung wird definiert, indem die <xref:System.Windows.TemplateBindingExtension> Klasse.  
  
 `TemplateBinding` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax, dies ist die Konvention mit dem ein XAML-Prozessor erkannt wird, dass das Attribut von eine Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [RelativeSource-Markuperweiterung](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [Bindung als Markuperweiterung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
