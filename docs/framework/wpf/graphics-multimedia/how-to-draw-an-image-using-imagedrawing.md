---
title: "Gewusst wie: Zeichnen eines Bilds mit ImageDrawing | Microsoft Docs"
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
  - "Klassen, ImageDrawing"
  - "Zeichnen, Bilder"
  - "Grafiken, Zeichnen von Bildern"
  - "ImageDrawing-Klasse"
  - "Bilder, Zeichnen"
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Zeichnen eines Bilds mit ImageDrawing
In diesem Beispiel ist dargestellt, wie mit <xref:System.Windows.Media.ImageDrawing> ein Bild gezeichnet wird.  Mit <xref:System.Windows.Media.ImageDrawing> können Sie eine <xref:System.Windows.Media.ImageSource> mit <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage> oder <xref:System.Windows.Media.Visual> anzeigen.  Um ein Bild zu zeichnen, erstellen Sie eine <xref:System.Windows.Media.ImageDrawing>, und legen Sie deren Eigenschaften <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> und <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName> fest.  Mit der <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName>\-Eigenschaft wird das zu zeichnende Bild angegeben. Mit der <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName>\-Eigenschaft wird die Position und die Größe der Bilder angegeben.  
  
## Beispiel  
 Im folgenden Beispiel wird eine zusammengesetzte Zeichnung mit vier <xref:System.Windows.Media.ImageDrawing>\-Objekten erstellt.  Mit diesem Beispiel wird das folgende Bild erzeugt:  
  
 ![Mehrere DrawingImage&#45;Objekte](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.png "graphicsmm\_ImageDrawingExample")  
Vier ImageDrawing\-Objekte  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Ein Beispiel für eine einfache Möglichkeit zur Anzeige eines Bilds, ohne <xref:System.Windows.Media.ImageDrawing> zu verwenden, finden Sie unter [Verwenden des Image\-Elements](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).  
  
## Siehe auch  
 <xref:System.Windows.Freezable.Freeze%2A>   
 <xref:System.Windows.Controls.Image>   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [PresentationOptions:Freeze\-Attribut](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)