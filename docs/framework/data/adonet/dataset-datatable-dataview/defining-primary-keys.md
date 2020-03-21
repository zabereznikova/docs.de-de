---
title: Definieren von Primärschlüsseln
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 159b23eb4ef5ca38ebce6e488080d315ec3be081
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151181"
---
# <a name="defining-primary-keys"></a>Definieren von Primärschlüsseln
Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert. Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.  
  
 Wenn Sie eine <xref:System.Data.DataColumn> Single <xref:System.Data.DataTable.PrimaryKey%2A> als <xref:System.Data.DataTable>für eine identifizieren, legt die Tabelle <xref:System.Data.DataColumn.AllowDBNull%2A> die Eigenschaft der Spalte automatisch auf **false** und die <xref:System.Data.DataColumn.Unique%2A> Eigenschaft auf **true**fest. Bei mehrspaltigen Primärschlüsseln wird nur die **AllowDBNull-Eigenschaft** automatisch auf **false**festgelegt.  
  
 Die **PrimaryKey-Eigenschaft** eines <xref:System.Data.DataTable> empfängt als Wert ein Array eines oder mehrerer **DataColumn-Objekte,** wie in den folgenden Beispielen gezeigt. Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 	Im folgenden Beispiel werden zwei Spalten als Primärschlüssel definiert.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataTable>
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- ["DataTables"](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
