---
title: Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: 5e967c1bbe54095cc11e48b014600158da7fe6a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011683"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fa67f-102">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fa67f-103">Die `DataGridView` Steuerelement erleichtert Ihnen die grundlegende Darstellung von Zellen sowie das Anzeigeformat der Zellenwerte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="fa67f-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="fa67f-104">Sie können die Darstellung definieren und die Formatierung für einzelne Zellen, für die Zellen in bestimmte Spalten und Zeilen oder für alle Zellen im Steuerelement durch Festlegen der Eigenschaften von der `DataGridViewCellStyle` Objekte zugegriffen, die über verschiedene `DataGridView` Steuerelementeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="fa67f-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="fa67f-105">Darüber hinaus können Sie ändern diese Formate dynamisch basierend auf Faktoren wie der Wert der Zelle durch Behandeln der `CellFormatting` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fa67f-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa67f-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fa67f-106">In This Section</span></span>  
 [<span data-ttu-id="fa67f-107">Vorgehensweise: Ändern Sie die Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="fa67f-108">Beschreibt `DataGridView` Eigenschaften, die die Darstellung von den Rahmen des Steuerelements und die Zeilen der Grenze zwischen den Zellen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="fa67f-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="fa67f-109">Zellstile im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fa67f-110">Beschreibt die `DataGridViewCellStyle` -Klasse und die Interaktion von Eigenschaften zum definieren, wie die Zellen im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa67f-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="fa67f-111">Vorgehensweise: Festlegen von Standardzellenformaten für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fa67f-112">Beschreibt, wie `DataGridViewCellStyle` Eigenschaften, die die standarddarstellung der Zellen in Zeilen und Spalten und das gesamte Steuerelement definieren.</span><span class="sxs-lookup"><span data-stu-id="fa67f-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="fa67f-113">Vorgehensweise: Formatieren von Daten in der Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fa67f-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fa67f-114">Beschreibt, wie Sie die Anzeige Zellenwerten durch formatieren `DataGridViewCellStyle` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="fa67f-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="fa67f-115">Vorgehensweise: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fa67f-116">Beschreibt, wie die `DefaultCellStyle` grundlegende festzulegende Eigenschaft Anzeigeeigenschaften für alle Zellen im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fa67f-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="fa67f-117">Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fa67f-118">Beschreibt, wie einen Ledger-ähnlichen Effekt zu erstellen, in das Steuerelement mit abwechselnden Zeilen, die unterschiedlich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa67f-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="fa67f-119">Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="fa67f-120">Beschreibt, wie die `RowTemplate` -Eigenschaft zum Festlegen von Zeileneigenschaften, die für alle Zeilen im Steuerelement verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa67f-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fa67f-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="fa67f-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="fa67f-122">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fa67f-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="fa67f-123">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse.</span><span class="sxs-lookup"><span data-stu-id="fa67f-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="fa67f-124">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="fa67f-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="fa67f-125">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fa67f-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fa67f-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="fa67f-126">Related Sections</span></span>  
 [<span data-ttu-id="fa67f-127">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fa67f-128">Enthält Themen, in denen das benutzerdefinierte Zeichnen von <xref:System.Windows.Forms.DataGridView>-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="fa67f-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="fa67f-129">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa67f-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="fa67f-130">Enthält Themen, in denen häufig Eigenschaften von Zellen, Zeilen und Spalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa67f-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa67f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa67f-131">See also</span></span>

- [<span data-ttu-id="fa67f-132">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fa67f-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
