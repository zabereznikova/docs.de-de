---
title: 'Vorgehensweise: Einfrieren von Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: b4e65f0fd329f624aa186748d298257b15617c17
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584264"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="671db-102">Vorgehensweise: Einfrieren von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="671db-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="671db-103">Wenn Benutzer Daten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement in Windows Forms angezeigt werden, müssen sie mitunter häufig auf eine bestimmte Spalte oder Gruppe von Spalten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="671db-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="671db-104">Wenn Sie beispielsweise eine Tabelle mit Kundendaten anzeigen, die viele Spalten enthält, ist es hilfreich, wenn die Namen der Kunden immer angezeigt werden, während andere Spalten außerhalb des sichtbaren Bereichs liegen.</span><span class="sxs-lookup"><span data-stu-id="671db-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="671db-105">Zu diesem Zweck können Sie Spalten im Steuerelement fixieren.</span><span class="sxs-lookup"><span data-stu-id="671db-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="671db-106">Wenn Sie eine Spalte fixieren, werden automatisch auch alle Spalten links daneben (bzw. rechts daneben in von rechts nach links geschriebenen Sprachen) fixiert.</span><span class="sxs-lookup"><span data-stu-id="671db-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="671db-107">Fixierte Spalten behalten ihre Position bei, während alle anderen Spalten bei einem Bildlauf mitwandern.</span><span class="sxs-lookup"><span data-stu-id="671db-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="671db-108">Wenn die Neuanordnung von Spalten aktiviert ist, werden die fixierten Spalten als eine Gruppe im Unterschied zu den nicht fixierten Spalten behandelt.</span><span class="sxs-lookup"><span data-stu-id="671db-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="671db-109">Benutzer können Spalten in beiden Gruppen neu positionieren, jedoch keine Spalte aus einer Gruppe in die andere verschieben.</span><span class="sxs-lookup"><span data-stu-id="671db-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="671db-110">Die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>-Eigenschaft einer Spalte bestimmt, ob die Spalte immer innerhalb des Rasters sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="671db-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="671db-111">Visual Studio bietet Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="671db-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="671db-112">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Fixieren von Spalten in der Windows Forms-DataGridView-Steuerelement mithilfe des Designers](freeze-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="671db-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](freeze-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="671db-113">So fixieren Sie eine Spalte programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="671db-113">To freeze a column programmatically</span></span>  
  
-   <span data-ttu-id="671db-114">Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="671db-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="671db-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="671db-115">Compiling the Code</span></span>  
 <span data-ttu-id="671db-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="671db-116">This example requires:</span></span>  
  
-   <span data-ttu-id="671db-117">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte namens `AddToCartButton` enthält.</span><span class="sxs-lookup"><span data-stu-id="671db-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
-   <span data-ttu-id="671db-118">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="671db-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="671db-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="671db-119">See also</span></span>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="671db-120">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="671db-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="671db-121">Vorgehensweise: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="671db-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
