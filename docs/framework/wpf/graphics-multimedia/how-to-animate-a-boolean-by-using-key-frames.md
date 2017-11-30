---
title: 'Gewusst wie: Animieren eines booleschen Werts mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ac129bf133cca88a6d2f6a724d25ea2519cb72e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="240c5-102">Gewusst wie: Animieren eines booleschen Werts mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="240c5-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="240c5-103">In diesem Beispiel wird gezeigt, wie zu animierende den booleschen Eigenschaftswert, der eine <xref:System.Windows.Controls.Button> Steuerung mithilfe des Keyframes.</span><span class="sxs-lookup"><span data-stu-id="240c5-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="240c5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="240c5-104">Example</span></span>  
 <span data-ttu-id="240c5-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.UIElement.IsEnabled%2A> Eigenschaft ein <xref:System.Windows.Controls.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="240c5-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="240c5-106">Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> Klasse.</span><span class="sxs-lookup"><span data-stu-id="240c5-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="240c5-107">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> erstellen Sie einen plötzlichen Sprünge zwischen Werten, d. h., die Verschiebung der Animation holprig ist.</span><span class="sxs-lookup"><span data-stu-id="240c5-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="240c5-108">Das vollständige Beispiel finden Sie unter [Beispiel für KeyFrame-Animationen](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="240c5-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240c5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="240c5-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>  
 <xref:System.Windows.UIElement.IsEnabled%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="240c5-110">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="240c5-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="240c5-111">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="240c5-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
