---
title: "Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Zeichenfolgen mit Keyframes"
  - "Keyframes, Animieren von Zeichenfolgen mit"
  - "Zeichenfolgen, Animieren mit Keyframes"
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie eine Zeichenfolge mithilfe von Keyframes animiert wird. Es handelt sich in diesem Fall um die <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Button>\-Steuerelements.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Button> zu animieren.  
  
 Die Keyframes in diesem Beispiel verwenden eine Instanz der <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>\-Klasse, da eine mit Keyframes erstellte Animation einer Zeichenfolge ausschließlich diskrete Keyframes verwenden kann.  Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> ermöglichen abrupte Sprünge zwischen Werten, d. h. Änderungen der Animation treten schnell und deutlich sichtbar auf.  
  
 [!code-xml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>   
 <xref:System.Windows.Controls.ContentControl.Content%2A>   
 <xref:System.Windows.Controls.Button>   
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)