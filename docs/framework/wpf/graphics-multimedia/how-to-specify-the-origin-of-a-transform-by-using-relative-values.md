---
title: "Gewusst wie: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten | Microsoft Docs"
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
  - "Grafiken, Ursprung von Transformationen"
  - "Ursprung von Transformationen"
  - "Transformationen, Ursprung von"
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten
In diesem Beispiel wird gezeigt, wie mithilfe von relativen Werten der Ursprung einer <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angegeben wird, die auf ein <xref:System.Windows.FrameworkElement> angewendet wird.  
  
 Beim Drehen, Skalieren oder [Neigen](GTMT) eines <xref:System.Windows.FrameworkElement>\-Objekts mithilfe der <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft wird die Transformation durch die Standardeinstellung auf die linke obere Ecke des Elements angewendet.  Wenn Sie von der Mitte des Elements aus drehen, skalieren oder neigen möchten, können Sie dies ändern, indem Sie für den Mittelpunkt der Transformation den Mittelpunkt des Elements festlegen.  Für diese Lösung müssen Sie jedoch die Größe des Elements kennen.  Einfacher lässt sich eine Transformation auf den Mittelpunkt eines Elements anwenden, wenn statt der Festlegung eines Werts für den Mittelpunkt der Transformation selbst die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft des Elements auf \(0.5, 0.5\) festgelegt wird.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.RotateTransform> verwendet, um ein <xref:System.Windows.Controls.Button>\-Steuerelement um 45 Grad im Uhrzeigersinn zu drehen.  Da in dem Beispiel kein Mittelpunkt angegeben ist, dreht sich die Schaltfläche um den Punkt \(0, 0\), die obere linke Ecke.  Die <xref:System.Windows.Media.RotateTransform>\-Klasse wird auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angewendet.  
  
 In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
  
        Eine Drehung um 45 Grad im Uhrzeigersinn unter Verwendung der RenderTransform\-Eigenschaft  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Im folgenden Beispiel wird außerdem eine <xref:System.Windows.Media.RotateTransform> verwendet, um eine <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn zu drehen. In diesem Beispiel wird jedoch der <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf \(0.5, 0.5\) festgelegt.   Dadurch erfolgt die Drehung um den Mittelpunkt der Schaltfläche, nicht um die obere linke Ecke.  
  
 In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
  
        Eine Drehung um 45 Grad unter Verwendung der RenderTransform\-Eigenschaft mit einem RenderTransformOrigin von \(0.5, 0.5\)  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Weitere Informationen zum Transformieren von <xref:System.Windows.FrameworkElement>\-Objekten finden Sie unter [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Transform>   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)