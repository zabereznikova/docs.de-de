---
title: Sortieren von Daten im DataGridView-Steuerelement
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742943"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9ffc5-102">Sortieren von Daten im Windows Forms DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9ffc5-102">Sorting data in the Windows Forms DataGridView control</span></span>

<span data-ttu-id="9ffc5-103">Standardmäßig können Benutzer die Daten in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement sortieren, indem Sie auf den Header einer Textfeld Spalte klicken (oder indem Sie F3 drücken, wenn sich eine Textfeld Zelle auf .NET Framework 4.7.2 und höhere Versionen konzentriert).</span><span class="sxs-lookup"><span data-stu-id="9ffc5-103">By default, users can sort the data in a <xref:System.Windows.Forms.DataGridView> control by clicking the header of a text box column (or by pressing F3 when a text box cell is focused on .NET Framework 4.7.2 and later versions).</span></span> <span data-ttu-id="9ffc5-104">Sie können die <xref:System.Windows.Forms.DataGridViewColumn.SortMode>-Eigenschaft bestimmter Spalten ändern, um Benutzern das Sortieren nach anderen Spaltentypen zu ermöglichen, wenn dies sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-104">You can modify the <xref:System.Windows.Forms.DataGridViewColumn.SortMode> property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="9ffc5-105">Sie können die Daten auch Programm gesteuert nach beliebigen Spalten oder nach mehreren Spalten sortieren.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9ffc5-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9ffc5-106">In this section</span></span>

[<span data-ttu-id="9ffc5-107">Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ffc5-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="9ffc5-108">Beschreibt die Optionen zum Sortieren von Daten im-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-108">Describes the options for sorting data in the control.</span></span>

[<span data-ttu-id="9ffc5-109">Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ffc5-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
<span data-ttu-id="9ffc5-110">Beschreibt, wie Sie es Benutzern ermöglichen, nach Spalten zu sortieren, die nicht standardmäßig sortierbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>

[<span data-ttu-id="9ffc5-111">Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ffc5-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
<span data-ttu-id="9ffc5-112">Beschreibt, wie Daten Programm gesteuert sortiert werden und wie die Sortierung mithilfe des <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> Ereignisses oder durch Implementieren der <xref:System.Collections.IComparer> Schnittstelle angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>

## <a name="reference"></a><span data-ttu-id="9ffc5-113">Referenz</span><span class="sxs-lookup"><span data-stu-id="9ffc5-113">Reference</span></span>

<xref:System.Windows.Forms.DataGridView>  
<span data-ttu-id="9ffc5-114">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
<span data-ttu-id="9ffc5-115">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridView.Sort%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
<span data-ttu-id="9ffc5-116">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
<span data-ttu-id="9ffc5-117">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridViewColumnSortMode>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9ffc5-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ffc5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ffc5-118">See also</span></span>

- [<span data-ttu-id="9ffc5-119">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9ffc5-119">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="9ffc5-120">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ffc5-120">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
