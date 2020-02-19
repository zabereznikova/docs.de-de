---
title: 'Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452895"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)
Dieses Beispiel zeigt, wie ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath>-Objekt verwendet wird, um eine <xref:System.Windows.Point> entlang eines gekrümmten Pfads zu animieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.EllipseGeometry> entlang eines durch einen <xref:System.Windows.Media.PathGeometry>definierten Pfads verschoben. Die <xref:System.Windows.Media.EllipseGeometry.Center%2A>-Eigenschaft der Ellipse, die einen <xref:System.Windows.Point> Wert annimmt, gibt die Position an. zum Verschieben der Ellipse-Geometrie animieren Sie die <xref:System.Windows.Media.EllipseGeometry.Center%2A>-Eigenschaft. Im Beispiel wird eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> verwendet, um die <xref:System.Windows.Media.EllipseGeometry.Center%2A>-Eigenschaft des <xref:System.Windows.Media.EllipseGeometry>-Objekts zu animieren.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Das komplette Beispiel finden Sie unter [Beispiel für Pfad Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 In der Code Version des vorangehenden Beispiels wurde ein <xref:System.Windows.Media.Animation.Storyboard> zum Animieren des <xref:System.Windows.Media.EllipseGeometry>verwendet, obwohl nur eine Animation angewendet wurde. Eine <xref:System.Windows.Media.Animation.Storyboard> ist oft die einfachste Möglichkeit, mehrere Animationen anzuwenden, da diese Animationen durch denselben <xref:System.Windows.Media.Animation.Storyboard>gesteuert werden können. Eine einfachere Möglichkeit, eine einzelne Animation auf eine Eigenschaft anzuwenden, wenn Sie Code verwenden, ist jedoch die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>-Methode. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel zu Textanimation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Übersicht über Animationen](animation-overview.md)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
