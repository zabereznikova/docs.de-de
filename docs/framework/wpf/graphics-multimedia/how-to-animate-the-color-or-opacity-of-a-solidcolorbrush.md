---
title: "Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bac3ae90fa0fa2229e236f46b8884c942b99bef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush
In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet drei Animationen zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.  
  
-   Die erste Animation eine <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels zum <xref:System.Windows.Media.Colors.Gray%2A> Wenn der Mauszeiger in das Rechteck eintritt.  
  
-   Die nächste Animation, eine andere <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels zum <xref:System.Windows.Media.Colors.Orange%2A> Wenn die Maus das Rechteck verlässt.  
  
-   Die endgültige Animation eine <xref:System.Windows.Media.Animation.DoubleAnimation>, ändert sich die Durchlässigkeit des Pinsels in 0,0, wenn die linke Maustaste gedrückt wird.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Ein ausführlicheres Beispiel, das zeigt, wie verschiedene Typen von Pinsel animiert, finden Sie unter der [Pinsel Beispiel](http://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen zur Animation finden Sie unter der [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Aus Gründen der Konsistenz mit anderen Animation Beispiele für die Codeversionen der in diesem Beispiel verwenden eine <xref:System.Windows.Media.Animation.Storyboard> Objekt, das ihre Animationen angewendet. Beim Anwenden einer Animation im Code ist es jedoch einfacher zu verwenden, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973)
