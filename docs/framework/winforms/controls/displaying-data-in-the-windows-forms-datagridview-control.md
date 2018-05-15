---
title: Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: 06df9bbcb1e8b1b53d061dbd219a25378a311072
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cc1dd-102">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cc1dd-103">Die `DataGridView` Steuerelement wird verwendet, um Daten aus einer Vielzahl externer Datenquellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="cc1dd-104">Alternativ können Sie Zeilen und Spalten zum Steuerelement hinzufügen und es manuell mit Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="cc1dd-105">Wenn Sie das Steuerelement an eine Datenquelle binden, können Sie die Spalten automatisch basierend auf dem Schema der Datenquelle generieren.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="cc1dd-106">Wenn diese Spalten nicht angezeigt werden, ebenso wie gewünscht, können Sie ausblenden, entfernen oder anordnen.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="cc1dd-107">Sie können auch hinzufügen ungebundene Spalten, um zusätzliche Daten anzeigen, die nicht aus der Datenquelle stammt.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="cc1dd-108">Darüber hinaus können Sie Ihre Daten mithilfe von Standardformaten (z. B. Währungsformat) anzeigen, oder Sie können anpassen, die anzeigeformatierung, um Ihre Daten zu präsentieren, jedoch werden (z. B. Ändern der Hintergrundfarbe für negative Zahlen oder Zeichenfolgenwerte ersetzen müssen mit entsprechenden Bildern).</span><span class="sxs-lookup"><span data-stu-id="cc1dd-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc1dd-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cc1dd-109">In This Section</span></span>  
 [<span data-ttu-id="cc1dd-110">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-111">Beschreibt die Optionen für das Steuerelement mit Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="cc1dd-112">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-113">Beschreibt die Optionen für die Formatierung der Zelle Anzeigewerte.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="cc1dd-114">Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-115">Beschreibt, wie Sie manuell das Steuerelement mit Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="cc1dd-116">Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-117">Beschreibt, wie das Steuerelement mit Daten auffüllen, indem Sie ihn zum Binden einer `BindingSource` , die aus einer Datenbank abgerufene Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="cc1dd-118">Gewusst wie: Automatisches Generieren von Spalten in einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="cc1dd-119">Beschreibt, wie zum automatischen Generieren von Spalten, die auf eine gebundene Datenquelle basieren.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="cc1dd-120">Gewusst wie: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="cc1dd-121">Beschreibt das Ausblenden oder Löschen von Spalten aus einer gebundenen Datenquelle automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="cc1dd-122">Gewusst wie: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-123">Beschreibt, wie aus einer gebundenen Datenquelle automatisch generierte Spalten neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="cc1dd-124">Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="cc1dd-125">Beschreibt, wie Daten aus einer Datenquelle gebundenen Daten, die durch die Anzeige zusätzlicher ungebundener Spalten ergänzen.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="cc1dd-126">Vorgehensweise: Binden von Objekten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="cc1dd-127">Beschreibt, wie zum Binden des Steuerelements an eine Auflistung beliebiger Objekte, sodass jedes Objekt in einer eigenen Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="cc1dd-128">Vorgehensweise: Aufrufen von Objekten, die an DataGridView-Zeilen in Windows Forms gebunden sind</span><span class="sxs-lookup"><span data-stu-id="cc1dd-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="cc1dd-129">Beschreibt, wie ein Objekt, das an einer bestimmten Zeile des Steuerelements gebunden abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="cc1dd-130">Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="cc1dd-131">Beschreibt, wie Daten aus zwei verknüpften Tabellen angezeigt, damit die Werte in einer `DataGridView` Steuerelement richten sich nach der ausgewählten Zeile in einem anderen Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="cc1dd-132">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-133">Beschreibt das Behandeln der <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis, um die Darstellung von Zellen abhängig von deren Werten geändert.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cc1dd-134">Referenz</span><span class="sxs-lookup"><span data-stu-id="cc1dd-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="cc1dd-135">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="cc1dd-136">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="cc1dd-137">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cc1dd-138">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cc1dd-138">Related Sections</span></span>  
 [<span data-ttu-id="cc1dd-139">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-139">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="cc1dd-140">Enthält Themen, in denen beschrieben wird, wie die Art und Weise geändert wird, in der Benutzer Daten im Steuerelement hinzufügen und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc1dd-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc1dd-141">See Also</span></span>  
 [<span data-ttu-id="cc1dd-142">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cc1dd-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="cc1dd-143">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc1dd-143">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
