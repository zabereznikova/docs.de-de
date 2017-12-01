---
title: 'Gewusst wie: Formatieren von "UIElement" als transparent oder halbtransparent'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec35ae2e064acf78d1165f64ce8c9e34b153299d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="39580-102">Gewusst wie: Formatieren von "UIElement" als transparent oder halbtransparent</span><span class="sxs-lookup"><span data-stu-id="39580-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="39580-103">Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.UIElement> transparenten oder halb transparent.</span><span class="sxs-lookup"><span data-stu-id="39580-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="39580-104">Um ein Element transparenten oder halb transparent zu gestalten, legen Sie dessen <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="39580-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="39580-105">Der Wert `0.0` Blendet das Element vollständig transparent, während ein Wert von `1.0` vollständig deckend das Element.</span><span class="sxs-lookup"><span data-stu-id="39580-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="39580-106">Der Wert `0.5` Blendet das Element 50 % undurchsichtig usw..</span><span class="sxs-lookup"><span data-stu-id="39580-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="39580-107">Ein Element <xref:System.Windows.UIElement.Opacity%2A> festgelegt ist, um `1.0` standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="39580-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39580-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39580-108">Example</span></span>  
 <span data-ttu-id="39580-109">Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Opacity%2A> einer Schaltfläche `0.25`, dass die Schaltfläche und dessen Inhalt (in diesem Fall wird der Text der Schaltfläche) mit 25 % nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="39580-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="39580-110">Wenn Inhalt des Elements eigene haben <xref:System.Windows.UIElement.Opacity%2A> Einstellungen, die diese Werte werden auf das enthaltende Elemente multipliziert <xref:System.Windows.UIElement.Opacity%2A>.</span><span class="sxs-lookup"><span data-stu-id="39580-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="39580-111">Im folgenden Beispiel wird einer Schaltfläche <xref:System.Windows.UIElement.Opacity%2A> auf `0.25`, und die <xref:System.Windows.UIElement.Opacity%2A> von einer <xref:System.Windows.Controls.Image> Steuerelement auf die Schaltfläche mit `0.5`.</span><span class="sxs-lookup"><span data-stu-id="39580-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="39580-112">Daher wird das Bild 12,5 % undurchsichtig angezeigt wird: 0,25 * 0,5 = 0,125.</span><span class="sxs-lookup"><span data-stu-id="39580-112">As a result, the image appears 12.5% opaque: 0.25 * 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="39580-113">Eine weitere Möglichkeit zum Steuern der Deckkraft eines Elements wird die Deckkraft der Festlegen der <xref:System.Windows.Media.Brush> , zeichnet das Element.</span><span class="sxs-lookup"><span data-stu-id="39580-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="39580-114">Dieser Ansatz ermöglicht es Ihnen, gezielt die Deckkraft der Teile eines Elements zu ändern, und bietet Leistungsvorteile gegenüber des Elements <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="39580-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="39580-115">Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A> von einer <xref:System.Windows.Media.SolidColorBrush> verwendet, um der Schaltfläche zu zeichnen <xref:System.Windows.Controls.Control.Background%2A> festgelegt ist, um `0.25`.</span><span class="sxs-lookup"><span data-stu-id="39580-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="39580-116">Folglich des Pinsels Hintergrund ist 25 % undurchsichtig, aber dessen Inhalt (der Text der Schaltfläche) bleiben 100 % undurchsichtig.</span><span class="sxs-lookup"><span data-stu-id="39580-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="39580-117">Sie können auch die Deckkraft einzelner Farben innerhalb eines Pinsels steuern.</span><span class="sxs-lookup"><span data-stu-id="39580-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="39580-118">Weitere Informationen zu Farben und Pinsel, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="39580-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="39580-119">Ein Beispiel zum Animieren der Deckkraft eines Elements finden Sie unter [Animieren der Deckkraft eines Elements oder Pinsel](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span><span class="sxs-lookup"><span data-stu-id="39580-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
