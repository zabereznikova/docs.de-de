---
title: Festlegen der Sortierungs Modi für Spalten im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742997"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="79f50-102">Gewusst wie: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f50-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="79f50-103">Im <xref:System.Windows.Forms.DataGridView> Steuerelement wird bei Text Feld Spalten standardmäßig die automatische Sortierung verwendet, während andere Spaltentypen nicht automatisch sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="79f50-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="79f50-104">Manchmal sollten Sie diese Standardeinstellungen überschreiben.</span><span class="sxs-lookup"><span data-stu-id="79f50-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="79f50-105">Beispielsweise können Sie Bilder anstelle von Text-, Zahlen-oder enumerationszellwerten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="79f50-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="79f50-106">Obwohl die Bilder nicht sortiert werden können, können die zugrunde liegenden Werte sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="79f50-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="79f50-107">Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschafts Wert einer Spalte das Sortier Verhalten.</span><span class="sxs-lookup"><span data-stu-id="79f50-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="79f50-108">Das folgende Verfahren zeigt die `Priority` Spalte unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="79f50-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="79f50-109">Diese Spalte ist eine Image-Spalte und ist nicht standardmäßig sortierbar.</span><span class="sxs-lookup"><span data-stu-id="79f50-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="79f50-110">Sie enthält jedoch tatsächliche Zellwerte, bei denen es sich um Zeichen folgen handelt, sodass Sie automatisch sortiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="79f50-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="79f50-111">So legen Sie den Sortiermodus für eine Spalte fest</span><span class="sxs-lookup"><span data-stu-id="79f50-111">To set the sort mode for a column</span></span>  
  
- <span data-ttu-id="79f50-112">Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="79f50-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79f50-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="79f50-113">Compiling the Code</span></span>  
 <span data-ttu-id="79f50-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="79f50-114">This example requires:</span></span>  
  
- <span data-ttu-id="79f50-115">Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte namens `Priority` enthält.</span><span class="sxs-lookup"><span data-stu-id="79f50-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
- <span data-ttu-id="79f50-116">Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79f50-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f50-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79f50-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="79f50-118">Sortieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f50-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79f50-119">Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f50-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79f50-120">Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79f50-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
