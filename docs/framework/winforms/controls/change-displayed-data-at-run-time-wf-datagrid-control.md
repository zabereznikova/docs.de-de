---
title: 'Vorgehensweise: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit'
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
ms.openlocfilehash: 60ba1e9304320346d505f3f73e1ba93ff6edab63
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315854"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="179fb-102">Vorgehensweise: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="179fb-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="179fb-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="179fb-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="179fb-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="179fb-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="179fb-105">Nach der Erstellung einer Windows Forms <xref:System.Windows.Forms.DataGrid> mit den Funktionen zur Entwurfszeit können Sie auch den Elemente dynamisch ändern der <xref:System.Data.DataSet> Objekt des Rasters zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="179fb-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="179fb-106">Dies kann Änderungen an der Tabelle entweder einzelne Werte einschließen, oder ändern die Datenquelle gebunden ist, um die <xref:System.Windows.Forms.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="179fb-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="179fb-107">Änderungen an einzelnen Werten werden stets die <xref:System.Data.DataSet> -Objekt und nicht die <xref:System.Windows.Forms.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="179fb-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="179fb-108">Programmgesteuertes Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="179fb-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="179fb-109">Geben Sie die gewünschte Tabelle aus der <xref:System.Data.DataSet> Objekt und die gewünschte Zeile, und das Feld aus der Tabelle, und legen Sie die Zelle auf den neuen Wert.</span><span class="sxs-lookup"><span data-stu-id="179fb-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="179fb-110">Der ersten Tabelle des an den <xref:System.Data.DataSet> oder die erste Zeile der Tabelle, verwenden Sie 0.</span><span class="sxs-lookup"><span data-stu-id="179fb-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="179fb-111">Das folgende Beispiel zeigt, wie Sie durch Klicken auf den zweiten Eintrag in der ersten Zeile der ersten Tabelle eines Datasets zu ändern `Button1`.</span><span class="sxs-lookup"><span data-stu-id="179fb-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="179fb-112">Die <xref:System.Data.DataSet> (`ds`) und Tabellen (`0` und `1`) waren zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="179fb-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="179fb-113">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="179fb-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="179fb-114">Zur Laufzeit können Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode zum Binden der <xref:System.Windows.Forms.DataGrid> Steuerelement mit einer anderen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="179fb-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="179fb-115">Angenommen, Sie verfügen möglicherweise über mehrere [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Datensteuerelementen, jeweils mit einer anderen Datenbank verbunden.</span><span class="sxs-lookup"><span data-stu-id="179fb-115">For example, you may have several [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="179fb-116">So ändern Sie die Datenquelle programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="179fb-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="179fb-117">Legen Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode, um den Namen der Datenquelle und der Tabelle, die Sie binden möchten.</span><span class="sxs-lookup"><span data-stu-id="179fb-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="179fb-118">Das folgende Beispiel zeigt, wie Sie die Datenquelle mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode, um eine [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Datensteuerelement (adoPubsAuthors gebunden), die mit der Autorentabelle in der Pubs-Datenbank verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="179fb-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="179fb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="179fb-119">See also</span></span>

- [<span data-ttu-id="179fb-120">ADO.NET-DataSets</span><span class="sxs-lookup"><span data-stu-id="179fb-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="179fb-121">Vorgehensweise: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="179fb-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="179fb-122">Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="179fb-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="179fb-123">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="179fb-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
