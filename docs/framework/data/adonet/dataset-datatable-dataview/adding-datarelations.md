---
title: Hinzufügen von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202382"
---
# <a name="adding-datarelations"></a>Hinzufügen von "DataRelations"

In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.  
  
 Die Argumente, die zum Erstellen einer **DataRelations** erforderlich sind, sind ein Name für die zu **erstellende DataRelations** und ein Array mit einem oder mehreren <xref:System.Data.DataColumn> verweisen auf die Spalten, die als übergeordnete und untergeordnete Spalten in der Beziehung fungieren. Nachdem Sie eine **DataRelations**erstellt haben, können Sie Sie zum Navigieren zwischen den Tabellen und zum Abrufen von Werten verwenden.  
  
 Beim Hinzufügen einer **DataRelations** zu einer wird der über <xref:System.Data.DataSet> geordneten Tabelle standardmäßig ein hinzugefügt <xref:System.Data.UniqueConstraint> <xref:System.Data.ForeignKeyConstraint> . Weitere Informationen zu diesen Standard Einschränkungen finden Sie unter [databel-Einschränkungen](datatable-constraints.md).  
  
 Im folgenden Codebeispiel wird eine **DataRelations** mithilfe von zwei- <xref:System.Data.DataTable> Objekten in einem erstellt <xref:System.Data.DataSet> . Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen " **CustId**", die als Link zwischen den beiden <xref:System.Data.DataTable> Objekten dient. Im Beispiel wird der **Beziehungs** Auflistung von eine einzelne **DataRelations** hinzugefügt <xref:System.Data.DataSet> . Das erste Argument im Beispiel gibt den Namen der zu **erstellenden DataRelations** an. Mit dem zweiten Argument wird die übergeordnete **datacolumschlag** festgelegt, und das dritte Argument legt die untergeordnete **datacolumschlag**fest.  
  
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
  
 Eine **DataRelations** verfügt auch über eine geschachtelte **Eigenschaft,** die bei Festlegung auf **true**bewirkt, dass die Zeilen aus der untergeordneten Tabelle in der zugeordneten Zeile aus der übergeordneten Tabelle geschachtelt werden, wenn Sie mithilfe von als XML-Elemente geschrieben werden <xref:System.Data.DataSet.WriteXml%2A> . Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Weitere Informationen

- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
