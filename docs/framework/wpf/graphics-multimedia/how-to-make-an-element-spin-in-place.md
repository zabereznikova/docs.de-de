---
title: "Gewusst wie: Drehen von Elementen ohne Positions&#228;nderung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen, DoubleAnimation"
  - "Klassen, RotateTransform"
  - "DoubleAnimation-Klasse"
  - "Grafiken, Sich drehende Elemente"
  - "RotateTransform-Klasse"
  - "Sich drehende Elemente"
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Drehen von Elementen ohne Positions&#228;nderung
In diesem Beispiel wird dargestellt, wie Elemente mithilfe von <xref:System.Windows.Media.RotateTransform> und <xref:System.Windows.Media.Animation.DoubleAnimation> gedreht werden können.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft des Elements angewendet.  Im Beispiel wird <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet, um den <xref:System.Windows.Media.RotateTransform.Angle%2A> der <xref:System.Windows.Media.RotateTransform> zu animieren.  Um das Element ohne Positionsänderung zu drehen, wird im Beispiel die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft des Elements auf den Punkt \(0.5, 0.5\) festgelegt.  
  
## Beispiel  
 [!code-xml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Das vollständige Beispiel mit weiteren Transformationsbeispielen finden Sie unter [Beispiel für 2D\-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)