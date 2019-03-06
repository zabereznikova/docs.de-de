---
title: 'Vorgehensweise: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: f27a214d4fa6fd33d993e7ae458ebb736b60bed7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351956"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="0b21f-102">Vorgehensweise: Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert</span><span class="sxs-lookup"><span data-stu-id="0b21f-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="0b21f-103">Dieses Beispiel zeigt das Hinzufügen ein Animationsausgabewerts zu einem Animationsstartwert.</span><span class="sxs-lookup"><span data-stu-id="0b21f-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b21f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b21f-104">Example</span></span>  
 <span data-ttu-id="0b21f-105">Die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft gibt an, ob den Ausgabewert einer Animation, auf den Startwert (Basiswert) einer animierten Eigenschaft hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b21f-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="0b21f-106">Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Eigenschaft mit dem meisten grundlegenden und die meisten Keyframe-Animationen.</span><span class="sxs-lookup"><span data-stu-id="0b21f-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="0b21f-107">Weitere Informationen finden Sie unter [Übersicht über Animationen](animation-overview.md) und [Übersicht über Keyframe Animationen](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0b21f-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="0b21f-108">Das folgende Beispiel zeigt die Auswirkungen der Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimation> und Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> Eigenschaft mit dem <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="0b21f-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0b21f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b21f-109">See also</span></span>
- [<span data-ttu-id="0b21f-110">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="0b21f-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="0b21f-111">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="0b21f-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0b21f-112">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="0b21f-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="0b21f-113">Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="0b21f-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
