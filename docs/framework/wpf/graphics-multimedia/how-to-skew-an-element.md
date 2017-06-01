---
title: "Gewusst wie: Neigen eines Elements | Microsoft Docs"
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
  - "Klassen, SkewTransform"
  - "Grafiken, Zerren von Elementen"
  - "Zerren von Elementen"
  - "SkewTransform-Klasse"
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Neigen eines Elements
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.SkewTransform> verwendet wird, um ein Element zu neigen.  Eine [Neigung](GTMT) ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.  Eine typische Verwendung einer <xref:System.Windows.Media.SkewTransform> ist das Simulieren von [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-Tiefe in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]\-Objekten.  
  
 Verwenden Sie die <xref:System.Windows.Media.SkewTransform.CenterX%2A>\-Eigenschaft und die <xref:System.Windows.Media.SkewTransform.CenterY%2A>\-Eigenschaft, um den Mittelpunkt der <xref:System.Windows.Media.SkewTransform> anzugeben.  
  
 Verwenden Sie die <xref:System.Windows.Media.SkewTransform.AngleX%2A>\-Eigenschaft und die <xref:System.Windows.Media.SkewTransform.AngleY%2A>\-Eigenschaft, um den Neigungswinkels der x\-Achse und der y\-Achse anzugeben, und um das aktuelle Koordinatensystem entlang dieser Achsen zu neigen.  
  
 Berücksichtigen Sie beim Vorhersagen der Auswirkungen einer Neigungstransformation, dass <xref:System.Windows.Media.SkewTransform.AngleX%2A> die Werte der X\-Achse im Verhältnis zum ursprünglichen Koordinatensystem neigt.  Daher rotiert bei einem <xref:System.Windows.Media.SkewTransform.AngleX%2A> von 30, die y\-Achse um 30° durch den Ursprung und neigt die Werte auf der x\-Achse um 30° vom Ursprung.  Entsprechend neigt ein <xref:System.Windows.Media.SkewTransform.AngleY%2A> von 30 die y\-Werte der Form um 30° vom Ursprung.  Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen \(Bewegen\) des Koordinatensystems um 30° in der x\- oder y\-Achse.  
  
 Im folgenden Beispiel wird aus einem Mittelpunkt \(0,0\) eine horizontale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> angewendet.  
  
## Beispiel  
 [!code-xml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Im folgenden Beispiel wird aus einem Mittelpunkt \(25,25\) eine horizontale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> angewendet.  
  
 [!code-xml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 Im folgenden Beispiel wird aus einem Mittelpunkt \(25,25\) eine vertikale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> angewendet.  
  
 [!code-xml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 Die folgende Illustration zeigt die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.  
  
 ![SkewTransform&#45;Beispiele](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.png "img\_wcpsdk\_graphicsmm\_skewtransformexample")  
  
        Die drei SkewTransform\-Beispiele veranschaulicht  
  
 Das vollständige Beispiel finden Sie unter [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Siehe auch  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.SkewTransform>   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)