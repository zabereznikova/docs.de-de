---
title: "Gewusst wie: Abrufen oder Festlegen eines Dockwerts | Microsoft Docs"
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
  - "Dock-Werte, Abrufen"
  - "Dock-Werte, Festlegen"
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Abrufen oder Festlegen eines Dockwerts
Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Dock>\-Wert einem Objekt zugewiesen wird.  Im Beispiel werden die <xref:System.Windows.Controls.DockPanel.GetDock%2A>\-Methode und die <xref:System.Windows.Controls.DockPanel.SetDock%2A>\-Methode von <xref:System.Windows.Controls.DockPanel> verwendet.  
  
## Beispiel  
 Das Beispiel erstellt eine Instanz des <xref:System.Windows.Controls.TextBlock>\-Elements `txt1` und weist einen <xref:System.Windows.Controls.Dock>\-Wert von `Top` durch die Verwendung der <xref:System.Windows.Controls.DockPanel.SetDock%2A>\-Methode von <xref:System.Windows.Controls.DockPanel> zu.  Anschließend wird der Wert der <xref:System.Windows.Controls.Dock>\-Eigenschaft dem <xref:System.Windows.Controls.TextBlock.Text%2A> des <xref:System.Windows.Controls.TextBlock>\-Elements unter Verwendung der <xref:System.Windows.Controls.DockPanel.GetDock%2A>\-Methode hinzugefügt.  Im Beispiel wird schließlich das <xref:System.Windows.Controls.TextBlock>\-Element dem übergeordneten <xref:System.Windows.Controls.DockPanel>, `dp1` hinzugefügt.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.DockPanel>   
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>   
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)