---
title: 'Vorgehensweise: Auswählen von StackPanel oder DockPanel'
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
ms.openlocfilehash: 458ba2fe23ecde28b3eb15400e7a9fa49c4cca68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622532"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Vorgehensweise: Auswählen von StackPanel oder DockPanel
Dieses Beispiel zeigt die Auswahl zwischen der Verwendung einer <xref:System.Windows.Controls.StackPanel> oder ein <xref:System.Windows.Controls.DockPanel> Wenn Sie Inhalte in Stapeln eine <xref:System.Windows.Controls.Panel>.  
  
## <a name="example"></a>Beispiel  
 Sie können zwar entweder verwenden <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.StackPanel> zum Stapeln von untergeordneten Elementen, die beiden Steuerelemente immer erzeugen nicht die gleichen Ergebnisse. Z. B. die Reihenfolge, in der untergeordneten Elemente kann Auswirkungen auf die Größe von untergeordneten Elementen in einem <xref:System.Windows.Controls.DockPanel> jedoch nicht in einer <xref:System.Windows.Controls.StackPanel>. Dieses unterschiedliche Verhalten tritt auf, weil <xref:System.Windows.Controls.StackPanel> Measures in der Richtung des Stapels bei <xref:System.Double>.<xref:System.Double.PositiveInfinity>jedoch <xref:System.Windows.Controls.DockPanel> misst nur die verfügbare Größe.  
  
 Das folgende Beispiel veranschaulicht diese unterscheiden sich hauptsächlich <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
