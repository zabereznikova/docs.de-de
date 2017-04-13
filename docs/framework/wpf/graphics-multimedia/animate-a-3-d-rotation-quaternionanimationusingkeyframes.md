---
title: "Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes (QuaternionAnimationUsingKeyFrames) | Microsoft Docs"
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
  - "3D-Übersetzungen, Animation, mit Keyframes (QuaternionAnimationUsingKeyFrames)"
  - "Animation, 3D-Übersetzungen, mit Keyframes (QuaternionAnimationUsingKeyFrames)"
  - "Keyframes, QuaternionAnimationUsingKeyFrames"
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes (QuaternionAnimationUsingKeyFrames)
Im folgenden Beispiel wird mithilfe von <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> ein 3D\-Objekt gedreht.  Die Animation verwendet folgende Keyframes:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> wird verwendet, um abrupte "Sprünge" zwischen Werten \(keine Interpolation\) zu erstellen.  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> wird verwendet, um abhängig von der <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>\-Eigenschaft einen variablen Übergang zwischen Werten zu erstellen.  Im nachfolgenden Beispiel ist dieser Teil der Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
## Beispiel  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## Siehe auch  
 [Animieren einer 3D\-Drehung mit Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Animieren einer 3D\-Drehung mit Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Animieren einer 3D\-Drehung mit Quaternionen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [Animieren einer 3D\-Drehung mithilfe von Keyframes \(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)