---
title: 'Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle'
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
ms.openlocfilehash: 62f61eb2d294baf007b0b3f749f3cf6b7f4857c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> Steuerelement ist speziell für die Anzeige von Informationen aus einer Datenquelle. Binden des Steuerelements zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode. Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Um das DataGrid-Steuerelement programmgesteuert Datenbindung  
  
1.  Schreiben Sie Code zum Füllen des Datasets.  
  
     Ist die Datenquelle ein Dataset oder einer Datenansicht basierend auf einer Dataset-Tabelle, fügen Sie Code zum Formular, um das Dataset zu füllen.  
  
     Der genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält. Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Beispiel, das ein Dataset mit dem Namen füllt `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Das Dataset aus einem XML-Webdienst gefüllt wird, Sie erstellen Sie eine Instanz des Diensts in der Regel in Ihrem Code, und rufen Sie eine der Methoden ein Dataset zurückgegeben. Dort haben Sie das Dataset aus der XML-Webdienst in Ihrem lokalen Dataset zusammenführen. Das folgende Beispiel zeigt die Erstellung einer Instanz von einem XML-Webdienst aufgerufen `CategoriesService`, rufen Sie die `GetCategories` -Methode und den Merge-wird aufgerufen, das sich ergebende Dataset in ein lokales Dataset `DsCategories1`:  
  
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
  
2.  Rufen Sie die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> -Methode, und übergeben sie die Datenquelle und einen Datenmember. Wenn Sie nicht explizit einen Datenmember übergeben müssen, übergeben Sie eine leere Zeichenfolge.  
  
    > [!NOTE]
    >  Wenn Sie das Raster zum ersten Mal binden, können Sie festlegen, dass des Steuerelements <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften. Allerdings können nicht Sie diese Eigenschaften zurückgesetzt, nachdem diese festgelegt wurden. Aus diesem Grund wird empfohlen, dass Sie immer verwenden die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.  
  
     Das folgende Beispiel zeigt, wie Sie eine Bindung zur Customers-Tabelle in einem Dataset mit dem Namen programmgesteuert `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Wenn die Customers-Tabelle lediglich die Tabelle im Dataset ist, konnte Sie alternativ im Raster auf diese Weise binden:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  (Optional) Fügen Sie die entsprechenden Tabellenformate und Spaltenformate zum Raster an. Wenn keine Tabellenformate sind, sehen Sie die Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über das DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md)
