---
title: "Gewusst wie: Erstellen einer zusammengesetzten Form | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zusammengesetzte Formen"
  - "Grafiken, Zusammengesetzte Formen"
  - "Formen, Zusammengesetzt"
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen einer zusammengesetzten Form
Dieses Beispiel zeigt, wie Sie zusammengesetzte Formen erstellen, indem Sie <xref:System.Windows.Media.Geometry>\-Objekte verwenden, und diese anzeigen, indem Sie ein <xref:System.Windows.Shapes.Path>\-Element verwenden.  Im folgenden Beispiel werden eine <xref:System.Windows.Media.LineGeometry>, eine <xref:System.Windows.Media.EllipseGeometry> und eine <xref:System.Windows.Media.RectangleGeometry> zusammen mit <xref:System.Windows.Media.GeometryGroup> verwendet, um eine zusammengesetzte Form zu erstellen.  Die Geometrien werden dann mithilfe eines <xref:System.Windows.Shapes.Path>\-Elements gezeichnet.  
  
## Beispiel  
 [!code-xml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 In der folgenden Abbildung wird die im vorherigen Beispiel erstellte Form dargestellt.  
  
 ![Eine zusammengesetzte Geometrie, die mit einer GeometryGroup erstellt wird](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.png "wcpsdk\_graphicsmm\_compositegeometryexample1")  
Zusammengesetzte Geometrie  
  
 Komplexere Formen, zum Beispiel Polygone und Formen mit gekrümmten Segmenten, können Sie mithilfe einer <xref:System.Windows.Media.PathGeometry> erstellen.  Ein Beispiel für die Erstellung einer Form mithilfe einer <xref:System.Windows.Media.PathGeometry> finden Sie unter [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Obwohl in diesem Beispiel eine Form auf dem Bildschirm mithilfe eines <xref:System.Windows.Shapes.Path>\-Elements gerendert wird, können Sie auch <xref:System.Windows.Media.Geometry>\-Objekte verwenden, um den Inhalt eines <xref:System.Windows.Media.GeometryDrawing>\- oder <xref:System.Windows.Media.DrawingContext>\-Elements zu beschreiben.  Sie können die Objekte auch für das Clipping und für Treffertests verwenden.  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).