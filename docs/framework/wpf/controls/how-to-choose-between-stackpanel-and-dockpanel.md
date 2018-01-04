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
ms.workload: dotnet
ms.openlocfilehash: 0274a0f078c378a101bdf4a4ae456fd2ce9f4185
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="37b77-102">Gewusst wie: Auswählen von StackPanel oder DockPanel</span><span class="sxs-lookup"><span data-stu-id="37b77-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="37b77-103">Dieses Beispiel zeigt, wie Sie zwischen der Verwendung auswählen einer <xref:System.Windows.Controls.StackPanel> oder ein <xref:System.Windows.Controls.DockPanel> Wenn Sie Inhalte in Stapeln eine <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="37b77-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37b77-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37b77-104">Example</span></span>  
 <span data-ttu-id="37b77-105">Obwohl Sie entweder verwenden können <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.StackPanel> zum Stapeln von untergeordneten Elementen, die beiden Steuerelemente immer erzeugen nicht die gleichen Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="37b77-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="37b77-106">Beispielsweise kann die Reihenfolge der untergeordneten Elemente beeinflussen die Größe von untergeordneten Elementen in einer <xref:System.Windows.Controls.DockPanel> jedoch nicht in eine <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="37b77-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="37b77-107">Dieses unterschiedliche Verhalten tritt auf, weil <xref:System.Windows.Controls.StackPanel> Measures in Richtung stapeln an <xref:System.Double>.<xref:System.Double.PositiveInfinity>jedoch <xref:System.Windows.Controls.DockPanel> misst nur die verfügbare Größe.</span><span class="sxs-lookup"><span data-stu-id="37b77-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="37b77-108">Das folgende Beispiel zeigt diese wesentliche Unterschied zwischen <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="37b77-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="37b77-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37b77-109">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="37b77-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="37b77-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
