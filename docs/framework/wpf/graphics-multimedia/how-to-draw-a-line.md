---
title: "Gewusst wie: Zeichnen einer Linie | Microsoft Docs"
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
  - "Zeichnen, Linien"
  - "Grafiken [WPF], Linien"
  - "Linien, Zeichnen"
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Zeichnen einer Linie
In diesem Beispiel wird veranschaulicht, wie Sie mithilfe des <xref:System.Windows.Shapes.Line>\-Elements Linien zeichnen.  
  
 Zum Zeichnen einer Linie erstellen Sie ein <xref:System.Windows.Shapes.Line>\-Element.  Verwenden Sie die <xref:System.Windows.Shapes.Line.X1%2A>\-Eigenschaft und die <xref:System.Windows.Shapes.Line.Y1%2A>\-Eigenschaft des Elements, um dessen Startpunkt festzulegen, und verwenden Sie die <xref:System.Windows.Shapes.Line.X2%2A>\-Eigenschaft und die <xref:System.Windows.Shapes.Line.Y2%2A>\-Eigenschaft, um den Endpunkt festzulegen.  Legen Sie abschließend <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> für das Element fest, da eine Linie ohne einen Strich nicht sichtbar ist.  
  
 Das Festlegen des <xref:System.Windows.Shapes.Shape.Fill%2A>\-Elements für eine Linie hat keine Auswirkungen, da Linien keinen Innenbereich aufweisen.  
  
 Im folgenden Beispiel werden drei Linien in einem <xref:System.Windows.Controls.Canvas>\-Element gezeichnet.  
  
## Beispiel  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Siehe auch  
 <xref:System.Windows.Shapes.Line>   
 [Beispiel für Formelemente](http://go.microsoft.com/fwlink/?LinkID=160037)