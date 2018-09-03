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
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="57295-102">TemplateBinding-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="57295-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="57295-103">Verknüpft den Wert einer Eigenschaft in einer Steuerelementvorlage so, dass er der Wert einer anderen Eigenschaft des Steuerelements mit Vorlagen ist.</span><span class="sxs-lookup"><span data-stu-id="57295-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="57295-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="57295-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="57295-105">Verwendung von XAML-Attributen (für Setter-Eigenschaft in Vorlage oder Stil)</span><span class="sxs-lookup"><span data-stu-id="57295-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="57295-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="57295-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="57295-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> der Eigenschaft, der in der Setter-Syntax festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="57295-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="57295-108">Eine weitere Abhängigkeitseigenschaft für den auf Vorlagen basierenden Typ, die durch ihren <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="57295-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="57295-109">- oder -</span><span class="sxs-lookup"><span data-stu-id="57295-109">- or -</span></span><br /><br /> <span data-ttu-id="57295-110">Ein Eigenschaftenname in Punktnotation, der durch einen anderen Typ als den auf Vorlagen basierenden Zieltyp definiert wird.</span><span class="sxs-lookup"><span data-stu-id="57295-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="57295-111">Hierbei handelt es sich eigentlich um einen <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="57295-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="57295-112">Finden Sie unter ["PropertyPath"-XAML-Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="57295-112">See [PropertyPath XAML Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57295-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57295-113">Remarks</span></span>  
 <span data-ttu-id="57295-114">Ein `TemplateBinding` ist eine optimierte Form der eine [Bindung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) für Vorlagenszenarios, analog zu einem `Binding` mit erstellt `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="57295-114">A `TemplateBinding` is an optimized form of a [Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="57295-115">Eine `TemplateBinding` ist immer eine unidirektionale Bindung, auch wenn die betroffenen Eigenschaften standardmäßig bidirektionale Bindungen sind.</span><span class="sxs-lookup"><span data-stu-id="57295-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="57295-116">Beide betroffenen Eigenschaften müssen Abhängigkeitseigenschaften sein.</span><span class="sxs-lookup"><span data-stu-id="57295-116">Both properties involved must be dependency properties.</span></span> <span data-ttu-id="57295-117">Um zu erreichen bidirektionale Bindung an einem vorlagenbasierten übergeordneten Element stattdessen die folgende bindungsanweisung `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span><span class="sxs-lookup"><span data-stu-id="57295-117">In order to achieve two-way binding to a templated parent use the following binding statement instead `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`.</span></span> 
  
 <span data-ttu-id="57295-118">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) ist eine weitere Markuperweiterung, die manchmal in Verbindung mit oder anstelle von dient `TemplateBinding` um relative eigenschaftenbindung in einer Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="57295-118">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="57295-119">Beschreiben von Steuerelementvorlagen als ein Konzept ist hier nicht behandelt; Weitere Informationen finden Sie unter [Steuerelementformate und-Vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="57295-119">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="57295-120">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="57295-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="57295-121">Das Zeichenfolgentoken, das auf die `TemplateBinding`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.TemplateBindingExtension.Property%2A>-Wert der zugrunde liegenden <xref:System.Windows.TemplateBindingExtension>-Erweiterungsklasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="57295-121">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="57295-122">Die Objektelementsyntax ist zwar möglich, wird jedoch nicht gezeigt, da sie keine realistische Anwendung hat.</span><span class="sxs-lookup"><span data-stu-id="57295-122">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="57295-123">`TemplateBinding` wird verwendet, um Werte mithilfe von ausgewerteten Ausdrücken innerhalb von Settern zu füllen. Die Verwendung der Objektelementsyntax für `TemplateBinding` zum Füllen der `<Setter.Property>`-Eigenschaftenelementsyntax ist unnötig ausführlich.</span><span class="sxs-lookup"><span data-stu-id="57295-123">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="57295-124">`TemplateBinding` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.TemplateBindingExtension.Property%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:</span><span class="sxs-lookup"><span data-stu-id="57295-124">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="57295-125">Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.</span><span class="sxs-lookup"><span data-stu-id="57295-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="57295-126">Da für `TemplateBinding` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.</span><span class="sxs-lookup"><span data-stu-id="57295-126">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="57295-127">In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-prozessorimplementierung wird die Handhabung dieser Markuperweiterung wird definiert, indem die <xref:System.Windows.TemplateBindingExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="57295-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="57295-128">`TemplateBinding` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="57295-128">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="57295-129">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="57295-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="57295-130">Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax, dies ist die Konvention mit dem ein XAML-Prozessor erkannt wird, dass das Attribut von eine Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="57295-130">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="57295-131">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="57295-131">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57295-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57295-132">See Also</span></span>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="57295-133">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="57295-133">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="57295-134">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="57295-134">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="57295-135">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="57295-135">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="57295-136">RelativeSource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="57295-136">RelativeSource MarkupExtension</span></span>](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [<span data-ttu-id="57295-137">Bindung als Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="57295-137">Binding Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
