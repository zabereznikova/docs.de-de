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
ms.openlocfilehash: de8b8d16f45221fbafe9f61ca634f144d8f6f6ae
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040010"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="af6a4-102">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="af6a4-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="af6a4-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="af6a4-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="af6a4-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="af6a4-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="af6a4-105">Das Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement wurde speziell zum Anzeigen von Informationen aus einer Datenquelle entwickelt.</span><span class="sxs-lookup"><span data-stu-id="af6a4-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="af6a4-106">Sie binden das Steuerelement zur Entwurfszeit, indem <xref:System.Windows.Forms.DataGrid.DataSource%2A> Sie <xref:System.Windows.Forms.DataGrid.DataMember%2A> die-Eigenschaft und die-Eigenschaft festlegen oder <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> zur Laufzeit durch Aufrufen der-Methode.</span><span class="sxs-lookup"><span data-stu-id="af6a4-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="af6a4-107">Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, handelt es sich bei den meisten Quellen um Datasets und Datenansichten.</span><span class="sxs-lookup"><span data-stu-id="af6a4-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>

 <span data-ttu-id="af6a4-108">Wenn die Datenquelle zur Entwurfszeit verfügbar ist – z. b. wenn das Formular eine Instanz eines Datasets oder einer Daten Sicht enthält – können Sie das Raster zur Entwurfszeit an die Datenquelle binden.</span><span class="sxs-lookup"><span data-stu-id="af6a4-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="af6a4-109">Sie können dann eine Vorschau der Daten anzeigen, die im Raster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="af6a4-109">You can then preview what the data will look like in the grid.</span></span>

 <span data-ttu-id="af6a4-110">Sie können das Raster zur Laufzeit auch Programm gesteuert binden.</span><span class="sxs-lookup"><span data-stu-id="af6a4-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="af6a4-111">Dies ist hilfreich, wenn Sie eine Datenquelle basierend auf Informationen festlegen möchten, die Sie zur Laufzeit erhalten.</span><span class="sxs-lookup"><span data-stu-id="af6a4-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="af6a4-112">Die Anwendung kann z. b. den Namen einer Tabelle angeben, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="af6a4-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="af6a4-113">Dies ist auch in Situationen erforderlich, in denen die Datenquelle zur Entwurfszeit nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="af6a4-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="af6a4-114">Dies schließt Datenquellen ein, z. b. Arrays, Auflistungen, nicht typisierte Datasets und Daten Leser.</span><span class="sxs-lookup"><span data-stu-id="af6a4-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>

 <span data-ttu-id="af6a4-115">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGrid> das ein-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="af6a4-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="af6a4-116">Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="af6a4-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="af6a4-117">In Visual Studio 2005 ist das <xref:System.Windows.Forms.DataGrid> Steuerelement standardmäßig nicht in der **Toolbox** .</span><span class="sxs-lookup"><span data-stu-id="af6a4-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="af6a4-118">Weitere Informationen zum Hinzufügen finden [Sie unter Gewusst wie: Fügen Sie der Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="af6a4-118">For information about adding it, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="af6a4-119">Darüber hinaus können Sie in Visual Studio 2005 das Fenster **Datenquellen** für die Datenbindung zur Entwurfszeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="af6a4-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="af6a4-120">Weitere Informationen finden Sie unterbinden von Steuer [Elementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="af6a4-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="af6a4-121">So binden Sie das DataGrid-Steuerelement an eine einzelne Tabelle im Designer</span><span class="sxs-lookup"><span data-stu-id="af6a4-121">To data-bind the DataGrid control to a single table in the designer</span></span>

1. <span data-ttu-id="af6a4-122">Legen Sie die- <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft des Steuer Elements auf das-Objekt fest, das die Datenelemente enthält, an die Sie binden möchten</span><span class="sxs-lookup"><span data-stu-id="af6a4-122">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="af6a4-123">Wenn die Datenquelle ein DataSet ist, legen Sie <xref:System.Windows.Forms.DataGrid.DataMember%2A> die-Eigenschaft auf den Namen der Tabelle fest, an die die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="af6a4-123">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>

3. <span data-ttu-id="af6a4-124">Wenn es sich bei der Datenquelle um ein DataSet oder eine Datenansicht handelt, die auf einer Datasettabelle basiert, fügen Sie dem Formular Code hinzu, um das DataSet zu füllen.</span><span class="sxs-lookup"><span data-stu-id="af6a4-124">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>

     <span data-ttu-id="af6a4-125">Der genaue Code, den Sie verwenden, hängt davon ab, wo das DataSet Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="af6a4-125">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="af6a4-126">Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, wird in der Regel die `Fill` -Methode eines Daten Adapters aufgerufen, wie im folgenden Codebeispiel gezeigt, das ein DataSet mit dem `DsCategories1`Namen auffüllt:</span><span class="sxs-lookup"><span data-stu-id="af6a4-126">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. <span data-ttu-id="af6a4-127">Optionale Fügen Sie dem Raster die entsprechenden Tabellen Stile und Spalten Stile hinzu.</span><span class="sxs-lookup"><span data-stu-id="af6a4-127">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>

     <span data-ttu-id="af6a4-128">Wenn keine Tabellen Stile vorhanden sind, wird die Tabelle angezeigt, jedoch mit minimaler Formatierung und allen sichtbaren Spalten.</span><span class="sxs-lookup"><span data-stu-id="af6a4-128">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="af6a4-129">So binden Sie das DataGrid-Steuerelement an mehrere Tabellen in einem Dataset im Designer</span><span class="sxs-lookup"><span data-stu-id="af6a4-129">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>

1. <span data-ttu-id="af6a4-130">Legen Sie die- <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft des Steuer Elements auf das-Objekt fest, das die Datenelemente enthält, an die Sie binden möchten</span><span class="sxs-lookup"><span data-stu-id="af6a4-130">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="af6a4-131">Wenn das Dataset verknüpfte Tabellen enthält (d. h., wenn es ein Beziehungs Objekt enthält) <xref:System.Windows.Forms.DataGrid.DataMember%2A> , legen Sie die-Eigenschaft auf den Namen der übergeordneten Tabelle fest.</span><span class="sxs-lookup"><span data-stu-id="af6a4-131">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>

3. <span data-ttu-id="af6a4-132">Schreiben Sie Code, um das DataSet auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="af6a4-132">Write code to fill the dataset.</span></span>

## <a name="see-also"></a><span data-ttu-id="af6a4-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af6a4-133">See also</span></span>

- [<span data-ttu-id="af6a4-134">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af6a4-134">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="af6a4-135">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum Windows Forms DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af6a4-135">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="af6a4-136">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af6a4-136">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="af6a4-137">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="af6a4-137">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="af6a4-138">Zugreifen auf Daten in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af6a4-138">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
