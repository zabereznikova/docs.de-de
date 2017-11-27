---
title: "Beispiele für die Abfrageausdruckssyntax: Partitionierung"
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
ms.assetid: 7e41aed0-3be9-4f75-98de-860a85552a3c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 858d5c01c36516e3f1a8ca47c4d5500c0f24c80c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-partitioning"></a><span data-ttu-id="e71e9-102">Beispiele für die Abfrageausdruckssyntax: Partitionierung</span><span class="sxs-lookup"><span data-stu-id="e71e9-102">Query Expression Syntax Examples: Partitioning</span></span>
<span data-ttu-id="e71e9-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="e71e9-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="e71e9-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="e71e9-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e71e9-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="e71e9-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="e71e9-106">Skip</span><span class="sxs-lookup"><span data-stu-id="e71e9-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="e71e9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e71e9-107">Example</span></span>  
 <span data-ttu-id="e71e9-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten beiden Adressen, alle Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e71e9-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="e71e9-109">Take</span><span class="sxs-lookup"><span data-stu-id="e71e9-109">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="e71e9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e71e9-110">Example</span></span>  
 <span data-ttu-id="e71e9-111">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um die ersten drei Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e71e9-111">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="e71e9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e71e9-112">See Also</span></span>  
 [<span data-ttu-id="e71e9-113">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e71e9-113">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
