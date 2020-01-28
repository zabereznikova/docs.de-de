---
title: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744054"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fa340-102">Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa340-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fa340-103">Sie können die Darstellung jeder Zelle anpassen, indem Sie das <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis des <xref:System.Windows.Forms.DataGridView>-Steuer Elements verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fa340-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="fa340-104">Sie können die <xref:System.Drawing.Graphics> des <xref:System.Windows.Forms.DataGridView>-Steuer Elements aus der Eigenschaft <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>extrahieren.</span><span class="sxs-lookup"><span data-stu-id="fa340-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="fa340-105">Mit diesem <xref:System.Drawing.Graphics>können Sie die Darstellung des gesamten <xref:System.Windows.Forms.DataGridView> Steuer Elements beeinflussen, Sie sollten sich jedoch in der Regel nur auf die Darstellung der Zelle auswirken, die gerade gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="fa340-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="fa340-106">Mit der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> können Sie die Zeichnungsvorgänge auf die Zelle beschränken, die gerade gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="fa340-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="fa340-107">Im folgenden Codebeispiel zeichnen Sie alle Zellen in einer `ContactName` Spalte mit dem Farbschema des <xref:System.Windows.Forms.DataGridView> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="fa340-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="fa340-108">Der Text Inhalt jeder Zelle wird in <xref:System.Drawing.Color.Crimson%2A>gezeichnet, und ein einfügen-Rechteck wird in derselben Farbe wie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridView> Steuer Elements gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fa340-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa340-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa340-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa340-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fa340-110">Compiling the Code</span></span>  
 <span data-ttu-id="fa340-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fa340-111">This example requires:</span></span>  
  
- <span data-ttu-id="fa340-112">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1` mit einer `ContactName` Spalte, z. b. in der Customers-Tabelle der Beispieldatenbank Northwind.</span><span class="sxs-lookup"><span data-stu-id="fa340-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="fa340-113">Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".</span><span class="sxs-lookup"><span data-stu-id="fa340-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa340-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa340-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="fa340-115">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa340-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
