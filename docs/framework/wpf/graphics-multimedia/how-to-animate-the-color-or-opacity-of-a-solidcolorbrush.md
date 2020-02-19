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
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452882"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Gewusst wie: Animieren der Farbe oder der Durchlässigkeit von SolidColorBrush
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> eines <xref:System.Windows.Media.SolidColorBrush>animieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden drei Animationen verwendet, um die <xref:System.Windows.Media.SolidColorBrush.Color%2A> und <xref:System.Windows.Media.Brush.Opacity%2A> eines <xref:System.Windows.Media.SolidColorBrush>zu animieren.  
  
- Die erste Animation, eine <xref:System.Windows.Media.Animation.ColorAnimation>, ändert die Farbe des Pinsels in <xref:System.Windows.Media.Colors.Gray%2A>, wenn die Maus in das Rechteck gelangt.  
  
- Die nächste Animation, eine weitere <xref:System.Windows.Media.Animation.ColorAnimation>, ändert die Farbe des Pinsels in <xref:System.Windows.Media.Colors.Orange%2A>, wenn der Mauszeiger das Rechteck verlässt.  
  
- Die abschließende Animation, eine <xref:System.Windows.Media.Animation.DoubleAnimation>, ändert die Deckkraft des Pinsels in 0,0, wenn die linke Maustaste gedrückt wird.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Ein ausführeres Beispiel, das zeigt, wie Sie verschiedene Arten von Pinseln animieren, finden Sie im [Beispiel Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Weitere Informationen zur Animation finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
 Aus Gründen der Konsistenz mit anderen Animations Beispielen wird in den Code Versionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard> Objekt verwendet, um Ihre Animationen anzuwenden. Beim Anwenden einer einzelnen Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode zu verwenden, anstatt eine <xref:System.Windows.Media.Animation.Storyboard>zu verwenden. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
- [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
