---
title: Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1c6ae9c4159f8f9eafd73608e4fc3f4a646c1eaa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="35829-102">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="35829-103">Die `DataGridView` Steuerelement ganz einfach die grundlegende Darstellung von Zellen sowie das Anzeigeformat von Zellwerten definieren.</span><span class="sxs-lookup"><span data-stu-id="35829-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="35829-104">Sie können die Darstellung definieren und Formatierung für einzelne Zellen, für Zellen in bestimmte Spalten und Zeilen oder für alle Zellen im Steuerelement durch Festlegen der Eigenschaften von der `DataGridViewCellStyle` erfolgt über verschiedene Objekte `DataGridView` Eigenschaften zu steuern.</span><span class="sxs-lookup"><span data-stu-id="35829-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="35829-105">Darüber hinaus können Sie diese Faktoren wie z. B. der Wert der Zelle durch Behandeln dynamisch anhand Stile modifizieren die `CellFormatting` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="35829-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35829-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="35829-106">In This Section</span></span>  
 [<span data-ttu-id="35829-107">Gewusst wie: Ändern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="35829-108">Beschreibt, wie festzulegende `DataGridView` Eigenschaften, die die Darstellung des Steuerelementrahmens und die Grenzlinien zwischen den Zellen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="35829-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="35829-109">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="35829-110">Beschreibt die `DataGridViewCellStyle` Klasse und die Eigenschaften des betreffenden Typs wie interagieren, um zu definieren, wie die Zellen im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="35829-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="35829-111">Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="35829-112">Beschreibt, wie `DataGridViewCellStyle` Eigenschaften, um die standarddarstellung der Zellen in bestimmten Zeilen und Spalten und das gesamte Steuerelement zu definieren.</span><span class="sxs-lookup"><span data-stu-id="35829-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="35829-113">Vorgehensweise: Formatieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="35829-114">Beschreibt die zum Formatieren der Anzeige Zellenwerten durch `DataGridViewCellStyle` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="35829-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="35829-115">Gewusst wie: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="35829-116">Beschreibt, wie die `DefaultCellStyle` grundlegende festzulegende Eigenschaft Anzeigeeigenschaften für alle Zellen im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="35829-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="35829-117">Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="35829-118">Beschreibt das Erstellen von eines Ledger-ähnlichen Effekts in das Steuerelement mit abwechselnden Zeilen, die unterschiedlich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="35829-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="35829-119">Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="35829-120">Beschreibt, wie die `RowTemplate` Eigenschaft Zeileneigenschaften festlegen, die für alle Zeilen im Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="35829-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="35829-121">Verweis</span><span class="sxs-lookup"><span data-stu-id="35829-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="35829-122">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="35829-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="35829-123">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse.</span><span class="sxs-lookup"><span data-stu-id="35829-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="35829-124">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="35829-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="35829-125">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="35829-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="35829-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="35829-126">Related Sections</span></span>  
 [<span data-ttu-id="35829-127">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-127">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="35829-128">Enthält Themen, in denen das benutzerdefinierte Zeichnen von <xref:System.Windows.Forms.DataGridView>-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="35829-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="35829-129">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35829-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="35829-130">Enthält Themen, in denen häufig Zellen-, Zeilen- und Spalte Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="35829-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35829-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35829-131">See Also</span></span>  
 [<span data-ttu-id="35829-132">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="35829-132">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
