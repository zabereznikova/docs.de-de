---
title: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement
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
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730981"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Gewusst wie: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms
> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Wenn die <xref:System.Data.DataSet> eine Reihe verknüpfter Tabellen enthält, können Sie zwei <xref:System.Windows.Forms.DataGrid>-Steuerelemente verwenden, um die Daten im Master-/Detail-Format anzuzeigen. Eine <xref:System.Windows.Forms.DataGrid> die als Haupt Raster festgelegt ist, und die zweite ist als das Detail Raster festgelegt. Wenn Sie in der Liste Master einen Eintrag auswählen, werden alle zugehörigen untergeordneten Einträge in der Detail Liste angezeigt. Wenn Ihr <xref:System.Data.DataSet> z. b. eine Customers-Tabelle und eine zugehörige Orders-Tabelle enthält, geben Sie die Customers-Tabelle als Haupt Raster und die Orders-Tabelle als Detail Raster an. Wenn ein Kunde aus dem Haupt Raster ausgewählt wird, werden alle Bestellungen, die diesem Kunden in der Tabelle Orders zugeordnet sind, im Detail Raster angezeigt.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>So legen Sie eine Master/Detail-Beziehung Programm gesteuert fest  
  
1. Erstellen Sie zwei neue <xref:System.Windows.Forms.DataGrid> Steuerelemente, und legen Sie deren Eigenschaften fest.  
  
2. Fügen Sie dem Dataset Tabellen hinzu.  
  
3. Deklarieren Sie eine Variable vom Typ <xref:System.Data.DataRelation>, um die Beziehung darzustellen, die Sie erstellen möchten.  
  
4. Instanziieren Sie die Beziehung, indem Sie einen Namen für die Beziehung angeben und die Tabelle, die Spalte und das Element angeben, mit denen die beiden Tabellen verknüpft werden.  
  
5. Fügen Sie die Beziehung zur <xref:System.Data.DataSet.Relations%2A> Auflistung des <xref:System.Data.DataSet> Objekts hinzu.  
  
6. Verwenden Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode des <xref:System.Windows.Forms.DataGrid>, um die einzelnen Raster an die <xref:System.Data.DataSet>zu binden.  
  
     Im folgenden Beispiel wird gezeigt, wie eine Master/Detail-Beziehung zwischen den Tabellen Customers und Orders in einem zuvor generierten <xref:System.Data.DataSet> (`ds`) festgelegt wird.  
  
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

- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Übersicht über das DataGrid-Steuerelement](datagrid-control-overview-windows-forms.md)
- [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
