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
ms.openlocfilehash: c7bf70a67729744f4cf96318f6b270a5ea81b812
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917724"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Vorgehensweise: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nachdem Sie mithilfe der Entwurfszeit <xref:System.Windows.Forms.DataGrid> Features eine Windows Forms erstellt haben, möchten Sie möglicherweise auch die Elemente <xref:System.Data.DataSet> des Rasters zur Laufzeit dynamisch ändern. Dies kann entweder Änderungen an den einzelnen Werten der Tabelle oder an der Änderung der Datenquelle, die an <xref:System.Windows.Forms.DataGrid> das Steuerelement gebunden ist, enthalten. Änderungen an einzelnen Werten werden über das <xref:System.Data.DataSet> -Objekt, nicht über das <xref:System.Windows.Forms.DataGrid> -Steuerelement durchgeführt.  
  
### <a name="to-change-data-programmatically"></a>So ändern Sie Daten Programm gesteuert  
  
1. Geben Sie die gewünschte Tabelle aus <xref:System.Data.DataSet> dem-Objekt und die gewünschte Zeile und das gewünschte Feld aus der Tabelle an, und legen Sie die Zelle auf den neuen Wert fest.  
  
    > [!NOTE]
    > Um die erste Tabelle von <xref:System.Data.DataSet> oder der ersten Zeile der Tabelle anzugeben, verwenden Sie 0.  
  
     Im folgenden Beispiel wird gezeigt, wie der zweite Eintrag der ersten Zeile der ersten Tabelle eines Datasets durch Klicken `Button1`auf geändert wird. Die <xref:System.Data.DataSet> (`ds`)-Tabelle und`0` die `1`-Tabelle (und) wurden zuvor erstellt.  
  
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
  
     Zur Laufzeit können Sie die- <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode verwenden, um das <xref:System.Windows.Forms.DataGrid> Steuerelement an eine andere Datenquelle zu binden. Beispielsweise können mehrere ADO.NET-Daten Steuerelemente vorhanden sein, die jeweils mit einer anderen Datenbank verbunden sind.  
  
### <a name="to-change-the-datasource-programmatically"></a>So ändern Sie die Datenquelle Programm gesteuert  
  
1. Legen Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die-Methode auf den Namen der Datenquelle und der Tabelle fest, an die die Bindung erfolgen soll.  
  
     Im folgenden Beispiel wird gezeigt, wie Sie die Datums Quelle mithilfe <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> der-Methode in ein ADO.NET Data-Steuerelement (adoPubsAuthors) ändern können, das mit der authors-Tabelle in der pubs-Datenbank verbunden ist.  
  
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
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im Windows Forms DataGrid-Steuerelement](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum Windows Forms DataGrid-Steuerelement](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Vorgehensweise: Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
