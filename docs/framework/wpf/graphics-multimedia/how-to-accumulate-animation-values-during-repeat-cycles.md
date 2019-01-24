---
title: 'Vorgehensweise: Sammeln von Animationen während Wiederholungszyklen'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 6e98b7eefd0c30e728b60926096c0f082bc079ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587280"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Vorgehensweise: Sammeln von Animationen während Wiederholungszyklen
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft für "accumulate" Animationswerten während Wiederholungszyklen.  
  
## <a name="example"></a>Beispiel  
 Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft, um die Basiswerte einer Animation Wiederholungszyklen. Angenommen, Sie festlegen, dass eine Animation 9-Mal wiederholt werden soll (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 X"), und legen Sie die Eigenschaft animiert zwischen 10 und 15 (From = 10 To = 15), die Eigenschaft von 10 bis 15 animiert während des ersten Zyklus von 15 bis 20, bei der zweiten , von 20 bis 25 während der dritten Zyklus und So weiter. Daher verwendet jeder Animationszyklus den Endwert der Animation aus der vorherigen Animationszyklus als Basiswert.  
  
 Sie können die `IsCumulative` Eigenschaft mit dem meisten grundlegenden und die meisten Keyframe-Animationen. Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Übersicht über Keyframe Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Das folgende Beispiel zeigt dieses Verhalten, indem Sie die Breite von vier Rechtecken animieren. Beispiel:  
  
-   Erstellt eine Animation die erste Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft `true`.  
  
-   Animiert das zweite Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft auf den Standardwert des `false`.  
  
-   Animiert die dritte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `true`.  
  
-   Animiert die letzte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [Wiederholen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)
- [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
