---
title: "Gewusst wie: Animieren von Kameraposition und -richtung mithilfe von Keyframes | Microsoft Docs"
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
  - "Animation, Kamerarichtung mit Keyframes"
  - "Animation, Kameraposition mit Keyframes"
  - "Kamerarichtung, Animieren mit Keyframes"
  - "Kameraposition, Animieren mit Keyframes"
  - "Keyframes, Animieren der Kamerarichtung"
  - "Keyframes, Animieren der Kameraposition"
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Animieren von Kameraposition und -richtung mithilfe von Keyframes
Im folgenden Beispiel wird veranschaulicht, wie mit <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> die Position einer <xref:System.Windows.Media.Media3D.PerspectiveCamera> in einer 3D\-Szene animiert wird.  Darüber hinaus wird <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> dazu verwendet, die Richtung der Kamera in der 3D\-Szene zu animieren.  Beide dieser Animationen verwenden mehrere Keyframes, die eine Reihe von Animationseffekten erstellen:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> und <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> werden verwendet, um eine glatte, lineare Interpolation zwischen Werten zu ermöglichen.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> und <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> werden verwendet, um abrupte "Sprünge" zwischen Werten \(keine Interpolation\) zu erstellen.  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> und <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> werden verwendet, um einen variablen Übergang zwischen Werten abhängig von der <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A>\-Eigenschaft zu erstellen.  Im folgenden Beispiel ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.  
  
## Beispiel  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## Siehe auch  
 [Animieren der Kameraposition und –richtung in 3D\-Szenen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)