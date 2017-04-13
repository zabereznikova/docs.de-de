---
title: "Gewusst wie: Animieren eines booleschen Werts mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Boolesche Werte mit Keyframes"
  - "Boolesche Werte, Animieren mit Keyframes"
  - "Keyframes, Animieren von booleschen Werten mit"
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Animieren eines booleschen Werts mithilfe von Keyframes
In diesem Beispiel wird veranschaulicht, wie Sie den booleschen Eigenschaftswert eines <xref:System.Windows.Controls.Button>\-Steuerelements mithilfe von Keyframes animieren.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>\-Klasse verwendet, um die <xref:System.Windows.UIElement.IsEnabled%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Button>\-Steuerelements zu animieren.  Alle Keyframes in diesem Beispiel verwenden eine Instanz der <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>\-Klasse.  Diskrete Keyframes, wie <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>, ermöglichen abrupte Sprünge zwischen Werten, d. h. die Animation erfolgt ruckartig.  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe\-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>   
 <xref:System.Windows.UIElement.IsEnabled%2A>   
 <xref:System.Windows.Controls.Button>   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst\-wie\-Themen zu Keyframes](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)