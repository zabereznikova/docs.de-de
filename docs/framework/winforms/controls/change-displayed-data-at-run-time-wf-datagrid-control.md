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
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nachdem Sie ein Windows <xref:System.Windows.Forms.DataGrid> Forms mit den Entwurfszeitfeatures erstellt haben, können <xref:System.Data.DataSet> Sie auch Elemente des Objekts des Rasters zur Laufzeit dynamisch ändern. Dies kann Änderungen an einzelnen Werten der Tabelle oder das <xref:System.Windows.Forms.DataGrid> Ändern der Datenquelle, die an das Steuerelement gebunden ist, umfassen. Änderungen an einzelnen Werten <xref:System.Data.DataSet> werden über <xref:System.Windows.Forms.DataGrid> das Objekt und nicht über das Steuerelement vorgenommen.  
  
### <a name="to-change-data-programmatically"></a>So ändern Sie Daten programmgesteuert  
  
1. Geben Sie die <xref:System.Data.DataSet> gewünschte Tabelle aus dem Objekt und die gewünschte Zeile und das gewünschte Feld aus der Tabelle an, und legen Sie die Zelle gleich dem neuen Wert fest.  
  
    > [!NOTE]
    > Um die erste Tabelle <xref:System.Data.DataSet> der oder der ersten Zeile der Tabelle anzugeben, verwenden Sie 0.  
  
     Das folgende Beispiel zeigt, wie Sie den zweiten Eintrag der ersten Zeile `Button1`der ersten Tabelle eines Datasets ändern, indem Sie auf klicken. Die <xref:System.Data.DataSet> `ds`( )`0` und `1`Tabellen ( und ) wurden zuvor erstellt.  
  
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
  
     (Visual C, Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Zur Laufzeit können Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die Methode <xref:System.Windows.Forms.DataGrid> verwenden, um das Steuerelement an eine andere Datenquelle zu binden. Sie verfügen z. B. über mehrere ADO.NET Datensteuerelemente, die jeweils mit einer anderen Datenbank verbunden sind.  
  
### <a name="to-change-the-datasource-programmatically"></a>So ändern Sie DataSource programmgesteuert  
  
1. Legen <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Sie die Methode auf den Namen der Datenquelle und Tabelle fest, an die Sie binden möchten.  
  
     Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die Datumsquelle mithilfe der Methode in ein ADO.NET Datensteuerelement (adoPubsAuthors) ändern, das mit der Tabelle Authors in der Pubs-Datenbank verbunden ist.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [ADO.NET-DataSets](../../data/adonet/ado-net-datasets.md)
- [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
