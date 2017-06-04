---
title: "Gewusst wie: Ausw&#228;hlen von StackPanel oder DockPanel | Microsoft Docs"
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
  - "Steuerelemente [WPF], DockPanel"
  - "Steuerelemente [WPF], StackPanel"
  - "DockPanel-Steuerelement, StackPanel-Steuerelement verglichen mit"
  - "StackPanel-Steuerelement, DockPanel-Steuerelement verglichen mit"
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Ausw&#228;hlen von StackPanel oder DockPanel
Dieses Beispiel veranschaulicht, wie Sie zwischen einem <xref:System.Windows.Controls.StackPanel> und einem <xref:System.Windows.Controls.DockPanel> auswählen, wenn Sie Inhalt in einem <xref:System.Windows.Controls.Panel> stapeln.  
  
## Beispiel  
 Obwohl <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.StackPanel> zum Stapeln von untergeordneten Elementen verwendet werden können, führen die beiden Steuerelemente nicht immer zu demselben Ergebnis.  Die Reihenfolge der untergeordneten Elemente kann beispielsweise die Größe der untergeordneten Elemente in einem <xref:System.Windows.Controls.DockPanel>, jedoch nicht in einem <xref:System.Windows.Controls.StackPanel> beeinflussen.  Dieses unterschiedliche Verhalten tritt auf, da <xref:System.Windows.Controls.StackPanel> in Stapelrichtung bei <xref:System.Double>.<xref:System.Double.PositiveInfinity>misst, wohingegen der <xref:System.Windows.Controls.DockPanel> nur die verfügbare Größe misst.  
  
 Im folgenden Beispiel wird dieser Hauptunterschied zwischen <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel> veranschaulicht.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.DockPanel>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)