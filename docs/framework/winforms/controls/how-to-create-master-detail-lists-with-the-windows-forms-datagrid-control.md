---
title: "Gewusst wie: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "DataGrid-Steuerelement [Windows Forms], Master/Detail-Listen"
  - "Master/Detail-Listen"
  - "Verknüpfte Tabellen, Anzeigen in DataGrid-Steuerelementen"
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows&#160;Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Wenn das <xref:System.Data.DataSet> mehrere verwandte Tabellen enthält, können Sie die Daten mit zwei <xref:System.Windows.Forms.DataGrid>\-Steuerelementen im Master\/Detail\-Format anzeigen.  Ein <xref:System.Windows.Forms.DataGrid> wird als Masterraster, das andere als Detailraster festgelegt.  Wenn Sie einen Eintrag in der Masterliste auswählen, werden auch alle zugehörigen Einträge in der Detailliste angezeigt.  Wenn <xref:System.Data.DataSet> beispielsweise die Tabelle Customers enthält, der eine Tabelle Orders zugeordnet ist, können Sie die Tabelle Customers als Masterraster und die Tabelle Orders als Detailraster festlegen.  Wenn ein Kunde aus dem Masterraster ausgewählt wurde, werden alle diesem Kunden zugeordneten Bestellungen in der Tabelle **Bestellungen** im Detailraster angezeigt.  
  
### So richten Sie programmgesteuert eine Master\/Detail\-Beziehung ein  
  
1.  Erstellen Sie zwei neue <xref:System.Windows.Forms.DataGrid>\-Steuerelemente, und legen Sie deren Eigenschaften fest.  
  
2.  Fügen Sie dem Dataset Tabellen hinzu.  
  
3.  Deklarieren Sie zur Darstellung der gewünschten Beziehung eine Variable des Typs <xref:System.Data.DataRelation>.  
  
4.  Instanziieren Sie die Beziehung, indem Sie einen Namen für die Beziehung eingeben und die Tabelle, die Spalte sowie das Element festlegen, die bzw. das beide Tabellen verbindet.  
  
5.  Fügen Sie die Beziehung zur <xref:System.Data.DataSet.Relations%2A>\-Auflistung des <xref:System.Data.DataSet>\-Objekts hinzu.  
  
6.  Binden Sie mithilfe der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\-Methode des <xref:System.Windows.Forms.DataGrid> jedes der Raster an das <xref:System.Data.DataSet>.  
  
     Im folgenden Beispiel wird gezeigt, wie in einem zuvor generierten <xref:System.Data.DataSet> \(`ds`\) zwischen den Tabellen Customers und Orders eine Master\/Detail\-Beziehung festgelegt wird.  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## Siehe auch  
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Übersicht über das DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Gewusst wie: Binden des DataGrid\-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)