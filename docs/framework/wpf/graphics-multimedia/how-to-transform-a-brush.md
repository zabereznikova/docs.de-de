---
title: "Gewusst wie: Transformieren eines Pinsels | Microsoft Docs"
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
  - "Pinsel, Drehen des Inhalts"
  - "Pinsel, Transform-Eigenschaft"
  - "Drehen des Inhalts von Pinseln"
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Transformieren eines Pinsels
Dieses Beispiel veranschaulicht die Transformation von <xref:System.Windows.Media.Brush>\-Objekten mithilfe von zwei Transformationseigenschaften: <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 In den folgenden Beispielen wird eine <xref:System.Windows.Media.RotateTransform> verwendet, um den Inhalt eines <xref:System.Windows.Media.ImageBrush> um 45 Grad zu drehen.  
  
 Die Abbildung enthält die folgenden Darstellungen: <xref:System.Windows.Media.ImageBrush> ohne <xref:System.Windows.Media.RotateTransform>, mit <xref:System.Windows.Media.RotateTransform> angewendet auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft und mit der <xref:System.Windows.Media.RotateTransform> angewendet auf die <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft.  
  
 ![RelativeTransform&#45; und Transform&#45;Pinseleinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
## Beispiel  
 Im ersten Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft eines <xref:System.Windows.Media.ImageBrush> angewendet.  Die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> eines <xref:System.Windows.Media.RotateTransform>\-Objekts sind auf 0,5, d. h. die relative Koordinate des Inhaltsmittelpunkts, festgelegt.  Als Ergebnis dreht sich der <xref:System.Windows.Media.ImageBrush>\-Inhalt um seinen Mittelpunkt.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Im zweiten Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf einen <xref:System.Windows.Media.ImageBrush> angewendet. Dieses Beispiel verwendet jedoch die <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft, anstelle der <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft.  
  
 In dem Beispiel werden die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> des <xref:System.Windows.Media.RotateTransform>\-Objekts auf absolute Koordinaten festgelegt, um den Pinsel um seinen Mittelpunkt zu drehen.  Da der Pinsel ein Rechteck mit der Größe 175 mal 90 [Pixel](GTMT) zeichnet, liegt der Mittelpunkt des Rechtecks bei \(87,5\/45\).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Eine Beschreibung der Funktionsweise der Eigenschaften <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A> finden Sie unter [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  Weitere Informationen über Pinsel finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## Siehe auch  
 [Übersicht über Pinseltransformationen](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)