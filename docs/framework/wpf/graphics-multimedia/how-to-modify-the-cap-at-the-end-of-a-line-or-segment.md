---
title: "Gewusst wie: &#196;ndern des Endes einer Zeile oder eines Segments | Microsoft Docs"
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
  - "Grafiken, Shape-Caps"
  - "Shape-Elemente, Caps"
  - "Shape-Elemente, Ends"
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: &#196;ndern des Endes einer Zeile oder eines Segments
In diesem Beispiel wird das Ändern der Form am Anfang oder Ende eines offenen <xref:System.Windows.Shapes.Shape>\-Elements erläutert.  Um das Endstück am Anfang eines offenen <xref:System.Windows.Shapes.Shape> zu ändern, verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>\-Eigenschaft.  Verwenden Sie die <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>\-Eigenschaft, um das Endstück am Ende eines offenen <xref:System.Windows.Shapes.Shape> zu ändern.  Die verfügbaren Zeilenenden finden Sie unter <xref:System.Windows.Media.PenLineCap>\-Enumeration.  
  
> [!NOTE]
>  Diese Eigenschaft ist nur auf offenen Elemente wie <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline> oder <xref:System.Windows.Shapes.Path> anwendbar.  
  
 Im folgenden Beispiel werden vier <xref:System.Windows.Shapes.Polyline>\-Elemente gezeichnet. Dabei wird an den Enden eines jeden Elements ein anderer Formensatz verwendet.  
  
## Beispiel  
 [!code-xml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Siehe auch  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Media.PenLineCap>