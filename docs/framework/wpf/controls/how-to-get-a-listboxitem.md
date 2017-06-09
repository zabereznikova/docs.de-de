---
title: "Gewusst wie: Abrufen eines ListBoxItem | Microsoft Docs"
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
  - "ListBox-Steuerelemente, Abrufen eines ListBoxItem"
  - "ListBoxItem"
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Abrufen eines ListBoxItem
Wenn Sie ein bestimmtes <xref:System.Windows.Controls.ListBoxItem> an einem bestimmten Index in <xref:System.Windows.Controls.ListBox> abrufen müssen, können Sie <xref:System.Windows.Controls.ItemContainerGenerator> verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.ListBox> mit den zugehörigen Elementen veranschaulicht.  
  
 [!code-xml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie das Element abrufen, indem Sie den Index des Elements in der <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A>\-Eigenschaft von <xref:System.Windows.Controls.ItemContainerGenerator> angeben.  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 Nachdem Sie das Listenfeldelement abgerufen haben, können Sie den Inhalt des Elements anzeigen, wie im folgenden Beispiel dargestellt.  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]