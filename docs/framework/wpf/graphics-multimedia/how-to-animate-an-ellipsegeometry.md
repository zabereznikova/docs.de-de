---
title: "Gewusst wie: Animieren eines &quot;EllipseGeometry&quot;-Elements | Microsoft Docs"
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
  - "Animation EllipseGeometry-Objekte"
  - "Animieren von EllipseGeometry-Objekte"
  - "Grafiken [WPF], animation"
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Animieren eines &quot;EllipseGeometry&quot;-Elements
Dieses Beispiel zeigt, wie Sie Animieren einer <xref:System.Windows.Media.Geometry> innerhalb einer <xref:System.Windows.Shapes.Path> Element. Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.PointAnimation> wird verwendet, um, Animieren der <xref:System.Windows.Media.EllipseGeometry.Center%2A> von einer <xref:System.Windows.Media.EllipseGeometry>.  
  
## <a name="example"></a>Beispiel  
 [!code-xml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)