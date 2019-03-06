---
title: 'Vorgehensweise: Anwenden eines FocusVisualStyle auf ein Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: c4b379d3c57b6d0ae29952c23a35d7cc2cdf7f96
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366594"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="8aab7-102">Vorgehensweise: Anwenden eines FocusVisualStyle auf ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8aab7-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="8aab7-103">Dieses Beispiel zeigt Ihnen das Erstellen eines visuellen Fokusstils in Ressourcen und Anwenden der Formatvorlage auf ein Steuerelement, mit der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8aab7-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aab7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8aab7-104">Example</span></span>  
 <span data-ttu-id="8aab7-105">Das folgende Beispiel definiert ein Format, das zusätzliche Zusammensetzung von Steuerelementen, die nur gültig, wenn das Steuerelement mit Fokus im Tastatur wird die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aab7-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="8aab7-106">Dies erfolgt durch die Definition eines Stils mit einem <xref:System.Windows.Controls.ControlTemplate>, und klicken Sie dann diesen Stil als eine Ressource verweisen, beim Festlegen der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8aab7-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="8aab7-107">Ein externes Rechteck, einem Rahmen ähnelt befindet sich außerhalb des rechteckigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="8aab7-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="8aab7-108">Es sei denn, die andernfalls geändert wird, verwendet die Größe des Formats der <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A> des rechteckigen-Steuerelements, in dem der visuelle Fokusstil angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aab7-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="8aab7-109">In diesem Beispiel wird die negative Werte für die <xref:System.Windows.FrameworkElement.Margin%2A> zu der Rahmen etwas außerhalb das Steuerelement mit Fokus dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8aab7-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="8aab7-110">Ein <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> wird auf alle Steuerelement-Vorlage-Format, das ist additiv expliziter Stil oder einem Designstil der primäre Stil für ein Steuerelement kann immer noch mit erstellt werden ein <xref:System.Windows.Controls.ControlTemplate> und diesen Stil auf die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8aab7-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="8aab7-111">Fokus visuelle Stile konsistent werden, über ein Thema oder eine Benutzeroberfläche verwendet sollten, anstatt einen anderen Wert für jedes Element den Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="8aab7-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="8aab7-112">Weitere Informationen finden Sie unter [Fokusstile in Steuerelementen und FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="8aab7-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aab7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8aab7-113">See also</span></span>
- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="8aab7-114">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8aab7-114">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="8aab7-115">Fokusstile in Steuerelementen und FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="8aab7-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
