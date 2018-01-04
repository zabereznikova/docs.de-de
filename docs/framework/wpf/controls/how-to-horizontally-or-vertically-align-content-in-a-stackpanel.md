---
title: 'Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel'
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
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad3252b249c716d59b72a6c5af7bd96f2d058126
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="b23c6-102">Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel</span><span class="sxs-lookup"><span data-stu-id="b23c6-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="b23c6-103">In diesem Beispiel wird gezeigt, wie zum Anpassen der <xref:System.Windows.Controls.StackPanel.Orientation%2A> von Inhalten innerhalb einer <xref:System.Windows.Controls.StackPanel> Element sowie zum Anpassen der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> von untergeordnetem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="b23c6-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b23c6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b23c6-104">Example</span></span>  
 <span data-ttu-id="b23c6-105">Das folgende Beispiel erstellt drei <xref:System.Windows.Controls.ListBox> Elemente im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b23c6-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="b23c6-106">Jede <xref:System.Windows.Controls.ListBox> stellt die möglichen Werte für die <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften eine <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="b23c6-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="b23c6-107">Wenn ein Benutzer einen Wert in einem der auswählt der <xref:System.Windows.Controls.ListBox> Elemente, die zugeordnete Eigenschaft von der <xref:System.Windows.Controls.StackPanel> und seiner untergeordneten <xref:System.Windows.Controls.Button> Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="b23c6-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b23c6-108">Der folgende Code-Behind-Datei definiert die Änderungen auf die Ereignisse, die zugeordnet sind die <xref:System.Windows.Controls.ListBox> Menüauswahl ändert.</span><span class="sxs-lookup"><span data-stu-id="b23c6-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="b23c6-109"><xref:System.Windows.Controls.StackPanel>wird durch identifiziert die <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span><span class="sxs-lookup"><span data-stu-id="b23c6-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b23c6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b23c6-110">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [<span data-ttu-id="b23c6-111">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="b23c6-111">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
