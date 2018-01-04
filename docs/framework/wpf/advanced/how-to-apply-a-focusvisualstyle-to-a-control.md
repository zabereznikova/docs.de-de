---
title: 'Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41895974b7e6c128d979e362f2dcef1c68e0a5c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="7d59f-102">Gewusst wie: Anwenden eines FocusVisualStyle auf ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7d59f-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="7d59f-103">Dieses Beispiel zeigt, wie einen visuelle Stil des Fokus in Ressourcen erstellen und Anwenden der Formatvorlage auf ein Steuerelement mit der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d59f-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d59f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d59f-104">Example</span></span>  
 <span data-ttu-id="7d59f-105">Das folgende Beispiel definiert ein Format, das zusätzliche Kontrolle Compositing, die gilt nur erstellt, wenn das Steuerelement den Tastaturfokus wird die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d59f-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="7d59f-106">Dies erfolgt durch die Definition eines Stils mit einem <xref:System.Windows.Controls.ControlTemplate>, und klicken Sie dann auf diesem Format als Ressource verweisen, beim Festlegen der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d59f-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="7d59f-107">Ein externes Rechteck, einem Rahmen ähnelt befindet sich außerhalb des rechteckigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="7d59f-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="7d59f-108">Sofern nicht anderweitig modifiziert wurde, verwendet die Größe des Formats der <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A> des rechteckigen Steuerelements der visuellen Stil der Fokus wird angewendet.</span><span class="sxs-lookup"><span data-stu-id="7d59f-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="7d59f-109">In diesem Beispiel wird die negative Werte für die <xref:System.Windows.FrameworkElement.Margin%2A> Rahmens außerhalb das Steuerelement mit Fokus etwas angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d59f-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="7d59f-110">Ein <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> ist additiv zu jeder Vorlage Steuerelementformats, der geliefert wird entweder von einem expliziten Stil oder einem Designstil der primäre Stil für ein Steuerelement kann weiterhin mit erstellt werden ein <xref:System.Windows.Controls.ControlTemplate> und Festlegen von diesem Format auf die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d59f-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="7d59f-111">Fokus visuelle Stile einheitlich werden, über ein Design oder eine Benutzeroberfläche verwendet sollten, anstatt eine andere Definition für jedes Element den Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="7d59f-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="7d59f-112">Weitere Informationen finden Sie unter [Formatierung für den Fokus in Steuerelementen und FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="7d59f-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d59f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d59f-113">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [<span data-ttu-id="7d59f-114">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="7d59f-114">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="7d59f-115">Fokusstile in Steuerelementen und FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="7d59f-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
