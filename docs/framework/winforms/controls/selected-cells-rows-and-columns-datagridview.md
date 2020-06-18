---
title: Ausgewählte Zellen, Zeilen und Spalten im DataGridView-Steuerelement
description: Erfahren Sie, wie Sie die ausgewählten Zellen, Zeilen oder Spalten mithilfe entsprechender Eigenschaften aus einem DataGridView-Steuerelement erhalten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 32ddae34104d23b8e5fbc0cce7da79f33fcce1d2
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904168"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="47305-103">Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47305-103">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="47305-104">Die ausgewählten Zellen, Zeilen oder Spalten können Sie <xref:System.Windows.Forms.DataGridView> mithilfe der entsprechenden Eigenschaften aus einem-Steuerelement erhalten: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> , <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> .</span><span class="sxs-lookup"><span data-stu-id="47305-104">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="47305-105">In den folgenden Prozeduren werden die ausgewählten Zellen angezeigt, und die Zeilen-und Spalten Indizes werden in einem angezeigt <xref:System.Windows.Forms.MessageBox> .</span><span class="sxs-lookup"><span data-stu-id="47305-105">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="47305-106">So erhalten Sie die ausgewählten Zellen in einem DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="47305-106">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="47305-107">Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47305-107">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="47305-108">Verwenden Sie die- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode, um die Anzeige einer potenziell großen Anzahl von Zellen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="47305-108">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="47305-109">So erhalten Sie die ausgewählten Zeilen in einem DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="47305-109">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="47305-110">Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47305-110">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="47305-111">Um Benutzern das Auswählen von Zeilen zu ermöglichen, müssen Sie die- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder festlegen <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="47305-111">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="47305-112">So erhalten Sie die ausgewählten Spalten in einem DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="47305-112">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="47305-113">Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="47305-113">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="47305-114">Um Benutzern die Auswahl von Spalten zu ermöglichen, müssen Sie die- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> oder festlegen <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> .</span><span class="sxs-lookup"><span data-stu-id="47305-114">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="47305-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="47305-115">Compiling the Code</span></span>  
 <span data-ttu-id="47305-116">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="47305-116">This example requires:</span></span>  
  
- <span data-ttu-id="47305-117"><xref:System.Windows.Forms.Button>Steuerelemente `selectedCellsButton` `selectedRowsButton` mit den Namen, und `selectedColumnsButton` , jeweils mit Handlern für das <xref:System.Windows.Forms.Control.Click> angefügte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="47305-117"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="47305-118">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="47305-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="47305-119">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Text?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47305-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="47305-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="47305-120">Robust Programming</span></span>  
 <span data-ttu-id="47305-121">Die in diesem Thema beschriebenen Sammlungen werden nicht effizient durchgeführt, wenn eine große Anzahl von Zellen, Zeilen oder Spalten ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="47305-121">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="47305-122">Weitere Informationen zur Verwendung dieser Sammlungen mit großen Datenmengen finden Sie unter [bewährte Methoden zum Skalieren des Windows Forms DataGridView-Steuer](best-practices-for-scaling-the-windows-forms-datagridview-control.md)Elements.</span><span class="sxs-lookup"><span data-stu-id="47305-122">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47305-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47305-123">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="47305-124">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47305-124">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
