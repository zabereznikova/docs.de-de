---
title: 'Gewusst wie: Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: 1741ce84fab1639409a7c834845573239c51cc35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554910"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="837f1-102">Gewusst wie: Verwenden von Triggern zum Formatieren ausgewählter Elemente in einem ListView</span><span class="sxs-lookup"><span data-stu-id="837f1-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="837f1-103">In diesem Beispiel wird gezeigt, wie definiert <xref:System.Windows.Style.Triggers%2A> für eine <xref:System.Windows.Controls.ListViewItem> Steuerelement, damit bei einem Eigenschaftswert des eine <xref:System.Windows.Controls.ListViewItem> Änderungen, die <xref:System.Windows.Style> von der <xref:System.Windows.Controls.ListViewItem> Änderungen als Reaktion.</span><span class="sxs-lookup"><span data-stu-id="837f1-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="837f1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="837f1-104">Example</span></span>  
 <span data-ttu-id="837f1-105">Gegebenenfalls die <xref:System.Windows.Style> von einem <xref:System.Windows.Controls.ListViewItem> definieren, um als Reaktion auf eigenschaftenänderungen zu ändern, <xref:System.Windows.Style.Triggers%2A> für die <xref:System.Windows.Style> ändern.</span><span class="sxs-lookup"><span data-stu-id="837f1-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="837f1-106">Das folgende Beispiel definiert eine <xref:System.Windows.Trigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft, um <xref:System.Windows.Media.Brushes.Blue%2A> und ändert die <xref:System.Windows.FrameworkElement.Cursor%2A> anzuzeigenden eine <xref:System.Windows.Input.CursorType.Hand> bei der <xref:System.Windows.UIElement.IsMouseOver%2A> eigenschaftsänderungen `true`.</span><span class="sxs-lookup"><span data-stu-id="837f1-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="837f1-107">Das folgende Beispiel definiert eine <xref:System.Windows.MultiTrigger> festlegt, die <xref:System.Windows.Controls.Control.Foreground%2A> Eigenschaft eine <xref:System.Windows.Controls.ListViewItem> zu <xref:System.Windows.Media.Brushes.Yellow%2A> bei der <xref:System.Windows.Controls.ListViewItem> das ausgewählte Element ist und über den Tastaturfokus verfügt.</span><span class="sxs-lookup"><span data-stu-id="837f1-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="837f1-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="837f1-108">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="837f1-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="837f1-109">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="837f1-110">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="837f1-110">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="837f1-111">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="837f1-111">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
