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
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nachdem Sie mithilfe der Entwurfszeit Features eine Windows Forms <xref:System.Windows.Forms.DataGrid> erstellt haben, möchten Sie möglicherweise auch Elemente des <xref:System.Data.DataSet> Objekts des Rasters zur Laufzeit dynamisch ändern. Dies kann Änderungen an den einzelnen Werten der Tabelle oder die Änderung der Datenquelle, die an das <xref:System.Windows.Forms.DataGrid> Steuerelement gebunden ist, einschließen. Änderungen an einzelnen Werten werden über das <xref:System.Data.DataSet> Objekt, nicht über das <xref:System.Windows.Forms.DataGrid> Steuerelement durchgeführt.  
  
### <a name="to-change-data-programmatically"></a>So ändern Sie Daten Programm gesteuert  
  
1. Geben Sie die gewünschte Tabelle aus dem <xref:System.Data.DataSet> Objekt und die gewünschte Zeile und das gewünschte Feld aus der Tabelle an, und legen Sie die Zelle auf den neuen Wert fest.  
  
    > [!NOTE]
    > Um die erste Tabelle des <xref:System.Data.DataSet> oder die erste Zeile der Tabelle anzugeben, verwenden Sie 0.  
  
     Im folgenden Beispiel wird gezeigt, wie Sie den zweiten Eintrag der ersten Zeile der ersten Tabelle eines Datasets ändern, indem Sie auf `Button1`klicken. Die <xref:System.Data.DataSet> (`ds`) und die Tabellen (`0` und `1`) wurden bereits erstellt.  
  
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
  
     (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Zur Laufzeit können Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode verwenden, um das <xref:System.Windows.Forms.DataGrid> Steuerelement an eine andere Datenquelle zu binden. Beispielsweise können mehrere ADO.NET-Daten Steuerelemente vorhanden sein, die jeweils mit einer anderen Datenbank verbunden sind.  
  
### <a name="to-change-the-datasource-programmatically"></a>So ändern Sie die Datenquelle Programm gesteuert  
  
1. Legen Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode auf den Namen der Datenquelle und der Tabelle fest, an die die Bindung erfolgen soll.  
  
     Im folgenden Beispiel wird gezeigt, wie Sie die Datums Quelle mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode in ein ADO.NET Data-Steuerelement (adoPubsAuthors) ändern können, das mit der Autoren Tabelle in der pubs-Datenbank verbunden ist.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET-DataSets](../../data/adonet/ado-net-datasets.md)
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
