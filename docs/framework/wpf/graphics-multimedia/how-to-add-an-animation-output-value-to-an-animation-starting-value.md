---
title: 'Gewusst wie: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: bae7bf57507e3345c92cbbaf24491d86772425a4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407050"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="07e6b-102">Gewusst wie: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert</span><span class="sxs-lookup"><span data-stu-id="07e6b-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="07e6b-103">Dieses Beispiel zeigt das Hinzufügen ein Animationsausgabewerts zu einem Animationsstartwert.</span><span class="sxs-lookup"><span data-stu-id="07e6b-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07e6b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07e6b-104">Example</span></span>  
 <span data-ttu-id="07e6b-105">Die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft gibt an, ob den Ausgabewert einer Animation, auf den Startwert (Basiswert) einer animierten Eigenschaft hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="07e6b-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="07e6b-106">Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft mit dem meisten grundlegenden und die meisten Keyframe-Animationen.</span><span class="sxs-lookup"><span data-stu-id="07e6b-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="07e6b-107">Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="07e6b-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="07e6b-108">Das folgende Beispiel zeigt die Auswirkungen der Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimation> und Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="07e6b-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="07e6b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07e6b-109">See Also</span></span>  
 [<span data-ttu-id="07e6b-110">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="07e6b-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="07e6b-111">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="07e6b-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="07e6b-112">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="07e6b-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="07e6b-113">Animations- und Zeitsteuerungssystem</span><span class="sxs-lookup"><span data-stu-id="07e6b-113">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="07e6b-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="07e6b-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
