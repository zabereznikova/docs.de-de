---
title: Inlinestile und -vorlagen
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051012"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="9336f-102">Inlinestile und -vorlagen</span><span class="sxs-lookup"><span data-stu-id="9336f-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="9336f-103">bietet <xref:System.Windows.Style> Objekte und die Vorlagenobjekte (<xref:System.Windows.FrameworkTemplate> Unterklassen) als eine Möglichkeit, um die visuelle Darstellung eines Elements in den Ressourcen zu definieren, sodass sie verwendet werden können mehrmals.</span><span class="sxs-lookup"><span data-stu-id="9336f-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="9336f-104">Aus diesem Grund Attribute [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , die die Typen nehmen <xref:System.Windows.Style> und <xref:System.Windows.FrameworkTemplate> fast immer Verweise auf vorhandene Stile und Vorlagen, anstatt neue zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9336f-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="9336f-105">Einschränkungen von Inlinestile und-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9336f-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="9336f-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Stil- und Vorlageneigenschaften können technisch auf zwei Arten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9336f-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="9336f-107">Sie können die Attributsyntax verwenden, auf einen Stil verweisen, die in eine Ressource, z. B. definiert wurde `<` *Objekt*`Style="{StaticResource`*MyResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="9336f-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="9336f-108">Oder Sie können Eigenschaftenelement-Syntax verwenden, z. B. einen Inlinestil zu definieren:</span><span class="sxs-lookup"><span data-stu-id="9336f-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="9336f-109">`<` *Objekt* `>`</span><span class="sxs-lookup"><span data-stu-id="9336f-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="9336f-110">`<` *Objekt* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="9336f-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="9336f-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="9336f-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="9336f-112">`</` *Objekt* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="9336f-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="9336f-113">`</` *Objekt* `>`</span><span class="sxs-lookup"><span data-stu-id="9336f-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="9336f-114">Die Verwendung von Attributen ist sehr viel häufiger.</span><span class="sxs-lookup"><span data-stu-id="9336f-114">The attribute usage is much more common.</span></span> <span data-ttu-id="9336f-115">Ein Format, das Inline definiert und nicht in Ressourcen definiert ist unbedingt auf das enthaltende Element ausgerichtet ist, und kann nicht erneut verwendet werden so einfach, da sie keine Ressourcenschlüssel besitzt.</span><span class="sxs-lookup"><span data-stu-id="9336f-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="9336f-116">Im Allgemeinen ein definierten Stil vielseitiger und nützlicher und weitere in Übereinstimmung mit den allgemeinen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Prinzip der Trennung von Programmlogik in Code vom Entwurf im Markup-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="9336f-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="9336f-117">In der Regel besteht kein Grund eine Inline Stil oder Vorlage festlegen, auch wenn Sie nur an diesem Speicherort Stil oder die Vorlage verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9336f-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="9336f-118">Die meisten Elemente, die einen Stil oder Vorlage können unterstützen auch eine Content-Eigenschaft und einem Inhaltsmodell.</span><span class="sxs-lookup"><span data-stu-id="9336f-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="9336f-119">Wenn Sie nur den logischen Struktur verwenden, werden Sie über Stile oder Vorlagen einmal erstellen, wäre es sogar noch einfacher zu Inhaltseigenschaft nur mit der entsprechenden untergeordneten Elemente in direkten Markup zu füllen.</span><span class="sxs-lookup"><span data-stu-id="9336f-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="9336f-120">Dies würde die Stil- und Vorlagenressourcen Mechanismen vollständig umgehen.</span><span class="sxs-lookup"><span data-stu-id="9336f-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="9336f-121">Andere Syntax aktiviert, indem Markuperweiterungen, die ein Objekt zurückzugeben sind auch möglich, dass die Stile und Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9336f-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="9336f-122">Zwei für diese Szenarien, in denen Erweiterungen umfassen [TemplateBinding](templatebinding-markup-extension.md) und <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="9336f-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9336f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9336f-123">See also</span></span>

- [<span data-ttu-id="9336f-124">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9336f-124">Styling and Templating</span></span>](../controls/styling-and-templating.md)
