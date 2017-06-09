---
title: "Gewusst wie: Verwenden einer Zeichnung als Bildquelle | Microsoft Docs"
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
  - "Zeichnungen, Als Bildquellen"
  - "Grafiken, Zeichnungen, Als Bildquellen"
  - "Bildquellen, Zeichnungen"
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Verwenden einer Zeichnung als Bildquelle
In diesem Beispiel wird die Verwendung von <xref:System.Windows.Media.Drawing> als <xref:System.Windows.Controls.Image.Source%2A> für ein <xref:System.Windows.Controls.Image>\-Steuerelement dargestellt.  Um eine <xref:System.Windows.Media.Drawing> mit einem <xref:System.Windows.Controls.Image>\-Steuerelement anzuzeigen, verwenden Sie ein <xref:System.Windows.Media.DrawingImage> als <xref:System.Windows.Controls.Image.Source%2A> für das <xref:System.Windows.Controls.Image>\-Steuerelement, und legen Sie die <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName>\-Eigenschaft des <xref:System.Windows.Media.DrawingImage>\-Objekts auf die anzuzeigende Zeichnung fest.  
  
## Beispiel  
 Im folgenden Beispiel wird mit einem <xref:System.Windows.Media.DrawingImage> und einem <xref:System.Windows.Controls.Image>\-Steuerelement eine <xref:System.Windows.Media.GeometryDrawing> angezeigt.  Dieses Beispiel erzeugt folgende Ausgabe:  
  
 ![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
Ein DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Zeichnen eines Bilds mit ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [PresentationOptions:Freeze\-Attribut](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)