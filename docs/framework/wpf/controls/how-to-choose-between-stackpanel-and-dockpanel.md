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
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="d07f8-102">Gewusst wie: Auswählen von StackPanel oder DockPanel</span><span class="sxs-lookup"><span data-stu-id="d07f8-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="d07f8-103">Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Controls.StackPanel> oder eine <xref:System.Windows.Controls.DockPanel> auswählen, wenn Sie Inhalte in einem <xref:System.Windows.Controls.Panel>stapeln.</span><span class="sxs-lookup"><span data-stu-id="d07f8-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>

## <a name="example"></a><span data-ttu-id="d07f8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d07f8-104">Example</span></span>
 <span data-ttu-id="d07f8-105">Obwohl Sie entweder <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.StackPanel> verwenden können, um untergeordnete Elemente zu stapeln, werden die beiden-Steuerelemente nicht immer dieselben Ergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="d07f8-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="d07f8-106">Beispielsweise kann sich die Reihenfolge, in der Sie untergeordnete Elemente platzieren, auf die Größe der untergeordneten Elemente in einem <xref:System.Windows.Controls.DockPanel>, aber nicht in einem <xref:System.Windows.Controls.StackPanel>auswirken.</span><span class="sxs-lookup"><span data-stu-id="d07f8-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="d07f8-107">Dieses unterschiedliche Verhalten tritt auf, weil <xref:System.Windows.Controls.StackPanel> Measures in der stapelweise bei [Double. positivabfinity](xref:System.Double.PositiveInfinity); <xref:System.Windows.Controls.DockPanel> misst jedoch nur die verfügbare Größe.</span><span class="sxs-lookup"><span data-stu-id="d07f8-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at [Double.PositiveInfinity](xref:System.Double.PositiveInfinity); however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>

 <span data-ttu-id="d07f8-108">Im folgenden Beispiel wird dieser Hauptunterschied zwischen <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel>veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d07f8-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="d07f8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d07f8-109">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="d07f8-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="d07f8-110">Panels Overview</span></span>](panels-overview.md)
