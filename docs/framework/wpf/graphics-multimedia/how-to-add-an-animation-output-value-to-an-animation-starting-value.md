---
title: "Gewusst wie: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1a6a5923655c5857b813df778b36b6c7fd208b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="ae173-102">Gewusst wie: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert</span><span class="sxs-lookup"><span data-stu-id="ae173-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="ae173-103">In diesem Beispiel wird gezeigt, wie ein Anfangswert der Animation einen Ausgabewert der Animation hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ae173-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae173-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae173-104">Example</span></span>  
 <span data-ttu-id="ae173-105">Die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft gibt an, ob den Ausgabewert der Animation auf den Startwert (Basiswert) einer animierten Eigenschaft hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae173-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="ae173-106">Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft mit dem meisten grundlegenden und die meisten Keyframes Animationen.</span><span class="sxs-lookup"><span data-stu-id="ae173-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="ae173-107">Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ae173-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="ae173-108">Das folgende Beispiel zeigt die Auswirkung der Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimation> und mithilfe der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="ae173-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ae173-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae173-109">See Also</span></span>  
 [<span data-ttu-id="ae173-110">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="ae173-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="ae173-111">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="ae173-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ae173-112">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="ae173-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="ae173-113">Animation und zeitlichen Steuerung</span><span class="sxs-lookup"><span data-stu-id="ae173-113">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="ae173-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="ae173-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
