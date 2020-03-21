---
title: Binden von DataGrid-Steuerelementen an eine Datenquelle
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182246"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="7386f-102">Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="7386f-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="7386f-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7386f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="7386f-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7386f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="7386f-105">Das Windows <xref:System.Windows.Forms.DataGrid> Forms-Steuerelement wurde speziell für die Anzeige von Informationen aus einer Datenquelle entwickelt.</span><span class="sxs-lookup"><span data-stu-id="7386f-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="7386f-106">Sie binden das Steuerelement zur <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Laufzeit, indem Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7386f-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="7386f-107">Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die typischsten Quellen Datasets und Datenansichten.</span><span class="sxs-lookup"><span data-stu-id="7386f-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="7386f-108">So binden Sie das DataGrid-Steuerelement programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="7386f-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="7386f-109">Schreiben Sie Code, um das Dataset zu füllen.</span><span class="sxs-lookup"><span data-stu-id="7386f-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="7386f-110">Wenn es sich bei der Datenquelle um ein Dataset oder eine Datenansicht handelt, die auf einer Datasettabelle basiert, fügen Sie dem Formular Code hinzu, um das Dataset auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="7386f-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="7386f-111">Der genaue Code, den Sie verwenden, hängt davon ab, wo das Dataset Daten abgibt.</span><span class="sxs-lookup"><span data-stu-id="7386f-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="7386f-112">Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, rufen Sie in der Regel die `Fill` Methode eines `DsCategories1`Datenadapters auf, wie im folgenden Beispiel, das ein Dataset mit dem Namen :</span><span class="sxs-lookup"><span data-stu-id="7386f-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="7386f-113">Wenn das Dataset aus einem XML-Webdienst gefüllt wird, erstellen Sie in der Regel eine Instanz des Dienstes im Code und rufen dann eine der Methoden auf, um ein Dataset zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="7386f-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="7386f-114">Anschließend führen Sie das Dataset aus dem XML-Webdienst in Ihrem lokalen Dataset zusammen.</span><span class="sxs-lookup"><span data-stu-id="7386f-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="7386f-115">Das folgende Beispiel zeigt, wie Sie eine Instanz `CategoriesService`eines `GetCategories` XML-Webdiensts mit dem Namen `DsCategories1`erstellen können, seine Methode aufrufen und das resultierende Dataset in einem lokalen Dataset namens :</span><span class="sxs-lookup"><span data-stu-id="7386f-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="7386f-116">Rufen <xref:System.Windows.Forms.DataGrid> Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode des Steuerelements auf und übergeben Sie sie an die Datenquelle und ein Datenelement.</span><span class="sxs-lookup"><span data-stu-id="7386f-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="7386f-117">Wenn Sie einen Datenmember nicht explizit übergeben müssen, übergeben Sie eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7386f-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7386f-118">Wenn Sie das Raster zum ersten Mal binden, können <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> Sie die Steuerelemente und Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="7386f-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="7386f-119">Sie können diese Eigenschaften jedoch nicht zurücksetzen, nachdem sie festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="7386f-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="7386f-120">Daher wird empfohlen, dass Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> immer die Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="7386f-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="7386f-121">Das folgende Beispiel zeigt, wie Sie programmgesteuert an die `DsCustomers1`Customers-Tabelle in einem Dataset namens :</span><span class="sxs-lookup"><span data-stu-id="7386f-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="7386f-122">Wenn die Customers-Tabelle die einzige Tabelle im Dataset ist, können Sie das Raster alternativ auf diese Weise binden:</span><span class="sxs-lookup"><span data-stu-id="7386f-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="7386f-123">(Optional) Fügen Sie dem Raster die entsprechenden Tabellenstile und Spaltenstile hinzu.</span><span class="sxs-lookup"><span data-stu-id="7386f-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="7386f-124">Wenn keine Tabellenformatvorlagen vorhanden sind, wird die Tabelle angezeigt, jedoch mit minimaler Formatierung und mit allen spaltensichtbaren.</span><span class="sxs-lookup"><span data-stu-id="7386f-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7386f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7386f-125">See also</span></span>

- [<span data-ttu-id="7386f-126">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7386f-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="7386f-127">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7386f-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="7386f-128">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7386f-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="7386f-129">Datenbindung in Web Forms</span><span class="sxs-lookup"><span data-stu-id="7386f-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
