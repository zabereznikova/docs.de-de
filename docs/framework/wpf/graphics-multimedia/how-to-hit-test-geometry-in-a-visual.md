---
title: "Gewusst wie: Treffertest f&#252;r eine Geometrie in einem visuellen Objekt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Geometry-Objekte, Visuelle Objekte mit"
  - "Treffertests, In visuellen Objekten mit Geometry-Objekten"
  - "Visuelle Objekte, Treffertests für"
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Treffertest f&#252;r eine Geometrie in einem visuellen Objekt
Dieses Beispiel zeigt, wie Sie einen [Treffertest](GTMT) für ein visuelles Objekt durchführen, das aus einem oder mehreren <xref:System.Windows.Media.Geometry>\-Objekten besteht.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Media.DrawingGroup> aus einem visuellen Objekt abrufen, das die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>\-Methode verwendet.  Anschließend wird ein Treffertest für den gerenderten Inhalt der einzelnen Zeichnungen in der <xref:System.Windows.Media.DrawingGroup> durchgeführt, um zu bestimmen, welche Geometrie getroffen wurde.  
  
> [!NOTE]
>  In den meisten Fällen verwenden Sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>\-Methode, um zu bestimmen, ob ein Punkt innerhalb des gerenderten Inhalts eines visuellen Objekts liegt.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Die <xref:System.Windows.Media.Geometry.FillContains%2A>\-Methode ist eine überladene Methode, mit der Sie einen Treffertest durchführen können, indem Sie einen angegebenen <xref:System.Windows.Point> oder eine <xref:System.Windows.Media.Geometry> verwenden.  Wenn eine Geometrie gestrichelt ist, kann die Strichelung ggf. über die Füllbereichsgrenzen hinaus reichen.  In diesem Fall sollten Sie zusätzlich zu <xref:System.Windows.Media.Geometry.FillContains%2A> auch <xref:System.Windows.Media.Geometry.StrokeContains%2A> aufrufen.  
  
 Sie können auch einen <xref:System.Windows.Media.ToleranceType> angeben, der für die Bézier\-Abflachung verwendet wird.  
  
> [!NOTE]
>  Bei diesem Beispiel werden keine Clippings oder Transformationen berücksichtigt, die ggf. auf die Geometrie angewendet werden.  Außerdem funktioniert dieses Beispiel nicht mit einem formatierten Steuerelement, da diesem keine Zeichnungen direkt zugeordnet sind.  
  
## Siehe auch  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Treffertest mit Geometrie als Parameter](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)