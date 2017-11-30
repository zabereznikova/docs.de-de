---
title: 'Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation'
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
- key frames [WPF], timing
- timing key-fram animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bc3566cf25282749a09c5f2372cd1c81e3ce881
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-key-frame-animation-timing"></a>Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation
Dieses Beispiel zeigt, wie die zeitliche Abfolge von Keyframes innerhalb einer Keyframe Animation steuern. Wie andere Animationen Keyframe-Animationen haben eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Eigenschaft. Zusätzlich zur Angabe der Dauer der Animation, müssen Sie angeben, welcher Teil dieser Dauer auf die einzelnen Keyframes zugewiesen wird. Um die Zeit zuzuweisen, geben Sie einen <xref:System.Windows.Media.Animation.KeyTime> für jeden Keyframe in der Animation.  
  
 Die <xref:System.Windows.Media.Animation.KeyTime> für jede Keyframes gibt an, wenn eine Keyframes endet (es gibt keinen die Zeitdauer, die ein Keyframe spielt). Können Sie angeben, eine <xref:System.Windows.Media.Animation.KeyTime> als eine <xref:System.TimeSpan> als Prozentsatz oder als Wert der <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> Spezialwert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> um ein Rechteck über den Bildschirm bewegen. Wie oft der Keyframes-Schlüssel festgelegt <xref:System.TimeSpan> Werte.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")  
  
 Das nächste Beispiel zeigt eine Animation, die nahezu identisch, außer, dass der Keyframes Key Zeiten mit Prozentwerten festgelegt sind.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xaml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")  
  
 Im nächste Beispiel wird <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key Time-Werten.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xaml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden am 3.3,6.6 und 9,9 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")  
  
 Im abschließenden Beispiel verwendet <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key Time-Werten.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xaml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 Die folgende Abbildung zeigt, wenn der Wert der einzelnen Keyframes erreicht wird.  
  
 ![Schlüsselwerte werden nach 0, 5 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")  
  
 Der Einfachheit halber die Codeversionen dieses Beispiels lokale Animationen, storyboards, da nur eine Animation auf eine einzelne Eigenschaft angewendet wird, aber in den Beispielen möglicherweise geändert werden, um Storyboards stattdessen zu verwenden. Ein Beispiel zeigt, wie ein Storyboard im Code deklariert ist, finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für KeyFrame-Animationen](http://go.microsoft.com/fwlink/?LinkID=160012). Weitere Informationen zu Keyframe-Animationen, finden Sie unter der [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
