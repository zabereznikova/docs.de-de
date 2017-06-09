---
title: "Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Keyframes [WPF], Planen"
  - "Zeitsteuerung der Keyframe-Animation"
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Zeitliche Steuerung einer Keyframe-Animation
Dieses Beispiel zeigt, wie Keyframes innerhalb einer Keyframe\-Animation zeitlich gesteuert werden können.  Wie andere Animationen, verfügen auch Keyframe\-Animationen über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A>\-Eigenschaft.  Zusätzlich zu der Animationsdauer muss auch angegeben werden, welcher Teil dieser Dauer den einzelnen Keyframes zugewiesen wird.  Um die Zeit zuzuweisen, wird eine <xref:System.Windows.Media.Animation.KeyTime> für jeden Keyframe in der Animation angegeben.  
  
 Die <xref:System.Windows.Media.Animation.KeyTime> gibt das Ende für jeden Keyframe an \(es wird nicht angegeben, wie lange ein Keyframe läuft\).  Sie können eine <xref:System.Windows.Media.Animation.KeyTime> als <xref:System.TimeSpan>\-Wert, in Prozent oder als speziellen <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>\- oder <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\-Wert angeben.  
  
## Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> verwendet, um ein Rechteck über den Bildschirm zu bewegen.  Die Schlüsselzeiten der Keyframes werden mit <xref:System.TimeSpan>\-Werten festgelegt.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 Die folgende Abbildung zeigt, wann der Wert jedes Keyframes erreicht ist.  
  
 ![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm\_keyframe\_keytime1\_timespan")  
  
 Das folgende Beispiel zeigt eine beinah identische Animation, bei der jedoch die Schlüsselzeiten der Keyframes mit Prozentwerten festgelegt sind.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 Die folgende Abbildung zeigt, wann der Wert jedes Keyframes erreicht ist.  
  
 ![Schlüsselwerte werden nach 3, 4 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm\_keyframe\_keytime2\_percentage")  
  
 Im folgenden Beispiel werden <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>\-Schlüsselzeitwerte verwendet.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 Die folgende Abbildung zeigt, wann der Wert jedes Keyframes erreicht ist.  
  
 ![Schlüsselwerte werden nach 3,3, 6,6 und 9,9 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm\_keyframe\_keytime3\_uniform")  
  
 Im abschließenden Beispiel werden <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\-Schlüsselzeitwerte verwendet.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 Die folgende Abbildung zeigt, wann der Wert jedes Keyframes erreicht ist.  
  
 ![Schlüsselwerte werden nach 0, 5 und 10 Sekunden erreicht](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm\_keyframe\_keytime4\_paced")  
  
 Der Einfachheit halber verwenden die Codeversionen dieses Beispiels lokale Animationen statt Storyboards, da nur eine Animation auf eine Eigenschaft angewendet wird. Das Beispiel kann jedoch auch für den Gebrauch von Storyboards geändert werden.  Ein Beispiel für ein im Code deklariertes Storyboard finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  Weitere Informationen zu Keyframe\-Animationen finden Sie unter [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
## Siehe auch  
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)