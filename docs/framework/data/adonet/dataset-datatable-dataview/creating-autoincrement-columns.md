---
title: Erstellen von AutoIncrement-Spalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205133"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="1ec32-102">Erstellen von AutoIncrement-Spalten</span><span class="sxs-lookup"><span data-stu-id="1ec32-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="1ec32-103">Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1ec32-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="1ec32-104">Um eine automatische Inkrementierung <xref:System.Data.DataColumn>zu erstellen, legen Sie die <xref:System.Data.DataColumn.AutoIncrement%2A> -Eigenschaft der Spalte auf **true**fest.</span><span class="sxs-lookup"><span data-stu-id="1ec32-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="1ec32-105">Der <xref:System.Data.DataColumn> beginnt dann mit dem Wert, der in <xref:System.Data.DataColumn.AutoIncrementSeed%2A> der-Eigenschaft definiert ist, und mit jeder hinzugefügten Zeile wird der Wert der **AutoIncrement** -Spalte <xref:System.Data.DataColumn.AutoIncrementStep%2A> um den in der-Eigenschaft der Spalte definierten Wert vergrößert.</span><span class="sxs-lookup"><span data-stu-id="1ec32-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="1ec32-106">Für **AutoIncrement** -Spalten wird empfohlen, dass <xref:System.Data.DataColumn.ReadOnly%2A> die-Eigenschaft der **datacolenn** auf **true**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1ec32-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="1ec32-107">Im folgenden Beispiel wird veranschaulicht, wie eine Spalte erstellt wird, die mit dem Wert 200 beginnt und deren Werte inkrementell jeweils um 3 erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="1ec32-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ec32-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ec32-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="1ec32-109">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="1ec32-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="1ec32-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="1ec32-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="1ec32-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1ec32-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
