---
title: "Gewusst wie: Erstellen einer Bitmap mit einem visuellen Element | Microsoft Docs"
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
  - "Bitmaps, Rendern aus grafischen Elementen"
  - "Grafische Elemente, Rendern in Bitmaps"
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen einer Bitmap mit einem visuellen Element
In diesem Beispiel wird gezeigt, wie Sie eine Bitmap mit einem <xref:System.Windows.Media.Visual> erstellen können.  Ein <xref:System.Windows.Media.DrawingVisual> wird mit <xref:System.Windows.Media.FormattedText> gerendert.  Das <xref:System.Windows.Media.Visual> wird dann in <xref:System.Windows.Media.Imaging.RenderTargetBitmap> gerendert, und eine Bitmap des jeweiligen Texts wird erstellt.  
  
## Beispiel  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingContext>   
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)