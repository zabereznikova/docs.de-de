---
title: Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: c777366124a3cc5f43df8efca54fc366245bcb75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537641"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="7edd0-102">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7edd0-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7edd0-103">Die `DataGridView` gesteuert, die Sie mit einer Vielzahl von Optionen zum Konfigurieren, wie Benutzer Zellen, Zeilen und Spalten auswählen können.</span><span class="sxs-lookup"><span data-stu-id="7edd0-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="7edd0-104">Beispielsweise können Sie aktivieren einfach- oder Mehrfachauswahl, Auswahl der ganze Zeilen oder Spalten, wenn Benutzer Zellen klicken oder Auswahl ganzer Zeilen oder Spalten nur, wenn Benutzer ihre Header auf die Zellenauswahl sowie ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="7edd0-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="7edd0-105">Wenn Sie eine eigene Benutzeroberfläche für die Auswahl bereitstellen möchten, können normale Auswahl deaktivieren und die gesamte Auswahl programmgesteuert zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="7edd0-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="7edd0-106">Darüber hinaus können Sie Benutzern die ausgewählten Werte in die Zwischenablage kopieren.</span><span class="sxs-lookup"><span data-stu-id="7edd0-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7edd0-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7edd0-107">In This Section</span></span>  
 [<span data-ttu-id="7edd0-108">Auswahlmodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7edd0-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7edd0-109">Beschreibt die Optionen für den Benutzer und programmgesteuerte Auswahl im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7edd0-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="7edd0-110">Gewusst wie: Festlegen des Auswahlmodus des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7edd0-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7edd0-111">Beschreibt, wie das Steuerelement für einzeilige Auswahl konfigurieren, wenn ein Benutzer eine Zelle klickt.</span><span class="sxs-lookup"><span data-stu-id="7edd0-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="7edd0-112">Gewusst wie: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7edd0-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="7edd0-113">Beschreibt, wie mit der ausgewählten Zelle, Zeile und Spalte Auflistungen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7edd0-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="7edd0-114">Gewusst wie: Festlegen, dass mehrere Zellen aus dem DataGridView-Steuerelement in Windows Forms in die Zwischenablage kopiert werden können</span><span class="sxs-lookup"><span data-stu-id="7edd0-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="7edd0-115">Beschreibt die Unterstützung der Zwischenablage in das Steuerelement zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7edd0-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7edd0-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="7edd0-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="7edd0-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7edd0-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="7edd0-118">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7edd0-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="7edd0-119">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7edd0-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="7edd0-120">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7edd0-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="7edd0-121">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7edd0-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="7edd0-122">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7edd0-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edd0-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7edd0-123">See Also</span></span>  
 [<span data-ttu-id="7edd0-124">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7edd0-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="7edd0-125">Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7edd0-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
