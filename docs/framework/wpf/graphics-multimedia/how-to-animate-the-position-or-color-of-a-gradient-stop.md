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
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452843"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> von <xref:System.Windows.Media.GradientStop> Objekten animieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden drei Farbverlaufs Stopps in einer <xref:System.Windows.Media.LinearGradientBrush>animiert. In diesem Beispiel werden drei Animationen verwendet, von denen jede einen anderen Farbverlaufs-halte Vorgang animiert:  
  
- Die erste Animation, eine <xref:System.Windows.Media.Animation.DoubleAnimation>, animiert die <xref:System.Windows.Media.GradientStop.Offset%2A> des ersten Farbverlaufs Stopps von 0,0 auf 1,0 und dann zurück zu 0,0. Folglich verschiebt sich die erste Farbe im Farbverlauf von der linken zum rechten Rand des Rechtecks und dann zurück zur linken Seite.  
  
- Die zweite Animation, eine <xref:System.Windows.Media.Animation.ColorAnimation>, animiert die <xref:System.Windows.Media.GradientStop.Color%2A> des zweiten Farbverlaufs Stopps von <xref:System.Windows.Media.Colors.Purple%2A> bis <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück zu <xref:System.Windows.Media.Colors.Purple%2A>. Folglich wechselt die Mittel Farbe im Farbverlauf von lila in gelb und zurück zu Lila.  
  
- Die dritte Animation, eine weitere <xref:System.Windows.Media.Animation.ColorAnimation>, animiert die Deckkraft des <xref:System.Windows.Media.GradientStop.Color%2A> des dritten Farbverlaufs Stopps durch-1 und dann zurück. Folglich wird die dritte Farbe im Farbverlauf ausgeblendet und dann wieder transparent.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Obwohl in diesem Beispiel eine <xref:System.Windows.Media.LinearGradientBrush>verwendet wird, ist der Prozess für das Animieren <xref:System.Windows.Media.GradientStop> Objekten innerhalb einer <xref:System.Windows.Media.RadialGradientBrush>identisch.  
  
 Weitere Beispiele finden Sie im [Beispiel Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.GradientStop>
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
