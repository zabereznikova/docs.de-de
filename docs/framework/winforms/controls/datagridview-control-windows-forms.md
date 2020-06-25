---
title: DataGridView-Steuerelement
description: Erfahren Sie, wie Sie das-Steuerelement verwenden, `DataGridView` um schreibgeschützte Sichten einer kleinen Datenmenge anzuzeigen, oder Skalieren Sie es, um bearbeitbare Sichten von sehr großen Datenmengen anzuzeigen.
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: f9a45e8be7975697ca5c0d019c6bc4119f562aea
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325898"
---
# <a name="datagridview-control-windows-forms"></a><span data-ttu-id="6737c-103">DataGridView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6737c-103">DataGridView Control (Windows Forms)</span></span>
<span data-ttu-id="6737c-104">Das `DataGridView`-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form.</span><span class="sxs-lookup"><span data-stu-id="6737c-104">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="6737c-105">Sie können das `DataGridView`-Steuerelement verwenden, um schreibgeschützte Ansichten mit kleinen Datenmengen anzuzeigen, oder Sie können es skalieren, um bearbeitbare Ansichten von sehr umfangreichen Datasets anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6737c-105">You can use the `DataGridView` control to show read-only views of a small amount of data, or you can scale it to show editable views of very large sets of data.</span></span>  
  
 <span data-ttu-id="6737c-106">Es gibt mehrere Möglichkeiten zum Erweitern des `DataGridView`-Steuerelements, um Ihre Anwendungen mit benutzerdefinierten Verhaltensweisen auszustatten.</span><span class="sxs-lookup"><span data-stu-id="6737c-106">You can extend the `DataGridView` control in a number of ways to build custom behaviors into your applications.</span></span> <span data-ttu-id="6737c-107">So können Sie beispielsweise programmgesteuert Ihre eigenen Sortieralgorithmen angeben und eigene Zelltypen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6737c-107">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="6737c-108">Die Darstellung des `DataGridView`-Steuerelements kann mithilfe mehrerer Eigenschaften ganz einfach angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="6737c-108">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="6737c-109">Als Datenquelle können viele Arten von Datenspeichern verwendet werden, oder das `DataGridView`-Steuerelement kann ohne eine hieran gebundene Datenquelle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6737c-109">Many types of data stores can be used as a data source, or the `DataGridView` control can operate with no data source bound to it.</span></span>  
  
 <span data-ttu-id="6737c-110">In den Themen in diesem Abschnitt werden die Konzepte und Techniken beschrieben, die Sie verwenden können, um `DataGridView`-Features in Ihre Anwendungen einzubinden.</span><span class="sxs-lookup"><span data-stu-id="6737c-110">The topics in this section describe the concepts and techniques that you can use to build `DataGridView` features into your applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6737c-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6737c-111">In This Section</span></span>  
 [<span data-ttu-id="6737c-112">Übersicht über das DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6737c-112">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)  
 <span data-ttu-id="6737c-113">Enthält Themen, in denen die Architektur und die Kernkonzepte des `DataGridView`-Steuerelements in Windows Forms beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6737c-113">Provides topics that describe the architecture and core concepts of the Windows Forms `DataGridView` control.</span></span>  
  
 [<span data-ttu-id="6737c-114">Standardfunktionalität des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-114">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-115">Beschreibt die Standarddarstellung und das Standardverhalten des `DataGridView`-Steuerelements von Windows Forms, wenn es an eine Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="6737c-115">Describes the default appearance and behavior of the Windows Forms `DataGridView` control when it is bound to a data source.</span></span>  
  
 [<span data-ttu-id="6737c-116">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-116">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-117">Beschreibt die Spaltentypen im `DataGridView`-Steuerelement in Windows Forms, die verwendet werden, um Daten anzuzeigen und es dem Benutzer ermöglichen, Daten zu ändern oder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6737c-117">Describes the column types in the Windows Forms `DataGridView` control used to display data and allow users to modify or add data.</span></span>  
  
 [<span data-ttu-id="6737c-118">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-118">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="6737c-119">Enthält Themen, in denen häufig verwendete Zellen-, Zeilen- und Spalteneigenschaften beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6737c-119">Provides topics that describe commonly-used cell, row, and column properties.</span></span>  
  
 [<span data-ttu-id="6737c-120">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-121">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6737c-121">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="6737c-122">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-122">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-123">Enthält Themen, in denen beschrieben wird, wie das Steuerelement entweder manuell oder mit Daten aus einer externen Datenquelle gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="6737c-123">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="6737c-124">Größenanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-124">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-125">Enthält Themen, in denen erläutert wird, wie die Größe von Zeilen und Spalten automatisch angepasst werden kann, um dem Zellinhalt oder der verfügbaren Breite des Steuerelements zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6737c-125">Provides topics that describe how the size of rows and columns can be adjusted automatically to fit cell content or to fit the available width of the control.</span></span>  
  
 [<span data-ttu-id="6737c-126">Sortieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-126">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-127">Unter diesen Themen werden die Sortierfunktionen des Steuerelements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6737c-127">Provides topics that describe the sorting features in the control.</span></span>  
  
 [<span data-ttu-id="6737c-128">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-128">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-129">Enthält Themen, in denen beschrieben wird, wie die Art und Weise geändert wird, in der Benutzer Daten im Steuerelement hinzufügen und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="6737c-129">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
 [<span data-ttu-id="6737c-130">Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-130">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-131">Enthält Themen, in denen die Auswahlfunktionen für Zellen, Zeilen und Spalten im Steuerelement beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6737c-131">Provides topics that describe the cell, row, and column selection features in the control.</span></span>  
  
 [<span data-ttu-id="6737c-132">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-132">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="6737c-133">Enthält Themen, in denen die Programmierung mit Zellen-, Zeilen- und Spaltenobjekten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6737c-133">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
 [<span data-ttu-id="6737c-134">Anpassen des DataGridView-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-134">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-135">Enthält Themen, in denen das benutzerdefinierte Zeichnen von `DataGridView`-Zellen und Zeilen und das Erstellen von abgeleiteten Zell-, Spalten- und Zeilentypen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="6737c-135">Provides topics that describe custom painting `DataGridView` cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="6737c-136">Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-136">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-137">Enthält Themen, in den erläutert wird, wie das Steuerelement effizient eingesetzt wird, um bei der Arbeit mit großen Datenmengen Leistungsprobleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6737c-137">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="6737c-138">Standardbehandlung von Tastatur und Maus im DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-138">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="6737c-139">Beschreibt, wie Benutzer per Tastatur und Maus mit dem `DataGridView`-Steuerelement interagieren können.</span><span class="sxs-lookup"><span data-stu-id="6737c-139">Describes how users can interact with the `DataGridView` control through a keyboard and a mouse.</span></span>  
  
 [<span data-ttu-id="6737c-140">Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-140">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 <span data-ttu-id="6737c-141">Beschreibt, in welcher Weise das `DataGridView`-Steuerelement verbessert wurde, das das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt.</span><span class="sxs-lookup"><span data-stu-id="6737c-141">Describes how the `DataGridView` control improves upon and replaces the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
 <span data-ttu-id="6737c-142">Siehe auch [Verwenden des Designers mit dem Windows Forms DataGridView-Steuer](using-the-designer-with-the-windows-forms-datagridview-control.md)Element.</span><span class="sxs-lookup"><span data-stu-id="6737c-142">Also see [Using the Designer with the Windows Forms DataGridView Control](using-the-designer-with-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6737c-143">Verweis</span><span class="sxs-lookup"><span data-stu-id="6737c-143">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="6737c-144">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6737c-144">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="6737c-145">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="6737c-145">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="6737c-146">Das <xref:System.Windows.Forms.DataGridView>-Steuerelement und die <xref:System.Windows.Forms.BindingSource>-Komponente sind auf eine enge Zusammenarbeit ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="6737c-146">The <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component are designed to work closely together.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6737c-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6737c-147">See also</span></span>

- [<span data-ttu-id="6737c-148">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6737c-148">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
