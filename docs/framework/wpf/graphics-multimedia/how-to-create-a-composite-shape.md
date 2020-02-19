---
title: 'Gewusst wie: Erstellen einer zusammengesetzten Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452096"
---
# <a name="how-to-create-a-composite-shape"></a>Gewusst wie: Erstellen einer zusammengesetzten Form
In diesem Beispiel wird gezeigt, wie zusammengesetzte Formen mithilfe von <xref:System.Windows.Media.Geometry> Objekten erstellt und mithilfe eines <xref:System.Windows.Shapes.Path> Elements angezeigt werden. Im folgenden Beispiel werden eine <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>und eine <xref:System.Windows.Media.RectangleGeometry> mit einer <xref:System.Windows.Media.GeometryGroup> verwendet, um eine zusammengesetzte Form zu erstellen. Die Geometrien werden dann mithilfe eines <xref:System.Windows.Shapes.Path>-Elements gezeichnet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Eine zusammengesetzte Geometrie, die mithilfe einer GeometryGroup erstellt wurde.](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Zusammengesetzte Geometrie  
  
 Komplexere Formen (z. b. Polygone und Formen mit gekrümmten Segmenten) können mithilfe eines <xref:System.Windows.Media.PathGeometry>erstellt werden. Ein Beispiel, das zeigt, wie eine Form mit einer <xref:System.Windows.Media.PathGeometry>erstellt wird, finden Sie unter [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  Obwohl in diesem Beispiel eine Form mithilfe eines <xref:System.Windows.Shapes.Path> Elements auf dem Bildschirm gerendert wird, können <xref:System.Windows.Media.Geometry> Objekte auch verwendet werden, um den Inhalt eines <xref:System.Windows.Media.GeometryDrawing> oder eines <xref:System.Windows.Media.DrawingContext>zu beschreiben. Sie können auch für Clipping-und Treffer Tests verwendet werden.  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).
