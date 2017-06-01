---
title: "Gewusst wie: Abrunden der Ecken einer &quot;RectangleGeometry&quot; | Microsoft Docs"
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
  - "Ecken, Runden von"
  - "Grafiken, Runden der Ecken von RectangleGeometry-Objekten"
  - "RectangleGeometry-Klasse, Runden von Ecken"
  - "Runden der Ecken von RectangleGeometry-Objekten"
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Abrunden der Ecken einer &quot;RectangleGeometry&quot;
Um die Ecken einer <xref:System.Windows.Media.RectangleGeometry> abzurunden, setzen Sie ihre Eigenschaften <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> auf einen Wert, der größer als 0 ist.  Je größer die Werte, desto runder die Ecken des Rechtecks.  
  
## Beispiel  
 Das folgende Beispiel zeigt mehrere <xref:System.Windows.Media.RectangleGeometry>\-Objekte mit verschiedenen Einstellungen für <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  Die <xref:System.Windows.Media.RectangleGeometry>\-Objekte werden mithilfe von <xref:System.Windows.Shapes.Path>\-Elementen angezeigt.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rechtecke mit unterschiedlichen RadiusX&#47;RadiusY&#45;Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm\_rounded")  
Rechtecke mit abgerundeten Ecken  
  
## Siehe auch  
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)