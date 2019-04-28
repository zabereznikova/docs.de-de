---
title: 'Vorgehensweise: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: 03348aa0eb5b6c1791c27683c1c6c6a5d4a8a9d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771032"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="b6845-102">Vorgehensweise: Horizontales oder vertikales Ausrichten von Inhalt in einem StackPanel-Objekt</span><span class="sxs-lookup"><span data-stu-id="b6845-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="b6845-103">Dieses Beispiel zeigt, wie Sie Anpassen der <xref:System.Windows.Controls.StackPanel.Orientation%2A> des Inhalts in einer <xref:System.Windows.Controls.StackPanel> -Element sowie Gewusst wie: Anpassen der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> von untergeordnetem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="b6845-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6845-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6845-104">Example</span></span>  
 <span data-ttu-id="b6845-105">Das folgende Beispiel erstellt drei <xref:System.Windows.Controls.ListBox> Elemente im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6845-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="b6845-106">Jede <xref:System.Windows.Controls.ListBox> stellt die möglichen Werte der <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften eine <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="b6845-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="b6845-107">Wenn ein Benutzer einen Wert in einem der auswählt der <xref:System.Windows.Controls.ListBox> Elemente, die zugeordnete Eigenschaft die <xref:System.Windows.Controls.StackPanel> und ihre untergeordneten <xref:System.Windows.Controls.Button> Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="b6845-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b6845-108">Der folgende Code-Behind-Datei definiert die Ereignisse, die zugeordnet werden die Änderungen der <xref:System.Windows.Controls.ListBox> Änderungen der Auswahl.</span><span class="sxs-lookup"><span data-stu-id="b6845-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="b6845-109"><xref:System.Windows.Controls.StackPanel> wird durch identifiziert die <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span><span class="sxs-lookup"><span data-stu-id="b6845-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b6845-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6845-110">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="b6845-111">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="b6845-111">Panels Overview</span></span>](panels-overview.md)
