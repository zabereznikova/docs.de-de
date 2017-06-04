---
title: "Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts | Microsoft Docs"
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
  - "Animation, Farbe von GradientStop-Objekten"
  - "Animation, Position von GradientStop-Objekten"
  - "Farben, Animation"
  - "GradientStop-Objekte, Animieren der Farbe von"
  - "GradientStop-Objekte, Animieren der Position von"
  - "Position, Animation"
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Animieren der Position oder Farbe eines Farbverlaufunterbrechungspunkts
In diesem Beispiel wird das Animieren von <xref:System.Windows.Media.GradientStop.Color%2A> und <xref:System.Windows.Media.GradientStop.Offset%2A> für <xref:System.Windows.Media.GradientStop>\-Objekte gezeigt.  
  
## Beispiel  
 Im folgenden Beispiel werden drei Farbverlaufsunterbrechungspunkte in einem <xref:System.Windows.Media.LinearGradientBrush> animiert.  Die drei Animationen in dem Beispiel animieren drei unterschiedliche Farbverlaufsunterbrechungspunkte:  
  
-   Mit der ersten Animation \(<xref:System.Windows.Media.Animation.DoubleAnimation>\) wird der <xref:System.Windows.Media.GradientStop.Offset%2A>\-Wert des ersten Farbverlaufsstopps von 0,0 in 1,0 und zurück in 0,0 geändert.  Das Ergebnis: Die erste Farbe im Farbverlauf verändert sich im Rechteck von links nach rechts und dann zurück nach links.  
  
-   Mit der zweiten Animation \(<xref:System.Windows.Media.Animation.ColorAnimation>\) wird der <xref:System.Windows.Media.GradientStop.Color%2A>\-Wert des zweiten Unterbrechungspunkts von <xref:System.Windows.Media.Colors.Purple%2A> in <xref:System.Windows.Media.Colors.Yellow%2A> und dann zurück in <xref:System.Windows.Media.Colors.Purple%2A> geändert.  Das Ergebnis: Die zweite Farbe im Verlauf ändert sich von violett in gelb und dann zurück in violett.  
  
-   Mit der dritten Animation \(<xref:System.Windows.Media.Animation.ColorAnimation>\) wird die Durchlässigkeit des <xref:System.Windows.Media.GradientStop.Color%2A>\-Werts für den dritten Unterbrechungspunkt um \-1 und zurück geändert.  Das Ergebnis: Die dritte Farbe im Verlauf wird transparenter und anschließend wieder deckend.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 In diesem Beispiel wird ein <xref:System.Windows.Media.LinearGradientBrush> verwendet. Der Prozess für die Animation von <xref:System.Windows.Media.GradientStop>\-Objekten in einem <xref:System.Windows.Media.RadialGradientBrush> ist jedoch derselbe.  
  
 Weitere Beispiele finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## Siehe auch  
 <xref:System.Windows.Media.GradientStop>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)