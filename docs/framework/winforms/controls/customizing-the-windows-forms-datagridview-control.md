---
title: Anpassen des DataGridView-Steuer Elements
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744020"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="584ef-102">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="584ef-103">Das `DataGridView`-Steuerelement bietet mehrere Eigenschaften, mit denen Sie die Darstellung und das grundlegende Verhalten (Aussehen und Verhalten) der Zellen, Zeilen und Spalten anpassen können.</span><span class="sxs-lookup"><span data-stu-id="584ef-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="584ef-104">Wenn Sie besondere Anforderungen haben, die über die Funktionen der <xref:System.Windows.Forms.DataGridViewCellStyle>-Klasse hinausgehen, können Sie jedoch auch die Besitzer Zeichnung für das Steuerelement implementieren oder die Funktionen erweitern, indem Sie benutzerdefinierte Zellen, Spalten und Zeilen erstellen.</span><span class="sxs-lookup"><span data-stu-id="584ef-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="584ef-105">Um Zellen und Zeilen selbst zu zeichnen, können Sie verschiedene `DataGridView` Zeichnungs Ereignisse verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="584ef-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="584ef-106">Wenn Sie vorhandene Funktionen ändern oder neue Funktionen bereitstellen möchten, können Sie eigene Typen erstellen, die von den vorhandenen `DataGridViewCell`-, `DataGridViewColumn`-und `DataGridViewRow`-Typen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="584ef-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="584ef-107">Sie können auch neue Bearbeitungsfunktionen bereitstellen, indem Sie abgeleitete Typen erstellen, die ein Steuerelement ihrer Wahl anzeigen, wenn sich eine Zelle im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="584ef-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="584ef-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="584ef-108">In This Section</span></span>  
 [<span data-ttu-id="584ef-109">Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="584ef-110">Beschreibt, wie das <xref:System.Windows.Forms.DataGridView.CellPainting>-Ereignis behandelt wird, um Zellen manuell zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="584ef-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="584ef-111">Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="584ef-112">Beschreibt, wie die <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> Ereignisse behandelt werden, um Zeilen mit einem benutzerdefinierten, Farbverlaufs Hintergrund und Inhalt zu zeichnen, der mehrere Spalten umfasst.</span><span class="sxs-lookup"><span data-stu-id="584ef-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="584ef-113">Gewusst wie: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens</span><span class="sxs-lookup"><span data-stu-id="584ef-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="584ef-114">Beschreibt, wie benutzerdefinierte Typen erstellt werden, die von `DataGridViewCell` und `DataGridViewColumn` abgeleitet werden, um Zellen hervorzuheben, wenn der Mauszeiger darauf liegt.</span><span class="sxs-lookup"><span data-stu-id="584ef-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="584ef-115">Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="584ef-116">Beschreibt, wie benutzerdefinierte Typen erstellt werden, die von <xref:System.Windows.Forms.DataGridViewButtonCell> und <xref:System.Windows.Forms.DataGridViewButtonColumn> abgeleitet werden, um deaktivierte Schaltflächen in einer Schaltflächen Spalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="584ef-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="584ef-117">Gewusst wie: Hosten von Steuerelementen in DataGridView-Zellen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="584ef-118">Beschreibt, wie die `IDataGridViewEditingControl`-Schnittstelle implementiert und benutzerdefinierte Typen erstellt werden, die von `DataGridViewCell` und `DataGridViewColumn` abgeleitet sind, um ein <xref:System.Windows.Forms.DateTimePicker>-Steuerelement anzuzeigen, wenn sich eine Zelle im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="584ef-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="584ef-119">Verweis</span><span class="sxs-lookup"><span data-stu-id="584ef-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="584ef-120">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="584ef-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="584ef-121">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridViewCell>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="584ef-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="584ef-122">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridViewRow>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="584ef-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="584ef-123">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridViewColumn>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="584ef-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="584ef-124">Enthält eine Referenz Dokumentation für die <xref:System.Windows.Forms.IDataGridViewEditingControl>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="584ef-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="584ef-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="584ef-125">Related Sections</span></span>  
 [<span data-ttu-id="584ef-126">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="584ef-127">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="584ef-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584ef-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="584ef-128">See also</span></span>

- [<span data-ttu-id="584ef-129">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="584ef-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="584ef-130">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="584ef-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
