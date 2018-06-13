---
title: 'Gewusst wie: Abrufen oder Festlegen eines Dockwerts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: b792c8b2342416fb380827b702efa28885145d66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554780"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="09cdb-102">Gewusst wie: Abrufen oder Festlegen eines Dockwerts</span><span class="sxs-lookup"><span data-stu-id="09cdb-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="09cdb-103">Das folgende Beispiel zeigt das Zuweisen einer <xref:System.Windows.Controls.Dock> Wert für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="09cdb-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="09cdb-104">Im Beispiel wird die <xref:System.Windows.Controls.DockPanel.GetDock%2A> und <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methoden der <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="09cdb-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09cdb-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09cdb-105">Example</span></span>  
 <span data-ttu-id="09cdb-106">Das Beispiel erstellt eine Instanz von der <xref:System.Windows.Controls.TextBlock> Element, `txt1`, und weist eine <xref:System.Windows.Controls.Dock> Wert `Top` mithilfe der <xref:System.Windows.Controls.DockPanel.SetDock%2A> Methode <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="09cdb-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="09cdb-107">Anschließend fügt den Wert des der <xref:System.Windows.Controls.Dock> Eigenschaft, um die <xref:System.Windows.Controls.TextBlock.Text%2A> von der <xref:System.Windows.Controls.TextBlock> -Element mithilfe der <xref:System.Windows.Controls.DockPanel.GetDock%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="09cdb-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="09cdb-108">Im Beispiel wird schließlich fügt die <xref:System.Windows.Controls.TextBlock> Element an der übergeordneten Tabelle <xref:System.Windows.Controls.DockPanel>, `dp1`.</span><span class="sxs-lookup"><span data-stu-id="09cdb-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="09cdb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09cdb-109">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [<span data-ttu-id="09cdb-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="09cdb-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
