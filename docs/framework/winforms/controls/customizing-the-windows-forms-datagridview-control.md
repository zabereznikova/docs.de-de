---
title: Anpassen des DataGridView-Steuerelements von Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: ab8d1f07c608aca4f14f5e73860f8c3e263a4610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011414"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="d5deb-102">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5deb-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d5deb-103">Die `DataGridView` -Steuerelement umfasst mehrere Eigenschaften, die Sie verwenden können, um die Darstellung und das grundlegende Verhalten (Aussehen und Verhalten), der die Zellen, Zeilen und Spalten anzupassen.</span><span class="sxs-lookup"><span data-stu-id="d5deb-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="d5deb-104">Wenn Sie besondere Anforderungen verfügen, die über die Funktionen von hinausgehen der <xref:System.Windows.Forms.DataGridViewCellStyle> Klasse, allerdings können Sie auch Ownerdrawing für das Steuerelement implementieren oder Erweitern Sie die Funktionen, durch das Erstellen von benutzerdefinierten Zellen, Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="d5deb-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="d5deb-105">Um Zeilen und Zellen selbst zeichnen, können Sie verschiedene behandeln `DataGridView` zeichnen-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d5deb-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="d5deb-106">Um vorhandene Funktionalität ändern oder neue Funktionen bereitzustellen, können Sie Ihre eigenen Typen abgeleitet, die vorhandene erstellen `DataGridViewCell`, `DataGridViewColumn`, und `DataGridViewRow` Typen.</span><span class="sxs-lookup"><span data-stu-id="d5deb-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="d5deb-107">Sie können auch neue Funktionen bereitstellen, durch das Erstellen von abgeleiteten Typen, die Anzeigen eines Steuerelements Ihrer Wahl an, wenn eine Zelle im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="d5deb-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5deb-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d5deb-108">In This Section</span></span>  
 [<span data-ttu-id="d5deb-109">Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5deb-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="d5deb-110">Beschreibt, wie Sie behandelt die <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis, um zeichnen Zellen manuell.</span><span class="sxs-lookup"><span data-stu-id="d5deb-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="d5deb-111">Vorgehensweise: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5deb-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="d5deb-112">Beschreibt, wie Sie behandelt die <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> Ereignisse, um Zeilen mit einem benutzerdefinierten, Farbverlauf als Hintergrund zeichnen und den Inhalt, der mehrere Spalten umfasst.</span><span class="sxs-lookup"><span data-stu-id="d5deb-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="d5deb-113">Vorgehensweise: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern Aussehens und Verhaltens</span><span class="sxs-lookup"><span data-stu-id="d5deb-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="d5deb-114">Beschreibt das Erstellen von benutzerdefinierter Typen, die von abgeleiteten `DataGridViewCell` und `DataGridViewColumn` um Zellen zu markieren, wenn der Mauszeiger darauf zeigt.</span><span class="sxs-lookup"><span data-stu-id="d5deb-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="d5deb-115">Vorgehensweise: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5deb-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="d5deb-116">Beschreibt das Erstellen von benutzerdefinierter Typen, die von abgeleiteten <xref:System.Windows.Forms.DataGridViewButtonCell> und <xref:System.Windows.Forms.DataGridViewButtonColumn> um deaktivierte Schaltflächen in einer Schaltflächenspalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d5deb-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="d5deb-117">Vorgehensweise: Hoststeuerelementen in Windows Forms-DataGridView-Zellen</span><span class="sxs-lookup"><span data-stu-id="d5deb-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="d5deb-118">Beschreibt das Implementieren der `IDataGridViewEditingControl` Schnittstelle, und erstellen Sie benutzerdefinierte Typen, die von abgeleiteten `DataGridViewCell` und `DataGridViewColumn` zum Anzeigen einer <xref:System.Windows.Forms.DateTimePicker> steuern, wenn eine Zelle im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="d5deb-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d5deb-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="d5deb-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d5deb-120">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d5deb-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="d5deb-121">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewCell> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d5deb-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="d5deb-122">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewRow> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d5deb-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="d5deb-123">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumn> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d5deb-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="d5deb-124">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.IDataGridViewEditingControl> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d5deb-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5deb-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d5deb-125">Related Sections</span></span>  
 [<span data-ttu-id="d5deb-126">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5deb-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d5deb-127">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d5deb-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5deb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5deb-128">See also</span></span>

- [<span data-ttu-id="d5deb-129">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d5deb-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="d5deb-130">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d5deb-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
