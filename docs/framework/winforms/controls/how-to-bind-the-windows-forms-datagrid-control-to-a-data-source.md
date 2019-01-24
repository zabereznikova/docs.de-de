---
title: 'Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle'
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
ms.openlocfilehash: 5f8c0c2865d219eecb88ddd176d99f80521c9ab3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664212"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="65fa1-102">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="65fa1-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="65fa1-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="65fa1-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="65fa1-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="65fa1-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="65fa1-105">Die Windows-Formulare <xref:System.Windows.Forms.DataGrid> Steuerelement wurde speziell zur Anzeige von Informationen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="65fa1-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="65fa1-106">Binden des Steuerelements zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="65fa1-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="65fa1-107">Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.</span><span class="sxs-lookup"><span data-stu-id="65fa1-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="65fa1-108">Klicken Sie auf dem DataGrid-Steuerelement programmgesteuert Datenbindung</span><span class="sxs-lookup"><span data-stu-id="65fa1-108">To data-bind the DataGrid control programmatically</span></span>  
  
1.  <span data-ttu-id="65fa1-109">Schreiben Sie Code aus, um das Dataset zu füllen.</span><span class="sxs-lookup"><span data-stu-id="65fa1-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="65fa1-110">Ist die Datenquelle ein Dataset oder eine basierend auf einer Dataset-Tabelle an, fügen Sie Code zum Formular, um das Dataset zu füllen.</span><span class="sxs-lookup"><span data-stu-id="65fa1-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="65fa1-111">Die genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="65fa1-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="65fa1-112">Wenn der Dataset direkt aus einer Datenbank gefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Beispiel an, die aufgefüllt, ein Dataset mit dem Namen wird `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="65fa1-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="65fa1-113">Wenn das Dataset aus einem XML-Webdienst gefüllt wird, Sie erstellen Sie eine Instanz des Diensts in der Regel in Ihrem Code und rufen Sie dann eine der zugehörigen Methoden, die ein Dataset zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="65fa1-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="65fa1-114">Sie werden klicken Sie dann das Dataset aus den XML-Webdienst mit Ihrem lokalen Dataset zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="65fa1-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="65fa1-115">Das folgende Beispiel zeigt, wie Sie eine Instanz von einem XML-Webdienst, der Namen erstellen können `CategoriesService`, rufen Sie die `GetCategories` -Methode und den Merge-wird aufgerufen, das sich ergebende Dataset in ein lokales Dataset `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="65fa1-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
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
  
2.  <span data-ttu-id="65fa1-116">Rufen Sie die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> -Methode, und übergeben sie die Datenquelle und ein Datenelement.</span><span class="sxs-lookup"><span data-stu-id="65fa1-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="65fa1-117">Wenn Sie nicht benötigen, um ein Datenmember explizit zu übergeben, übergeben Sie eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="65fa1-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65fa1-118">Wenn Sie zum ersten Mal im Raster binden, können Sie festlegen, dass des Steuerelements <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="65fa1-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="65fa1-119">Allerdings kann diese Eigenschaften nicht zurückgesetzt, nachdem sie festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="65fa1-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="65fa1-120">Es wird daher empfohlen, immer verwenden, die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="65fa1-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="65fa1-121">Das folgende Beispiel zeigt, wie Sie eine Bindung zur Customers-Tabelle in einem Dataset mit dem Namen programmgesteuert `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="65fa1-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="65fa1-122">Ist die Customers-Tabelle lediglich die Tabelle im Dataset, können Sie alternativ das Raster auf diese Weise binden:</span><span class="sxs-lookup"><span data-stu-id="65fa1-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  <span data-ttu-id="65fa1-123">(Optional) Fügen Sie die geeigneten Tabellen- und Spaltenformate zum Raster an.</span><span class="sxs-lookup"><span data-stu-id="65fa1-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="65fa1-124">Wenn es keine Tabellenformate sind, sehen Sie in der Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65fa1-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fa1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65fa1-125">See also</span></span>
- [<span data-ttu-id="65fa1-126">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65fa1-126">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="65fa1-127">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65fa1-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="65fa1-128">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65fa1-128">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [<span data-ttu-id="65fa1-129">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="65fa1-129">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
