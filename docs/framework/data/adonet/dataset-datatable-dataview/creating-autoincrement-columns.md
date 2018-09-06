---
title: Erstellen von AutoIncrement-Spalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9c6b5393e1928828bca001ba1d2336f09e64c22c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776945"
---
# <a name="creating-autoincrement-columns"></a>Erstellen von AutoIncrement-Spalten
Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden. Zum Erstellen einer automatisch inkrementierten <xref:System.Data.DataColumn>legen die <xref:System.Data.DataColumn.AutoIncrement%2A> Eigenschaft der Spalte, die **"true"**. Die <xref:System.Data.DataColumn> startet dann mit dem Wert im definierten die <xref:System.Data.DataColumn.AutoIncrementSeed%2A> -Eigenschaft, und mit jeder hinzugefügten Zeile den Wert des der **AutoIncrement** Spalte erhöht wird, um den Wert, der definiert, der <xref:System.Data.DataColumn.AutoIncrementStep%2A> -Eigenschaft der Spalte.  
  
 Für **AutoIncrement** -Spalten wird empfohlen, die die <xref:System.Data.DataColumn.ReadOnly%2A> Eigenschaft der **DataColumn** festgelegt werden, um **"true"**.  
  
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
 <xref:System.Data.DataColumn>  
 [DataTable-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
