---
title: "Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Rahmenstärke mit Keyframes"
  - "Rahmenstärke, Animieren mit Keyframes"
  - "Keyframes, Animieren der Rahmenstärke mit"
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes
In diesem Beispiel wird das Animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Border> dargestellt.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Controls.Control.BorderThickness%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Border> zu animieren.  In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In der ersten halben Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>\-Klasse verwendet, um die Breite des Rahmens graduell zu erhöhen.  Im Beispiel wird <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> für eine glatte, lineare Erhöhung von Werten verwendet.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>\-Klasse verwendet, um die Breite des Rahmens abrupt zu erhöhen.  Diskrete Keyframes, wie z. B. von <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> abgeleitete Keyframes, ermöglichen abrupte Sprünge zwischen Werten, d. h. die Animation ist ruckartig.  
  
3.  In den letzten beiden Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>\-Klasse verwendet, um die Breite des Rahmens zu verringern.  [Spline](GTMT)\-Keyframes wie die von <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> abngeleiteten, erzeugen einen variablen Übergang zwischen Werten gemäß den Werten der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>\-Eigenschaft.  In diesem Keyframe ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
 [!code-xml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [Animieren eines BorderThickness\-Werts](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)