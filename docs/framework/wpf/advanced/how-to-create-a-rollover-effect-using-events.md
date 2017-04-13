---
title: "Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen | Microsoft Docs"
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
  - "Farben von Elementen, Ändern"
  - "Elementfarben, Ändern"
  - "Rollovereffekt"
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen eines Rollovereffekts mit Ereignissen
Dieses Beispiel zeigt, wie Sie die Farbe eines Elements ändern können, wenn der Mauszeiger in den durch das Element belegten Bereich kommt bzw. diesen verlässt.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei und einer Code\-Behind\-Datei.  
  
> [!NOTE]
>  In diesem Beispiel wird die Verwendung von Ereignissen veranschaulicht. Es wird jedoch empfohlen, diesen Effekt über einen <xref:System.Windows.Trigger> in einem Stil zu erzielen.  Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Beispiel  
 Der folgende [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]\-Code erstellt die Benutzeroberfläche, die aus einem <xref:System.Windows.Controls.Border> rund um einen <xref:System.Windows.Controls.TextBlock> besteht und den <xref:System.Windows.Input.Mouse.MouseEnter>\-Ereignishandler und den <xref:System.Windows.UIElement.MouseLeave>\-Ereignishandler an den <xref:System.Windows.Controls.Border> anfügt.  
  
 [!code-xml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 Der folgende Code\-Behind erstellt die Ereignishandler <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.UIElement.MouseLeave>.  Wenn der Mauszeiger in den <xref:System.Windows.Controls.Border> gelangt, wird der Hintergrund des <xref:System.Windows.Controls.Border> rot .  Wenn der Mauszeiger den <xref:System.Windows.Controls.Border> verlässt, wird der Hintergrund des <xref:System.Windows.Controls.Border> wieder weiß.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]