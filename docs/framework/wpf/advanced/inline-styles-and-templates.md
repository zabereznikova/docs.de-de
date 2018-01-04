---
title: Inlinestile und -vorlagen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dccf0b274121ff4fe88c9270119a2f631ffcf29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="94126-102">Inlinestile und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="94126-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="94126-103">bietet <xref:System.Windows.Style> Objekte und die Vorlagenobjekte (<xref:System.Windows.FrameworkTemplate> Unterklassen) als eine Möglichkeit, um die visuelle Darstellung eines Elements in den Ressourcen zu definieren, sodass sie verwendet werden können mehrere Male auf.</span><span class="sxs-lookup"><span data-stu-id="94126-103"> provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="94126-104">Aus diesem Grund Attribute im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , die anhand von den Typen <xref:System.Windows.Style> und <xref:System.Windows.FrameworkTemplate> fast immer Ressourcenverweise auf vorhandene Stile und Vorlagen, anstatt neue zu definieren.</span><span class="sxs-lookup"><span data-stu-id="94126-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="94126-105">Einschränkungen von Inlinestile und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="94126-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="94126-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Stil- und Eigenschaften können auf zwei Arten technisch festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="94126-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="94126-107">Können Sie auf um einen Stil zu verweisen, die in einer Ressource, z. B. definiert wurde Attributsyntax `<` *Objekt*`Style="{StaticResource`*MyResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="94126-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="94126-108">Oder Sie können Eigenschaftenelementsyntax verwenden, um einen Inlinestil für die Instanz zu definieren:</span><span class="sxs-lookup"><span data-stu-id="94126-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="94126-109">`<`*Objekt*`>`</span><span class="sxs-lookup"><span data-stu-id="94126-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="94126-110">`<`*Objekt*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="94126-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="94126-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="94126-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="94126-112">`</`*Objekt*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="94126-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="94126-113">`</`*Objekt*`>`</span><span class="sxs-lookup"><span data-stu-id="94126-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="94126-114">Für die Attributverwendung ist sehr viel häufiger.</span><span class="sxs-lookup"><span data-stu-id="94126-114">The attribute usage is much more common.</span></span> <span data-ttu-id="94126-115">Ein Format, das Inline definiert und nicht in Ressourcen definiert ist unbedingt auf das enthaltende Element nur begrenzt, und kann nicht erneut verwendet werden genauso einfach, da sie keine Ressourcenschlüssel besitzt.</span><span class="sxs-lookup"><span data-stu-id="94126-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="94126-116">Im Allgemeinen ein Stil Ressource definiert vielseitiger und hilfreich ist, und wird in Übereinstimmung mit den allgemeinen weitere [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Programmierung Prinzip Programmlogik im Code vom Entwurf in Markup zu trennen.</span><span class="sxs-lookup"><span data-stu-id="94126-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="94126-117">In der Regel besteht kein Grund eine Inline Stil oder eine Vorlage festlegen, auch wenn Sie nur an diesem Speicherort Stil oder die Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="94126-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="94126-118">Die meisten Elemente, die einen Stil oder eine Vorlage übernehmen können unterstützen auch ein Content-Eigenschaft und einem Inhaltsmodell.</span><span class="sxs-lookup"><span data-stu-id="94126-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="94126-119">Wenn Sie nur die logische Struktur verwenden Sie erstellen durch formatieren oder Datenvorlagen einmal, wäre es noch einfacher, Content-Eigenschaft nur mit den entsprechenden untergeordneten Elementen im direkten Markup zu füllen.</span><span class="sxs-lookup"><span data-stu-id="94126-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="94126-120">Dies würde die Mechanismen Stil- und vollständig umgehen.</span><span class="sxs-lookup"><span data-stu-id="94126-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="94126-121">Andere Syntax aktiviert, die für Markuperweiterungen, die ein Objekt zurückgeben, sind auch für Stile und Vorlagen möglich.</span><span class="sxs-lookup"><span data-stu-id="94126-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="94126-122">Zwei diese Erweiterungen, die über mögliche Szenarien umfassen [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) und <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="94126-122">Two such extensions that have possible scenarios include [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94126-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94126-123">See Also</span></span>  
 [<span data-ttu-id="94126-124">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="94126-124">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
