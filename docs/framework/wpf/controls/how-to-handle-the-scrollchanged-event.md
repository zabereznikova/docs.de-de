---
title: "Gewusst wie: Behandeln des ScrollChanged-Ereignisses | Microsoft Docs"
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
  - "ScrollChanged-Ereignisse"
  - "ScrollViewer-Steuerelement, Auslösen von ScrollChanged-Ereignissen"
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Behandeln des ScrollChanged-Ereignisses
## Beispiel  
 In diesem Beispiel wird dargestellt, wie das <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>\-Ereignis eines <xref:System.Windows.Controls.ScrollViewer> behandelt wird.  
  
 Ein <xref:System.Windows.Documents.FlowDocument>\-Element mit <xref:System.Windows.Documents.Paragraph>\-Teilen wird in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] definiert.  Wenn das <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>\-Ereignis aufgrund der Benutzerinteraktion eintritt, wird ein Handler aufgerufen, und Text wird in einen <xref:System.Windows.Controls.TextBlock> geschrieben, der angibt, dass das Ereignis eingetreten ist.  
  
 [!code-xml[scrollchangedeventargsLayout#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xml[scrollchangedeventargsLayout#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>   
 <xref:System.Windows.Controls.ScrollChangedEventHandler>   
 <xref:System.Windows.Controls.ScrollChangedEventArgs>