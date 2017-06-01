---
title: "Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation) | Microsoft Docs"
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
  - "Offsetakkumulation"
  - "Animation Objekte entlang Pfade (Matrixanimation mit Offsetakkumulation)"
  - "Matrixanimation mit Offsetakkumulation"
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation)
Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> -Klasse zum Animieren eines Objekts entlang eines Pfads und der Animation den Offset-Werte sowie die Akkumulation.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft ein <xref:System.Windows.Media.MatrixTransform> auf eine Schaltfläche angewendet. Daher wird eine Schaltfläche einem gekrümmten Pfad verschoben.  
  
 Außerdem im Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> Eigenschaft `true`, sodass der Offset der animierten Matrix bei jeder Wiederholung der Animation akkumuliert. Da die Offsetakkumulation verschiebt die Schaltfläche Weiter auf dem Bildschirm beim Wiederholen der Animation, sondern an die Anfangsposition zurücksetzen.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Beachten Sie, dass, obwohl die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> Eigenschaft bewirkt, dass Offsetwerten über Wiederholungen ansammeln, nicht dadurch Drehung Werte kumuliert. Drehwinkel akkumuliert legen fest, um der Animation <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> und <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> Eigenschaften `true`.  
  
 Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028). Ein Beispiel für das Animieren einer <xref:System.Windows.Media.Matrix> Wert entlang eines Pfads ohne Offsetakkumulation, finden Sie unter [animieren Sie ein Objekt entlang einer Pfad (Matrixanimation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Pfad-Themen zur Pfadanimation](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)