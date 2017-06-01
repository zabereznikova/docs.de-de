---
title: "Gewusst wie: Zeichnen von Text in grafischen Elementen | Microsoft Docs"
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
  - "Zeichnen, Text in grafische Elemente"
  - "Text, Zeichnen in grafische Elemente"
  - "Typografie, Zeichnen von Text in grafische Elemente"
  - "Grafische Elemente, Zeichnen von Text in"
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Zeichnen von Text in grafischen Elementen
Im folgenden Beispiel wird gezeigt, wie Text mithilfe eines <xref:System.Windows.Media.DrawingContext>\-Objekts in ein <xref:System.Windows.Media.DrawingVisual> gezeichnet wird.  Zeichnungskontext wird durch Aufrufen der <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>\-Methode eines <xref:System.Windows.Media.DrawingVisual>\-Objekts zurückgegeben.  Sie können Grafiken und Text in einen Zeichnungskontext zeichnen.  
  
 Um Text im Zeichnungskontext zu zeichnen, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawText%2A>\-Methode eines <xref:System.Windows.Media.DrawingContext>\-Objekts.  Wenn Sie den Text in den Zeichnungskontext gezeichnet haben, rufen Sie die <xref:System.Windows.Media.DrawingContext.Close%2A>\-Methode auf, um den Zeichnungskontext zu schließen und den Inhalt beizubehalten.  
  
## Beispiel  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Das vollständige Codebeispiel, aus dem das vorangehende Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit "DrawingVisuals"](http://go.microsoft.com/fwlink/?LinkID=159994).