---
title: 'Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: fe54c650e1d19f36d681053c7da47e12527c5827
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320885"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="ad706-102">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="ad706-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="ad706-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ad706-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ad706-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ad706-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ad706-105">Die Windows-Formulare <xref:System.Windows.Forms.DataGrid> Steuerelement wurde speziell zur Anzeige von Informationen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ad706-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="ad706-106">Binden des Steuerelements zur Entwurfszeit durch Festlegen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften oder zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ad706-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="ad706-107">Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.</span><span class="sxs-lookup"><span data-stu-id="ad706-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="ad706-108">Wenn die Datenquelle zur Entwurfszeit verfügbar ist – z. B., wenn das Formular eine Instanz eines Datasets oder eine Data source View enthält – Sie können im Raster mit der Datenquelle zur Entwurfszeit zu binden.</span><span class="sxs-lookup"><span data-stu-id="ad706-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="ad706-109">Sie können dann anzeigen, wie die Daten im Raster aussehen werden.</span><span class="sxs-lookup"><span data-stu-id="ad706-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="ad706-110">Sie können im Raster auch programmgesteuert zur Laufzeit binden.</span><span class="sxs-lookup"><span data-stu-id="ad706-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="ad706-111">Dies ist nützlich, wenn Sie eine Datenquelle basierend auf Informationen, die Sie zur Laufzeit erhalten festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad706-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="ad706-112">Beispielsweise kann die Anwendung den Benutzer aus, geben Sie den Namen einer Tabelle anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ad706-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="ad706-113">Es ist auch in Situationen, in dem die Datenquelle zur Entwurfszeit noch nicht vorhanden ist, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad706-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="ad706-114">Dazu gehören Datenquellen wie z. B. Arrays, Auflistungen, nicht typisierte Datasets und Datenleser.</span><span class="sxs-lookup"><span data-stu-id="ad706-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="ad706-115">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ad706-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="ad706-116">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ad706-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="ad706-117">In Visual Studio 2005 die <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox** standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="ad706-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="ad706-118">Informationen zum Hinzufügen, finden Sie unter [Vorgehensweise: Hinzufügen von Elementen zur Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ad706-118">For information about adding it, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="ad706-119">Darüber hinaus in Visual Studio 2005 können Sie mithilfe der **Datenquellen** Fenster für die Datenbindung zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="ad706-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="ad706-120">Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ad706-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad706-121">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="ad706-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ad706-122">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ad706-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ad706-123">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ad706-123">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="ad706-124">An Daten des DataGrid-Steuerelements an eine einzelne Tabelle im Designer gebunden werden soll</span><span class="sxs-lookup"><span data-stu-id="ad706-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1. <span data-ttu-id="ad706-125">Legen Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft, um das Objekt, enthält die Datenelemente, die Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad706-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2. <span data-ttu-id="ad706-126">Wenn die Datenquelle ein Dataset ist, legen Sie die <xref:System.Windows.Forms.DataGrid.DataMember%2A> -Eigenschaft auf den Namen der Tabelle zu binden.</span><span class="sxs-lookup"><span data-stu-id="ad706-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3. <span data-ttu-id="ad706-127">Ist die Datenquelle ein Dataset oder eine basierend auf einer Dataset-Tabelle an, fügen Sie Code zum Formular, um das Dataset zu füllen.</span><span class="sxs-lookup"><span data-stu-id="ad706-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="ad706-128">Die genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="ad706-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="ad706-129">Wenn der Dataset direkt aus einer Datenbank gefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Codebeispiel wird, die aufgefüllt, ein Dataset mit dem Namen wird `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="ad706-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4. <span data-ttu-id="ad706-130">(Optional) Fügen Sie die geeigneten Tabellen- und Spaltenformate zum Raster an.</span><span class="sxs-lookup"><span data-stu-id="ad706-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="ad706-131">Wenn es keine Tabellenformate sind, sehen Sie in der Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad706-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="ad706-132">Klicken Sie auf dem DataGrid-Steuerelement an mehrere Tabellen in einem Dataset in der Designer Datenbindung</span><span class="sxs-lookup"><span data-stu-id="ad706-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1. <span data-ttu-id="ad706-133">Legen Sie die <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft, um das Objekt, enthält die Datenelemente, die Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad706-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2. <span data-ttu-id="ad706-134">Wenn das Dataset über verknüpfte Tabellen enthält (d. h. wenn er ein Relation-Objekt enthält), legen die <xref:System.Windows.Forms.DataGrid.DataMember%2A> -Eigenschaft auf den Namen der übergeordneten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ad706-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3. <span data-ttu-id="ad706-135">Schreiben Sie Code aus, um das Dataset zu füllen.</span><span class="sxs-lookup"><span data-stu-id="ad706-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad706-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad706-136">See also</span></span>

- [<span data-ttu-id="ad706-137">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ad706-137">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="ad706-138">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad706-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="ad706-139">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ad706-139">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="ad706-140">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="ad706-140">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="ad706-141">Zugreifen auf Daten in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ad706-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
