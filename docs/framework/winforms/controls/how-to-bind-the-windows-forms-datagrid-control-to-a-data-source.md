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
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das Windows <xref:System.Windows.Forms.DataGrid> Forms-Steuerelement wurde speziell für die Anzeige von Informationen aus einer Datenquelle entwickelt. Sie binden das Steuerelement zur <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Laufzeit, indem Sie die Methode aufrufen. Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die typischsten Quellen Datasets und Datenansichten.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>So binden Sie das DataGrid-Steuerelement programmgesteuert  
  
1. Schreiben Sie Code, um das Dataset zu füllen.  
  
     Wenn es sich bei der Datenquelle um ein Dataset oder eine Datenansicht handelt, die auf einer Datasettabelle basiert, fügen Sie dem Formular Code hinzu, um das Dataset auszufüllen.  
  
     Der genaue Code, den Sie verwenden, hängt davon ab, wo das Dataset Daten abgibt. Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, rufen Sie in der Regel die `Fill` Methode eines `DsCategories1`Datenadapters auf, wie im folgenden Beispiel, das ein Dataset mit dem Namen :  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Wenn das Dataset aus einem XML-Webdienst gefüllt wird, erstellen Sie in der Regel eine Instanz des Dienstes im Code und rufen dann eine der Methoden auf, um ein Dataset zurückzugeben. Anschließend führen Sie das Dataset aus dem XML-Webdienst in Ihrem lokalen Dataset zusammen. Das folgende Beispiel zeigt, wie Sie eine Instanz `CategoriesService`eines `GetCategories` XML-Webdiensts mit dem Namen `DsCategories1`erstellen können, seine Methode aufrufen und das resultierende Dataset in einem lokalen Dataset namens :  
  
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
  
2. Rufen <xref:System.Windows.Forms.DataGrid> Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode des Steuerelements auf und übergeben Sie sie an die Datenquelle und ein Datenelement. Wenn Sie einen Datenmember nicht explizit übergeben müssen, übergeben Sie eine leere Zeichenfolge.  
  
    > [!NOTE]
    > Wenn Sie das Raster zum ersten Mal binden, können <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> Sie die Steuerelemente und Eigenschaften festlegen. Sie können diese Eigenschaften jedoch nicht zurücksetzen, nachdem sie festgelegt wurden. Daher wird empfohlen, dass Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> immer die Methode verwenden.  
  
     Das folgende Beispiel zeigt, wie Sie programmgesteuert an die `DsCustomers1`Customers-Tabelle in einem Dataset namens :  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Wenn die Customers-Tabelle die einzige Tabelle im Dataset ist, können Sie das Raster alternativ auf diese Weise binden:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (Optional) Fügen Sie dem Raster die entsprechenden Tabellenstile und Spaltenstile hinzu. Wenn keine Tabellenformatvorlagen vorhanden sind, wird die Tabelle angezeigt, jedoch mit minimaler Formatierung und mit allen spaltensichtbaren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das DataGrid-Steuerelement](datagrid-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Datenbindung in Web Forms](../windows-forms-data-binding.md)
