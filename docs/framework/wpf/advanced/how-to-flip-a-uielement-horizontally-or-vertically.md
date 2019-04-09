---
title: 'Vorgehensweise: Horizontales oder vertikales Kippen eines UIElement'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215520"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="a6573-102">Vorgehensweise: Horizontales oder vertikales Kippen eines UIElement</span><span class="sxs-lookup"><span data-stu-id="a6573-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="a6573-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.ScaleTransform> So kippen Sie ein <xref:System.Windows.UIElement> horizontal oder vertikal.</span><span class="sxs-lookup"><span data-stu-id="a6573-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="a6573-104">In diesem Beispiel eine <xref:System.Windows.Controls.Button> Steuerelement (eine Art von <xref:System.Windows.UIElement>) gekippt wird, durch Anwenden einer <xref:System.Windows.Media.ScaleTransform> zu seine <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a6573-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6573-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6573-105">Example</span></span>  
 <span data-ttu-id="a6573-106">Die folgende Abbildung zeigt die Schaltfläche, um kippen.</span><span class="sxs-lookup"><span data-stu-id="a6573-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="a6573-107">![Eine Schaltfläche ohne Transformierung](./media/graphicsmm-buttonflipbeforeflip.gif "Graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="a6573-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="a6573-108">Das zu kippende UIElement</span><span class="sxs-lookup"><span data-stu-id="a6573-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="a6573-109">Das folgende Beispiel zeigt den Code, der die Schaltfläche erstellt.</span><span class="sxs-lookup"><span data-stu-id="a6573-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="a6573-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6573-110">Example</span></span>  
 <span data-ttu-id="a6573-111">Um die Schaltfläche horizontal zu kippen, erstellen eine <xref:System.Windows.Media.ScaleTransform> und legen Sie dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft auf-1 fest.</span><span class="sxs-lookup"><span data-stu-id="a6573-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="a6573-112">Anwenden der <xref:System.Windows.Media.ScaleTransform> auf der Schaltfläche " <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a6573-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="a6573-113">![Eine gekippte Schaltfläche horizontal &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "Graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="a6573-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="a6573-114">Die Schaltfläche nach Anwendung von ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="a6573-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6573-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6573-115">Example</span></span>  
 <span data-ttu-id="a6573-116">Wie Sie aus der obigen Abbildung sehen können, wurde die Schaltfläche gekippt, aber gleichzeitig verschoben.</span><span class="sxs-lookup"><span data-stu-id="a6573-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="a6573-117">Das ist da die Schaltfläche mit der von der oberen linken Ecke gedreht wurde.</span><span class="sxs-lookup"><span data-stu-id="a6573-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="a6573-118">Um die Schaltfläche direktes kippen, die Sie anwenden möchten die <xref:System.Windows.Media.ScaleTransform> um seinen Mittelpunkt, die nicht in der Ecke.</span><span class="sxs-lookup"><span data-stu-id="a6573-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="a6573-119">Eine einfache Möglichkeit zum Anwenden der <xref:System.Windows.Media.ScaleTransform> auf Schaltflächen Center besteht darin, der der Schaltfläche <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft auf 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="a6573-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="a6573-120">![Eine Schaltfläche horizontal ihren Mittelpunkt gekippte](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "Graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="a6573-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="a6573-121">Die Schaltfläche mit einem RenderTransformOrigin von 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="a6573-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6573-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6573-122">Example</span></span>  
 <span data-ttu-id="a6573-123">Um die Schaltfläche vertikal zu kippen, legen die <xref:System.Windows.Media.ScaleTransform> des Objekts <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> -Eigenschaft anstelle der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a6573-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="a6573-124">![Eine Schaltfläche vertikal ihren Mittelpunkt gekippte](./media/graphicsmm-buttonflipverticalflip-inplace.gif "Graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="a6573-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="a6573-125">Die Schaltfläche "vertikal gekippt."</span><span class="sxs-lookup"><span data-stu-id="a6573-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6573-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6573-126">See also</span></span>

- [<span data-ttu-id="a6573-127">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="a6573-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
