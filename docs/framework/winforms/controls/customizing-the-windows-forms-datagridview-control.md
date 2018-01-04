---
title: Anpassen des DataGridView-Steuerelements von Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 348651784ef2b4d99679038a1875fc6650688a6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="b1077-102">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b1077-103">Die `DataGridView` Steuerelement bietet mehrere Eigenschaften, die Sie zum Anpassen der Darstellung und das grundlegende Verhalten (Aussehen und Verhalten) Zellen, Zeilen und Spalten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b1077-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="b1077-104">Wenn Sie besondere Anforderungen verfügen, die hinausgehen, das die Funktionen des die <xref:System.Windows.Forms.DataGridViewCellStyle> -Klasse, allerdings können Sie auch Ownerdrawing für das Steuerelement implementieren oder erweitern die Funktionen durch das Erstellen von benutzerdefinierten Zellen, Spalten und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="b1077-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="b1077-105">Um Zeilen und Zellen selbst zeichnen, können Sie verschiedene behandeln `DataGridView` zeichnen-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="b1077-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="b1077-106">Um vorhandene Funktionen zu ändern oder neue Funktionen bereitzustellen, können Sie Ihre eigenen Typen abgeleitet werden, aus der vorhandenen erstellen `DataGridViewCell`, `DataGridViewColumn`, und `DataGridViewRow` Typen.</span><span class="sxs-lookup"><span data-stu-id="b1077-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="b1077-107">Sie können auch neue Bearbeitungsfunktionen bereitstellen, durch das Erstellen von abgeleiteter Typen, die Anzeigen eines Steuerelements Ihrer Wahl an, wenn eine Zelle im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="b1077-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b1077-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b1077-108">In This Section</span></span>  
 [<span data-ttu-id="b1077-109">Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="b1077-110">Beschreibt das Behandeln der <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis um zeichnen Zellen manuell.</span><span class="sxs-lookup"><span data-stu-id="b1077-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="b1077-111">Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="b1077-112">Beschreibt das Behandeln der <xref:System.Windows.Forms.DataGridView.RowPrePaint> und <xref:System.Windows.Forms.DataGridView.RowPostPaint> Ereignisse, um Zeilen mit einem benutzerdefinierten, Farbverlauf Hintergrund zeichnen, und Inhalte, die mehrere Spalten umfasst.</span><span class="sxs-lookup"><span data-stu-id="b1077-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="b1077-113">Gewusst wie: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens</span><span class="sxs-lookup"><span data-stu-id="b1077-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="b1077-114">Enthält Informationen zum Erstellen von benutzerdefinierter Typen abgeleitet `DataGridViewCell` und `DataGridViewColumn` um Zellen hervorgehoben, wenn der Mauszeiger darauf verbleibt.</span><span class="sxs-lookup"><span data-stu-id="b1077-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="b1077-115">Gewusst wie: Deaktivieren von Schaltflächen in einer Schaltflächenspalte im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="b1077-116">Enthält Informationen zum Erstellen von benutzerdefinierter Typen abgeleitet <xref:System.Windows.Forms.DataGridViewButtonCell> und <xref:System.Windows.Forms.DataGridViewButtonColumn> um deaktivierte Schaltflächen in einer Schaltflächenspalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1077-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="b1077-117">Gewusst wie: Hosten von Steuerelementen in DataGridView-Zellen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="b1077-118">Beschreibt das Implementieren der `IDataGridViewEditingControl` Schnittstelle, und erstellen Sie benutzerdefinierte Typen abgeleitet `DataGridViewCell` und `DataGridViewColumn` um anzeigen eine <xref:System.Windows.Forms.DateTimePicker> steuern, wenn eine Zelle im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="b1077-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b1077-119">Verweis</span><span class="sxs-lookup"><span data-stu-id="b1077-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="b1077-120">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b1077-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="b1077-121">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewCell> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b1077-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="b1077-122">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewRow> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b1077-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="b1077-123">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridViewColumn> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b1077-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="b1077-124">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.IDataGridViewEditingControl> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b1077-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b1077-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b1077-125">Related Sections</span></span>  
 [<span data-ttu-id="b1077-126">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b1077-127">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b1077-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1077-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1077-128">See Also</span></span>  
 [<span data-ttu-id="b1077-129">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b1077-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="b1077-130">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1077-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
