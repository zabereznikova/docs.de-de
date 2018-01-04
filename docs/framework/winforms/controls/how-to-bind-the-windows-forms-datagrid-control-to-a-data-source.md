---
title: "Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c136aca0eda9ea906ad8bf6853a263adf6130609
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="3ad05-102">Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="3ad05-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="3ad05-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3ad05-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3ad05-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3ad05-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="3ad05-105">Windows Forms <xref:System.Windows.Forms.DataGrid> Steuerelement ist speziell für die Anzeige von Informationen aus einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="3ad05-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="3ad05-106">Binden des Steuerelements zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="3ad05-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="3ad05-107">Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.</span><span class="sxs-lookup"><span data-stu-id="3ad05-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="3ad05-108">Um das DataGrid-Steuerelement programmgesteuert Datenbindung</span><span class="sxs-lookup"><span data-stu-id="3ad05-108">To data-bind the DataGrid control programmatically</span></span>  
  
1.  <span data-ttu-id="3ad05-109">Schreiben Sie Code zum Füllen des Datasets.</span><span class="sxs-lookup"><span data-stu-id="3ad05-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="3ad05-110">Ist die Datenquelle ein Dataset oder einer Datenansicht basierend auf einer Dataset-Tabelle, fügen Sie Code zum Formular, um das Dataset zu füllen.</span><span class="sxs-lookup"><span data-stu-id="3ad05-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="3ad05-111">Der genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="3ad05-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="3ad05-112">Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Beispiel, das ein Dataset mit dem Namen füllt `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="3ad05-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="3ad05-113">Das Dataset aus einem XML-Webdienst gefüllt wird, Sie erstellen Sie eine Instanz des Diensts in der Regel in Ihrem Code, und rufen Sie eine der Methoden ein Dataset zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ad05-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="3ad05-114">Dort haben Sie das Dataset aus der XML-Webdienst in Ihrem lokalen Dataset zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="3ad05-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="3ad05-115">Das folgende Beispiel zeigt die Erstellung einer Instanz von einem XML-Webdienst aufgerufen `CategoriesService`, rufen Sie die `GetCategories` -Methode und den Merge-wird aufgerufen, das sich ergebende Dataset in ein lokales Dataset `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="3ad05-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
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
  
2.  <span data-ttu-id="3ad05-116">Rufen Sie die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> -Methode, und übergeben sie die Datenquelle und einen Datenmember.</span><span class="sxs-lookup"><span data-stu-id="3ad05-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="3ad05-117">Wenn Sie nicht explizit einen Datenmember übergeben müssen, übergeben Sie eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3ad05-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3ad05-118">Wenn Sie das Raster zum ersten Mal binden, können Sie festlegen, dass des Steuerelements <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3ad05-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="3ad05-119">Allerdings können nicht Sie diese Eigenschaften zurückgesetzt, nachdem diese festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="3ad05-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="3ad05-120">Aus diesem Grund wird empfohlen, dass Sie immer verwenden die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="3ad05-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="3ad05-121">Das folgende Beispiel zeigt, wie Sie eine Bindung zur Customers-Tabelle in einem Dataset mit dem Namen programmgesteuert `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="3ad05-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="3ad05-122">Wenn die Customers-Tabelle lediglich die Tabelle im Dataset ist, konnte Sie alternativ im Raster auf diese Weise binden:</span><span class="sxs-lookup"><span data-stu-id="3ad05-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  <span data-ttu-id="3ad05-123">(Optional) Fügen Sie die entsprechenden Tabellenformate und Spaltenformate zum Raster an.</span><span class="sxs-lookup"><span data-stu-id="3ad05-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="3ad05-124">Wenn keine Tabellenformate sind, sehen Sie die Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ad05-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad05-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ad05-125">See Also</span></span>  
 [<span data-ttu-id="3ad05-126">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3ad05-126">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="3ad05-127">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ad05-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="3ad05-128">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3ad05-128">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="3ad05-129">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="3ad05-129">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
