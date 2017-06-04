---
title: "Gewusst wie: Animieren eines Doubles mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Doubles mit Keyframes"
  - "Doppelt, Animieren mit Keyframes"
  - "Keyframes, Animieren von Doubles mit"
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Animieren eines Doubles mithilfe von Keyframes
In diesem Beispiel wird veranschaulicht, wie Sie den Wert einer Eigenschaft, die ein <xref:System.Double> annimmt, mithilfe von Keyframes animieren.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Rechteck über den Bildschirm bewegt.  Im Beispiel wird die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>\-Klasse zum Animieren der <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft einer <xref:System.Windows.Media.TranslateTransform> verwendet, die auf ein <xref:System.Windows.Shapes.Rectangle> angewendet wird.  In dieser sich ständig wiederholenden Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In den ersten drei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>\-Klasse  verwendet, um das Rechteck mit konstanter Geschwindigkeit auf einem Pfad von der Startposition bis zur Position 500 zu bewegen.  Durch lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> wird ein glatter, linearer Übergang zwischen Werten ermöglicht.  
  
2.  Am Ende der vierten Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>\-Klasse verwendet, um das Rechteck sofort an die nächste Position zu bewegen.  Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> ermöglichen abrupte Sprünge zwischen Werten.  In diesem Beispiel befindet sich das Rechteck an der Startposition und wird anschließend plötzlich an der Position 500 angezeigt.  
  
3.  In den letzten zwei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>\-Klasse verwendet, um das Rechteck zurück an seine Ausgangsposition zu verschieben.  [Spline](GTMT)\-Keyframes wie <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> erzeugen einen variablen Übergang zwischen Werten, der von der <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>\-Eigenschaft bestimmt wird.  In diesem Beispiel bewegt sich das Rechteck zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Aus Gründen der Konsistenz mit anderen Animationsbeispielen wird in den Codeversionen dieses Beispiels ein <xref:System.Windows.Media.Animation.Storyboard>\-Objekt zum Anwenden von <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> verwendet.  Beim Anwenden einer einzelnen Animation in Code ist es einfacher, die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode anstatt von <xref:System.Windows.Media.Animation.Storyboard> zu verwenden.  Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Shapes.Rectangle>   
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)