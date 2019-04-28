---
title: 'Vorgehensweise: Animieren der Position eines Objekts mithilfe von PointAnimation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651349"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Vorgehensweise: Animieren der Position eines Objekts mithilfe von PointAnimation
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.PointAnimation> -Klasse zum Animieren eines Objekts entlang einer <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Ellipse entlang einer <xref:System.Windows.Shapes.Path> von einem Punkt auf dem Bildschirm in eine andere. Im Beispiel wird die Position des animiert ein <xref:System.Windows.Media.EllipseGeometry> mit <xref:System.Windows.Media.Animation.PointAnimation> zum Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [Übersicht über Animationen](animation-overview.md)
- [Grafiken und Multimedia](index.md)
- [Grafiken: Themen zur Vorgehensweise](graphics-how-to-topics.md)
- [Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen](animation-and-timing-how-to-topics.md)
