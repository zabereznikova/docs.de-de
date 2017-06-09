---
title: "Gewusst wie: Animieren einer 3D-Drehung mit Storyboards | Microsoft Docs"
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
  - "3D-Übersetzungen, Animation, Mit Storyboards"
  - "Animation, 3D-Übersetzungen, Mit Storyboards"
  - "Storyboards"
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Animieren einer 3D-Drehung mit Storyboards
Im folgenden Beispiel wird dargestellt, wie durch Animation der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>\-Eigenschaft und der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>\-Eigenschaft eines <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>\-Objekts ein 3D\-Objekt gedreht wird, während es "wackelt".  Dieses <xref:System.Windows.Media.Media3D.AxisAngleRotation3D>\-Objekt gibt die Drehungstransformation des 3D\-Objekts an, sodass durch die Animation seiner Eigenschaften der gewünschte Dreheffekt zustande kommt.  Im Storyboard wird mit <xref:System.Windows.Media.Animation.DoubleAnimation> die <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>\-Eigenschaft animiert, während mit <xref:System.Windows.Media.Animation.Vector3DAnimation> die <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>\-Eigenschaft animiert wird.  
  
## Beispiel  
 [!code-xml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## Siehe auch  
 [Animieren einer 3D\-Drehung mit Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [Animieren einer 3D\-Drehung mithilfe von Keyframes \(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)