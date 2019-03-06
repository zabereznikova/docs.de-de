---
title: 'Vorgehensweise: Erstellen einer Linie mit einer LineGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 6d5d0b413f940a2c7f70e05135ff070c1fe5ba21
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374660"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Vorgehensweise: Erstellen einer Linie mit einer LineGeometry
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.LineGeometry> Klasse, die eine Zeile beschreibt. Ein <xref:System.Windows.Media.LineGeometry> wird durch die Anfangs- und Endpunkte definiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.LineGeometry>.  Ein <xref:System.Windows.Shapes.Path> Element wird verwendet, um die Linie zu rendern.  Da eine Linie keinen Bereich aufweist. die <xref:System.Windows.Shapes.Path> des Objekts <xref:System.Windows.Shapes.Shape.Fill%2A> nicht angegeben ist; stattdessen die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften verwendet werden.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![Eine LineGeometry](./media/graphicsmm-line.gif "Graphicsmm_line")  
Eine LineGeometry, gezeichnet von (10,20) bis (100,130)  
  
 Andere Klassen der einfachen Geometrie sind <xref:System.Windows.Media.LineGeometry> und <xref:System.Windows.Media.EllipseGeometry>. Diese Geometrien, als auch eine komplexere, kann auch erstellt werden mit einem <xref:System.Windows.Media.PathGeometry> oder <xref:System.Windows.Media.StreamGeometry>. Weitere Informationen finden Sie unter den [Übersicht über die Geometrie](geometry-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Geometrien](geometry-overview.md)
- [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md)
- [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
