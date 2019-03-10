---
title: Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: d35fd2d17ce8d1b3c4759da1bab2370c450d2fbf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703267"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="68cb5-102">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="68cb5-103">Die `DataGridView` Steuerelement zum Anzeigen von Daten aus einer Vielzahl von Daten aus externen Quellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="68cb5-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="68cb5-104">Alternativ können Sie Zeilen und Spalten zum Steuerelement hinzufügen und manuell mit Daten aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="68cb5-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="68cb5-105">Wenn Sie das Steuerelement an eine Datenquelle binden, können Sie die Spalten automatisch basierend auf dem Schema der Datenquelle generieren.</span><span class="sxs-lookup"><span data-stu-id="68cb5-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="68cb5-106">Wenn diese Spalten nicht angezeigt werden, genau wie gewünscht, können Sie ausblenden, entfernen oder anordnen.</span><span class="sxs-lookup"><span data-stu-id="68cb5-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="68cb5-107">Sie können auch hinzufügen ungebundene Spalten, um zusätzliche Daten anzuzeigen, die nicht von der Datenquelle stammt.</span><span class="sxs-lookup"><span data-stu-id="68cb5-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="68cb5-108">Darüber hinaus können Sie Ihre Daten mithilfe von standard-Formate (z. B. Währungsformat) anzeigen, oder Sie können anpassen, die anzeigeformatierung, um Ihre Daten so darzustellen, müssen Sie allerdings auf (z. B. Ändern der Hintergrundfarbe für negative Zahlen oder Ersetzen von Zeichenfolgenwerten durch entsprechende Bilder).</span><span class="sxs-lookup"><span data-stu-id="68cb5-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68cb5-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="68cb5-109">In This Section</span></span>  
 [<span data-ttu-id="68cb5-110">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-111">Beschreibt die Optionen für das Steuerelement mit Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="68cb5-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="68cb5-112">Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-113">Beschreibt die Optionen für die Formatierung der Zellenwerte.</span><span class="sxs-lookup"><span data-stu-id="68cb5-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="68cb5-114">Exemplarische Vorgehensweise: Erstellen eine nicht gebundene Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="68cb5-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-115">Beschreibt, wie Sie manuell das Steuerelement mit Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="68cb5-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="68cb5-116">Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-117">Beschreibt, wie Sie das Steuerelement mit Daten zu füllen, indem Sie ihn zum Binden einer `BindingSource` mit den Informationen aus einer Datenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="68cb5-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="68cb5-118">Vorgehensweise: Automatisches Generieren von Spalten in einem datengebundenen Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="68cb5-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="68cb5-119">Automatisches Generieren von Spalten, die basierend auf einer gebundenen Datenquelle beschreibt.</span><span class="sxs-lookup"><span data-stu-id="68cb5-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="68cb5-120">Vorgehensweise: Entfernen von automatisch generierten Spalten aus einem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="68cb5-121">Beschreibt das Ausblenden oder Löschen von Spalten aus einer gebundenen Datenquelle automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="68cb5-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="68cb5-122">Vorgehensweise: Ändern Sie die Reihenfolge der Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-123">Beschreibt, wie aus einer gebundenen Datenquelle automatisch generierte Spalten neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="68cb5-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="68cb5-124">Vorgehensweise: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen Windows Forms-DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="68cb5-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="68cb5-125">Beschreibt, wie Daten aus einer gebundenen Datenquelle, die durch das Anzeigen zusätzlicher ungebundener Spalten zu ergänzen.</span><span class="sxs-lookup"><span data-stu-id="68cb5-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="68cb5-126">Vorgehensweise: Binden von Objekten an Windows Forms-DataGridView-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="68cb5-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="68cb5-127">Beschreibt, wie das Steuerelement an eine Auflistung von beliebigen Objekten zu binden, sodass jedes Objekt in einer eigenen Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="68cb5-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="68cb5-128">Vorgehensweise: Zugreifen auf Objekte an in Windows Forms DataGridView-Zeilen gebunden.</span><span class="sxs-lookup"><span data-stu-id="68cb5-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="68cb5-129">Beschreibt, wie zum Abrufen eines Objekts zu einer bestimmten Zeile des Steuerelements gebunden.</span><span class="sxs-lookup"><span data-stu-id="68cb5-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="68cb5-130">Exemplarische Vorgehensweise: Erstellen eine Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="68cb5-131">Beschreibt, wie Sie Daten aus zwei verknüpften Datenbanktabellen angezeigt, damit die Werte in einem `DataGridView` Steuerelement hängen von der aktuell ausgewählten Zeile in einem anderen Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="68cb5-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="68cb5-132">Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-133">Beschreibt, wie Sie behandelt die <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> Ereignis, um die Darstellung von Zellen je nach ihren Werten ändern.</span><span class="sxs-lookup"><span data-stu-id="68cb5-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="68cb5-134">Referenz</span><span class="sxs-lookup"><span data-stu-id="68cb5-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="68cb5-135">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="68cb5-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="68cb5-136">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.DataSource%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="68cb5-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="68cb5-137">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.BindingSource>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="68cb5-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68cb5-138">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="68cb5-138">Related Sections</span></span>  
 [<span data-ttu-id="68cb5-139">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-139">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="68cb5-140">Enthält Themen, in denen beschrieben wird, wie die Art und Weise geändert wird, in der Benutzer Daten im Steuerelement hinzufügen und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="68cb5-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68cb5-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68cb5-141">See also</span></span>
- [<span data-ttu-id="68cb5-142">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="68cb5-142">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="68cb5-143">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68cb5-143">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
