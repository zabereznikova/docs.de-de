---
title: "Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements | Microsoft Docs"
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
  - "Geschlossene Formen, Zeichnen mit Polygonelementen"
  - "Zeichnen, Geschlossene Formen mit Polygonelementen"
  - "Grafiken, Polygonelemente"
  - "Polygonelemente"
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements
In diesem Beispiel wird veranschaulicht, wie eine geschlossene Form mithilfe des <xref:System.Windows.Shapes.Polygon>\-Elements gezeichnet wird.  Erstellen Sie zum Zeichnen einer geschlossenen Form ein <xref:System.Windows.Shapes.Polygon>\-Element. Verwenden Sie dessen <xref:System.Windows.Shapes.Polygon.Points%2A>\-Eigenschaft, um die Eckpunkte der Form anzugeben.  Eine Verbindungslinie zwischen dem ersten und dem letzten Punkt wird automatisch gezeichnet.  Geben Sie zum Abschluss <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A> oder beides an.  
  
## Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ist die gültige Syntax für Punkte eine durch Leerzeichen getrennte Liste von x\- und y\-Koordinatenpaaren, die durch Trennzeichen getrennt sind.  
  
 [!code-xml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> als Container für die Vielecke verwendet wird, können vieleckige Elemente \(sowie alle anderen Formelemente\) mit allen <xref:System.Windows.Controls.Panel> oder allen <xref:System.Windows.Controls.Control> verwendet werden, die Inhalte unterstützen, bei denen es sich nicht um Text handelt.  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).