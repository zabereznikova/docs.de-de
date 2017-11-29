---
title: 'Gewusst wie: Horizontales oder vertikales Kippen eines UIElement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84d1360246141cfa565d669fff108e3e4db3ce33
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="1de0c-102">Gewusst wie: Horizontales oder vertikales Kippen eines UIElement</span><span class="sxs-lookup"><span data-stu-id="1de0c-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="1de0c-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.ScaleTransform> Blättern eine <xref:System.Windows.UIElement> horizontal oder vertikal.</span><span class="sxs-lookup"><span data-stu-id="1de0c-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="1de0c-104">In diesem Beispiel eine <xref:System.Windows.Controls.Button> Steuerelement (eine Art von <xref:System.Windows.UIElement>) wird durch Anwenden von gekippt eine <xref:System.Windows.Media.ScaleTransform> auf seine <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1de0c-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de0c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de0c-105">Example</span></span>  
 <span data-ttu-id="1de0c-106">Die folgende Abbildung zeigt die Schaltfläche, um die flip.</span><span class="sxs-lookup"><span data-stu-id="1de0c-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="1de0c-107">![Eine Schaltfläche ohne Transformierung](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "Graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="1de0c-107">![A button with no transform](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="1de0c-108">UIElement Blättern</span><span class="sxs-lookup"><span data-stu-id="1de0c-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="1de0c-109">Im folgenden sehen den Code, der die Schaltfläche "" erstellt.</span><span class="sxs-lookup"><span data-stu-id="1de0c-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="1de0c-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de0c-110">Example</span></span>  
 <span data-ttu-id="1de0c-111">Um die Schaltfläche horizontal kippen, erstellen eine <xref:System.Windows.Media.ScaleTransform> und legen Sie dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft auf-1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1de0c-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="1de0c-112">Anwenden der <xref:System.Windows.Media.ScaleTransform> auf der Schaltfläche <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1de0c-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="1de0c-113">![Eine horizontal gekippte Schaltfläche &#40; 0,0 &#41; ] (../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "Graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="1de0c-113">![A button flipped horizontally about &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="1de0c-114">Die Schaltfläche nach Anwendung von ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="1de0c-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de0c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de0c-115">Example</span></span>  
 <span data-ttu-id="1de0c-116">Wie Sie aus der obigen Abbildung sehen können, wurde die Schaltfläche gekippt, aber es wurde auch verschoben.</span><span class="sxs-lookup"><span data-stu-id="1de0c-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="1de0c-117">Ist, dass die Schaltfläche mit der von der linken oberen Ecke umgekehrt wurde.</span><span class="sxs-lookup"><span data-stu-id="1de0c-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="1de0c-118">Um die Schaltfläche mit den festliegen Blättern, die Sie anwenden möchten die <xref:System.Windows.Media.ScaleTransform> auf seinen Mittelpunkt, die nicht in der Ecke.</span><span class="sxs-lookup"><span data-stu-id="1de0c-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="1de0c-119">Eine einfache Möglichkeit zum Anwenden der <xref:System.Windows.Media.ScaleTransform> zu den Schaltflächen Center besteht darin, der Schaltfläche <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft auf 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="1de0c-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="1de0c-120">![Eine Schaltfläche horizontal ihren Mittelpunkt gekippte](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "Graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="1de0c-120">![A button flipped horizontally about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="1de0c-121">Die Schaltfläche mit einem RenderTransformOrigin von 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="1de0c-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de0c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1de0c-122">Example</span></span>  
 <span data-ttu-id="1de0c-123">Um die Schaltfläche vertikal kippen, legen Sie die <xref:System.Windows.Media.ScaleTransform> des Objekts <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> -Eigenschaft anstelle von dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1de0c-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="1de0c-124">![Eine Schaltfläche vertikal ihren Mittelpunkt gekippte](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "Graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="1de0c-124">![A button flipped vertically about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="1de0c-125">Die vertikal gekippte Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="1de0c-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de0c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1de0c-126">See Also</span></span>  
 [<span data-ttu-id="1de0c-127">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="1de0c-127">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
