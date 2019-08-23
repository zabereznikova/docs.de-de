---
title: 'Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle'
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
ms.openlocfilehash: bac24c2dd622ea780408e902d08708ac09561044
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922722"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Das Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement wurde speziell zum Anzeigen von Informationen aus einer Datenquelle entwickelt. Sie binden das Steuerelement zur Laufzeit, indem Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die-Methode aufrufen. Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, handelt es sich bei den meisten Quellen um Datasets und Datenansichten.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>So binden Sie das DataGrid-Steuerelement Programm gesteuert ein  
  
1. Schreiben Sie Code, um das DataSet auszufüllen.  
  
     Wenn es sich bei der Datenquelle um ein DataSet oder eine Datenansicht handelt, die auf einer Datasettabelle basiert, fügen Sie dem Formular Code hinzu, um das DataSet zu füllen.  
  
     Der genaue Code, den Sie verwenden, hängt davon ab, wo das DataSet Daten erhält. Wenn das Dataset direkt aus einer Datenbank aufgefüllt wird, wird in der Regel die `Fill` -Methode eines Daten Adapters aufgerufen, wie im folgenden Beispiel gezeigt, das ein DataSet mit dem `DsCategories1`Namen auffüllt:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Wenn das DataSet von einem XML-Webdienst ausgefüllt wird, erstellen Sie in der Regel eine Instanz des Diensts im Code und rufen dann eine seiner Methoden auf, um ein DataSet zurückzugeben. Anschließend führen Sie das DataSet aus dem XML-Webdienst in Ihr lokales DataSet zusammen. Im folgenden Beispiel wird gezeigt, wie Sie eine Instanz eines XML-Webdiensts `CategoriesService`mit dem Namen `GetCategories` erstellen, seine-Methode aufrufen und das resultierende DataSet in einem lokalen `DsCategories1`DataSet mit dem Namen zusammenführen können:  
  
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
  
2. Wenden Sie <xref:System.Windows.Forms.DataGrid> die- <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode des-Steuer Elements an, und übergeben Sie dabei die Datenquelle und einen Datenmember. Wenn Sie einen Datenmember nicht explizit übergeben müssen, übergeben Sie eine leere Zeichenfolge.  
  
    > [!NOTE]
    > Wenn Sie das Raster zum ersten Mal binden, können Sie die-Eigenschaft und <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> die-Eigenschaft des-Steuer Elements festlegen. Sie können diese Eigenschaften jedoch nicht zurücksetzen, sobald Sie festgelegt wurden. Daher wird empfohlen, immer die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> -Methode zu verwenden.  
  
     Im folgenden Beispiel wird gezeigt, wie Sie Programm gesteuert an die Customers-Tabelle in einem DataSet `DsCustomers1`mit dem Namen binden können:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Wenn die Customers-Tabelle die einzige Tabelle im DataSet ist, können Sie das Raster wahlweise wie folgt binden:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. Optionale Fügen Sie dem Raster die entsprechenden Tabellen Stile und Spalten Stile hinzu. Wenn keine Tabellen Stile vorhanden sind, wird die Tabelle angezeigt, jedoch mit minimaler Formatierung und allen sichtbaren Spalten.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das DataGrid-Steuerelement](datagrid-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum Windows Forms DataGrid-Steuerelement](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
