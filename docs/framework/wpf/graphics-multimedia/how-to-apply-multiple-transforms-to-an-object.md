---
title: "Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt | Microsoft Docs"
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
  - "Grafiken, Gruppieren von Transform-Objekten"
  - "Gruppieren von Transform-Objekten"
  - "Transform-Objekte, Gruppieren"
  - "TransformGroup"
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Anwenden mehrerer Transformationen auf ein Objekt
In diesem Beispiel wird dargestellt, wie mithilfe von <xref:System.Windows.Media.TransformGroup> mindestens zwei <xref:System.Windows.Media.Transform>\-Objekte in einem einzigen zusammengesetzten <xref:System.Windows.Media.Transform>\-Objekt gruppiert werden können.  
  
## Beispiel  
 In folgendem Beispiel wird mithilfe von <xref:System.Windows.Media.TransformGroup> eine <xref:System.Windows.Media.ScaleTransform> und eine <xref:System.Windows.Media.RotateTransform> auf <xref:System.Windows.Controls.Button> angewendet.  
  
 [!code-xml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Media.TransformGroup>   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Beispiel für 2D\-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252)