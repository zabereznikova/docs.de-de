---
title: 'Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)'
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47cafab505bcbab7008385393bbacf093e264cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zu animierende Objekt eine <xref:System.Windows.Point> entlang eines Kurvenpfads.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.EllipseGeometry> entlang eines Pfads, definiert durch eine <xref:System.Windows.Media.PathGeometry>. Der Ellipsengeometrie <xref:System.Windows.Media.EllipseGeometry.Center%2A> -Eigenschaft, die nimmt eine <xref:System.Windows.Point> Wert und gibt dessen Position; zum Verschieben der Geometrie Ellipse animieren Sie seine <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft. Im Beispiel wird eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zum Animieren der <xref:System.Windows.Media.EllipseGeometry> des Objekts <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Die Codeversion des obigen Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.Media.EllipseGeometry>, obwohl nur eine einzige Animation angewendet wurde. Ein <xref:System.Windows.Media.Animation.Storyboard> ist häufig der einfachste Weg, mehrere Animationen anzuwenden, da diese mit dem gleichen gesteuert werden können <xref:System.Windows.Media.Animation.Storyboard>. Eine einfachere Möglichkeit zum Anwenden einer einzelnen Animation auf eine Eigenschaft, wenn Code mit allerdings ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel zu Textanimation](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
