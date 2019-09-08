---
title: Erstellen von AutoIncrement-Spalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786456"
---
# <a name="creating-autoincrement-columns"></a>Erstellen von AutoIncrement-Spalten
Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden. Um eine automatische Inkrementierung <xref:System.Data.DataColumn>zu erstellen, legen Sie die <xref:System.Data.DataColumn.AutoIncrement%2A> -Eigenschaft der Spalte auf **true**fest. Der <xref:System.Data.DataColumn> beginnt dann mit dem Wert, der in <xref:System.Data.DataColumn.AutoIncrementSeed%2A> der-Eigenschaft definiert ist, und mit jeder hinzugefügten Zeile wird der Wert der **AutoIncrement** -Spalte <xref:System.Data.DataColumn.AutoIncrementStep%2A> um den in der-Eigenschaft der Spalte definierten Wert vergrößert.  
  
 Für **AutoIncrement** -Spalten wird empfohlen, dass <xref:System.Data.DataColumn.ReadOnly%2A> die-Eigenschaft der **datacolenn** auf **true**festgelegt ist.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Spalte erstellt wird, die mit dem Wert 200 beginnt und deren Werte inkrementell jeweils um 3 erhöht werden.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataColumn>
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
