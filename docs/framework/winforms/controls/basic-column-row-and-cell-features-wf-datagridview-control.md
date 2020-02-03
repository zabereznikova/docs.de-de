---
title: Grundlegende Spalten-, Zeilen-und Zellfunktionen im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 02f8ad7e11a61e9434748a8b3b2f853f98b013d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746216"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="edd2c-102">Grundlegende Spalten-, Zeilen- und Zellfeatures im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="edd2c-103">Viele grundlegende Verhalten `DataGridView` Zellen, Zeilen und Spalten können durch Festlegen einzelner Eigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="edd2c-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="edd2c-104">In den Themen in diesem Abschnitt werden einige der am häufigsten verwendeten Funktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edd2c-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="edd2c-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="edd2c-105">In This Section</span></span>  
 [<span data-ttu-id="edd2c-106">Gewusst wie: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-107">Beschreibt, wie verhindert wird, dass bestimmte Spalten im-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="edd2c-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="edd2c-108">Gewusst wie: Ausblenden von Spaltenheadern im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-109">Beschreibt, wie verhindert wird, dass die Spaltenheader im-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="edd2c-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="edd2c-110">Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-111">Beschreibt, wie Sie es Benutzern ermöglichen, Spalten im-Steuerelement neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="edd2c-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="edd2c-112">Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-113">Beschreibt, wie das Scrollen von einer oder mehreren angrenzenden Spalten verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="edd2c-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="edd2c-114">Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-115">Beschreibt, wie Benutzer daran gehindert werden, bestimmte Spalten im-Steuerelement zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="edd2c-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="edd2c-116">Gewusst wie: Verhindern, das Zeilen im DataGridView-Steuerelement in Windows Forms hinzugefügt und gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="edd2c-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="edd2c-117">Beschreibt, wie die Zeile für neue Datensätze am unteren Rand des-Steuer Elements entfernt wird, um Benutzer daran zu hindern, Zeilen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="edd2c-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="edd2c-118">Außerdem wird beschrieben, wie Sie verhindern können, dass Benutzer Zeilen löschen.</span><span class="sxs-lookup"><span data-stu-id="edd2c-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="edd2c-119">Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="edd2c-120">Beschreibt den Zugriff auf die Zelle, die derzeit im-Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="edd2c-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="edd2c-121">Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-122">Beschreibt, wie eine Bild Spalte erstellt wird, in der in jeder Zelle ein Symbol angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="edd2c-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="edd2c-123">Verweis</span><span class="sxs-lookup"><span data-stu-id="edd2c-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="edd2c-124">Enthält die Referenz Dokumentation für das-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="edd2c-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="edd2c-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="edd2c-125">Related Sections</span></span>  
 [<span data-ttu-id="edd2c-126">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="edd2c-127">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="edd2c-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="edd2c-128">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="edd2c-129">Enthält Themen, in denen die Programmierung mit Zellen-, Zeilen- und Spaltenobjekten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="edd2c-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd2c-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edd2c-130">See also</span></span>

- [<span data-ttu-id="edd2c-131">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="edd2c-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="edd2c-132">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="edd2c-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
