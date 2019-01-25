---
title: 'Vorgehensweise: Erstellen von Master / Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 6ff13264709c4557d698435ac05b7759be58f1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712891"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Vorgehensweise: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Wenn Ihre <xref:System.Data.DataSet> enthält eine Reihe verknüpfter Tabellen, können Sie mithilfe von zwei <xref:System.Windows.Forms.DataGrid> Steuerelemente zum Anzeigen der Daten in einem Master/Detail-Format. Eine <xref:System.Windows.Forms.DataGrid> als master-Raster, festgelegt und die Sekunde als das Raster festgelegt. Wenn Sie einen Eintrag in der master-Liste auswählen, werden alle zugehörigen untergeordneten Einträge in der Liste angezeigt. Beispielsweise wenn Ihre <xref:System.Data.DataSet> enthält eine Kundentabelle und einer verknüpften Tabelle Orders würden Sie angeben, der Customers-Tabelle der master-Raster sein und die Tabelle Orders, das Detailraster sein. Wenn ein Kunde aus der master-Raster ausgewählt ist, würden alle Bestellungen dieses Kunden in der Orders-Tabelle zugeordnet im Raster angezeigt werden.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>So legen Sie eine Master-/detailbeziehung programmgesteuert fest  
  
1.  Erstellen Sie zwei neue <xref:System.Windows.Forms.DataGrid> steuert und deren Eigenschaften festlegen.  
  
2.  Hinzufügen von Tabellen für das Dataset.  
  
3.  Deklarieren Sie eine Variable vom Typ <xref:System.Data.DataRelation> Beziehung darstellen, erstellt werden soll.  
  
4.  Instanziieren Sie die Beziehung, indem Sie einen Namen für die Beziehung und Angeben der Tabellen-, Spalten- und Element, das die zwei Tabellen verknüpft werden.  
  
5.  Fügen Sie die Beziehung zu den <xref:System.Data.DataSet> des Objekts <xref:System.Data.DataSet.Relations%2A> Auflistung.  
  
6.  Verwenden der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode der <xref:System.Windows.Forms.DataGrid> jedes der Raster zum Binden der <xref:System.Data.DataSet>.  
  
     Das folgende Beispiel zeigt, wie Sie eine Master/Detail-Beziehung zwischen den Tabellen Customers und Orders in einer zuvor generierten festlegen <xref:System.Data.DataSet> (`ds`).  
  
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
- [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Übersicht über das DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
