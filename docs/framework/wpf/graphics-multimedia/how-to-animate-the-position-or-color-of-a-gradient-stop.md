---
title: 'Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: fcbb546b64810416d3f7dbe052da77b7bc941e7a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395322"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> von <xref:System.Windows.Media.GradientStop> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Animation drei Farbverlaufstopps in einem <xref:System.Windows.Media.LinearGradientBrush>. Im Beispiel werden drei Animationen, von die jede eine unterschiedliche Farbverlaufsunterbrechungspunkte verwendet:  
  
-   Der ersten Animation, einer <xref:System.Windows.Media.Animation.DoubleAnimation>, erstellt eine Animation die ersten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Offset%2A> von 0,0 bis 1,0 und wieder auf 0,0 setzen. Daher wird die erste Farbe im Farbverlauf verändert sich von der linken Seite auf die rechte Seite des Rechtecks, und klicken Sie dann auf der linken Seite zurück.  
  
-   Die zweite Animation, einer <xref:System.Windows.Media.Animation.ColorAnimation>, des zweiten Farbverlaufsstopps animiert <xref:System.Windows.Media.GradientStop.Color%2A> aus <xref:System.Windows.Media.Colors.Purple%2A> zu <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück zur <xref:System.Windows.Media.Colors.Purple%2A>. Daher ändert sich die mittlere Farbe im Farbverlauf von Violett, Gelb und zurück in Violett.  
  
-   Der dritte Animation, einer anderen <xref:System.Windows.Media.Animation.ColorAnimation>, wird die Durchlässigkeit des des dritten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Color%2A> durch 1 und anschließend wieder. Daher wird die dritte Farbe im Farbverlauf verblasst, und klicken Sie dann erneut wird nicht transparent.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Media.LinearGradientBrush>, der Prozess ist identisch für die Animation <xref:System.Windows.Media.GradientStop> Objekte innerhalb einer <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Weitere Beispiele finden Sie unter den [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.GradientStop>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
