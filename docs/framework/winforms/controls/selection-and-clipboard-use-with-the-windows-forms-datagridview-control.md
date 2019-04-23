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
ms.openlocfilehash: 1836fbc1887082ca685c49bef2bc42bdb167578f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105850"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="8f252-102">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f252-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8f252-103">Die `DataGridView` gesteuert, die Sie mit einer Vielzahl von Optionen zum Konfigurieren, wie Benutzer die Zellen, Zeilen und Spalten auswählen können.</span><span class="sxs-lookup"><span data-stu-id="8f252-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="8f252-104">Beispielsweise können Sie aktivieren einfach- oder Mehrfachauswahl, Auswahl ganzer Zeilen oder Spalten, wenn der Benutzer die Zellen klicken Sie auf oder die Auswahl ganzer Zeilen oder Spalten nur, wenn Benutzer ihre Header klicken dadurch auch die Auswahl der Zelle.</span><span class="sxs-lookup"><span data-stu-id="8f252-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="8f252-105">Wenn Sie eine eigene Benutzeroberfläche für die Auswahl bereitstellen möchten, können normale Auswahl deaktivieren und die gesamte Auswahl programmgesteuert verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f252-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="8f252-106">Darüber hinaus können Sie Benutzer auf die ausgewählten Werte in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="8f252-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f252-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8f252-107">In This Section</span></span>  
 [<span data-ttu-id="8f252-108">Auswahlmodi im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f252-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8f252-109">Beschreibt die Optionen für Benutzer und die programmgesteuerte Auswahl im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8f252-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="8f252-110">Vorgehensweise: Festlegen des Auswahlmodus des DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f252-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8f252-111">Beschreibt, wie das Steuerelement für die Auswahl einzelner Zeilen konfigurieren, wenn ein Benutzer eine Zelle klickt.</span><span class="sxs-lookup"><span data-stu-id="8f252-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="8f252-112">Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f252-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="8f252-113">Beschreibt, wie mit den ausgewählten Sammlungen von Zellen, Zeilen und Spalten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f252-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="8f252-114">Vorgehensweise: Aktivieren von Benutzern für mehrere Zellen aus dem Windows Forms-DataGridView-Steuerelement in die Zwischenablage kopieren</span><span class="sxs-lookup"><span data-stu-id="8f252-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="8f252-115">Beschreibt die Unterstützung der Zwischenablage in das Steuerelement zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f252-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8f252-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="8f252-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="8f252-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="8f252-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="8f252-118">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f252-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="8f252-119">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8f252-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="8f252-120">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8f252-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="8f252-121">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8f252-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="8f252-122">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8f252-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f252-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f252-123">See also</span></span>

- [<span data-ttu-id="8f252-124">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8f252-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="8f252-125">Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f252-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
