---
title: Sortieren von Daten in das Windows Forms-DataGridView-Steuerelement
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1cbfb4a19e9bb0db5cbb595a91a254a3a8e3f309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536012"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8fd29-102">Sortieren von Daten in das Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8fd29-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="8fd29-103">Standardmäßig können Benutzer sortieren Sie die Daten in einem <xref:System.Windows.Forms.DataGridView> Steuerelement, indem Sie auf die Kopfzeile der Spalte ein Text-Feld (oder drücken F3, wenn sich der Fokus einer Zelle der Text im Feld unter .NET Framework 4.7.2 und höheren Versionen ist).</span><span class="sxs-lookup"><span data-stu-id="8fd29-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="8fd29-104">Sie können die <xref:System.Windows.Forms.DataGridViewColumn.SortMode> Eigenschaft bestimmter Spalten, damit Benutzer nach anderen Spaltentypen zu sortieren, wenn es sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="8fd29-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="8fd29-105">Sie können die Daten auch Sortieren programmgesteuert durch eine Spalte oder mehreren Spalten.</span><span class="sxs-lookup"><span data-stu-id="8fd29-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8fd29-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8fd29-106">In this section</span></span>

[<span data-ttu-id="8fd29-107">Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd29-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="8fd29-108">Beschreibt die Optionen zum Sortieren der Daten im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8fd29-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="8fd29-109">Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd29-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="8fd29-110">Beschreibt, wie Benutzern das Sortieren nach Spalten, die nicht standardmäßig sortierbar sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8fd29-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="8fd29-111">Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd29-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="8fd29-112">Beschreibt, wie Daten programmgesteuert sortiert und Gewusst wie: Anpassen der Sortierung mithilfe der <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> Ereignis oder durch Implementierung der <xref:System.Collections.IComparer> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8fd29-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="8fd29-113">Verweis</span><span class="sxs-lookup"><span data-stu-id="8fd29-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="8fd29-114">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8fd29-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="8fd29-115">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8fd29-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="8fd29-116">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8fd29-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="8fd29-117">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumnSortMode> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="8fd29-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fd29-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fd29-118">See also</span></span>

[<span data-ttu-id="8fd29-119">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8fd29-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
[<span data-ttu-id="8fd29-120">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fd29-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  