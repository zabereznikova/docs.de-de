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
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="41aa8-102">Erstellen von AutoIncrement-Spalten</span><span class="sxs-lookup"><span data-stu-id="41aa8-102">Creating AutoIncrement Columns</span></span>

<span data-ttu-id="41aa8-103">Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="41aa8-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="41aa8-104">Um eine automatische Inkrementierung zu erstellen <xref:System.Data.DataColumn> , legen <xref:System.Data.DataColumn.AutoIncrement%2A> Sie die-Eigenschaft der Spalte auf **true**fest.</span><span class="sxs-lookup"><span data-stu-id="41aa8-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="41aa8-105">Der <xref:System.Data.DataColumn> beginnt dann mit dem Wert, der in der- <xref:System.Data.DataColumn.AutoIncrementSeed%2A> Eigenschaft definiert ist, und mit jeder hinzugefügten Zeile wird der Wert der **AutoIncrement** -Spalte um den in der- <xref:System.Data.DataColumn.AutoIncrementStep%2A> Eigenschaft der Spalte definierten Wert vergrößert.</span><span class="sxs-lookup"><span data-stu-id="41aa8-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="41aa8-106">Für **AutoIncrement** -Spalten wird empfohlen, dass die- <xref:System.Data.DataColumn.ReadOnly%2A> Eigenschaft der **datacolenn** auf **true**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="41aa8-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="41aa8-107">Im folgenden Beispiel wird veranschaulicht, wie eine Spalte erstellt wird, die mit dem Wert 200 beginnt und deren Werte inkrementell jeweils um 3 erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="41aa8-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="41aa8-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41aa8-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="41aa8-109">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="41aa8-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="41aa8-110">"DataTables"</span><span class="sxs-lookup"><span data-stu-id="41aa8-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="41aa8-111">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="41aa8-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
