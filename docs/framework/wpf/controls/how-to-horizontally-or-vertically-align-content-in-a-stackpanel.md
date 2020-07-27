---
title: 'Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel'
description: Erfahren Sie, wie Sie die Inhalts Orientierung in einem Windows Presentation Foundation StackPanel und HorizontalAlignment und VerticalAlignment von untergeordnetem Inhalt anpassen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: d3c7215d8193d1d8a72597c44cf265f5bd400ea1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167634"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="b2334-103">Gewusst wie: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel</span><span class="sxs-lookup"><span data-stu-id="b2334-103">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="b2334-104">In diesem Beispiel wird gezeigt, wie der <xref:System.Windows.Controls.StackPanel.Orientation%2A> Inhalt in einem- <xref:System.Windows.Controls.StackPanel> Element angepasst wird und wie der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> der untergeordnete Inhalt angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="b2334-104">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2334-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2334-105">Example</span></span>  
 <span data-ttu-id="b2334-106">Im folgenden Beispiel werden drei <xref:System.Windows.Controls.ListBox> Elemente in erstellt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2334-106">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="b2334-107">Jede <xref:System.Windows.Controls.ListBox> stellt die möglichen Werte der <xref:System.Windows.Controls.StackPanel.Orientation%2A> -Eigenschaft, der-Eigenschaft <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und der-Eigenschaft <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> eines dar <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="b2334-107">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="b2334-108">Wenn ein Benutzer in einem der-Elemente einen Wert auswählt <xref:System.Windows.Controls.ListBox> , ändern sich die zugeordnete-Eigenschaft der und der untergeordneten <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.Button> Elemente.</span><span class="sxs-lookup"><span data-stu-id="b2334-108">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b2334-109">Mit der folgenden Code Behind-Datei werden die Änderungen an den Ereignissen definiert, die mit den <xref:System.Windows.Controls.ListBox> Auswahl Änderungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="b2334-109">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="b2334-110"><xref:System.Windows.Controls.StackPanel>wird vom identifiziert <xref:System.Windows.FrameworkElement.Name%2A> `sp1` .</span><span class="sxs-lookup"><span data-stu-id="b2334-110"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b2334-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2334-111">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="b2334-112">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="b2334-112">Panels Overview</span></span>](panels-overview.md)
