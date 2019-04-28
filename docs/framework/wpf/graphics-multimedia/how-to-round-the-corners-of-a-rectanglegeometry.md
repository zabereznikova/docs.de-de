---
title: 'Vorgehensweise: Abrunden der Ecken einer RectangleGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651398"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Vorgehensweise: Abrunden der Ecken einer RectangleGeometry
Zum Abrunden der Ecken des eine <xref:System.Windows.Media.RectangleGeometry>legen die <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Eigenschaften, die einen Wert größer als 0 (null). Je größer die Werte, desto runder die Ecken des Rechtecks.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt mehrere <xref:System.Windows.Media.RectangleGeometry> Objekte mit unterschiedlichen <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Einstellungen. Die <xref:System.Windows.Media.RectangleGeometry> Objekte angezeigt werden, mithilfe von <xref:System.Windows.Shapes.Path> Elemente.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rechtecke mit verschiedenen RadiusX&#47;RadiusY-Einstellungen](./media/graphicsmm-rounded.png "Graphicsmm_rounded")  
Rechtecke mit abgerundeten Ecken  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Geometrien](geometry-overview.md)
- [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md)
- [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
