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
ms.openlocfilehash: d425d17405bc8241c3fd85c77c6672265a060900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546919"
---
# <a name="templatebinding-markup-extension"></a><span data-ttu-id="2c63e-102">TemplateBinding-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="2c63e-102">TemplateBinding Markup Extension</span></span>
<span data-ttu-id="2c63e-103">Verknüpft den Wert einer Eigenschaft in einer Steuerelementvorlage so, dass er der Wert einer anderen Eigenschaft des Steuerelements mit Vorlagen ist.</span><span class="sxs-lookup"><span data-stu-id="2c63e-103">Links the value of a property in a control template to be the value of another property on the templated control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2c63e-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="2c63e-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a><span data-ttu-id="2c63e-105">Verwendung von XAML-Attributen (für Setter-Eigenschaft in Vorlage oder Stil)</span><span class="sxs-lookup"><span data-stu-id="2c63e-105">XAML Attribute Usage (for Setter property in template or style)</span></span>  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2c63e-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="2c63e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`propertyName`|<span data-ttu-id="2c63e-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> der Eigenschaft, der in der Setter-Syntax festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2c63e-107"><xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> of the property being set in the setter syntax.</span></span>|  
|`sourceProperty`|<span data-ttu-id="2c63e-108">Eine weitere Abhängigkeitseigenschaft für den auf Vorlagen basierenden Typ, die durch ihren <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2c63e-108">Another dependency property that exists on the type being templated, specified by its <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.</span></span><br /><br /> <span data-ttu-id="2c63e-109">- oder -</span><span class="sxs-lookup"><span data-stu-id="2c63e-109">- or -</span></span><br /><br /> <span data-ttu-id="2c63e-110">Ein Eigenschaftenname in Punktnotation, der durch einen anderen Typ als den auf Vorlagen basierenden Zieltyp definiert wird.</span><span class="sxs-lookup"><span data-stu-id="2c63e-110">A "dotted-down" property name that is defined by a different type than the target type being templated.</span></span> <span data-ttu-id="2c63e-111">Hierbei handelt es sich eigentlich um einen <xref:System.Windows.PropertyPath>.</span><span class="sxs-lookup"><span data-stu-id="2c63e-111">This is actually a <xref:System.Windows.PropertyPath>.</span></span> <span data-ttu-id="2c63e-112">Finden Sie unter ["PropertyPath" XAML-Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="2c63e-112">See [PropertyPath XAML Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c63e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c63e-113">Remarks</span></span>  
 <span data-ttu-id="2c63e-114">Ein `TemplateBinding` ist eine optimierte Form einer [binden](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) Vorlage Szenarien, die analog zu einer `Binding` mit erstellt `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span><span class="sxs-lookup"><span data-stu-id="2c63e-114">A `TemplateBinding` is an optimized form of a [Binding](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) for template scenarios, analogous to a `Binding` constructed with `{Binding RelativeSource={RelativeSource TemplatedParent}}`.</span></span> <span data-ttu-id="2c63e-115">Eine `TemplateBinding` ist immer eine unidirektionale Bindung, auch wenn die betroffenen Eigenschaften standardmäßig bidirektionale Bindungen sind.</span><span class="sxs-lookup"><span data-stu-id="2c63e-115">A `TemplateBinding` is always a one-way binding, even if properties involved default to two-way binding.</span></span> <span data-ttu-id="2c63e-116">Beide betroffenen Eigenschaften müssen Abhängigkeitseigenschaften sein.</span><span class="sxs-lookup"><span data-stu-id="2c63e-116">Both properties involved must be dependency properties.</span></span>  
  
 <span data-ttu-id="2c63e-117">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) ist einem anderen Markuperweiterung, die in Verbindung mit oder anstelle von verwendet wird `TemplateBinding` um relative eigenschaftenbindung innerhalb einer Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2c63e-117">[RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) is another markup extension that is sometimes used in conjunction with or instead of `TemplateBinding` in order to perform relative property binding within a template.</span></span>  
  
 <span data-ttu-id="2c63e-118">Beschreiben von Steuerelementvorlagen als ein Konzept wird hier nicht behandelt; Weitere Informationen finden Sie unter [Steuerelementstile und Vorlagen](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="2c63e-118">Describing control templates as a concept is not covered here; for more information, see [Control Styles and Templates](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).</span></span>  
  
 <span data-ttu-id="2c63e-119">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="2c63e-119">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="2c63e-120">Das Zeichenfolgentoken, das auf die `TemplateBinding`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.TemplateBindingExtension.Property%2A>-Wert der zugrunde liegenden <xref:System.Windows.TemplateBindingExtension>-Erweiterungsklasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2c63e-120">The string token provided after the `TemplateBinding` identifier string is assigned as the <xref:System.Windows.TemplateBindingExtension.Property%2A> value of the underlying <xref:System.Windows.TemplateBindingExtension> extension class.</span></span>  
  
 <span data-ttu-id="2c63e-121">Die Objektelementsyntax ist zwar möglich, wird jedoch nicht gezeigt, da sie keine realistische Anwendung hat.</span><span class="sxs-lookup"><span data-stu-id="2c63e-121">Object element syntax is possible, but it is not shown because it has no realistic application.</span></span> <span data-ttu-id="2c63e-122">`TemplateBinding` wird verwendet, um Werte mithilfe von ausgewerteten Ausdrücken innerhalb von Settern zu füllen. Die Verwendung der Objektelementsyntax für `TemplateBinding` zum Füllen der `<Setter.Property>`-Eigenschaftenelementsyntax ist unnötig ausführlich.</span><span class="sxs-lookup"><span data-stu-id="2c63e-122">`TemplateBinding` is used to fill values within setters, using evaluated expressions, and using object element syntax for `TemplateBinding` to fill `<Setter.Property>` property element syntax is unnecessarily verbose.</span></span>  
  
 <span data-ttu-id="2c63e-123">`TemplateBinding` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.TemplateBindingExtension.Property%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:</span><span class="sxs-lookup"><span data-stu-id="2c63e-123">`TemplateBinding` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.TemplateBindingExtension.Property%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 <span data-ttu-id="2c63e-124">Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.</span><span class="sxs-lookup"><span data-stu-id="2c63e-124">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="2c63e-125">Da für `TemplateBinding` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.</span><span class="sxs-lookup"><span data-stu-id="2c63e-125">Because `TemplateBinding` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="2c63e-126">In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -XAML-Prozessor-Implementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.TemplateBindingExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2c63e-126">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.TemplateBindingExtension> class.</span></span>  
  
 <span data-ttu-id="2c63e-127">`TemplateBinding` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="2c63e-127">`TemplateBinding` is a markup extension.</span></span> <span data-ttu-id="2c63e-128">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c63e-128">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="2c63e-129">Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax normalerweise wird mit dem ein XAML-Prozessor erkennt, dass das Attribut eine Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="2c63e-129">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="2c63e-130">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="2c63e-130">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c63e-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c63e-131">See Also</span></span>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="2c63e-132">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2c63e-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="2c63e-133">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="2c63e-133">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="2c63e-134">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="2c63e-134">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="2c63e-135">RelativeSource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="2c63e-135">RelativeSource MarkupExtension</span></span>](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [<span data-ttu-id="2c63e-136">Bindung als Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="2c63e-136">Binding Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
