---
title: "Gewusst wie: Animieren eines Point mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Punkte mit Keyframes"
  - "Keyframes, Animieren von Punkten mit"
  - "Punkte, Animieren mit Keyframes"
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Animieren eines Point mithilfe von Keyframes
In diesem Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>\-Klasse zum Animieren eines <xref:System.Windows.Point> dargestellt.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Ellipse entlang eines dreieckigen Pfads verschoben.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Media.EllipseGeometry.Center%2A>\-Eigenschaft einer <xref:System.Windows.Media.EllipseGeometry> zu animieren.  In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In der ersten halben Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.LinearPointKeyFrame>\-Klasse verwendet, um die Ellipse von der Startposition mit konstanter Geschwindigkeit auf einem Pfad zu bewegen.  Durch lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearPointKeyFrame> wird eine glatte, lineare Interpolation zwischen Werten ermöglicht.  
  
2.  Am Ende der folgenden halben Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.DiscretePointKeyFrame>\-Klasse verwendet, um die Ellipse entlang des Pfads abrupt an die nächste Position zu bewegen.  Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> ermöglichen abrupte Sprünge zwischen Werten.  
  
3.  In den letzten zwei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.SplinePointKeyFrame>\-Klasse verwendet, um die Ellipse zurück an ihre Ausgangsposition zu verschieben.  [Spline](GTMT)\-Keyframes wie <xref:System.Windows.Media.Animation.SplinePointKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>\-Eigenschaft bestimmt werden.  In diesem Beispiel beginnt die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Aus Gründen der Konsistenz mit anderen Animationsbeispielen wird in den Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard>\-Objekt zum Anwenden des <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>\-Elements verwendet.  Beim Anwenden einer Animation im Code ist es jedoch einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode anstelle von <xref:System.Windows.Media.Animation.Storyboard> zu verwenden.  Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.EllipseGeometry>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)