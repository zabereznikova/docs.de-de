---
title: "Gewusst wie: Horizontales oder vertikales Kippen eines UIElement | Microsoft Docs"
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
  - "Kippen von UIElements"
  - "UIElements, Kippen"
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Horizontales oder vertikales Kippen eines UIElement
In diesem Beispiel wird gezeigt, wie mit <xref:System.Windows.Media.ScaleTransform> ein <xref:System.Windows.UIElement> horizontal oder vertikal gekippt wird.  In diesem Beispiel wird ein <xref:System.Windows.Controls.Button>\-Steuerelement \(ein <xref:System.Windows.UIElement>\-Typ\) gekippt, indem <xref:System.Windows.Media.ScaleTransform> auf die zugehörige <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angewendet wird.  
  
## Beispiel  
 In der folgenden Abbildung ist die zu kippende Schaltfläche dargestellt.  
  
 ![Eine Schaltfläche ohne Transformierung](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.png "graphicsmm\_buttonflipbeforeflip")  
Das zu kippende UIElement  
  
 Im Folgenden wird der Code dargestellt, durch den die Schaltfläche erstellt wird.  
  
 [!code-xml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## Beispiel  
 Um die Schaltfläche horizontal zu kippen, erstellen Sie eine <xref:System.Windows.Media.ScaleTransform>, und legen Sie die zugehörige <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>\-Eigenschaft auf \-1 fest.  Wenden Sie die <xref:System.Windows.Media.ScaleTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft der Schaltfläche an.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Eine horizontal um &#40;0,0&#41; gekippte Schaltfläche](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.png "graphicsmm\_buttonfliphorizontalflip\_displaced")  
Die Schaltfläche nach Anwendung von ScaleTransform  
  
## Beispiel  
 Wie in der vorherigen Abbildung zu sehen ist, wurde die Schaltfläche gekippt und gleichzeitig verschoben.  Dies ist darauf zurückzuführen, dass die Schaltfläche ausgehend von der linken oberen Ecke gekippt wurde.  Um die Schaltfläche an der gleichen Position zu kippen, müssen Sie <xref:System.Windows.Media.ScaleTransform> auf den Mittelpunkt anstatt auf eine Ecke anwenden.  Eine einfache Möglichkeit, um <xref:System.Windows.Media.ScaleTransform> auf den Mittelpunkt der Schaltfläche anzuwenden, besteht darin, die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft der Schaltfläche auf 0,5, 0,5 festzulegen.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Eine horizontal um ihren Mittelpunkt gekippte Schaltfläche](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.png "graphicsmm\_buttonfliphorizontalflip\_inplace")  
Die Schaltfläche mit dem Wert 0,5, 0,5 für RenderTransformOrigin  
  
## Beispiel  
 Um die Schaltfläche vertikal zu kippen, legen Sie die <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>\-Eigenschaft des <xref:System.Windows.Media.ScaleTransform>\-Objekts anstelle der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A>\-Eigenschaft fest.  
  
 [!code-xml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Eine vertikal um ihren Mittelpunkt gekippte Schaltfläche](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.png "graphicsmm\_buttonflipverticalflip\_inplace")  
Die vertikal gekippte Schaltfläche  
  
## Siehe auch  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)