---
title: "Gewusst wie: Animieren der Farbe oder der Durchl&#228;ssigkeit von SolidColorBrush | Microsoft Docs"
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
  - "Animation, Farbe von SolidColorBrush"
  - "Animation, Durchlässigkeit von SolidColorBrush"
  - "Farben, Animation"
  - "Durchlässigkeit, Animation"
  - "SolidColorBrush, Animieren der Farbe von"
  - "SolidColorBrush, Animieren der Durchlässigkeit von"
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Animieren der Farbe oder der Durchl&#228;ssigkeit von SolidColorBrush
In diesem Beispiel wird das Animieren von <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> für <xref:System.Windows.Media.SolidColorBrush> gezeigt.  
  
## Beispiel  
 Im folgenden Beispiel werden drei Animationen verwendet, um <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> für <xref:System.Windows.Media.SolidColorBrush> zu animieren.  
  
-   Mit der ersten Animation, einer <xref:System.Windows.Media.Animation.ColorAnimation>, wird die Farbe des Pinsels in <xref:System.Windows.Media.Colors.Gray%2A> geändert, wenn die Maus in das Rechteck eintritt.  
  
-   Mit der nächsten Animation, einer anderen <xref:System.Windows.Media.Animation.ColorAnimation>, wird die Farbe des Pinsels in <xref:System.Windows.Media.Colors.Orange%2A> geändert, wenn die Maus das Rechteck verlässt.  
  
-   Mit der letzten Animation, einer <xref:System.Windows.Media.Animation.DoubleAnimation>, wird die Durchlässigkeit des Pinsels zu 0,0 geändert, wenn die linke Maustaste gedrückt wird.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Ein ausführlicheres Beispiel, mit dem gezeigt wird, wie unterschiedliche Pinseltypen animiert werden, finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  Weitere Informationen zur Animation finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Aus Gründen der Konsistenz mit anderen Animationsbeispielen wird in den Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard>\-Objekt zum Anwenden der Animationen verwendet.  Beim Anwenden einer Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode anstelle von <xref:System.Windows.Media.Animation.Storyboard> zu verwenden.  Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973)