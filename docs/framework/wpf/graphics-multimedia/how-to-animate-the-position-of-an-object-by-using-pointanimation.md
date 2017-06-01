---
title: "Gewusst wie: Animieren der Position eines Objekts mit PointAnimation | Microsoft Docs"
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
  - "Animation, PointAnimation"
  - "Klassen, PointAnimation"
  - "Grafiken [WPF], Animation"
  - "PointAnimation-Klasse"
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Animieren der Position eines Objekts mit PointAnimation
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Windows.Media.Animation.PointAnimation>\-Klasse verwendet wird, um ein Objekt entlang eines <xref:System.Windows.Shapes.Path> zu animieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Ellipse entlang eines <xref:System.Windows.Shapes.Path> von einem Punkt auf dem Bildschirm zu einem anderen verschoben.  Im Beispiel wird die Position einer <xref:System.Windows.Media.EllipseGeometry> animiert, indem es <xref:System.Windows.Media.Animation.PointAnimation> verwendet, um die <xref:System.Windows.Media.EllipseGeometry.Center%2A>\-Eigenschaft zu animieren.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.PointAnimation>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.EllipseGeometry>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/de-de/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)