---
title: Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eebd0f36fbf1bf3bfc37b8fa836d318a9b8ac007
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5b7dc-102">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5b7dc-103">Viele grundlegende Verhaltensweisen von `DataGridView` Zellen, Zeilen und Spalten können durch das Festlegen einzelner Eigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="5b7dc-104">Die Themen in diesem Abschnitt werden einige der am häufigsten verwendeten Features beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b7dc-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b7dc-105">In This Section</span></span>  
 [<span data-ttu-id="5b7dc-106">Gewusst wie: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-107">Beschreibt, wie zu verhindern, dass bestimmte Spalten im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="5b7dc-108">Gewusst wie: Ausblenden von Spaltenheadern im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-109">Beschreibt, wie zu verhindern, dass die Spaltenüberschriften im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="5b7dc-110">Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-111">Beschreibt, wie Benutzer zum Neuanordnen von Spalten im Steuerelement zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="5b7dc-112">Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-113">Beschreibt, wie verschwinden eine oder mehrere angrenzende Spalten.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="5b7dc-114">Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-115">Beschreibt, wie Sie verhindern, dass Benutzer bestimmte Spalten im Steuerelement bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="5b7dc-116">Gewusst wie: Verhindern, das Zeilen im DataGridView-Steuerelement in Windows Forms hinzugefügt und gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="5b7dc-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="5b7dc-117">Beschreibt, wie die Zeile für neue Datensätze am unteren Rand das Steuerelement, um zu verhindern, dass Benutzer hinzufügen von Zeilen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="5b7dc-118">Beschreibt auch verhindern, dass Benutzer Zeilen löschen.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="5b7dc-119">Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="5b7dc-120">Beschreibt, wie auf die Zelle, die im Steuerelement gerade den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="5b7dc-121">Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-122">Beschreibt, wie eine Image-Spalte erstellen, die auf jede Zelle ein Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5b7dc-123">Verweis</span><span class="sxs-lookup"><span data-stu-id="5b7dc-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="5b7dc-124">Enthält die Referenzdokumentation für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5b7dc-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5b7dc-125">Related Sections</span></span>  
 [<span data-ttu-id="5b7dc-126">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5b7dc-127">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="5b7dc-128">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="5b7dc-129">Enthält Themen, in denen die Programmierung mit Zellen-, Zeilen- und Spaltenobjekten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="5b7dc-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7dc-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b7dc-130">See Also</span></span>  
 [<span data-ttu-id="5b7dc-131">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5b7dc-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="5b7dc-132">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b7dc-132">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
