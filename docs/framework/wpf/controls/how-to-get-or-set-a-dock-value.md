---
title: 'Gewusst wie: Abrufen oder Festlegen eines Dockwerts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d663acf446ee2f7a36fc2d0c8605c31a0f2a84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-or-set-a-dock-value"></a>Gewusst wie: Abrufen oder Festlegen eines Dockwerts
Das folgende Beispiel zeigt das Zuweisen einer <xref:System.Windows.Controls.Dock> Wert für ein Objekt. Im Beispiel wird die <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methoden der <xref:System.Windows.Controls.DockPanel>.  
  
## <a name="example"></a>Beispiel  
 Das Beispiel erstellt eine Instanz von der <xref:System.Windows.Controls.TextBlock> Element, `txt1`, und weist eine <xref:System.Windows.Controls.Dock> Wert `Top` mithilfe der <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode <xref:System.Windows.Controls.DockPanel>. Anschließend fügt den Wert des der <xref:System.Windows.Controls.Dock> Eigenschaft, um die <xref:System.Windows.Controls.TextBlock.Text%2A> von der <xref:System.Windows.Controls.TextBlock> -Element mithilfe der <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode. Im Beispiel wird schließlich fügt die <xref:System.Windows.Controls.TextBlock> Element an der übergeordneten Tabelle <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
