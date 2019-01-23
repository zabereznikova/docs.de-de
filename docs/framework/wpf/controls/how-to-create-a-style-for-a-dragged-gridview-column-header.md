---
title: 'Vorgehensweise: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dd347781451c9e574fed97c1a553c25bda1b8d7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545396"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="3870a-102">Vorgehensweise: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader</span><span class="sxs-lookup"><span data-stu-id="3870a-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="3870a-103">Dieses Beispiel zeigt, wie Sie das Erscheinungsbild eines gezogenen <xref:System.Windows.Controls.GridViewColumnHeader> Wenn der Benutzer die Position einer Spalte ändert.</span><span class="sxs-lookup"><span data-stu-id="3870a-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3870a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3870a-104">Example</span></span>  
 <span data-ttu-id="3870a-105">Wenn Sie eine Spaltenüberschrift ziehen, an einen anderen Speicherort in einen <xref:System.Windows.Controls.ListView> , verwendet <xref:System.Windows.Controls.GridView> für den Ansichtsmodus an, die für die Spalte an die neue Position verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="3870a-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="3870a-106">Während Sie die Kopfzeile der Spalte ziehen, wird eine schwebende Kopie des Headers zusätzlich zu der ursprünglichen Überschrift angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3870a-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="3870a-107">Einen Spaltenkopf in einem <xref:System.Windows.Controls.GridView> durch dargestellt wird ein <xref:System.Windows.Controls.GridViewColumnHeader> Objekt.</span><span class="sxs-lookup"><span data-stu-id="3870a-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="3870a-108">Sie können zum Anpassen der Darstellung der Gleitkomma- und der ursprüngliche Header festlegen <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="3870a-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="3870a-109">Diese <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> angewendet werden, wenn die <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> Eigenschaftswert ist `true` und <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> Eigenschaftswert ist <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="3870a-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="3870a-110">Wenn der Benutzer die Maustaste drückt und gedrückt hält, während der Mauszeiger über die <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> -Eigenschaftswert auf `true`.</span><span class="sxs-lookup"><span data-stu-id="3870a-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="3870a-111">Ebenso, wenn der Benutzer beginnt der Ziehvorgang, der <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> eigenschaftsänderungen <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="3870a-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="3870a-112">Das folgende Beispiel zeigt, wie festgelegt <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.Background%2A> Farben, der die ursprünglichen und unverankerte-Header, wenn der Benutzer eine Spalte zu einer neuen Position zieht.</span><span class="sxs-lookup"><span data-stu-id="3870a-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="3870a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3870a-113">See also</span></span>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="3870a-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="3870a-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [<span data-ttu-id="3870a-115">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="3870a-115">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
- [<span data-ttu-id="3870a-116">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="3870a-116">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
