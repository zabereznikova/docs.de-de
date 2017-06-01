---
title: "Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement | Microsoft Docs"
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
  - "Binden von Daten an InkCanvas"
  - "Binden von Daten, an InkCanvas"
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaft ein <xref:System.Windows.Controls.InkCanvas> zu einem anderen <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft an eine Datenquelle.  
  
 [!code-xml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 Das folgende Beispiel deklariert zwei <xref:System.Windows.Controls.InkCanvas> -Objekte in XAML und stellt die Bindung zwischen ihnen und anderen Datenquellen her.  Die erste <xref:System.Windows.Controls.InkCanvas>namens `ic`, zwei Datenquellen gebunden ist.  Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> und <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften `ic` gebunden sind, um <xref:System.Windows.Controls.ListBox> -Objekte, die ihrerseits an in XAML definierte Arrays gebunden sind.  Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, und <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaften des zweiten <xref:System.Windows.Controls.InkCanvas> gebunden sind mit dem ersten <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]