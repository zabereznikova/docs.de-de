---
title: 'Gewusst wie: Erstellen einer zusammengesetzten Form'
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
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ded7bd25f7f416bc512051f883b4ae12b2fa56d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
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
