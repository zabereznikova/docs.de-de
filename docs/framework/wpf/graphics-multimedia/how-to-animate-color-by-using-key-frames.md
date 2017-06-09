---
title: "Gewusst wie: Animieren von Color mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Farben mit Keyframes"
  - "Farben, Animieren mit Keyframes"
  - "Keyframes, Animieren von Farben mit"
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Animieren von Color mithilfe von Keyframes
In diesem Beispiel wird die Animation von <xref:System.Windows.Media.SolidColorBrush.Color%2A> eines <xref:System.Windows.Media.SolidColorBrush> mithilfe von Keyframes dargestellt.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Media.SolidColorBrush.Color%2A>\-Eigenschaft eines <xref:System.Windows.Media.SolidColorBrush> zu animieren.  In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In den ersten zwei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.LinearColorKeyFrame>\-Klasse verwendet, um die Farbe allmählich von Grün zu Rot zu ändern.  Durch lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearColorKeyFrame> wird ein glatter, linearer Übergang zwischen Werten ermöglicht.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>\-Klasse verwendet, um die Farbe schnell von Rot zu Gelb zu ändern.  Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> können abrupte Veränderungen zwischen Werten herstellen, d. h. die Farbveränderung in diesem Teil der Animation tritt schnell auf und ist deutlich sichtbar.  
  
3.  In den letzten zwei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.SplineColorKeyFrame>\-Klasse verwendet, um die Farbe erneut zu ändern: in diesem Fall von Gelb in Grün.  [Spline](GTMT)\-Keyframes wie <xref:System.Windows.Media.Animation.SplineColorKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>\-Eigenschaft bestimmt werden.  In diesem Beispiel beginnt die Farbveränderung zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)