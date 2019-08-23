---
title: 'Vorgehensweise: Aufteilen von Bereichen mithilfe des DockPanel-Elements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960197"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="9e243-102">Vorgehensweise: Aufteilen von Bereichen mithilfe des DockPanel-Elements</span><span class="sxs-lookup"><span data-stu-id="9e243-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="9e243-103">Im folgenden Beispiel wird ein einfaches [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Framework mit einem <xref:System.Windows.Controls.DockPanel> -Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e243-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="9e243-104">Der <xref:System.Windows.Controls.DockPanel> verfügbare Speicherplatz der Partitionen für seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="9e243-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e243-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e243-105">Example</span></span>  
 <span data-ttu-id="9e243-106">In diesem Beispiel wird <xref:System.Windows.Controls.DockPanel.Dock%2A> die-Eigenschaft, die eine angefügte Eigenschaft ist, zum <xref:System.Windows.Controls.Border> Andocken <xref:System.Windows.Controls.Dock.Top> zweier identischer Elemente an der des partitionierten Raums verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e243-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="9e243-107">Ein drittes <xref:System.Windows.Controls.Border> Element wird an den <xref:System.Windows.Controls.Dock.Left>angedockt, wobei seine Breite auf 200 Pixel festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9e243-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="9e243-108">Ein viertes <xref:System.Windows.Controls.Border> wird an den <xref:System.Windows.Controls.Dock.Bottom> des Bildschirms angedockt.</span><span class="sxs-lookup"><span data-stu-id="9e243-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="9e243-109">Das letzte <xref:System.Windows.Controls.Border> Element füllt den verbleibenden Platz automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="9e243-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="9e243-110">Standardmäßig füllt das letzte untergeordnete <xref:System.Windows.Controls.DockPanel> Element eines-Elements den verbleibenden nicht zugeordneten Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="9e243-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="9e243-111">Wenn Sie dieses Verhalten nicht wünschen, legen Sie `LastChildFill="False"` fest.</span><span class="sxs-lookup"><span data-stu-id="9e243-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="9e243-112">Die kompilierte Anwendung gibt eine neue Benutzeroberfläche aus, die folgendermaßen aussieht.</span><span class="sxs-lookup"><span data-stu-id="9e243-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="9e243-113">![Ein typisches DockPanel-Szenario.](./media/panel-intro-dockpanel.PNG "Panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="9e243-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e243-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e243-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="9e243-115">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="9e243-115">Panels Overview</span></span>](panels-overview.md)
