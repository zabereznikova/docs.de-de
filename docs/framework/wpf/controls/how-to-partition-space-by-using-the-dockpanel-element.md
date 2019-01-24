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
ms.openlocfilehash: 8b79b89e512ec9da27774188aeaeed8ebd5b1153
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577658"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="7fae2-102">Vorgehensweise: Aufteilen von Bereichen mithilfe des DockPanel-Elements</span><span class="sxs-lookup"><span data-stu-id="7fae2-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="7fae2-103">Das folgende Beispiel erstellt eine einfache [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Framework mit einer <xref:System.Windows.Controls.DockPanel> Element.</span><span class="sxs-lookup"><span data-stu-id="7fae2-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="7fae2-104">Die <xref:System.Windows.Controls.DockPanel> teilt den verfügbaren Platz für seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="7fae2-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fae2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7fae2-105">Example</span></span>  
 <span data-ttu-id="7fae2-106">Dieses Beispiel verwendet die <xref:System.Windows.Controls.DockPanel.Dock%2A> -Eigenschaft, die eine angefügte Eigenschaft, um zwei identische anzudocken <xref:System.Windows.Controls.Border> Elemente an die <xref:System.Windows.Controls.Dock.Top> des aufgeteilten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="7fae2-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="7fae2-107">Eine dritte <xref:System.Windows.Controls.Border> Elements angedockt ist die <xref:System.Windows.Controls.Dock.Left>, dessen Breite auf 200 Pixel festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7fae2-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="7fae2-108">Eine vierte <xref:System.Windows.Controls.Border> angedockt ist die <xref:System.Windows.Controls.Dock.Bottom> des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="7fae2-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="7fae2-109">Die letzte <xref:System.Windows.Controls.Border> Elements den verbleibenden Platz ausfüllt.</span><span class="sxs-lookup"><span data-stu-id="7fae2-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="7fae2-110">Standardmäßig ist das letzte untergeordnete Element von einem <xref:System.Windows.Controls.DockPanel> Element füllt die verbleibenden verfügbaren Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="7fae2-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="7fae2-111">Wenn Sie dieses Verhalten nicht wünschen, legen Sie `LastChildFill="False"` fest.</span><span class="sxs-lookup"><span data-stu-id="7fae2-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="7fae2-112">Die kompilierte Anwendung gibt eine neue Benutzeroberfläche aus, die folgendermaßen aussieht.</span><span class="sxs-lookup"><span data-stu-id="7fae2-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="7fae2-113">![Ein typisches DockPanel-Szenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "Panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="7fae2-113">![A typical DockPanel scenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fae2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fae2-114">See also</span></span>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="7fae2-115">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="7fae2-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
