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
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332572"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Die Windows-Formulare <xref:System.Windows.Forms.DataGrid> Steuerelement wurde speziell zur Anzeige von Informationen aus einer Datenquelle. Binden des Steuerelements zur Laufzeit durch Aufrufen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode. Obwohl Sie Daten aus einer Vielzahl von Datenquellen anzeigen können, sind die häufigsten Quellen Datasets und Ansichten.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Klicken Sie auf dem DataGrid-Steuerelement programmgesteuert Datenbindung  
  
1. Schreiben Sie Code aus, um das Dataset zu füllen.  
  
     Ist die Datenquelle ein Dataset oder eine basierend auf einer Dataset-Tabelle an, fügen Sie Code zum Formular, um das Dataset zu füllen.  
  
     Die genaue Code, den Sie verwenden, hängt davon ab, in dem das Dataset Daten erhält. Wenn der Dataset direkt aus einer Datenbank gefüllt wird, rufen Sie in der Regel die `Fill` Methode eines Datenadapters, wie im folgenden Beispiel an, die aufgefüllt, ein Dataset mit dem Namen wird `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Wenn das Dataset aus einem XML-Webdienst gefüllt wird, Sie erstellen Sie eine Instanz des Diensts in der Regel in Ihrem Code und rufen Sie dann eine der zugehörigen Methoden, die ein Dataset zurückgeben. Sie werden klicken Sie dann das Dataset aus den XML-Webdienst mit Ihrem lokalen Dataset zusammenführen. Das folgende Beispiel zeigt, wie Sie eine Instanz von einem XML-Webdienst, der Namen erstellen können `CategoriesService`, rufen Sie die `GetCategories` -Methode und den Merge-wird aufgerufen, das sich ergebende Dataset in ein lokales Dataset `DsCategories1`:  
  
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
  
2. Rufen Sie die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> -Methode, und übergeben sie die Datenquelle und ein Datenelement. Wenn Sie nicht benötigen, um ein Datenmember explizit zu übergeben, übergeben Sie eine leere Zeichenfolge.  
  
    > [!NOTE]
    >  Wenn Sie zum ersten Mal im Raster binden, können Sie festlegen, dass des Steuerelements <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften. Allerdings kann diese Eigenschaften nicht zurückgesetzt, nachdem sie festgelegt wurden. Es wird daher empfohlen, immer verwenden, die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode.  
  
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
  
     Ist die Customers-Tabelle lediglich die Tabelle im Dataset, können Sie alternativ das Raster auf diese Weise binden:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (Optional) Fügen Sie die geeigneten Tabellen- und Spaltenformate zum Raster an. Wenn es keine Tabellenformate sind, sehen Sie in der Tabelle, jedoch mit minimaler Formatierung und alle Spalten angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das DataGrid-Steuerelement](datagrid-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
