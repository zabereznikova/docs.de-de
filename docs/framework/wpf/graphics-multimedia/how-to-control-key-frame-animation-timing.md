---
title: 'Vorgehensweise: Steuern der Keyframe-Animationszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 02171c4e2bf444d0bd31bc53fab9d451f081a93c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353724"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Vorgehensweise: Steuern der Keyframe-Animationszeit
Dieses Beispiel zeigt, wie Sie den zeitlichen Ablauf mit Keyframes innerhalb einer Keyframe Animation steuern. Wie andere Animationen, verfügen auch Keyframe-Animationen eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft. Zusätzlich zur Angabe der Dauer einer Animation, müssen Sie angeben, welcher Teil dieser Dauer aller zugehörigen Keyframes zugewiesen wird. Um die Zeit zuzuweisen, geben Sie einen <xref:System.Windows.Media.Animation.KeyTime> für jeden Keyframe der Animation.  
  
 Die <xref:System.Windows.Media.Animation.KeyTime> für jedes Keyframes gibt an, wenn ein Keyframe endet (es gibt keinen die Zeitspanne, die Wiedergabedauer eines Keyframes). Können Sie angeben, ein <xref:System.Windows.Media.Animation.KeyTime> als eine <xref:System.TimeSpan> Wert, der als Prozentsatz oder als die <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> besonderen Wert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> um ein Rechteck auf dem Bildschirm zu animieren. Schlüsselzeiten für Keyframes festgelegt werden, mit <xref:System.TimeSpan> Werte.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")  
  
 Das nächste Beispiel zeigt eine Animation, die identisch ist, jedoch mit Prozentwerten Schlüsselzeiten für Keyframes festgelegt werden.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")  
  
 Im nächsten Beispiel wird <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key Time-Werten.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden am 3.3,6.6, 6,6 und 9,9 Sekunden erreicht](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")  
  
 Im letzten Beispiel wird <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key Time-Werten.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert jedes Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden auf 0, 5 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")  
  
 Der Einfachheit halber die Codeversionen dieses Beispiels lokale Animationen, storyboards, da nur eine einzelne Animation auf eine einzelne Eigenschaft angewendet wird, aber in den Beispielen können geändert werden, um Storyboards zu verwenden. Ein Beispiel, wie Sie ein Storyboard im Code deklarieren, finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012). Weitere Informationen zu den Keyframe-Animationen, finden Sie unter den [Übersicht über Keyframe Animationen](key-frame-animations-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Animationen](animation-overview.md)
- [Themen zu Vorgehensweisen](animation-and-timing-how-to-topics.md)
