---
title: DataGrid-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- datasets [Windows Forms], user interface
- DataGrid control [Windows Forms]
- datasets [Windows Forms], displaying in DataGrid control
- displaying data [Windows Forms], on forms
- data [Windows Forms], displaying on Windows Forms
ms.assetid: 1d9d5683-43d2-42dd-b6c3-e43f4cf0de99
ms.openlocfilehash: 5f8fcd21802c52d61d354c5ba85d665bd17237db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078914"
---
# <a name="datagrid-control-windows-forms"></a><span data-ttu-id="83a33-102">DataGrid-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="83a33-102">DataGrid Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="83a33-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das `DataGrid`-Steuerelement ersetzt und funktionell erweitert, wird das `DataGrid`-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="83a33-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the `DataGrid` control; however, the `DataGrid` control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="83a33-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="83a33-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="83a33-105">Das Windows Forms-Steuerelement `DataGrid` stellt eine Benutzeroberfläche für [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]-Datasets bereit, die Daten in tabellarischer Form anzeigt sowie Aktualisierungen der Datenquelle ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="83a33-105">The Windows Forms `DataGrid` control provides a user interface to [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] datasets, displaying tabular data and enabling updates to the data source.</span></span>  
  
 <span data-ttu-id="83a33-106">Wenn für das `DataGrid`-Steuerelement eine zulässige Datenquelle festgelegt wurde, wird das Steuerelement automatisch gefüllt, wobei Spalten und Zeilen entsprechend der Form der Daten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-106">When the `DataGrid` control is set to a valid data source, the control is automatically populated, creating columns and rows based on the shape of the data.</span></span> <span data-ttu-id="83a33-107">Das `DataGrid`-Steuerelement kann dazu verwendet werden, entweder eine einzelne Tabelle oder die hierarchischen Beziehungen zwischen mehreren Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="83a33-107">The `DataGrid` control can be used to display either a single table or the hierarchical relationships between a set of tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83a33-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="83a33-108">In This Section</span></span>  
 [<span data-ttu-id="83a33-109">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="83a33-109">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)  
 <span data-ttu-id="83a33-110">Beschreibt die grundlegenden Features des `DataGrid`-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="83a33-110">Describes the basic features of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-111">Vorgehensweise: Hinzufügen von Tabellen und Spalten zu der DataGrid-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="83a33-111">How to: Add Tables and Columns to the Windows Forms DataGrid Control Using the Designer</span></span>](add-tables-and-columns-to-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="83a33-112">Beschreibt das Hinzufügen von Tabellen und Spalten zum `DataGrid`-Steuerelement mithilfe des Designers.</span><span class="sxs-lookup"><span data-stu-id="83a33-112">Describes how to add tables and columns to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="83a33-113">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-113">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="83a33-114">Beschreibt das programmgesteuerte Hinzufügen von Tabellen und Spalten zum `DataGrid`-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="83a33-114">Describes how to add tables and columns to the `DataGrid` control programmatically.</span></span>  
  
 [<span data-ttu-id="83a33-115">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="83a33-115">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)  
 <span data-ttu-id="83a33-116">Beschreibt das Binden eines [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]-Datasets an das `DataGrid`-Steuerelement mithilfe des Designers.</span><span class="sxs-lookup"><span data-stu-id="83a33-116">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="83a33-117">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="83a33-117">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 <span data-ttu-id="83a33-118">Beschreibt das Binden eines [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]-Datasets an das `DataGrid`-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="83a33-118">Describes how to bind an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] dataset to the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-119">Vorgehensweise: Ändern der angezeigten Daten zur Laufzeit in das DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-119">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)  
 <span data-ttu-id="83a33-120">Beschreibt, wie Daten im `DataGrid`-Steuerelement programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-120">Describes how to change data programmatically in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-121">Vorgehensweise: Erstellen von Master-/ Detaillisten mit dem DataGrid-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="83a33-121">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>](create-master-details-lists-with-wf-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="83a33-122">Beschreibt, wie zwei Tabellen, die als übergeordnete und untergeordnete Tabelle miteinander verknüpft sind, mithilfe des Designers in zwei verschiedenen `DataGrid`-Steuerelementen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-122">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls using the designer.</span></span>  
  
 <span data-ttu-id="83a33-123">Vorgehensweise: Erstellen von Master-/ Detaillisten mit dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-123">How to: Create Master-Details Lists with the Windows Forms DataGrid Control</span></span>  
 <span data-ttu-id="83a33-124">Beschreibt, wie zwei Tabellen, die als übergeordnete und untergeordnete Tabelle miteinander verknüpft sind, in zwei verschiedenen `DataGrid`-Steuerelementen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-124">Describes how to display two tables, tied together with a parent/child relationship, in two separate `DataGrid` controls.</span></span>  
  
 [<span data-ttu-id="83a33-125">Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-125">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="83a33-126">Beschreibt das Entfernen von Spalten im `DataGrid`-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="83a33-126">Describes how to remove columns in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-127">Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="83a33-127">How to: Format the Windows Forms DataGrid Control Using the Designer</span></span>](how-to-format-the-windows-forms-datagrid-control-using-the-designer.md)  
 <span data-ttu-id="83a33-128">Beschreibt, wie die Darstellungseigenschaften des `DataGrid`-Steuerelements mithilfe des Designers geändert werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-128">Describes how to change the appearance-related properties of the `DataGrid` control using the designer.</span></span>  
  
 [<span data-ttu-id="83a33-129">Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-129">How to: Format the Windows Forms DataGrid Control</span></span>](how-to-format-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="83a33-130">Beschreibt, wie die Darstellungseigenschaften des `DataGrid`-Steuerelements geändert werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-130">Describes how to change the appearance-related properties of the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-131">Tastenkombinationen für das DataGrid-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-131">Keyboard Shortcuts for the Windows Forms DataGrid Control</span></span>](keyboard-shortcuts-for-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="83a33-132">Enthält eine Liste der Tastenkombinationen für die Navigation durch das `DataGrid`-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="83a33-132">Lists shortcuts for navigating through the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-133">Vorgehensweise: Reagieren Sie auf das Klicken in das DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-133">How to: Respond to Clicks in the Windows Forms DataGrid Control</span></span>](how-to-respond-to-clicks-in-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="83a33-134">Beschreibt, wie festgestellt wird, auf welche Zelle im `DataGrid`-Steuerelement ein Benutzer geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="83a33-134">Describes how to determine which cell a user has clicked in the `DataGrid` control.</span></span>  
  
 [<span data-ttu-id="83a33-135">Vorgehensweise: Überprüfen von Eingaben mit dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-135">How to: Validate Input with the Windows Forms DataGrid Control</span></span>](how-to-validate-input-with-the-windows-forms-datagrid-control.md)  
 <span data-ttu-id="83a33-136">Beschreibt, wie Eingaben in das an das `DataGrid`-Steuerelement gebundene Dataset validiert werden.</span><span class="sxs-lookup"><span data-stu-id="83a33-136">Describes how to validate input in the dataset bound to the `DataGrid` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="83a33-137">Referenz</span><span class="sxs-lookup"><span data-stu-id="83a33-137">Reference</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <span data-ttu-id="83a33-138">Bietet eine Übersicht über die <xref:System.Windows.Forms.DataGrid> Klasse.</span><span class="sxs-lookup"><span data-stu-id="83a33-138">Provides an overview of the <xref:System.Windows.Forms.DataGrid> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGrid.DataSource%2A>  
 <span data-ttu-id="83a33-139">Enthält Details zur Verwendung dieser Eigenschaft zum Binden der <xref:System.Windows.Forms.DataGrid> -Steuerelement an Daten.</span><span class="sxs-lookup"><span data-stu-id="83a33-139">Provides details about using this property to bind the <xref:System.Windows.Forms.DataGrid> control to data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="83a33-140">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="83a33-140">Related Sections</span></span>  
 [<span data-ttu-id="83a33-141">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="83a33-141">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="83a33-142">Enthält Links zu Themen über die Datenbindung in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="83a33-142">Provides links to topics on data binding in Windows Forms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a33-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83a33-143">See also</span></span>

- [<span data-ttu-id="83a33-144">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="83a33-144">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="83a33-145">Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83a33-145">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)
