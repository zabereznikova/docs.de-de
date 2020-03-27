---
title: 'Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344733"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation

In diesem Beispiel wird gezeigt, wie das Timing von Schlüsselbildern in einer Keyframe-Animation gesteuert wird. Wie andere Animationen verfügen Keyframe-Animationen über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft. Zusätzlich zur Angabe der Dauer einer Animation müssen Sie angeben, welcher Teil dieser Dauer jedem seiner Schlüsselbilder zugewiesen ist. Um die Zeit zuzumachen, geben Sie für jeden Schlüsselrahmen in der Animation eine <xref:System.Windows.Media.Animation.KeyTime> an.

Der <xref:System.Windows.Media.Animation.KeyTime> für jeden Schlüsselrahmen gibt an, wann ein Schlüsselrahmen endet (er gibt nicht an, wie lange ein Schlüsselrahmen abgespielt wird). Sie können <xref:System.Windows.Media.Animation.KeyTime> einen <xref:System.TimeSpan> Wert als Wert, als <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> Prozentsatz <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> oder als oder als Sonderwert angeben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> wird ein verwendet, um ein Rechteck auf dem Bildschirm zu animieren. Die Schlüsselzeiten der Keyframes <xref:System.TimeSpan> werden mit Werten festgelegt.

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.

![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

Das nächste Beispiel zeigt eine Animation, die identisch ist, mit der Ausnahme, dass die Schlüsselzeiten der Schlüsselrahmen mit Prozentwerten festgelegt sind.

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.

![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

Im nächsten <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> Beispiel werden wichtige Zeitwerte verwendet.

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.

![Schlüsselwerte werden nach 3,3, 6,6 und 9,9 Sekunden erreicht](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

Im letzten <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> Beispiel werden wichtige Zeitwerte verwendet.

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

Die folgende Abbildung zeigt, wann der Wert jedes Schlüsselrahmens erreicht ist.

![Schlüsselwerte werden nach 0, 5 und 10 Sekunden erreicht](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

Der Einfachheit halber verwenden die Codeversionen dieses Beispiels lokale Animationen und keine Storyboards, da nur eine einzelne Animation auf eine einzelne Eigenschaft angewendet wird, die Beispiele jedoch geändert werden können, um Storyboards stattdessen zu verwenden. Ein Beispiel zum Deklarieren eines Storyboards im Code finden Sie unter [Animieren einer Eigenschaft mithilfe eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md).

Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation). Weitere Informationen zu Keyframe-Animationen finden Sie in der [Key-Frame-Animationsübersicht](key-frame-animations-overview.md).

## <a name="see-also"></a>Siehe auch

- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Übersicht über Animationen](animation-overview.md)
- [Gewusst wie-Themen](animation-and-timing-how-to-topics.md)
