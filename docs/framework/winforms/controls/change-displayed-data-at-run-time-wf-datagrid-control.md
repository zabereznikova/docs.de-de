---
title: Ändern der angezeigten Daten zur Laufzeit im DataGrid-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: f91e2ea01ef4a52dd649efed70319017efb8368a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740592"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="f8b72-102">Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f8b72-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="f8b72-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="f8b72-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="f8b72-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f8b72-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="f8b72-105">Nachdem Sie mithilfe der Entwurfszeit Features eine Windows Forms <xref:System.Windows.Forms.DataGrid> erstellt haben, möchten Sie möglicherweise auch Elemente des <xref:System.Data.DataSet> Objekts des Rasters zur Laufzeit dynamisch ändern.</span><span class="sxs-lookup"><span data-stu-id="f8b72-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="f8b72-106">Dies kann Änderungen an den einzelnen Werten der Tabelle oder die Änderung der Datenquelle, die an das <xref:System.Windows.Forms.DataGrid> Steuerelement gebunden ist, einschließen.</span><span class="sxs-lookup"><span data-stu-id="f8b72-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="f8b72-107">Änderungen an einzelnen Werten werden über das <xref:System.Data.DataSet> Objekt, nicht über das <xref:System.Windows.Forms.DataGrid> Steuerelement durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8b72-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="f8b72-108">So ändern Sie Daten Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="f8b72-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="f8b72-109">Geben Sie die gewünschte Tabelle aus dem <xref:System.Data.DataSet> Objekt und die gewünschte Zeile und das gewünschte Feld aus der Tabelle an, und legen Sie die Zelle auf den neuen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="f8b72-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f8b72-110">Um die erste Tabelle des <xref:System.Data.DataSet> oder die erste Zeile der Tabelle anzugeben, verwenden Sie 0.</span><span class="sxs-lookup"><span data-stu-id="f8b72-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="f8b72-111">Im folgenden Beispiel wird gezeigt, wie Sie den zweiten Eintrag der ersten Zeile der ersten Tabelle eines Datasets ändern, indem Sie auf `Button1`klicken.</span><span class="sxs-lookup"><span data-stu-id="f8b72-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="f8b72-112">Die <xref:System.Data.DataSet> (`ds`) und die Tabellen (`0` und `1`) wurden bereits erstellt.</span><span class="sxs-lookup"><span data-stu-id="f8b72-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="f8b72-113">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="f8b72-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="f8b72-114">Zur Laufzeit können Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode verwenden, um das <xref:System.Windows.Forms.DataGrid> Steuerelement an eine andere Datenquelle zu binden.</span><span class="sxs-lookup"><span data-stu-id="f8b72-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="f8b72-115">Beispielsweise können mehrere ADO.NET-Daten Steuerelemente vorhanden sein, die jeweils mit einer anderen Datenbank verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f8b72-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="f8b72-116">So ändern Sie die Datenquelle Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="f8b72-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="f8b72-117">Legen Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode auf den Namen der Datenquelle und der Tabelle fest, an die die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="f8b72-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="f8b72-118">Im folgenden Beispiel wird gezeigt, wie Sie die Datums Quelle mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode in ein ADO.NET Data-Steuerelement (adoPubsAuthors) ändern können, das mit der Autoren Tabelle in der pubs-Datenbank verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="f8b72-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f8b72-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8b72-119">See also</span></span>

- [<span data-ttu-id="f8b72-120">ADO.NET-DataSets</span><span class="sxs-lookup"><span data-stu-id="f8b72-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="f8b72-121">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8b72-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="f8b72-122">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8b72-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="f8b72-123">Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f8b72-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
