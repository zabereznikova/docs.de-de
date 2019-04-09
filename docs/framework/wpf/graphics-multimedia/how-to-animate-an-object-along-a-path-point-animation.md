---
title: 'Vorgehensweise: Animieren eines Objekts entlang eines Pfads (Punktanimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: 4ef28118975d02500916676ca50e0f9622c7a3e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129584"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Vorgehensweise: Animieren eines Objekts entlang eines Pfads (Punktanimation)
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zu animierende Objekt eine <xref:System.Windows.Point> entlang eines gekrümmten Pfads.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.EllipseGeometry> entlang eines Pfads durch eine <xref:System.Windows.Media.PathGeometry>. Des EllipseGeometry-Objekts <xref:System.Windows.Media.EllipseGeometry.Center%2A> -Eigenschaft, die nimmt eine <xref:System.Windows.Point> Wert, gibt an, dessen Position an; um das EllipseGeometry-Objekt, animieren Sie verschieben die <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft. Im Beispiel wird eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zum Animieren der <xref:System.Windows.Media.EllipseGeometry> des Objekts <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Die Codeversion des vorhergehenden Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.Media.EllipseGeometry>, auch wenn nur eine einzige Animation angewendet wurde. Ein <xref:System.Windows.Media.Animation.Storyboard> ist häufig der einfachste Weg, mehrere Animationen anzuwenden, da diese vom selben gesteuert werden können <xref:System.Windows.Media.Animation.Storyboard>. Eine einfachere Möglichkeit, eine einzelne Animation auf eine Eigenschaft anwenden, wenn Sie Code verwenden jedoch ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Übersicht über Animationen](animation-overview.md)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
