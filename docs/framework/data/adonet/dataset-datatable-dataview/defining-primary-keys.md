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
# <a name="defining-primary-keys"></a><span data-ttu-id="1cc4e-102">Definieren von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="1cc4e-102">Defining Primary Keys</span></span>
<span data-ttu-id="1cc4e-103">Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="1cc4e-104">Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="1cc4e-105">Wenn Sie eine <xref:System.Data.DataColumn> Single <xref:System.Data.DataTable.PrimaryKey%2A> als <xref:System.Data.DataTable>für eine identifizieren, legt die Tabelle <xref:System.Data.DataColumn.AllowDBNull%2A> die Eigenschaft der Spalte automatisch auf **false** und die <xref:System.Data.DataColumn.Unique%2A> Eigenschaft auf **true**fest.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="1cc4e-106">Bei mehrspaltigen Primärschlüsseln wird nur die **AllowDBNull-Eigenschaft** automatisch auf **false**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="1cc4e-107">Die **PrimaryKey-Eigenschaft** eines <xref:System.Data.DataTable> empfängt als Wert ein Array eines oder mehrerer **DataColumn-Objekte,** wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="1cc4e-108">Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="1cc4e-109">	Im folgenden Beispiel werden zwei Spalten als Primärschlüssel definiert.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1cc4e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cc4e-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="1cc4e-111">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="1cc4e-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="1cc4e-112">"DataTables"</span><span class="sxs-lookup"><span data-stu-id="1cc4e-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="1cc4e-113">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1cc4e-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
