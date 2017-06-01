---
title: "Gewusst wie: Skalieren eines Elements | Microsoft Docs"
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
  - "Klassen, ScaleTransform"
  - "Grafiken, Skalieren von Elementen"
  - "ScaleTransform-Klasse"
  - "Skalieren, Elemente"
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Skalieren eines Elements
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.ScaleTransform> verwendet wird, um ein Element zu skalieren.  
  
 Mithilfe der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>\- und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>\-Eigenschaften können Sie die Größe des Elements um den von Ihnen angegebenen Faktor ändern.  Beispielsweise wird das Element durch einen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>\-Wert von 1,5 auf 150 Prozent der ursprünglichen Breite gestreckt.  Bei einem <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>\-Wert von 0,5 verringert sich die Höhe des Elements um 50 Prozent.  
  
 Verwenden Sie die <xref:System.Windows.Media.ScaleTransform.CenterX%2A>\- und die <xref:System.Windows.Media.ScaleTransform.CenterY%2A>\-Eigenschaft, um den Mittelpunkt der Skalierung anzugeben.  Standardmäßig wird eine <xref:System.Windows.Media.ScaleTransform> am Punkt \(0,0\) zentriert, was der oberen linken Ecke des Rechtecks entspricht.  Das bedeutet, dass das Element verschoben wird und größer erscheint, da durch Anwenden einer <xref:System.Windows.Media.Transform> der Koordinatenbereich geändert wird, in dem sich das Objekt befindet.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> verwendet, um die Größe eines 50x50 großen <xref:System.Windows.Shapes.Rectangle> zu verdoppeln.  Die <xref:System.Windows.Media.ScaleTransform> verfügt über einen Wert von 0 \(Standardwert\) für sowohl <xref:System.Windows.Media.ScaleTransform.CenterX%2A> als auch <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## Beispiel  
 [!code-xml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 In der Regel legen Sie <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> als Mittelpunkt des skalierten Objekts fest: \(<xref:System.Windows.FrameworkElement.Width%2A>\/2, <xref:System.Windows.FrameworkElement.Height%2A>\/2\).  
  
 Im folgenden Beispiel ist ein weiteres <xref:System.Windows.Shapes.Rectangle> dargestellt, dessen Größe verdoppelt wird, allerdings hat die <xref:System.Windows.Media.ScaleTransform> hier einen Wert von 25 für sowohl <xref:System.Windows.Media.ScaleTransform.CenterX%2A> als auch <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, was dem Mittelpunkt des Rechtecks entspricht.  
  
 [!code-xml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 In der folgenden Abbildung wird der Unterschied zwischen den beiden <xref:System.Windows.Media.ScaleTransform>\-Vorgängen veranschaulicht.  Die punktierte Linie stellt die Größe und die Position des Rechtecks vor der Skalierung dar.  
  
 ![2&#45;fach&#45;Skalierung mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.png "wcpsdk\_graphicsmm\_scalecenter")  
Zwei ScaleTransform\-Vorgänge mit demselben ScaleX\- und ScaleY\-Wert aber unterschiedlichen Mittelpunkten  
  
 Das vollständige Beispiel finden Sie unter [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Siehe auch  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)