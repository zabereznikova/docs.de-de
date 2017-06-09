---
title: "Gewusst wie: Animieren von Gr&#246;&#223;en&#228;nderungen mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Größenänderungen mit Keyframes"
  - "Keyframes, Animieren von Größenänderungen mit"
  - "Codeänderungen, Animieren mit Keyframes"
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Animieren von Gr&#246;&#223;en&#228;nderungen mithilfe von Keyframes
In diesem Beispiel wird das Animieren von Größenänderungen mithilfe von Keyframes veranschaulicht.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Media.ArcSegment.Size%2A>\-Eigenschaft eines <xref:System.Windows.Media.ArcSegment> zu animieren.  In dieser Animation werden drei Keyframes folgendermaßen verwendet:  
  
1.  In der ersten halben Sekunde der Animation wird eine Instanz der <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>\-Klasse verwendet, um die Größe des Bogens graduell zu erhöhen.  Durch lineare Keyframes wie <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> wird ein glatter, linearer Übergang zwischen Werten ermöglicht.  
  
2.  Am Ende der nächsten halben Sekunde wird eine Instanz der <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>\-Klasse verwendet, um die Größe des Bogens abrupt zu erhöhen.  Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> ermöglichen abrupte Sprünge zwischen Werten, d.h. Änderungen der Animation treten plötzlich und deutlich sichtbar auf.  
  
3.  Im Verlauf der letzten zwei Sekunden wird eine Instanz der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>\-Klasse verwendet, um die Größe des Bogens zu erhöhen.  [Spline](GTMT)\-Keyframes wie <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>\-Eigenschaft bestimmt werden.  In diesem Beispiel wächst die Größe des Bogens zunächst nur langsam und steigt dann exponentiell zum Ende des Zeitabschnitts.  
  
 [!code-xml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.ArcSegment.Size%2A>   
 <xref:System.Windows.Media.ArcSegment>   
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)