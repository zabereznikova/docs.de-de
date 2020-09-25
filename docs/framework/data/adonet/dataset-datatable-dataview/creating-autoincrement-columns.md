---
title: Erstellen von AutoIncrement-Spalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9a979f39003e60c70c03206bd886bdd6827c82e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203721"
---
# <a name="creating-autoincrement-columns"></a>Erstellen von AutoIncrement-Spalten

Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden. Um eine automatische Inkrementierung zu erstellen <xref:System.Data.DataColumn> , legen <xref:System.Data.DataColumn.AutoIncrement%2A> Sie die-Eigenschaft der Spalte auf **true**fest. Der <xref:System.Data.DataColumn> beginnt dann mit dem Wert, der in der- <xref:System.Data.DataColumn.AutoIncrementSeed%2A> Eigenschaft definiert ist, und mit jeder hinzugefügten Zeile wird der Wert der **AutoIncrement** -Spalte um den in der- <xref:System.Data.DataColumn.AutoIncrementStep%2A> Eigenschaft der Spalte definierten Wert vergrößert.  
  
 Für **AutoIncrement** -Spalten wird empfohlen, dass die- <xref:System.Data.DataColumn.ReadOnly%2A> Eigenschaft der **datacolenn** auf **true**festgelegt ist.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataColumn>
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- ["DataTables"](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
