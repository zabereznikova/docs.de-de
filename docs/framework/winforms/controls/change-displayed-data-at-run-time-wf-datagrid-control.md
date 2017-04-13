---
title: "Gewusst wie: &#196;ndern der angezeigten Daten im DataGrid-Steuerelement in Windows&#160;Forms zur Laufzeit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zellen, Ändern von DataGrid-Zellwerten"
  - "DataGrid-Steuerelement [Windows Forms], Datenbindung"
  - "DataGrid-Steuerelement [Windows Forms], Dynamisches Ändern zur Laufzeit"
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: &#196;ndern der angezeigten Daten im DataGrid-Steuerelement in Windows&#160;Forms zur Laufzeit
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nachdem Sie mithilfe der Entwurfszeitfeatures ein Windows Forms <xref:System.Windows.Forms.DataGrid> erstellt haben, können Sie Elemente des <xref:System.Data.DataSet>\-Objekts des Datenblatts auch dynamisch zur Laufzeit ändern.  Dies können Änderungen an einzelnen Werten der Tabelle oder Änderungen der an das <xref:System.Windows.Forms.DataGrid>\-Steuerelement gebundenen Datenquelle sein.  Änderungen an einzelnen Werten werden nicht mithilfe des <xref:System.Windows.Forms.DataGrid>\-Steuerelements, sondern mithilfe des <xref:System.Data.DataSet>\-Objekts ausgeführt.  
  
### So ändern Sie Daten programmgesteuert  
  
1.  Legen Sie im <xref:System.Data.DataSet>\-Objekt die gewünschte Tabelle sowie die gewünschte Zeile und das Feld der Tabelle fest, und gleichen Sie die Zelle mit dem neuen Wert ab.  
  
    > [!NOTE]
    >  Verwenden Sie zur Festlegung der ersten Tabelle von <xref:System.Data.DataSet> bzw. der ersten Zeile der Tabelle den Wert 0.  
  
     Im folgenden Beispiel wird gezeigt, wie in der ersten Tabelle eines Datasets der zweite Eintrag der ersten Zeile durch Klicken auf `Button1` geändert wird.  <xref:System.Data.DataSet> \(`ds`\) und die Tabellen \(`0`  und `1`\) wurden vorher erstellt.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Zur Laufzeit können Sie das <xref:System.Windows.Forms.DataGrid>\-Steuerelement mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode an eine andere Datenquelle binden.  Möglicherweise verfügen Sie über mehrere [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]\-Datensteuerelemente, die jeweils mit einer anderen Datenbank verbunden sind.  
  
### So ändern Sie die Datenquelle programmgesteuert  
  
1.  Legen Sie für die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode den Namen der Datenquelle und der Tabelle fest, mit der die Bindung hergestellt werden soll.  
  
     Im folgenden Beispiel wird gezeigt, wie die Datenquelle mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode an ein [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]\-Datensteuerelement \(adoPubsAuthors\) gebunden wird, das mit der Tabelle Authors in der Datenbank Pubs verbunden ist.  
  
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
  
## Siehe auch  
 [ADO.NET\-DataSets](../../../../docs/framework/data/adonet/ado-net-datasets.md)   
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Gewusst wie: Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)