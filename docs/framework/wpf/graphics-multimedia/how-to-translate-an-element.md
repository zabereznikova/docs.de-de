---
title: "Gewusst wie: &#220;bersetzen eines Elements | Microsoft Docs"
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
  - "Klassen, TranslateTransform"
  - "Grafiken, Übersetzungen"
  - "TranslateTransform-Klasse"
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: &#220;bersetzen eines Elements
In diesem Beispiel wird veranschaulicht, wie ein Element mithilfe von <xref:System.Windows.Media.TranslateTransform> übersetzt \(verschoben\) wird.  
  
 Die <xref:System.Windows.Media.TranslateTransform>\-Klasse ist besonders hilfreich beim Verschieben von Elementen in Bereichen, in denen keine absolute Positionierung unterstützt wird.  Sie können zum Beispiel durch Anwendung von <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft eines Elements ein Element innerhalb von <xref:System.Windows.Controls.StackPanel> oder <xref:System.Windows.Controls.DockPanel> verschieben.  
  
 Verwenden Sie die <xref:System.Windows.Media.TranslateTransform.X%2A>\-Eigenschaft von <xref:System.Windows.Media.TranslateTransform> zum Festlegen des Werts in [Pixel](GTMT), um den das Element entlang der x\-Achse verschoben werden soll.  Verwenden Sie die <xref:System.Windows.Media.TranslateTransform.Y%2A>\-Eigenschaft zum Festlegen des Werts in Pixel, um den das Element entlang der y\-Achse verschoben werden soll.  Wenden Sie anschließend <xref:System.Windows.Media.TranslateTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft des Elements an.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.TranslateTransform> verwendet, um ein Element 50 [Pixel](GTMT) nach rechts und 50 Pixel nach unten zu verschieben.  
  
## Beispiel  
 [!code-xml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Das vollständige Beispiel finden Sie unter [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## Siehe auch  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)