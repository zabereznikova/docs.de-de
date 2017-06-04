---
title: "Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, RectangleGeometry-Objekte mit Keyframes"
  - "Keyframes, Animieren von RectangleGeometry-Objekten mit"
  - "RectangleGeometry-Objekte, Animieren mit Keyframes"
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Animieren einer Rechteckgeometrie mithilfe von Keyframes
In diesem Beispiel wird die Animation der <xref:System.Windows.Media.RectangleGeometry.Rect%2A>\-Eigenschaft einer <xref:System.Windows.Media.RectangleGeometry> mithilfe von Keyframes veranschaulicht.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Media.RectangleGeometry.Rect%2A>\-Eigenschaft eines <xref:System.Windows.Media.RectangleGeometry> zu animieren.  In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In den ersten zwei Sekunden wird die Instanz der <xref:System.Windows.Media.Animation.LinearRectKeyFrame>\-Klasse verwendet, um Position, Breite und Höhe eines Rechtecks graduell zu ändern.  Durch lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearRectKeyFrame> wird ein glatter, linearer Übergang zwischen Werten ermöglicht.  
  
2.  Am Ende der nächsten halben Sekunde wird die Instanz einer <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>\-Klasse verwendet, um die Höhe des Rechtecks abrupt zu verringern.  Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> ermöglichen abrupte Änderungen zwischen Werten, d.h. die Verringerung der Höhe tritt schnell und deutlich sichtbar ein.  
  
3.  In den letzten zwei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.SplineRectKeyFrame>\-Klasse verwendet, um das Rechteck zurück auf seine Originalgröße und Ausgangsposition zu setzen.  [Spline](GTMT)\-Keyframes wie <xref:System.Windows.Media.Animation.SplineRectKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>\-Eigenschaft bestimmt werden.  In diesem Beispiel beginnt die Veränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.RectangleGeometry>   
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>   
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)