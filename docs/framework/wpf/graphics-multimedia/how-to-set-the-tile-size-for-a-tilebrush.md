---
title: "Gewusst wie: Festlegen der Fl&#228;chengr&#246;&#223;e f&#252;r ein TileBrush-Objekt | Microsoft Docs"
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
  - "TileBrush, Kachelgröße"
  - "Viewport-Eigenschaft von TileBrush"
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Festlegen der Fl&#228;chengr&#246;&#223;e f&#252;r ein TileBrush-Objekt
In diesem Beispiel wird das Festlegen der Flächengröße für ein <xref:System.Windows.Media.TileBrush>\-Objekt erläutert.  Standardmäßig erstellt ein <xref:System.Windows.Media.TileBrush>\-Objekt eine einzelne Fläche, die den gezeichneten Bereich vollständig ausfüllt.  Dieses Verhalten kann durch Festlegen der Eigenschaften <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> überschrieben werden.  
  
 Die <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft gibt die Flächengröße für ein <xref:System.Windows.Media.TileBrush>\-Objekt an.  Standardmäßig ist der Wert der <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft relativ zur Größe des gezeichneten Bereichs.  Wenn die <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Eigenschaft eine absolute Flächengröße angeben soll, müssen Sie die <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>\-Eigenschaft auf <xref:System.Windows.Media.BrushMappingMode> festlegen.  
  
## Beispiel  
 Im folgenden Beispiel wird mithilfe eines <xref:System.Windows.Media.ImageBrush>\-Objekts \(einem <xref:System.Windows.Media.TileBrush>\-Typ\) ein Rechteck mit Flächen gezeichnet.  In diesem Beispiel werden die Seiten der einzelnen Flächen auf 50 Prozent der Seiten des Ausgabebereichs \(des Rechtecks\) festgelegt.  Als Ergebnis wird das Rechteck mit vier Projektionen des Bilds gezeichnet.  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Beispiel für die Anordnung mit einem Bildpinsel](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.ImageBrush>\-Klasse erstellt, dessen <xref:System.Windows.Media.TileBrush.Viewport%2A>\-Objekt auf `0,0,25,25` und dessen <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>\-Objekt auf <xref:System.Windows.Media.BrushMappingMode> festgelegt werden. Mit dieser Klasse wird ein weiteres Rechteck gezeichnet.  Als Ergebnis erzeugt der Pinsel Flächen mit einer Breite von 25 [Pixel](GTMT) und einer Höhe von ebenfalls 25 [Pixel](GTMT).  
  
 In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.  
  
 ![Ein gekachelter TileBrush mit einem Viewport von 0,0;0,25;0,25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Die vorangehenden Beispiele sind Teil eines umfangreicheren Beispiels.  Das vollständige Beispiel finden Sie unter [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 In diesem Beispiel wird die <xref:System.Windows.Media.ImageBrush>\-Klasse verwendet. Die Eigenschaften <xref:System.Windows.Media.TileBrush.Viewport%2A> und <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> für die anderen <xref:System.Windows.Media.TileBrush>\-Objekte, also für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>, verhalten sich jedoch identisch.  Weitere Informationen über <xref:System.Windows.Media.ImageBrush> und die anderen <xref:System.Windows.Media.TileBrush>\-Objekte finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.TileBrush>   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Erstellen von unterschiedlichen Kachelmustern mit einem TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)