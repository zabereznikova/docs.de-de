---
title: StaticResource-Markuperweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97b83feb9d19760208d9cc103290c5c6293c30c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="ca5be-102">StaticResource-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="ca5be-102">StaticResource Markup Extension</span></span>
<span data-ttu-id="ca5be-103">Stellt einen Wert für eine beliebige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Eigenschaftsattribut, das durch einen Verweis auf eine bereits definierte Ressource nachschlagen.</span><span class="sxs-lookup"><span data-stu-id="ca5be-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="ca5be-104">Suchverhalten für diese Ressource ist analog zur Ladezeit Suche, bei der nach Ressourcen gesucht werden, die zuvor aus dem Markup des aktuellen geladen wurden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sowie andere Quellen für die Anwendung, und generiert dieses Ressourcenwert als der der Eigenschaftswert in der Laufzeit-Objekten.</span><span class="sxs-lookup"><span data-stu-id="ca5be-104">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ca5be-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="ca5be-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="ca5be-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="ca5be-106">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ca5be-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="ca5be-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="ca5be-108">Der Schlüssel für die angeforderte Ressource.</span><span class="sxs-lookup"><span data-stu-id="ca5be-108">The key for the requested resource.</span></span> <span data-ttu-id="ca5be-109">Dieser Schlüssel wurde ursprünglich zugewiesen, durch die [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) Wenn eine Ressource, die im Markup erstellt wurde, oder als bereitgestellt wurde die `key` -Parameter beim Aufrufen von <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> , wenn die Ressource im Code erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca5be-109">This key was initially assigned by the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca5be-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca5be-110">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca5be-111">Ein `StaticResource` auf keinen Fall einen Vorwärtsverweis auf eine Ressource, die definiert wird, stellen lexikalisch weiter innerhalb der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei.</span><span class="sxs-lookup"><span data-stu-id="ca5be-111">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="ca5be-112">Versuch wird nicht unterstützt, und auch wenn Sie ein solchen Verweis nicht fehlschlägt, versucht, den vorwärts gerichteten Verweis entstehen durch eine Ladezeit zu Leistungseinbußen bei der internen Hashtabellen darstellt eine <xref:System.Windows.ResourceDictionary> durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="ca5be-112">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="ca5be-113">Passen Sie für optimale Ergebnisse die Zusammensetzung der Ressourcenwörterbücher so, dass Vorwärtsverweisen vermieden werden können.</span><span class="sxs-lookup"><span data-stu-id="ca5be-113">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="ca5be-114">Wenn Sie einen Vorwärtsverweis nicht vermeiden können, verwenden Sie [DynamicResource Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="ca5be-114">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="ca5be-115">Das angegebene <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> sollte entsprechen, eine vorhandene Ressource, die mit identifiziert eine [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) auf einer bestimmten Ebene in der Seite, Anwendung, die verfügbare Steuerelementdesigns und externe Ressourcen oder Systemressourcen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ca5be-115">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="ca5be-116">Die Ressourcensuche wird in dieser Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ca5be-116">The resource lookup occurs in that order.</span></span> <span data-ttu-id="ca5be-117">Weitere Informationen zum Verhalten bei der Ressourcensuche für statische und dynamische Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="ca5be-117">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="ca5be-118">Ein Ressourcenschlüssel kann eine beliebige Zeichenfolge, die definiert, der [XamlName-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="ca5be-118">A resource key can be any string defined in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="ca5be-119">Ein Ressourcenschlüssel kann auch andere Objekttypen, z. B. eine <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="ca5be-119">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="ca5be-120">Ein <xref:System.Type> Schlüssel ist grundlegend, wie Steuerelemente mithilfe von Designs über einen impliziten Schlüssel formatiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ca5be-120">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="ca5be-121">Weitere Informationen finden Sie unter [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ca5be-121">For more information, see [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="ca5be-122">Die alternative deklaratives Mittel für verweisen auf eine Ressource wird als eine [DynamicResource Markuperweiterung](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="ca5be-122">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="ca5be-123">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="ca5be-123">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="ca5be-124">Das Zeichenfolgentoken, das auf die `StaticResource`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Wert der zugrunde liegenden <xref:System.Windows.StaticResourceExtension>-Erweiterungsklasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ca5be-124">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="ca5be-125">`StaticResource`kann in der Syntax der Object-Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca5be-125">`StaticResource` can be used in object element syntax.</span></span> <span data-ttu-id="ca5be-126">In diesem Fall geben Sie den Wert der <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> ist eine erforderliche Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ca5be-126">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="ca5be-127">`StaticResource` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:</span><span class="sxs-lookup"><span data-stu-id="ca5be-127">`StaticResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="ca5be-128">Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.</span><span class="sxs-lookup"><span data-stu-id="ca5be-128">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="ca5be-129">Da für `StaticResource` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.</span><span class="sxs-lookup"><span data-stu-id="ca5be-129">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="ca5be-130">In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.StaticResourceExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ca5be-130">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 <span data-ttu-id="ca5be-131">`StaticResource` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="ca5be-131">`StaticResource` is a markup extension.</span></span> <span data-ttu-id="ca5be-132">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ca5be-132">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="ca5be-133">Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ca5be-133">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="ca5be-134">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ca5be-134">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5be-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca5be-135">See Also</span></span>  
 [<span data-ttu-id="ca5be-136">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ca5be-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ca5be-137">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="ca5be-137">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="ca5be-138">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="ca5be-138">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="ca5be-139">XAML-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ca5be-139">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="ca5be-140">Ressourcen und Code</span><span class="sxs-lookup"><span data-stu-id="ca5be-140">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)
