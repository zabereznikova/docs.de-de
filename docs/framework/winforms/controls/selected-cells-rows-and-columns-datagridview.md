---
title: 'Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 95229f1915b25962a700a7d6aced0a012bbe6657
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626913"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6a7f7-102">Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a7f7-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6a7f7-103">Erhalten Sie die ausgewählten Zellen, Zeilen oder Spalten aus einer <xref:System.Windows.Forms.DataGridView> Kontrolle über die entsprechenden Eigenschaften: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="6a7f7-104">In den folgenden Verfahren Sie die ausgewählten Zellen abzurufen und zeigen die Zeilen- und Spaltenindizes in einem <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="6a7f7-105">Um die ausgewählten Zellen in einem DataGridView-Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-105">To get the selected cells in a DataGridView control</span></span>  
  
-   <span data-ttu-id="6a7f7-106">Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6a7f7-107">Verwenden der <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode, um zu verhindern, dass eine potenziell große Anzahl von Zellen.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="6a7f7-108">Um die ausgewählten Zeilen in einem DataGridView-Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-108">To get the selected rows in a DataGridView control</span></span>  
  
-   <span data-ttu-id="6a7f7-109">Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="6a7f7-110">Um Benutzer zum Auswählen von Zeilen zu aktivieren, müssen Sie legen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="6a7f7-111">Um die ausgewählten Spalten in einem DataGridView-Steuerelement zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-111">To get the selected columns in a DataGridView control</span></span>  
  
-   <span data-ttu-id="6a7f7-112">Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="6a7f7-113">Um Benutzern das Auswählen von Spalten zu aktivieren, müssen Sie festlegen der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a7f7-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6a7f7-114">Compiling the Code</span></span>  
 <span data-ttu-id="6a7f7-115">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6a7f7-115">This example requires:</span></span>  
  
-   <span data-ttu-id="6a7f7-116"><xref:System.Windows.Forms.Button> Steuerelemente, die mit dem Namen `selectedCellsButton`, `selectedRowsButton`, und `selectedColumnsButton`, jeweils mit Handlern für die <xref:System.Windows.Forms.Control.Click> Ereignis angefügt.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
-   <span data-ttu-id="6a7f7-117">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="6a7f7-118">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6a7f7-119">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6a7f7-119">Robust Programming</span></span>  
 <span data-ttu-id="6a7f7-120">Die Sammlungen, die in diesem Thema beschriebenen ist nicht effizient, wenn große Anzahl von Zellen, Zeilen oder Spalten ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="6a7f7-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="6a7f7-121">Weitere Informationen zur Verwendung dieser Sammlungen mit großen Mengen von Daten finden Sie unter [Best Practices für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="6a7f7-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7f7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a7f7-122">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="6a7f7-123">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a7f7-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
