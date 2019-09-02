---
title: Hinzufügen von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: fde1e2ace09e31234d199876ae7f063e01e7a7e4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203981"
---
# <a name="adding-datarelations"></a>Hinzufügen von "DataRelations"
In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.  
  
 Die Argumente, die zum Erstellen einer **DataRelations** erforderlich sind, sind ein Name für die zu erstellende **DataRelations** und ein <xref:System.Data.DataColumn> Array mit einem oder mehreren verweisen auf die Spalten, die als übergeordnete und untergeordnete Spalten in der Beziehung fungieren. Nachdem Sie eine **DataRelations**erstellt haben, können Sie Sie zum Navigieren zwischen den Tabellen und zum Abrufen von Werten verwenden.  
  
 Beim Hinzufügen einer **DataRelations** zu einer <xref:System.Data.DataSet> wird der übergeordneten <xref:System.Data.UniqueConstraint> Tabelle <xref:System.Data.ForeignKeyConstraint> standardmäßig ein hinzugefügt. Weitere Informationen zu diesen Standard Einschränkungen finden Sie unter [databel-Einschränkungen](datatable-constraints.md).  
  
 Im folgenden Codebeispiel wird eine **DataRelations** mithilfe von <xref:System.Data.DataTable> zwei-Objekten <xref:System.Data.DataSet>in einem erstellt. Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen " **CustId**", die als Link zwischen <xref:System.Data.DataTable> den beiden Objekten dient. Im Beispiel wird der **Beziehungs** Auflistung von <xref:System.Data.DataSet>eine einzelne **DataRelations** hinzugefügt. Das erste Argument im Beispiel gibt den Namen der zu erstellenden **DataRelations** an. Mit dem zweiten Argument wird die übergeordnete **datacolumschlag** festgelegt, und das dritte Argument legt die untergeordnete **datacolumschlag**fest.  
  
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
  
 Eine **DataRelations** verfügt auch über eine geschachtelte Eigenschaft, die bei Festlegung auf **true**bewirkt, dass die Zeilen aus der untergeordneten Tabelle in der zugeordneten Zeile aus der übergeordneten Tabelle geschachtelt <xref:System.Data.DataSet.WriteXml%2A> werden, wenn Sie mithilfe von als XML-Elemente geschrieben werden. Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Siehe auch

- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
