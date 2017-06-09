---
title: "Gewusst wie: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses | Microsoft Docs"
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
  - "Grafiken, Transformationen als Ereignisantwort"
  - "LayoutTransform-Eigenschaft"
  - "Eigenschaften, LayoutTransform"
  - "Eigenschaften, RenderTransform"
  - "RenderTransform-Eigenschaft"
  - "Transformationen als Ereignisantwort"
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses
In diesem Beispiel wird erläutert, wie Sie eine <xref:System.Windows.Media.ScaleTransform> anwenden, wenn ein Ereignis auftritt.  Mithilfe des hier dargestellten Konzepts können Sie auch andere Transformationstypen anwenden.  Weitere Informationen zu den verfügbaren Transformationstypen finden Sie in der <xref:System.Windows.Media.Transform>\-Klasse oder unter [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
 Sie können mit einem der folgenden beiden Verfahren eine Transformation auf ein Element anwenden:  
  
-   Wenn sich die Transformation *nicht* auf das Layout auswirken soll, verwenden Sie die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft des Elements.  
  
-   Wenn sich die Transformation auf das Layout auswirken soll, verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A>\-Eigenschaft des Elements.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft einer Schaltfläche angewendet.  Wenn der Mauszeiger über die Schaltfläche bewegt wird, werden <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>\-Eigenschaft und die <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>\-Eigenschaft der <xref:System.Windows.Media.ScaleTransform> auf `2` festgelegt. Die Schaltfläche wird dadurch vergrößert.  Wenn der Mauszeiger von der Schaltfläche weg bewegt wird, werden <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> auf `1` festgelegt, sodass die Schaltfläche auf die ursprüngliche Größe zurückgesetzt wird.  
  
## Beispiel  
 [!code-xml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)