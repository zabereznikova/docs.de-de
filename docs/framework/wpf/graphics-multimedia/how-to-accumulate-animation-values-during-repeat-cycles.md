---
title: 'Gewusst wie: Sammeln von Animationswerten während Wiederholungszyklen'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 7b954a388549f1bc6f3fa6ec1bcb2df61cc4e045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557666"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Gewusst wie: Sammeln von Animationswerten während Wiederholungszyklen
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft, um die Animationswerte Wiederholungszyklen.  
  
## <a name="example"></a>Beispiel  
 Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft, um Basiswerte einer Animation Wiederholungszyklen. Angenommen, Sie legen Sie eine Animation auf 9 Mal wiederholt (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 X") und legen Sie die zu animierende zwischen 10 und 15 Eigenschaft (From = 10 To = 15), die Eigenschaft von 10 bis 15 animiert während der ersten Zyklus von 15 bis 20 im zweiten Zyklus , von 20 bis 25 während der dritten Zyklus und So weiter. Daher wird jede Animationszyklus den Endwert der Animation aus der vorherigen Animationszyklus als Basiswert verwendet.  
  
 Sie können die `IsCumulative` Eigenschaft mit dem meisten grundlegenden und die meisten Keyframes Animationen. Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt dieses Verhalten, indem Sie die Breite von vier Rechtecken animieren. Beispiel:  
  
-   Animiert das erste Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft `true`.  
  
-   Animiert das zweite Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> auf den Standardwert der Eigenschaft `false`.  
  
-   Animiert das dritte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `true`.  
  
-   Animiert das letzte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [Wiederholen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
