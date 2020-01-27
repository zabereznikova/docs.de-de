---
title: Anzeigen von Daten im DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: d02362895d75df3735d19554bd44bb8ac443c6c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745867"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="782e5-102">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="782e5-103">Das `DataGridView`-Steuerelement wird zum Anzeigen von Daten aus einer Vielzahl externer Datenquellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="782e5-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="782e5-104">Alternativ können Sie dem Steuerelement Zeilen und Spalten hinzufügen und manuell mit Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="782e5-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="782e5-105">Wenn Sie das Steuerelement an eine Datenquelle binden, können Sie Spalten automatisch basierend auf dem Schema der Datenquelle generieren.</span><span class="sxs-lookup"><span data-stu-id="782e5-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="782e5-106">Wenn diese Spalten nicht wie gewünscht angezeigt werden, können Sie Sie ausblenden, entfernen oder neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="782e5-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="782e5-107">Sie können auch ungebundene Spalten hinzufügen, um ergänzende Daten anzuzeigen, die nicht aus der Datenquelle stammen.</span><span class="sxs-lookup"><span data-stu-id="782e5-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="782e5-108">Darüber hinaus können Sie Ihre Daten mithilfe von Standardformaten (z. b. dem Währungs Format) anzeigen, oder Sie können die Anzeige Formatierung anpassen, um Ihre Daten zu präsentieren (z. b. das Ändern der Hintergrundfarbe für negative Zahlen oder das Ersetzen von Zeichen folgen Werten). mit den entsprechenden Bildern).</span><span class="sxs-lookup"><span data-stu-id="782e5-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="782e5-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="782e5-109">In This Section</span></span>  
 [<span data-ttu-id="782e5-110">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-111">Beschreibt die Optionen zum Auffüllen des-Steuer Elements mit Daten.</span><span class="sxs-lookup"><span data-stu-id="782e5-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="782e5-112">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-113">Beschreibt die Optionen zum Formatieren von Zell Anzeige Werten.</span><span class="sxs-lookup"><span data-stu-id="782e5-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="782e5-114">Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-115">Beschreibt, wie das-Steuerelement manuell mit Daten aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="782e5-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="782e5-116">Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-117">Beschreibt, wie das-Steuerelement mit Daten aufgefüllt wird, indem es an eine `BindingSource` gebunden wird, die aus einer Datenbank abgerufene Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="782e5-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="782e5-118">Gewusst wie: Automatisches Generieren von Spalten in einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="782e5-119">Beschreibt, wie auf der Grundlage einer gebundenen Datenquelle automatisch Spalten generiert werden.</span><span class="sxs-lookup"><span data-stu-id="782e5-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="782e5-120">Gewusst wie: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="782e5-121">Beschreibt, wie Spalten, die automatisch aus einer gebundenen Datenquelle generiert werden, ausgeblendet oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="782e5-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="782e5-122">Gewusst wie: Ändern der Reihenfolge von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-123">Beschreibt, wie Spalten, die automatisch aus einer gebundenen Datenquelle generiert werden, neu angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="782e5-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="782e5-124">Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="782e5-125">Beschreibt, wie Daten aus einer gebundenen Datenquelle durch Anzeigen zusätzlicher, ungebundener Spalten ergänzt werden.</span><span class="sxs-lookup"><span data-stu-id="782e5-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="782e5-126">Vorgehensweise: Binden von Objekten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="782e5-127">Beschreibt, wie das Steuerelement an eine Auflistung beliebiger Objekte gebunden wird, sodass jedes Objekt in einer eigenen Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="782e5-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="782e5-128">Vorgehensweise: Aufrufen von Objekten, die an DataGridView-Zeilen in Windows Forms gebunden sind</span><span class="sxs-lookup"><span data-stu-id="782e5-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="782e5-129">Beschreibt, wie ein-Objekt abgerufen wird, das an eine bestimmte Zeile des-Steuer Elements gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="782e5-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="782e5-130">Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="782e5-131">Beschreibt, wie Daten aus zwei verknüpften Datenbanktabellen angezeigt werden, sodass die Werte, die in einem `DataGridView` Steuerelement angezeigt werden, von der aktuell ausgewählten Zeile in einem anderen Steuerelement abhängen.</span><span class="sxs-lookup"><span data-stu-id="782e5-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="782e5-132">Gewusst wie: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-133">Beschreibt, wie das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis behandelt wird, um die Darstellung von Zellen in Abhängigkeit von ihren Werten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="782e5-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="782e5-134">Referenz</span><span class="sxs-lookup"><span data-stu-id="782e5-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="782e5-135">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="782e5-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="782e5-136">Enthält die Referenz Dokumentation für die <xref:System.Windows.Forms.DataGridView.DataSource%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="782e5-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="782e5-137">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="782e5-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="782e5-138">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="782e5-138">Related Sections</span></span>  
 [<span data-ttu-id="782e5-139">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="782e5-140">Enthält Themen, in denen beschrieben wird, wie die Art und Weise geändert wird, in der Benutzer Daten im Steuerelement hinzufügen und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="782e5-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782e5-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="782e5-141">See also</span></span>

- [<span data-ttu-id="782e5-142">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="782e5-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="782e5-143">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="782e5-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
