---
title: 'Gewusst wie: Erstellen einer Linie mit einer LineGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: acb2c3db2027f8a4e9594212d1f5af9ea1c8a43b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Gewusst wie: Erstellen einer Linie mit einer LineGeometry
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.LineGeometry> Klasse, um eine Zeile zu beschreiben. Ein <xref:System.Windows.Media.LineGeometry> wird durch die Anfangs- und Endpunkte definiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.LineGeometry>.  Ein <xref:System.Windows.Shapes.Path> Element wird verwendet, um die Zeile zu rendern.  Da eine Linie keinen Bereich aufweist der <xref:System.Windows.Shapes.Path> des Objekts <xref:System.Windows.Shapes.Shape.Fill%2A> nicht angegeben ist; stattdessen die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften verwendet werden.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "Graphicsmm_line")  
Eine LineGeometry, gezeichnet von (10,20) bis (100,130)  
  
 Andere Klassen einfache Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>. Diese Geometrien sowie komplexere können auch erstellt werden mithilfe einer <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>. Weitere Informationen finden Sie unter der [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
