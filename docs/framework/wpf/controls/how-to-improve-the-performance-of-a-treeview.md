---
title: "Gewusst wie: Verbessern der Leistung von TreeView | Microsoft Docs"
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
  - "TreeView-Steuerelement [WPF], Verbessern der Leistung"
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Verbessern der Leistung von TreeView
Falls eine <xref:System.Windows.Controls.TreeView> viele Elemente enthält, kann die Zeit, die zum Laden benötigt wird, zu einer erheblichen Verzögerung in der Benutzeroberfläche führen.  Sie können die Ladezeit verbessern, indem Sie die angefügte <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName>\-Eigenschaft auf `true` festlegen.  Die Reaktion der Benutzeroberfläche kann auch langsam sein, wenn der Benutzer den Bildlauf von <xref:System.Windows.Controls.TreeView> durch Bewegen des Mausrads oder Ziehen des Bildlauffelds ausführt.  Die Leistung von <xref:System.Windows.Controls.TreeView> wird verbessert, wenn der Benutzer einen Bildlauf durch Festlegen der angefügten <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Controls.VirtualizationMode> ausführt.  
  
## Beispiel  
  
## Beschreibung  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TreeView> erstellt, die zur Leistungsoptimierung <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> auf wahr und <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> auf <xref:System.Windows.Controls.VirtualizationMode> festlegt.  
  
## Code  
 [!code-xml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Im folgenden Beispiel werden die im vorherigen Beispiel verwendeten Daten veranschaulicht.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## Siehe auch  
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)