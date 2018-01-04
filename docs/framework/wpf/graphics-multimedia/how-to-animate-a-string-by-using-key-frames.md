---
title: 'Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1692777a97754fb7f6481b2d9cb8942dcb62df77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="daee0-102">Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="daee0-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="daee0-103">In diesem Beispiel wird gezeigt, wie eine Zeichenfolge animiert in diesem Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft von einem <xref:System.Windows.Controls.Button> mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="daee0-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daee0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="daee0-104">Example</span></span>  
 <span data-ttu-id="daee0-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="daee0-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="daee0-106">Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> Klasse, da eine Zeichenfolge mit Keyframes erstellte Animation nur diskrete Keyframes verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="daee0-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="daee0-107">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> erstellen Sie einen plötzlichen Sprünge zwischen Werten, d. h., Änderungen an der Animation schnell ausgeführt und sind nicht feine.</span><span class="sxs-lookup"><span data-stu-id="daee0-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="daee0-108">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="daee0-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daee0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daee0-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="daee0-110">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="daee0-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="daee0-111">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="daee0-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
