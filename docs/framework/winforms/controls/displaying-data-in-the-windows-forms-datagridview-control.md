---
title: Anzeigen von Daten im DataGridView-Steuerelement
description: Erfahren Sie, wie Sie das Windows Forms DataGridView-Steuerelement verwenden, um Daten aus verschiedenen externen Datenquellen anzuzeigen.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: a0f3e6627290521b8c10477c31459f1486e79162
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174574"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="da3bd-103">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-103">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="da3bd-104">Das- `DataGridView` Steuerelement wird zum Anzeigen von Daten aus einer Vielzahl externer Datenquellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="da3bd-104">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="da3bd-105">Alternativ können Sie dem Steuerelement Zeilen und Spalten hinzufügen und manuell mit Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="da3bd-105">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="da3bd-106">Wenn Sie das Steuerelement an eine Datenquelle binden, können Sie Spalten automatisch basierend auf dem Schema der Datenquelle generieren.</span><span class="sxs-lookup"><span data-stu-id="da3bd-106">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="da3bd-107">Wenn diese Spalten nicht wie gewünscht angezeigt werden, können Sie Sie ausblenden, entfernen oder neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="da3bd-107">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="da3bd-108">Sie können auch ungebundene Spalten hinzufügen, um ergänzende Daten anzuzeigen, die nicht aus der Datenquelle stammen.</span><span class="sxs-lookup"><span data-stu-id="da3bd-108">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="da3bd-109">Darüber hinaus können Sie Ihre Daten mit Standardformaten (z. b. dem Währungs Format) anzeigen, oder Sie können die Anzeige Formatierung anpassen, um Ihre Daten zu präsentieren (z. b. zum Ändern der Hintergrundfarbe für negative Zahlen oder zum Ersetzen von Zeichen folgen Werten durch entsprechende Bilder).</span><span class="sxs-lookup"><span data-stu-id="da3bd-109">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da3bd-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="da3bd-110">In This Section</span></span>  
 [<span data-ttu-id="da3bd-111">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-111">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-112">Beschreibt die Optionen zum Auffüllen des-Steuer Elements mit Daten.</span><span class="sxs-lookup"><span data-stu-id="da3bd-112">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="da3bd-113">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-113">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-114">Beschreibt die Optionen zum Formatieren von Zell Anzeige Werten.</span><span class="sxs-lookup"><span data-stu-id="da3bd-114">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="da3bd-115">Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-115">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-116">Beschreibt, wie das-Steuerelement manuell mit Daten aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="da3bd-116">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="da3bd-117">Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-117">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-118">Beschreibt, wie das-Steuerelement mit Daten aufgefüllt wird, indem es an einen gebunden wird `BindingSource` , der Informationen enthält, die aus einer Datenbank abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="da3bd-118">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="da3bd-119">Vorgehensweise: Automatisches Generieren von Spalten in einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-119">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="da3bd-120">Beschreibt, wie auf der Grundlage einer gebundenen Datenquelle automatisch Spalten generiert werden.</span><span class="sxs-lookup"><span data-stu-id="da3bd-120">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="da3bd-121">Vorgehensweise: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-121">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="da3bd-122">Beschreibt, wie Spalten, die automatisch aus einer gebundenen Datenquelle generiert werden, ausgeblendet oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="da3bd-122">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="da3bd-123">Vorgehensweise: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-123">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-124">Beschreibt, wie Spalten, die automatisch aus einer gebundenen Datenquelle generiert werden, neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="da3bd-124">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="da3bd-125">Vorgehensweise: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-125">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="da3bd-126">Beschreibt, wie Daten aus einer gebundenen Datenquelle durch Anzeigen zusätzlicher, ungebundener Spalten ergänzt werden.</span><span class="sxs-lookup"><span data-stu-id="da3bd-126">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="da3bd-127">Vorgehensweise: Binden von Objekten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-127">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="da3bd-128">Beschreibt, wie das Steuerelement an eine Auflistung beliebiger Objekte gebunden wird, sodass jedes Objekt in einer eigenen Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="da3bd-128">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="da3bd-129">Gewusst wie: Aufrufen von Objekten, die an DataGridView-Zeilen in Windows Forms gebunden sind</span><span class="sxs-lookup"><span data-stu-id="da3bd-129">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="da3bd-130">Beschreibt, wie ein-Objekt abgerufen wird, das an eine bestimmte Zeile des-Steuer Elements gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="da3bd-130">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="da3bd-131">Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-131">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="da3bd-132">Beschreibt, wie Daten aus zwei verknüpften Datenbanktabellen angezeigt werden, sodass die Werte, die in einem Steuerelement angezeigt werden, von `DataGridView` der aktuell ausgewählten Zeile in einem anderen Steuerelement abhängen.</span><span class="sxs-lookup"><span data-stu-id="da3bd-132">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="da3bd-133">Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-134">Beschreibt, wie das- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis behandelt wird, um die Darstellung von Zellen in Abhängigkeit von ihren Werten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="da3bd-134">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da3bd-135">Reference</span><span class="sxs-lookup"><span data-stu-id="da3bd-135">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="da3bd-136">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="da3bd-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="da3bd-137">Enthält die Referenz Dokumentation für die- <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="da3bd-137">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="da3bd-138">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="da3bd-138">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da3bd-139">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="da3bd-139">Related Sections</span></span>  
 [<span data-ttu-id="da3bd-140">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-140">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="da3bd-141">Enthält Themen, in denen beschrieben wird, wie die Art und Weise geändert wird, in der Benutzer Daten im Steuerelement hinzufügen und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="da3bd-141">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3bd-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da3bd-142">See also</span></span>

- [<span data-ttu-id="da3bd-143">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="da3bd-143">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="da3bd-144">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da3bd-144">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
