---
title: "Gewusst wie: Zeichnen eines Bereichs mit einem Bild | Microsoft Docs"
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
  - "Pinsel, Zeichnen mit Bildern"
  - "Bilder, Zeichnen mit"
  - "Zeichnen, Mit Bildern"
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zeichnen eines Bereichs mit einem Bild
In diesem Beispiel wird veranschaulicht, wie mithilfe der <xref:System.Windows.Media.ImageBrush>\-Klasse ein Bereich mit einem Bild gezeichnet wird.  Mit <xref:System.Windows.Media.ImageBrush> wird ein einzelnes Bild angezeigt, das über die <xref:System.Windows.Media.ImageBrush.ImageSource%2A>\-Eigenschaft angegeben wird.  
  
## Beispiel  
 Im folgenden Beispiel wird der <xref:System.Windows.Controls.Control.Background%2A> einer Schaltfläche mithilfe von <xref:System.Windows.Media.ImageBrush> gezeichnet.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Standardmäßig wird ein Bild mithilfe von <xref:System.Windows.Media.ImageBrush> gestreckt, um den zu zeichnenden Bereich vollständig auszufüllen.  Im vorhergehenden Beispiel wird das Bild zum Ausfüllen der Schaltfläche gestreckt, wobei das Bild möglicherweise verzerrt wird.  Durch das Festlegen der <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft von <xref:System.Windows.Media.TileBrush> auf <xref:System.Windows.Media.Stretch> oder auf <xref:System.Windows.Media.Stretch> kann dieses Verhalten gesteuert werden. Dies hat zur Folge, dass der Pinsel das [Seitenverhältnis](GTMT) eines Bilds beibehält.  
  
 Wenn die <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft und die <xref:System.Windows.Media.TileBrush.TileMode%2A>\-Eigenschaft von <xref:System.Windows.Media.ImageBrush> festgelegt werden, wird ein sich wiederholendes Muster erstellt.  Im folgenden Beispiel wird eine Schaltfläche mithilfe eines Musters gezeichnet, das auf Basis eines Bilds erstellt wird.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Weitere Informationen über die <xref:System.Windows.Media.ImageBrush>\-Klasse finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels für die <xref:System.Windows.Media.ImageBrush>\-Klasse.  Das vollständige Beispiel finden Sie unter [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## Siehe auch  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)