---
title: Erstellen von AutoIncrement-Spalten
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
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0cef5944db5e926a4b2d81fd226abc9691b6d1bc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="9319b-102">Erstellen von AutoIncrement-Spalten</span><span class="sxs-lookup"><span data-stu-id="9319b-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="9319b-103">Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9319b-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="9319b-104">Zum Erstellen einer automatisch inkrementierten <xref:System.Data.DataColumn>legen die <xref:System.Data.DataColumn.AutoIncrement%2A> Eigenschaft der Spalte, die **"true"**.</span><span class="sxs-lookup"><span data-stu-id="9319b-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="9319b-105">Die <xref:System.Data.DataColumn> beginnt dann mit dem Wert im definierten der <xref:System.Data.DataColumn.AutoIncrementSeed%2A> -Eigenschaft, und mit jeder hinzugefügten Zeile den Wert des der **AutoIncrement** Spalte erhöht wird, um den Wert, der definiert, der <xref:System.Data.DataColumn.AutoIncrementStep%2A> -Eigenschaft der Spalte.</span><span class="sxs-lookup"><span data-stu-id="9319b-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="9319b-106">Für **AutoIncrement** -Spalten wird empfohlen, die die <xref:System.Data.DataColumn.ReadOnly%2A> Eigenschaft von der **DataColumn** festgelegt werden, um **"true"**.</span><span class="sxs-lookup"><span data-stu-id="9319b-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="9319b-107">Im folgenden Beispiel wird veranschaulicht, wie eine Spalte erstellt wird, die mit dem Wert 200 beginnt und deren Werte inkrementell jeweils um 3 erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="9319b-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9319b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9319b-108">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 [<span data-ttu-id="9319b-109">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="9319b-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="9319b-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="9319b-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="9319b-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9319b-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
