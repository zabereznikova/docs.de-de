---
title: "Gewusst wie: Verbessern der Bildlaufleistung eines Listenfelds | Microsoft Docs"
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
  - "ListBox-Steuerelement [WPF], Verbessern der Bildlaufleistung"
  - "ListBox-Steuerelement [WPF], Wiederverwenden von Elementcontainern"
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Verbessern der Bildlaufleistung eines Listenfelds
Falls ein <xref:System.Windows.Controls.ListBox> viele Elemente enthält, kann die Reaktion der Benutzeroberfläche langsam sein, wenn der Benutzer den Bildlauf von <xref:System.Windows.Controls.ListBox> durch Bewegen des Mausrads oder Ziehen des Bildlauffelds ausführt.  Die Leistung von <xref:System.Windows.Controls.ListBox> wird verbessert, wenn der Benutzer einen Bildlauf durch Festlegen der angefügten <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Controls.VirtualizationMode> ausführt.  
  
## Beispiel  
  
## Beschreibung  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ListBox> erstellt und <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> wird auf <xref:System.Windows.Controls.VirtualizationMode> festgelegt, um die Leistung während des Bildlaufs zu verbessern.  
  
## Code  
 [!code-xml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 Im folgenden Beispiel werden die im vorherigen Beispiel verwendeten Daten veranschaulicht.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]