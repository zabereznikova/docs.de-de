---
title: 'Vorgehensweise: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 415cf18aa4cf01b151a414dbc26609af638a7af7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213284"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fd22f-102">Vorgehensweise: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd22f-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fd22f-103">Sie können die Darstellung jeder Zelle anpassen, indem die Behandlung der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fd22f-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="fd22f-104">Extrahieren der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Drawing.Graphics> aus der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="fd22f-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="fd22f-105">Mit diesem <xref:System.Drawing.Graphics>, Sie können die Darstellung des gesamten beeinflussen <xref:System.Windows.Forms.DataGridView> -Steuerelement, aber Sie sollten in der Regel nur auf die Darstellung der Zelle zu beeinflussen, das gerade gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="fd22f-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="fd22f-106">Die <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> ermöglicht es Ihnen, Ihre Zeichenvorgänge auf die Zelle zu beschränken, die gerade gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="fd22f-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="fd22f-107">Das folgende Codebeispiel zeigt, zeichnen Sie alle Zellen in einer `ContactName` Spalte unter Verwendung der <xref:System.Windows.Forms.DataGridView> Farbschema des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="fd22f-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="fd22f-108">Jede Zelle des Text-Inhalt gezeichnet wird <xref:System.Drawing.Color.Crimson%2A>, und eine abgesenktes Rechteck gezeichnet wird, in die gleiche Farbe wie die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.GridColor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fd22f-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd22f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd22f-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd22f-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fd22f-110">Compiling the Code</span></span>  
 <span data-ttu-id="fd22f-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fd22f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="fd22f-112">Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1` mit einem `ContactName` Spalte wie in der Customers-Tabelle in der Northwind-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="fd22f-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="fd22f-113">Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".</span><span class="sxs-lookup"><span data-stu-id="fd22f-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd22f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd22f-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="fd22f-115">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd22f-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
