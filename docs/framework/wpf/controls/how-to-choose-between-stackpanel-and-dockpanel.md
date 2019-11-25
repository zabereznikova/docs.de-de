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
ms.openlocfilehash: bdf4b38e67a7856136224368e86609c135e5ad6f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976441"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>Gewusst wie: Auswählen von StackPanel oder DockPanel
Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Controls.StackPanel> oder eine <xref:System.Windows.Controls.DockPanel> auswählen, wenn Sie Inhalte in einem <xref:System.Windows.Controls.Panel>stapeln.

## <a name="example"></a>Beispiel
 Obwohl Sie entweder <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.StackPanel> verwenden können, um untergeordnete Elemente zu stapeln, werden die beiden-Steuerelemente nicht immer dieselben Ergebnisse erzielen. Beispielsweise kann sich die Reihenfolge, in der Sie untergeordnete Elemente platzieren, auf die Größe der untergeordneten Elemente in einem <xref:System.Windows.Controls.DockPanel>, aber nicht in einem <xref:System.Windows.Controls.StackPanel>auswirken. Dieses unterschiedliche Verhalten tritt auf, weil <xref:System.Windows.Controls.StackPanel> Measures in der stapelweise bei [Double. positivabfinity](xref:System.Double.PositiveInfinity); <xref:System.Windows.Controls.DockPanel> misst jedoch nur die verfügbare Größe.

 Im folgenden Beispiel wird dieser Hauptunterschied zwischen <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel>veranschaulicht.

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [Übersicht über Panel-Elemente](panels-overview.md)
