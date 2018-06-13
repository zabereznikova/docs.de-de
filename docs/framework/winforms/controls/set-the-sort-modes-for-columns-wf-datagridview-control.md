---
title: 'Gewusst wie: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 08d90bb45006af798b629f58821cbf50ee9ef089
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535730"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="33b33-102">Gewusst wie: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33b33-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="33b33-103">In der <xref:System.Windows.Forms.DataGridView> Steuerung, verwenden die im Feld Textspalten automatische Sortierung in der Standardeinstellung, während andere Spaltentypen nicht automatisch sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="33b33-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="33b33-104">In einigen Fällen möchten diese Standardeinstellungen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="33b33-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="33b33-105">Beispielsweise können Sie Bilder anstelle von Text, Zahlen oder Zelle Enumerationswerte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="33b33-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="33b33-106">Während die Bilder nicht sortiert werden, können die zugrunde liegenden Werte, die sie darstellen sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="33b33-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="33b33-107">In der <xref:System.Windows.Forms.DataGridView> -Steuerelement, das <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> ihr Sortierverhalten bestimmt der Wert einer Spalte.</span><span class="sxs-lookup"><span data-stu-id="33b33-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="33b33-108">Die folgende Prozedur zeigt die `Priority` Spalte aus [wie: Anpassen der Datenformatierung im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="33b33-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="33b33-109">Diese Spalte ist eine Image-Spalte und ist nicht standardmäßig sortierbar.</span><span class="sxs-lookup"><span data-stu-id="33b33-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="33b33-110">Es enthält tatsächlichen Zellwerte, die Zeichenfolgen, jedoch sind, damit automatisch sortiert werden können.</span><span class="sxs-lookup"><span data-stu-id="33b33-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="33b33-111">Um den Sortiermodus für eine Spalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="33b33-111">To set the sort mode for a column</span></span>  
  
-   <span data-ttu-id="33b33-112">Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="33b33-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33b33-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="33b33-113">Compiling the Code</span></span>  
 <span data-ttu-id="33b33-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="33b33-114">This example requires:</span></span>  
  
-   <span data-ttu-id="33b33-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte namens `Priority` enthält.</span><span class="sxs-lookup"><span data-stu-id="33b33-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
-   <span data-ttu-id="33b33-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33b33-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b33-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33b33-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="33b33-118">Sortieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33b33-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="33b33-119">Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33b33-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="33b33-120">Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33b33-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
