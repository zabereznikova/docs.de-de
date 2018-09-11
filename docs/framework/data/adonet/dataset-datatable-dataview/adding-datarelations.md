---
title: Hinzufügen von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: d0f481979ead7af775d462a2624ec43080e2c5a9
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365488"
---
# <a name="adding-datarelations"></a>Hinzufügen von "DataRelations"
In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.  
  
 Die Argumente, die zum Erstellen einer **DataRelation** sind ein Name für die **DataRelation** erstellt wird und ein Array von einem oder mehreren <xref:System.Data.DataColumn> Verweise auf die Spalten, die als den übergeordneten und untergeordneten dienen die Spalten in der Beziehung. Nach der Erstellung einer **DataRelation**, können Sie sie zwischen den Tabellen navigieren und die Werte abzurufen.  
  
 Hinzufügen einer **DataRelation** auf eine <xref:System.Data.DataSet> hinzugefügt wird, wird standardmäßig ein <xref:System.Data.UniqueConstraint> mit der übergeordneten Tabelle und eine <xref:System.Data.ForeignKeyConstraint> zur untergeordneten Tabelle. Weitere Informationen zu diesen standardeinschränkungen finden Sie unter [DataTable-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Das folgende Codebeispiel erstellt eine **DataRelation** unter Verwendung zweier <xref:System.Data.DataTable> Objekte in einer <xref:System.Data.DataSet>. Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen **CustID**, der als einen Link zwischen den beiden dient <xref:System.Data.DataTable> Objekte. Im Beispiel wird eine einzelne **DataRelation** auf die **Beziehungen** Auflistung von der <xref:System.Data.DataSet>. Das erste Argument im Beispiel gibt den Namen des der **DataRelation** erstellt wird. Das zweite Argument legt die übergeordnete **DataColumn** und das dritte Argument legt fest, das untergeordnete Element **DataColumn**.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 Ein **DataRelation** verfügt auch über eine **geschachtelte** Eigenschaft, die bei Festlegung auf **"true"**, werden die Zeilen der untergeordneten Tabelle, in die entsprechenden Zeilen aus der übergeordneten Tabelle geschachtelt werden. Beim Schreiben als XML-Elemente mit <xref:System.Data.DataSet.WriteXml%2A> . Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
