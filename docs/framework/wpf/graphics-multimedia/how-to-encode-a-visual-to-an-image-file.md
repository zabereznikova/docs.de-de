---
title: "Gewusst wie: Codieren eines Visual-Objekts in einer Bilddatei | Microsoft Docs"
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
  - "Codieren von Bildformaten"
  - "Bilddateien, Codieren aus grafischen Elementen"
  - "Grafische Elemente, Codieren in eine Bilddatei"
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Codieren eines Visual-Objekts in einer Bilddatei
Dieses Beispiel zeigt, wie Sie ein <xref:System.Windows.Media.Visual>\-Objekt in einer Bilddatei codieren, indem Sie eine <xref:System.Windows.Media.Imaging.RenderTargetBitmap> und einen  <xref:System.Windows.Media.Imaging.PngBitmapEncoder> verwenden.  
  
## Beispiel  
 Das <xref:System.Windows.Media.DrawingVisual> wird mithilfe eines <xref:System.Windows.Media.Imaging.BitmapImage> und <xref:System.Windows.Media.FormattedText> erstellt, der in einer <xref:System.Windows.Media.Imaging.RenderTargetBitmap> gerendert wird.  Die gerendete Bitmap wird anschließend verwendet, um einen <xref:System.Windows.Media.Imaging.BitmapFrame> zu erstellen, der dem <xref:System.Windows.Media.Imaging.PngBitmapEncoder> hinzugefügt wird, um eine neue [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)]\-Datei zu erstellen.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 In diesem Beispiel wurde ein <xref:System.Windows.Media.Imaging.PngBitmapEncoder> verwendet, aber zum Erstellen der Bilddatei hätte jedes der abgeleiteten <xref:System.Windows.Media.Imaging.BitmapEncoder>\-Objekte verwendet werden können.  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingContext>   
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)