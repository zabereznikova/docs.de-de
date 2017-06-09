---
title: "Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation) | Microsoft Docs"
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
  - "Animation Objekte entlang Pfade (Punktanimation)"
  - "Punktanimation"
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Animieren eines Objekts entlang eines Pfads (PointAnimation)
Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Media.Animation.PointAnimationUsingPath> zu animierende Objekt eine <xref:System.Windows.Point> einem gekrümmten Pfad.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.EllipseGeometry> entlang eines Pfads definiert eine <xref:System.Windows.Media.PathGeometry>. Des EllipseGeometry-Objekts <xref:System.Windows.Media.EllipseGeometry.Center%2A> -Eigenschaft und eine <xref:System.Windows.Point> -Wert, gibt die Position, um das EllipseGeometry-Objekt, animieren Sie verschieben die <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft. Im Beispiel wird ein <xref:System.Windows.Media.Animation.PointAnimationUsingPath> Animieren der <xref:System.Windows.Media.EllipseGeometry> des Objekts <xref:System.Windows.Media.EllipseGeometry.Center%2A> Eigenschaft.  
  
 [!code-xml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Die Codeversion des vorherigen Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> Animieren der <xref:System.Windows.Media.EllipseGeometry>, obwohl nur eine einzige Animation angewendet wurde. Ein <xref:System.Windows.Media.Animation.Storyboard> ist oft die einfachste Möglichkeit, mehrere Animationen anzuwenden, da diese vom selben gesteuert werden können <xref:System.Windows.Media.Animation.Storyboard>. Ist jedoch eine einfachere Möglichkeit, eine einzelne Animation auf eine Eigenschaft anwenden, wenn Sie Code verwenden, verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Pfad-Themen zur Pfadanimation](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)