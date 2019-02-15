---
title: 'Vorgehensweise: Animieren eines BorderThickness-Werts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 96467fd013ddd2b2e215520384da2000aec68866
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304218"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="41363-102">Vorgehensweise: Animieren eines BorderThickness-Werts</span><span class="sxs-lookup"><span data-stu-id="41363-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="41363-103">In diesem Beispiel wird gezeigt, wie zum Animieren von Änderungen an die Stärke eines Rahmens mithilfe der <xref:System.Windows.Media.Animation.ThicknessAnimation> Klasse.</span><span class="sxs-lookup"><span data-stu-id="41363-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41363-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41363-104">Example</span></span>  
 <span data-ttu-id="41363-105">Das folgende Beispiel erstellt eine Animation die Stärke eines Rahmens mithilfe von <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span><span class="sxs-lookup"><span data-stu-id="41363-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="41363-106">Im Beispiel wird die <xref:System.Windows.Controls.Border.BorderThickness%2A> Eigenschaft <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="41363-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="41363-107">Das vollständige Beispiel finden Sie unter [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="41363-107">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41363-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41363-108">See also</span></span>
- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="41363-109">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="41363-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="41363-110">Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="41363-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="41363-111">Animieren der Breite eines Rahmens mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="41363-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
