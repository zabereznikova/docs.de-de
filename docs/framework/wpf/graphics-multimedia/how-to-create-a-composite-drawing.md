---
title: "Gewusst wie: Erstellen einer zusammengesetzten Zeichnung | Microsoft Docs"
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
  - "Klassen, DrawingGroup"
  - "Zusammengesetzte Zeichnungen"
  - "DrawingGroup-Klasse"
  - "Zeichnungen, Zusammengesetzt"
  - "Grafiken, Zusammengesetzte Zeichnungen"
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen einer zusammengesetzten Zeichnung
Dieses Beispiel zeigt, wie mit einer <xref:System.Windows.Media.DrawingGroup> komplexe Zeichnungen erstellt werden, indem Sie mehrere <xref:System.Windows.Media.Drawing>\-Objekte in einer einzelnen, zusammengesetzten Zeichnung kombinieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingGroup> verwendet, um eine zusammengesetzte Zeichnung aus den Objekten <xref:System.Windows.Media.GeometryDrawing> und <xref:System.Windows.Media.ImageDrawing> zu erstellen.  In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
Eine mithilfe von DrawingGroup erstellte zusammengesetzte Zeichnung  
  
 Beachten Sie den grauen Rahmen, der die Grenzen der Zeichnung kennzeichnet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Sie können mit einer <xref:System.Windows.Media.DrawingGroup> die Einstellungen <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> oder <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> auf die enthaltenen Zeichnungen anwenden.  Da eine <xref:System.Windows.Media.DrawingGroup> gleichzeitig eine <xref:System.Windows.Media.Drawing> ist, kann sie andere <xref:System.Windows.Media.DrawingGroup>\-Objekte enthalten.  
  
 Das folgende Beispiel ähnelt dem vorgehenden Beispiel, es werden jedoch zusätzliche <xref:System.Windows.Media.DrawingGroup>\-Objekte verwendet, um Bitmapeffekte und eine Durchlässigkeitsmaske auf einen Teil der Zeichnungen anzuwenden.  In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Eine DrawingGroup mit mehreren Zeichnungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.png "graphicsmm\_multiple")  
Zusammengesetzte Zeichnung mit mehreren DrawingGroup\-Objekten  
  
 Beachten Sie den grauen Rahmen, der die Grenzen der Zeichnung kennzeichnet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Weitere Informationen über <xref:System.Windows.Media.Drawing>\-Objekte finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>   
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>   
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>   
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>   
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>   
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)