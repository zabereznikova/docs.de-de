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
ms.openlocfilehash: 6bb2a8a32938682af52343b971b840dbed16bcef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559969"
---
# <a name="how-to-create-a-composite-shape"></a>Gewusst wie: Erstellen einer zusammengesetzten Form
In diesem Beispiel wird gezeigt, wie zum Erstellen von zusammengesetzter Formen mit <xref:System.Windows.Media.Geometry> Objekte und angezeigt werden können mithilfe einer <xref:System.Windows.Shapes.Path> Element. Im folgenden Beispiel ein <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, und ein <xref:System.Windows.Media.RectangleGeometry> werden zusammen mit einer <xref:System.Windows.Media.GeometryGroup> um eine zusammengesetzte Form zu erstellen. Die Geometrie gezeichnet Klicken Sie dann mit einem <xref:System.Windows.Shapes.Path> Element.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.  
  
 ![Eine zusammengesetzte Geometrie, die mit einer GeometryGroup erstellt](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Zusammengesetzte Geometrie  
  
 Komplexere Formen, z. B. Polygone und Formen mit gekrümmten Segmenten möglicherweise erstellt mithilfe einer <xref:System.Windows.Media.PathGeometry>. Ein Beispiel zur Vorgehensweise: Erstellen einer Form mit einem <xref:System.Windows.Media.PathGeometry>, finden Sie unter [erstellen Sie eine Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Obwohl in diesem Beispiel wird eine Form, um den Bildschirm mit rendert eine <xref:System.Windows.Shapes.Path> Element <xref:System.Windows.Media.Geometry> Objekte möglicherweise auch verwendet werden, um den Inhalt zu beschreiben eine <xref:System.Windows.Media.GeometryDrawing> oder ein <xref:System.Windows.Media.DrawingContext>. Sie können auch zum Ausschneiden und Treffertests verwendet werden.  
  
 Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).
