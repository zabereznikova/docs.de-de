---
title: "Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes | Microsoft Docs"
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
  - "3D-Übersetzungen, Animation, Mit Keyframes (Rotation3DAnimation)"
  - "Animation, 3D-Übersetzungen, Mit Keyframes (Rotation3DAnimation)"
  - "Keyframes, Rotation3DAnimation"
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes
Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> verwendet, um ein 3D\-Objekt zum Drehen zu bringen. Die Rotationsachse wird dabei animiert, wodurch das Objekt "wackelnd" dargestellt wird.  Die Animation verwendet folgende Keyframes:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> wird verwendet, um abrupte "Sprünge" zwischen Werten \(keine Interpolation\) zu erstellen.  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> wird verwendet, um abhängig von der <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>\-Eigenschaft einen variablen Übergang zwischen Werten zu erstellen.  Im nachfolgenden Beispiel ist dieser Teil der Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
## Beispiel  
 [!code-xml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## Siehe auch  
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Animieren einer 3D\-Drehung mit Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Animieren einer 3D\-Drehung mit Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Animieren einer 3D\-Drehung mit Quaternionen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [Animieren einer 3D\-Drehung mit Keyframes \(QuaternionAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)