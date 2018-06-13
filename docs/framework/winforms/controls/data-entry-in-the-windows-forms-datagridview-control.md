---
title: Dateneingabe im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: f5870b3cedd18d605426c7e27981303adc9beb5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526819"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1fcc1-102">Dateneingabe im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1fcc1-103">Die `DataGridView` Steuerelement stellt mehrere Funktionen bereit, mit denen Sie ändern, wie Benutzer hinzufügen oder Ändern von Daten im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="1fcc1-104">Beispielsweise können Sie Dateneingabe effizienter gestalten, indem Sie Standardwerte für neue Zeilen bereitstellen und warnen der Benutzer bei Auftreten eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fcc1-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1fcc1-105">In This Section</span></span>  
 [<span data-ttu-id="1fcc1-106">Gewusst wie: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1fcc1-107">Beschreibt, wie die Art ändern, beginnen die Benutzer mit Zellen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="1fcc1-108">Gewusst wie: Angeben von Standardwerten für neue Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="1fcc1-109">Beschreibt, wie die Zeile für neue Datensätze Dateneingabe Zeit zu sparen vorab aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="1fcc1-110">Verwenden der Zeile für neue Datensätze im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1fcc1-111">Beschreibt die Zeile für neue Datensätze im Detail, einschließlich Informationen zum Ausblenden, zum Anpassen der Darstellung und im Zusammenhang mit der <xref:System.Windows.Forms.DataGridView.Rows%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="1fcc1-112">Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1fcc1-113">Beschreibt das Überprüfen von Benutzereingaben, um die Dateneingabe Formatierungsfehler zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="1fcc1-114">Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten</span><span class="sxs-lookup"><span data-stu-id="1fcc1-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="1fcc1-115">Beschreibt die Dateneingabe Fehler zu behandeln, die aus der Datenquelle stammen, wenn der Benutzer versucht, einen neuen Wert zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1fcc1-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="1fcc1-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="1fcc1-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="1fcc1-118">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.EditMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="1fcc1-119">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="1fcc1-120">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.DataError> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="1fcc1-121">Enthält die Referenzdokumentation für die <xref:System.Windows.Forms.DataGridView.CellValidating> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1fcc1-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1fcc1-122">Related Sections</span></span>  
 [<span data-ttu-id="1fcc1-123">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="1fcc1-124">Enthält Themen, die beschreiben, wie das Steuerelement mit Daten entweder manuell oder von einer externen Datenquelle gefüllt.</span><span class="sxs-lookup"><span data-stu-id="1fcc1-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcc1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fcc1-125">See Also</span></span>  
 [<span data-ttu-id="1fcc1-126">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1fcc1-126">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="1fcc1-127">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1fcc1-127">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
