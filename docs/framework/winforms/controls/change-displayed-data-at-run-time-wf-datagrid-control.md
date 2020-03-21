---
title: Angezeigte Daten zur Laufzeit in DataGrid Control ändern
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142380"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="b7c16-102">Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b7c16-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="b7c16-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b7c16-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="b7c16-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b7c16-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="b7c16-105">Nachdem Sie ein Windows <xref:System.Windows.Forms.DataGrid> Forms mit den Entwurfszeitfeatures erstellt haben, können <xref:System.Data.DataSet> Sie auch Elemente des Objekts des Rasters zur Laufzeit dynamisch ändern.</span><span class="sxs-lookup"><span data-stu-id="b7c16-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="b7c16-106">Dies kann Änderungen an einzelnen Werten der Tabelle oder das <xref:System.Windows.Forms.DataGrid> Ändern der Datenquelle, die an das Steuerelement gebunden ist, umfassen.</span><span class="sxs-lookup"><span data-stu-id="b7c16-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="b7c16-107">Änderungen an einzelnen Werten <xref:System.Data.DataSet> werden über <xref:System.Windows.Forms.DataGrid> das Objekt und nicht über das Steuerelement vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="b7c16-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="b7c16-108">So ändern Sie Daten programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b7c16-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="b7c16-109">Geben Sie die <xref:System.Data.DataSet> gewünschte Tabelle aus dem Objekt und die gewünschte Zeile und das gewünschte Feld aus der Tabelle an, und legen Sie die Zelle gleich dem neuen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="b7c16-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b7c16-110">Um die erste Tabelle <xref:System.Data.DataSet> der oder der ersten Zeile der Tabelle anzugeben, verwenden Sie 0.</span><span class="sxs-lookup"><span data-stu-id="b7c16-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="b7c16-111">Das folgende Beispiel zeigt, wie Sie den zweiten Eintrag der ersten Zeile `Button1`der ersten Tabelle eines Datasets ändern, indem Sie auf klicken.</span><span class="sxs-lookup"><span data-stu-id="b7c16-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="b7c16-112">Die <xref:System.Data.DataSet> `ds`( )`0` und `1`Tabellen ( und ) wurden zuvor erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7c16-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="b7c16-113">(Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b7c16-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="b7c16-114">Zur Laufzeit können Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die Methode <xref:System.Windows.Forms.DataGrid> verwenden, um das Steuerelement an eine andere Datenquelle zu binden.</span><span class="sxs-lookup"><span data-stu-id="b7c16-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="b7c16-115">Sie verfügen z. B. über mehrere ADO.NET Datensteuerelemente, die jeweils mit einer anderen Datenbank verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b7c16-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="b7c16-116">So ändern Sie DataSource programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b7c16-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="b7c16-117">Legen <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Sie die Methode auf den Namen der Datenquelle und Tabelle fest, an die Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="b7c16-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="b7c16-118">Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die Datumsquelle mithilfe der Methode in ein ADO.NET Datensteuerelement (adoPubsAuthors) ändern, das mit der Tabelle Authors in der Pubs-Datenbank verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="b7c16-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7c16-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7c16-119">See also</span></span>

- [<span data-ttu-id="b7c16-120">ADO.NET-DataSets</span><span class="sxs-lookup"><span data-stu-id="b7c16-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="b7c16-121">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7c16-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="b7c16-122">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7c16-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="b7c16-123">Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="b7c16-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
