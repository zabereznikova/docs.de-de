---
title: Sortieren von Daten in das Windows Forms-DataGridView-Steuerelement
ms.date: 02/13/2018
ms.prod: .net-framework
ms.technology:
- dotnet-winforms
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ab4ec958a4275ed805ed33ee3eff9ab67fde3dc
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2018
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b1b30-102">Sortieren von Daten in das Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1b30-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="b1b30-103">Standardmäßig können Benutzer sortieren Sie die Daten in einem <xref:System.Windows.Forms.DataGridView> Steuerelement, indem Sie auf die Kopfzeile der Spalte ein Text-Feld (oder drücken F3, wenn sich der Fokus einer Zelle der Text im Feld unter .NET Framework 4.7.2 und höheren Versionen ist).</span><span class="sxs-lookup"><span data-stu-id="b1b30-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="b1b30-104">Sie können die <xref:System.Windows.Forms.DataGridViewColumn.SortMode> Eigenschaft bestimmter Spalten, damit Benutzer nach anderen Spaltentypen zu sortieren, wenn es sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="b1b30-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="b1b30-105">Sie können die Daten auch Sortieren programmgesteuert durch eine Spalte oder mehreren Spalten.</span><span class="sxs-lookup"><span data-stu-id="b1b30-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b1b30-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b1b30-106">In this section</span></span>

[<span data-ttu-id="b1b30-107">Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1b30-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="b1b30-108">Beschreibt die Optionen zum Sortieren der Daten im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b1b30-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="b1b30-109">Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1b30-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="b1b30-110">Beschreibt, wie Benutzern das Sortieren nach Spalten, die nicht standardmäßig sortierbar sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b1b30-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="b1b30-111">Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1b30-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="b1b30-112">Beschreibt, wie Daten programmgesteuert sortiert und Gewusst wie: Anpassen der Sortierung mithilfe der <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> Ereignis oder durch Implementierung der <xref:System.Collections.IComparer> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b1b30-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="b1b30-113">Referenz</span><span class="sxs-lookup"><span data-stu-id="b1b30-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="b1b30-114">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b1b30-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="b1b30-115">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.Sort%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b1b30-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="b1b30-116">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b1b30-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="b1b30-117">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumnSortMode> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b1b30-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1b30-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1b30-118">See also</span></span>

[<span data-ttu-id="b1b30-119">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1b30-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
[<span data-ttu-id="b1b30-120">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1b30-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  