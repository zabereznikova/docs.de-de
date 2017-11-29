---
title: "Gewusst wie: Auswählen von StackPanel oder DockPanel"
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
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 40d99e090a0599c98560e4102d18d35ee7174259
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Gewusst wie: Auswählen von StackPanel oder DockPanel
Dieses Beispiel zeigt, wie Sie zwischen der Verwendung auswählen einer <xref:System.Windows.Controls.StackPanel> oder ein <xref:System.Windows.Controls.DockPanel> Wenn Sie Inhalte in Stapeln eine <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Beispiel  
 Obwohl Sie entweder verwenden können <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.StackPanel> zum Stapeln von untergeordneten Elementen, die beiden Steuerelemente immer erzeugen nicht die gleichen Ergebnisse. Beispielsweise kann die Reihenfolge der untergeordneten Elemente beeinflussen die Größe von untergeordneten Elementen in einer <xref:System.Windows.Controls.DockPanel> jedoch nicht in eine <xref:System.Windows.Controls.StackPanel>. Dieses unterschiedliche Verhalten tritt auf, weil <xref:System.Windows.Controls.StackPanel> Measures in Richtung stapeln an <xref:System.Double>.<xref:System.Double.PositiveInfinity>jedoch <xref:System.Windows.Controls.DockPanel> misst nur die verfügbare Größe.  
  
 Das folgende Beispiel zeigt diese wesentliche Unterschied zwischen <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
