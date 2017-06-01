---
title: "Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen | Microsoft Docs"
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
  - "3-D-Szenen, Animieren der Kamerarichtung"
  - "3-D-Szenen, Animieren der Kameraposition"
  - "Animation, Kamerarichtung in 3D-Szenen"
  - "Animation, Kameraposition in 3D-Szenen"
  - "Kamerarichtung, Animieren in 3D-Szenen"
  - "Kameraposition, Animieren in 3D-Szenen"
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen
Im folgenden Beispiel wird veranschaulicht, wie die Position und die Richtung einer Kamera in einer 3D\-Szene animiert werden.  Zu diesem Zweck werden die <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A>\-Eigenschaft bzw. die <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A>\-Eigenschaft der <xref:System.Windows.Media.Media3D.PerspectiveCamera> mithilfe von <xref:System.Windows.Media.Animation.Point3DAnimation> und <xref:System.Windows.Media.Animation.Vector3DAnimation> animiert.  Mit dieser Animation können Sie die Perspektive eines Betrachters der Szene als Reaktion auf ein bestimmtes Ereignis verändern.  
  
## Beispiel  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>   
 <xref:System.Windows.Media.Animation.Point3DAnimation>   
 [Animieren von Kameraposition und –richtung mithilfe von Keyframes](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)