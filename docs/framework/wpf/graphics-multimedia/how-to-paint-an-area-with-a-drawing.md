---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einer Zeichnung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010073"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a>Vorgehensweise: Zeichnen eines Bereichs mit einer Zeichnung
Dieses Beispiel zeigt, wie Sie einen Bereich mit einer Zeichnung zeichnen. Um einen Bereich mit einer Zeichnung zu zeichnen, verwenden Sie eine <xref:System.Windows.Media.DrawingBrush> und einem oder mehreren <xref:System.Windows.Media.Drawing> Objekte.   Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingBrush> um ein Objekt mit einer Zeichnung zweier Ellipsen zu zeichnen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Ausgabe eines DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "Graphicsmm_drawingbrush_simple")  
  
 (Die Mitte der Form ist weiß [Steuern des Ausfüllens einer zusammengesetzten Form](how-to-control-the-fill-of-a-composite-shape.md).)  
  
 Durch Festlegen einer <xref:System.Windows.Media.DrawingBrush> des Objekts <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.TileMode%2A> Eigenschaften, Sie können ein sich wiederholendes Muster erstellen. Im folgenden Beispiel wird ein Objekt mit einem aus einer Zeichnung von zwei Ellipsen erstellten Muster gezeichnet.  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 Die folgende Abbildung zeigt die nebeneinander <xref:System.Windows.Media.DrawingBrush> Ausgabe.  
  
 ![Ausgabe eines DrawingBrush in Kachelform](./media/graphicsmm-drawingbrush-tiled.png "Graphicsmm_drawingbrush_tiled")  
  
 Weitere Informationen zu Zeichenpinseln finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md). Weitere Informationen zu <xref:System.Windows.Media.Drawing> Objekten finden Sie die [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).
