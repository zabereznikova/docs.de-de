---
title: "Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9577f9f08fa1d19aa214bda5a1aef997c2cfa2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="c7e2f-102">Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="c7e2f-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="c7e2f-103">In diesem Beispiel wird das Animieren von Größenänderungen mithilfe von Keyframes veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7e2f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7e2f-104">Example</span></span>  
 <span data-ttu-id="c7e2f-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Media.ArcSegment.Size%2A> Eigenschaft ein <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="c7e2f-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="c7e2f-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="c7e2f-107">Bei der ersten halben Sekunde der Animation verwendet eine Instanz von der <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> Klasse, um die Größe des Bogens allmählich erhöhen. Lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> einen smooth linearen Übergang zwischen den Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="c7e2f-108">Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> Klasse, um die Größe des Bogens abrupt zu erhöhen. Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> erstellen Sie einen plötzlichen Sprünge zwischen Werten, d. h., die größenveränderung der plötzlich auftreten und nicht feine.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3.  <span data-ttu-id="c7e2f-109">Über den letzten zwei Sekunden nutzt eine Instanz von der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> Klasse, um die Größe des Bogens zu erhöhen. Spline-Keyframes wie <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> erstellen Sie einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c7e2f-110">In diesem Beispiel wächst die Größe des Bogens zunächst nur langsam und steigt dann exponentiell zum Ende des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="c7e2f-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c7e2f-111">Das vollständige Beispiel finden Sie unter [Beispiel für KeyFrame-Animationen](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="c7e2f-111">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e2f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e2f-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [<span data-ttu-id="c7e2f-113">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="c7e2f-113">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="c7e2f-114">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="c7e2f-114">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
