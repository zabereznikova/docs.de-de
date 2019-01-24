---
title: 'Vorgehensweise: Ändern der angezeigten Daten zur Laufzeit in das DataGrid-Steuerelement in Windows Forms'
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
ms.openlocfilehash: fc0fe47d728a196de81f7bf099e3a25ac2bb9211
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605564"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Vorgehensweise: Ändern der angezeigten Daten zur Laufzeit in das DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nach der Erstellung einer Windows Forms <xref:System.Windows.Forms.DataGrid> mit den Funktionen zur Entwurfszeit können Sie auch den Elemente dynamisch ändern der <xref:System.Data.DataSet> Objekt des Rasters zur Laufzeit. Dies kann Änderungen an der Tabelle entweder einzelne Werte einschließen, oder ändern die Datenquelle gebunden ist, um die <xref:System.Windows.Forms.DataGrid> Steuerelement. Änderungen an einzelnen Werten werden stets die <xref:System.Data.DataSet> -Objekt und nicht die <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
### <a name="to-change-data-programmatically"></a>Programmgesteuertes Ändern von Daten  
  
1.  Geben Sie die gewünschte Tabelle aus der <xref:System.Data.DataSet> Objekt und die gewünschte Zeile, und das Feld aus der Tabelle, und legen Sie die Zelle auf den neuen Wert.  
  
    > [!NOTE]
    >  Der ersten Tabelle des an den <xref:System.Data.DataSet> oder die erste Zeile der Tabelle, verwenden Sie 0.  
  
     Das folgende Beispiel zeigt, wie Sie durch Klicken auf den zweiten Eintrag in der ersten Zeile der ersten Tabelle eines Datasets zu ändern `Button1`. Die <xref:System.Data.DataSet> (`ds`) und Tabellen (`0` und `1`) waren zuvor erstellt haben.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Zur Laufzeit können Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode zum Binden der <xref:System.Windows.Forms.DataGrid> Steuerelement mit einer anderen Datenquelle. Angenommen, Sie verfügen möglicherweise über mehrere [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Datensteuerelementen, jeweils mit einer anderen Datenbank verbunden.  
  
### <a name="to-change-the-datasource-programmatically"></a>So ändern Sie die Datenquelle programmgesteuert  
  
1.  Legen Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode, um den Namen der Datenquelle und der Tabelle, die Sie binden möchten.  
  
     Das folgende Beispiel zeigt, wie Sie die Datenquelle mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode, um eine [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Datensteuerelement (adoPubsAuthors gebunden), die mit der Autorentabelle in der Pubs-Datenbank verbunden ist.  
  
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
- [ADO.NET-DataSets](../../../../docs/framework/data/adonet/ado-net-datasets.md)
- [Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Vorgehensweise: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
