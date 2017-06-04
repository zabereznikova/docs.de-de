---
title: "Gewusst wie: Animieren der Gr&#246;&#223;e von FrameworkElement | Microsoft Docs"
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
  - "Animation, FrameworkElement-Größe"
  - "FrameworkElement, Animieren der Größenänderung von"
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Animieren der Gr&#246;&#223;e von FrameworkElement
Sie können die Größe von <xref:System.Windows.FrameworkElement> animieren, indem Sie die Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> animieren oder eine animierte <xref:System.Windows.Media.ScaleTransform> verwenden.  
  
 Im folgenden Beispiel wird mit diesen zwei Ansätzen die Größe von zwei Schaltflächen animiert.  Die Größe einer Schaltfläche wird geändert, indem die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft animiert wird. Die Größe einer anderen Schaltfläche wird geändert, indem eine <xref:System.Windows.Media.ScaleTransform> animiert wird, die auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angewendet wird.  Jede Schaltfläche weist Text auf.  Zuerst sieht der Text auf beiden Schaltflächen gleich aus. Mit der Größenänderung der Schaltflächen wird der Text der zweiten Schaltfläche jedoch verzerrt.  
  
## Beispiel  
 [!code-xml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Wenn Sie ein Element transformieren, werden das gesamte Element und sein Inhalt transformiert.  Wenn Sie die Größe eines Elements direkt ändern, wie bei der ersten Schaltfläche, wird die Größe des Inhalts des Elements nur geändert, wenn dessen Größe und Position von der Größe des übergeordneten Elements abhängt.  
  
 Das Animieren der Größe eines Elements durch Anwenden einer animierten Transformation auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft weist eine bessere Leistung auf, als die direkte Animation von <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>, da die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft keinen Layoutdurchlauf auslöst.  
  
 Weitere Informationen über das Animieren von Eigenschaften finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Weitere Informationen zu Transformationen finden Sie unter [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).