---
title: "Hinzufügen von \"DataRelations\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4650ccc5324489fb5c577cf2542ae95e1904441a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="adding-datarelations"></a>Hinzufügen von "DataRelations"
In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.  
  
 Die Argumente erforderlich sind, erstellen eine **DataRelation** sind ein Name für die **DataRelation** erstellt wird, und ein Array aus einem oder mehreren <xref:System.Data.DataColumn> Verweise auf die Spalten, die als die über- und untergeordneten dienen Spalten in der Beziehung. Nach der Erstellung einer **DataRelation**, können Sie sie zwischen den Tabellen navigieren und Werte abrufen.  
  
 Hinzufügen einer **DataRelation** auf eine <xref:System.Data.DataSet> hinzufügt, wird standardmäßig ein <xref:System.Data.UniqueConstraint> mit der übergeordneten Tabelle und eine <xref:System.Data.ForeignKeyConstraint> zur untergeordneten Tabelle. Weitere Informationen zu diesen Default-Einschränkungen, finden Sie unter [DataTable-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Das folgende Codebeispiel erstellt eine **DataRelation** unter Verwendung zweier <xref:System.Data.DataTable> Objekte in einem <xref:System.Data.DataSet>. Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen **CustID**, dem dient als Link zwischen den beiden <xref:System.Data.DataTable> Objekte. Im Beispiel wird eine einzelne **DataRelation** auf die **Beziehungen** Auflistung von der <xref:System.Data.DataSet>. Das erste Argument im Beispiel gibt den Namen des der **DataRelation** erstellt wird. Das zweite Argument legt die übergeordnete **DataColumn** und das dritte Argument die untergeordnete **DataColumn**.  
  
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
  
 Ein **DataRelation** verfügt auch über eine **geschachtelte** Eigenschaft, die bei Festlegung auf **"true"**, bewirkt, dass die Zeilen aus der untergeordneten Tabelle in die entsprechenden Zeilen aus der übergeordneten Tabelle geschachtelt werden sollen Wenn als XML-Elemente geschrieben <xref:System.Data.DataSet.WriteXml%2A> . Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
