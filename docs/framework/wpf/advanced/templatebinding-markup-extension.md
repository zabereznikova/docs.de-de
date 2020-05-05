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
ms.openlocfilehash: 69698db8b51e3872d5941d4fba67271b1e61226e
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140460"
---
# <a name="templatebinding-markup-extension"></a>TemplateBinding-Markuperweiterung
Verknüpft den Wert einer Eigenschaft in einer Steuerelementvorlage so, dass er der Wert einer anderen Eigenschaft des Steuerelements mit Vorlagen ist.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{TemplateBinding sourceProperty}" ... />
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>Verwendung von XAML-Attributen (für Setter-Eigenschaft in Vorlage oder Stil)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" ... />  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`propertyName`|<xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> der Eigenschaft, der in der Setter-Syntax festgelegt wird.|  
|`sourceProperty`|Eine weitere Abhängigkeitseigenschaft für den auf Vorlagen basierenden Typ, die durch ihren <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> angegeben wird.<br /><br /> - oder -<br /><br /> Ein Eigenschaftenname in Punktnotation, der durch einen anderen Typ als den auf Vorlagen basierenden Zieltyp definiert wird. Hierbei handelt es sich eigentlich um einen <xref:System.Windows.PropertyPath>. Siehe [PropertyPath-XAML-Syntax](propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Hinweise  
 Eine `TemplateBinding` ist eine optimierte Form einer [Bindung](binding-markup-extension.md) für Vorlagen Szenarien, analog zu einer `Binding` , die mit `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`erstellt wurde. Eine `TemplateBinding` ist immer eine unidirektionale Bindung, auch wenn die betroffenen Eigenschaften standardmäßig bidirektionale Bindungen sind. Beide betroffenen Eigenschaften müssen Abhängigkeitseigenschaften sein. Verwenden Sie stattdessen `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`die folgende Bindungs Anweisung, um eine bidirektionale Bindung mit einem übergeordneten Element zu erreichen.
  
 [RelativeSource](relativesource-markupextension.md) ist eine andere Markup Erweiterung, die manchmal in Verbindung mit oder anstelle von `TemplateBinding` verwendet wird, um eine relative Eigenschaften Bindung innerhalb einer Vorlage auszuführen.  
  
 Das Beschreiben von Steuerelement Vorlagen als Konzept wird hier nicht behandelt. Weitere Informationen finden Sie unter [Steuerelement Stile und-Vorlagen](../controls/control-styles-and-templates.md).  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `TemplateBinding`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.TemplateBindingExtension.Property%2A>-Wert der zugrunde liegenden <xref:System.Windows.TemplateBindingExtension>-Erweiterungsklasse zugeordnet.  
  
 Die Objektelementsyntax ist zwar möglich, wird jedoch nicht gezeigt, da sie keine realistische Anwendung hat. `TemplateBinding` wird verwendet, um Werte mithilfe von ausgewerteten Ausdrücken innerhalb von Settern zu füllen. Die Verwendung der Objektelementsyntax für `TemplateBinding` zum Füllen der `<Setter.Property>`-Eigenschaftenelementsyntax ist unnötig ausführlich.  
  
 `TemplateBinding` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.TemplateBindingExtension.Property%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" ... />
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `TemplateBinding` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessor Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.TemplateBindingExtension> -Klasse definiert.  
  
 `TemplateBinding` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markup Erweiterungen in XAML verwenden die `{` Zeichen `}` und in der Attribut Syntax. dabei handelt es sich um die Konvention, mit der ein XAML-Prozessor erkennt, dass das Attribut von einer Markup Erweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [RelativeSource-Markuperweiterung](relativesource-markupextension.md)
- [Bindung als Markuperweiterung](binding-markup-extension.md)
