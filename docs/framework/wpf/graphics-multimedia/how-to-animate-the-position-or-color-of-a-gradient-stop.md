---
title: 'Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts'
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
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c5a72d5df9d7ff9cdd90d6e09a7dab574e2caaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts
In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> von <xref:System.Windows.Media.GradientStop> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Animation drei Farbverlaufsstopps innerhalb einer <xref:System.Windows.Media.LinearGradientBrush>. Das Beispiel verwendet drei Animationen, von die jedes einen anderen Farbverlaufsstopps animiert.  
  
-   Die erste Animation eine <xref:System.Windows.Media.Animation.DoubleAnimation>, erstellt eine Animation des ersten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Offset%2A> von 0,0 bis 1,0, und klicken Sie dann auf 0,0 sichern. Daher die erste im Farbverlauf verändert sich von der linken Seite auf die rechte Seite des Rechtecks-Farbe aus, und klicken Sie dann auf die linke Seite zurück.  
  
-   Die zweite Animation eine <xref:System.Windows.Media.Animation.ColorAnimation>, erstellt eine Animation des zweiten Farbverlaufsstopps <xref:System.Windows.Media.GradientStop.Color%2A> aus <xref:System.Windows.Media.Colors.Purple%2A> auf <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück in <xref:System.Windows.Media.Colors.Purple%2A>. Daher ändert sich die mittlere Farbe im Verlauf von Violett, Gelb und zurück in Violett.  
  
-   Die dritte Animation, eine andere <xref:System.Windows.Media.Animation.ColorAnimation>, wird die Durchlässigkeit des dritten Farbverlaufsstopps des <xref:System.Windows.Media.GradientStop.Color%2A> mit-1 und dann wieder. Daher wird die dritte Farbe im Farbverlauf ausgeblendet, und klicken Sie dann erneut wird nicht transparent.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Obwohl in diesem Beispiel verwendet eine <xref:System.Windows.Media.LinearGradientBrush>, der Prozess entspricht dem für die Animation <xref:System.Windows.Media.GradientStop> Objekte innerhalb einer <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Weitere Beispiele finden Sie unter der [Pinsel Beispiel](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.GradientStop>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
