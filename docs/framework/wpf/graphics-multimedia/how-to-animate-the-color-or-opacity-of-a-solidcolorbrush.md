---
title: 'Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 194f01d3d5aa4c2b5a08a6c3fdb3dc195b0e9e3e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392226"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden drei Animationen verwendet, zum Animieren der <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.SolidColorBrush>.  
  
-   Der ersten Animation, einer <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels auf <xref:System.Windows.Media.Colors.Gray%2A> Wenn die Maus in das Rechteck eintritt.  
  
-   Der nächsten Animation, einer anderen <xref:System.Windows.Media.Animation.ColorAnimation>, ändert sich die Farbe des Pinsels auf <xref:System.Windows.Media.Colors.Orange%2A> Wenn sich der Mauszeiger in des Rechtecks.  
  
-   Der letzten Animation, einer <xref:System.Windows.Media.Animation.DoubleAnimation>, wird die Durchlässigkeit des Pinsels zu 0,0 geändert, wenn die linke Maustaste gedrückt wird.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Ein ausführlicheres Beispiel, zeigt, wie sich unterschiedliche Pinseltypen animiert, finden Sie unter den [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen zur Animation finden Sie unter den [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Verwenden Sie für Konsistenz mit anderen Animationsbeispielen die Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt zum Anwenden der Animationen. Beim Anwenden einer Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode anstelle einer <xref:System.Windows.Media.Animation.Storyboard>. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973)
