---
title: 'Vorgehensweise: Erstellen von Master / Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63cb647e2ed6dcbc97fab15db3166b55c52f635a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Gewusst wie: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Wenn Ihre <xref:System.Data.DataSet> enthält eine Reihe verknüpfter Tabellen können Sie mithilfe von zwei <xref:System.Windows.Forms.DataGrid> Steuerelemente zum Anzeigen der Daten in einem Master/Detail-Format. Eine <xref:System.Windows.Forms.DataGrid> festgelegt wurde, werden die master-Raster, und die zweite ist vorgesehen, um das Raster Aktivitätsdetails werden. Wenn Sie einen Eintrag in der master-Liste auswählen, werden alle zugehörigen untergeordneten Einträge in der Detailliste angezeigt. Beispielsweise, wenn Ihre <xref:System.Data.DataSet> enthält eine Kundentabelle und einer verknüpften Tabelle der Aufträge, würden Sie angeben, der Customers-Tabelle der master-Raster sein und die Tabelle Orders, um das Raster Aktivitätsdetails werden. Wenn ein Kunde aus der master-Raster ausgewählt ist, würden alle Bestellungen dieses Kunden in der Tabelle Orders zugeordnet im Detailraster angezeigt.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>So legen Sie eine Master/Detail-Beziehung programmgesteuert fest  
  
1.  Erstellen Sie zwei neue <xref:System.Windows.Forms.DataGrid> -Steuerelemente sowie deren Eigenschaften festlegen.  
  
2.  Fügen Sie dem DataSet Tabellen hinzu.  
  
3.  Deklarieren Sie eine Variable vom Typ <xref:System.Data.DataRelation> zur Darstellung der Beziehungs, erstellt werden soll.  
  
4.  Instanziieren Sie die Beziehung durch Angabe eines Namens für die Beziehung und angeben, die Tabellen-, Spalten- und Element, das die beiden Tabellen verbunden wird.  
  
5.  Fügen Sie die Beziehung zu den <xref:System.Data.DataSet> des Objekts <xref:System.Data.DataSet.Relations%2A> Auflistung.  
  
6.  Verwenden der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode der <xref:System.Windows.Forms.DataGrid> jedes der Raster zum Binden der <xref:System.Data.DataSet>.  
  
     Im folgende Beispiel wird gezeigt, wie eine Master/Detail-Beziehung zwischen den Tabellen Customers und Orders in einer zuvor generierten festzulegende <xref:System.Data.DataSet> (`ds`).  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Übersicht über das DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
