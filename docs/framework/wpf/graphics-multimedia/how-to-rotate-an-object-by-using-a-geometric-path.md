---
title: "Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Drehen von Objekten um geometrische Pfade"
  - "Drehen von Objekten um geometrische Pfade"
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads
In diesem Beispiel wird gezeigt, wie zum Drehen ein Objekts entlang eines geometrischen Pfads, die durch definiert ist ein <xref:System.Windows.Media.PathGeometry> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet drei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben.  
  
-   Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert eine <xref:System.Windows.Media.RotateTransform> , die auf das Rechteck angewendet wird. Die Animation generiert Winkel. Es ist das Rechteck entlang der Konturen des Pfads drehen.  
  
-   Die anderen beiden Objekte animieren der <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Werte von einer <xref:System.Windows.Media.TranslateTransform> , die auf das Rechteck angewendet wird. Sie stellen das Rechteck horizontal und vertikal am Pfad entlang verschoben.  
  
 [!code-xml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Eine weitere Möglichkeit zum Drehen eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt, und legen seine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaft `true`. Weitere Informationen und ein Beispiel finden Sie unter [Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Pfad-Themen zur Pfadanimation](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)