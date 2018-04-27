---
title: 'Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ea90c3532203a61beded5eceeee5cf535a74b87b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nach der Erstellung einer Windows Forms <xref:System.Windows.Forms.DataGrid> mit den Funktionen zur Entwurfszeit können Sie möglicherweise auch dynamisch Elemente ändern möchten die <xref:System.Data.DataSet> Objekt des Rasters zur Laufzeit. Dazu kann Änderungen an der Tabelle entweder einzelne Werte oder ändern die Datenquelle gebunden ist, um die <xref:System.Windows.Forms.DataGrid> Steuerelement. Änderungen an einzelnen Werte erfolgen über die <xref:System.Data.DataSet> -Objekt und nicht die <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
### <a name="to-change-data-programmatically"></a>Programmgesteuertes Ändern von Daten  
  
1.  Geben Sie die gewünschte Tabelle aus der <xref:System.Data.DataSet> Objekt und die gewünschte Zeile und Feld aus der Tabelle, und legen Sie die Zelle auf den neuen Wert.  
  
    > [!NOTE]
    >  Die erste Tabelle der an die <xref:System.Data.DataSet> oder die erste Zeile der Tabelle, verwenden Sie 0.  
  
     Das folgende Beispiel zeigt, wie den zweiten Eintrag der ersten Zeile der ersten Tabelle eines Datasets ändern, indem Sie auf `Button1`. Die <xref:System.Data.DataSet> (`ds`) und Tabellen (`0` und `1`) wurden zuvor erstellt haben.  
  
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
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
     Im folgende Beispiel wird gezeigt, wie so ändern Sie die Datenquelle mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode, um eine [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Datensteuerelement (adoPubsAuthors gebunden), die mit der Tabelle "Authors" in der Pubs-Datenbank verbunden ist.  
  
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
 [ADO.NET-DataSets](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
