---
title: 'Gewusst wie: Abrunden der Ecken einer "RectangleGeometry"'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: e4f1d37e2c0f26967affff14ed6475fc8c0cb28c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561640"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Gewusst wie: Abrunden der Ecken einer "RectangleGeometry"
Um das Abrunden der Ecken des eine <xref:System.Windows.Media.RectangleGeometry>legen seine <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Eigenschaften auf einen Wert größer als 0 (null). Je größer die Werte, desto runder die Ecken des Rechtecks.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt mehrere <xref:System.Windows.Media.RectangleGeometry> Objekte mit unterschiedlichen <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Einstellungen. Die <xref:System.Windows.Media.RectangleGeometry> Objekte angezeigt werden, mit <xref:System.Windows.Shapes.Path> Elemente.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rechtecke mit verschiedenen-RadiusX&#47;RadiusY-Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "Graphicsmm_rounded")  
Rechtecke mit abgerundeten Ecken  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
