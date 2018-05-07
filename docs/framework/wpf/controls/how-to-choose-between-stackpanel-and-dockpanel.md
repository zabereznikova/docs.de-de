---
title: 'Gewusst wie: Auswählen von StackPanel oder DockPanel'
ms.date: 03/30/2017
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
ms.openlocfilehash: c9bfb8d29051a9cfa61d3fcb93b8bb9a68d14e00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
