---
title: 'Vorgehensweise: Erstellen einer zusammengesetzten Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: de9f7972c7a51ea623c3630fe62bb48f6109317e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052897"
---
# <a name="how-to-create-a-composite-shape"></a>Vorgehensweise: Erstellen einer zusammengesetzten Form
Dieses Beispiel zeigt, wie Sie zusammengesetzte Formen erstellen <xref:System.Windows.Media.Geometry> Objekte und zeigen Sie sie mithilfe einer <xref:System.Windows.Shapes.Path> Element. Im folgenden Beispiel eine <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, und ein <xref:System.Windows.Media.RectangleGeometry> werden verwendet, mit einem <xref:System.Windows.Media.GeometryGroup> zum Erstellen einer zusammengesetzten Form. Die Geometrie gezeichnet Klicken Sie dann mit einem <xref:System.Windows.Shapes.Path> Element.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Eine zusammengesetzte Geometrie, die mit einer GeometryGroup erstellt](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Zusammengesetzte Geometrie  
  
 Komplexere Formen, wie z. B. Polygone und Formen mit Kurvensegmente, können erstellt werden, mithilfe einer <xref:System.Windows.Media.PathGeometry>. Ein Beispiel zur Vorgehensweise: Erstellen einer Form mithilfe einer <xref:System.Windows.Media.PathGeometry>, finden Sie unter [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  Obwohl dieses Beispiel eine Form mit dem Bildschirm gerendert wird. eine <xref:System.Windows.Shapes.Path> Element <xref:System.Windows.Media.Geometry> Objekte können auch verwendet werden, um den Inhalt zu beschreiben eine <xref:System.Windows.Media.GeometryDrawing> oder <xref:System.Windows.Media.DrawingContext>. Sie können auch zum Ausschneiden und Treffertests verwendet werden.  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).
