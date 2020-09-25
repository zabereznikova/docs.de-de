---
title: 'Beispiele für die Abfrageausdruckssyntax: Partitionierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e41aed0-3be9-4f75-98de-860a85552a3c
ms.openlocfilehash: 548701f375b550e3a533a012bf34dc686ed42ac1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203604"
---
# <a name="query-expression-syntax-examples-partitioning"></a><span data-ttu-id="a828a-102">Beispiele für die Abfrageausdruckssyntax: Partitionierung</span><span class="sxs-lookup"><span data-stu-id="a828a-102">Query Expression Syntax Examples: Partitioning</span></span>

<span data-ttu-id="a828a-103">In den Beispielen in diesem Thema wird gezeigt, wie die <xref:System.Linq.Enumerable.Skip%2A> -Methode und die-Methode verwendet werden <xref:System.Linq.Enumerable.Take%2A> , um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Abfrage Ausdruckssyntax abzu</span><span class="sxs-lookup"><span data-stu-id="a828a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="a828a-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="a828a-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a828a-105">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="a828a-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="a828a-106">Überspringen</span><span class="sxs-lookup"><span data-stu-id="a828a-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="a828a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a828a-107">Example</span></span>  

 <span data-ttu-id="a828a-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten beiden Adressen, alle Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a828a-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="a828a-109">Take</span><span class="sxs-lookup"><span data-stu-id="a828a-109">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="a828a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a828a-110">Example</span></span>  

 <span data-ttu-id="a828a-111">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um die ersten drei Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a828a-111">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="a828a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a828a-112">See also</span></span>

- [<span data-ttu-id="a828a-113">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="a828a-113">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
