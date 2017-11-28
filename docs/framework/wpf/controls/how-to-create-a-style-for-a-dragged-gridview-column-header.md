---
title: "Gewusst wie: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 503683de875b8853e219139800eef2a5417a1574
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="f8b47-102">Gewusst wie: Erstellen eines Stils für einen gezogenen GridView-Spaltenheader</span><span class="sxs-lookup"><span data-stu-id="f8b47-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="f8b47-103">In diesem Beispiel wird gezeigt, wie die Darstellung eines gezogenen geändert <xref:System.Windows.Controls.GridViewColumnHeader> Wenn der Benutzer die Position einer Spalte ändert.</span><span class="sxs-lookup"><span data-stu-id="f8b47-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b47-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8b47-104">Example</span></span>  
 <span data-ttu-id="f8b47-105">Wenn Sie eine Spaltenüberschrift ziehen, an einen anderen Speicherort in einer <xref:System.Windows.Controls.ListView> , verwendet <xref:System.Windows.Controls.GridView> für den Ansichtsmodus an, die für die Spalte an die neue Position verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="f8b47-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="f8b47-106">Während Sie den Spaltenüberschrift ziehen, wird eine unverankerte Kopie des Headers zusätzlich zu der ursprünglichen Überschrift angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8b47-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="f8b47-107">Eine Spaltenüberschrift in einer <xref:System.Windows.Controls.GridView> wird dargestellt, indem Sie eine <xref:System.Windows.Controls.GridViewColumnHeader> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f8b47-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="f8b47-108">Sie können zum Anpassen der Darstellung der Gleitkomma- und ursprünglichen Header festlegen <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="f8b47-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="f8b47-109">Diese <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> werden angewendet, wenn die <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> Eigenschaftswert ist `true` und <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> Eigenschaftswert ist <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="f8b47-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="f8b47-110">Wenn der Benutzer die Maustaste drückt und gedrückt hält, während sich der Mauszeiger auf die <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> Eigenschaftswert geändert wird, um `true`.</span><span class="sxs-lookup"><span data-stu-id="f8b47-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="f8b47-111">Ebenso, wenn der Benutzer beginnt des Ziehvorgangs wird, die <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> eigenschaftsänderungen <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="f8b47-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="f8b47-112">Im folgende Beispiel wird gezeigt, wie festzulegende <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> so ändern Sie die <xref:System.Windows.Controls.Control.Foreground%2A> und <xref:System.Windows.Controls.Control.Background%2A> Farben, der die ursprünglichen "oder" floating-Header, wenn eine Spalte an eine neue Position bewegt.</span><span class="sxs-lookup"><span data-stu-id="f8b47-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="f8b47-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8b47-113">See Also</span></span>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="f8b47-114">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="f8b47-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="f8b47-115">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="f8b47-115">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="f8b47-116">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="f8b47-116">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
