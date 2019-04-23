---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Umwandeln'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: bf6c889fff2635cd50597e72151c46fbb4d9b97d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150617"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="bdc79-102">Beispiele für die methodenbasierte Abfragesyntax: Umwandeln</span><span class="sxs-lookup"><span data-stu-id="bdc79-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="bdc79-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> und <xref:System.Linq.Enumerable.ToList%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="bdc79-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="bdc79-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="bdc79-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="bdc79-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="bdc79-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="bdc79-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="bdc79-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="bdc79-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdc79-107">Example</span></span>  
 <span data-ttu-id="bdc79-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet, um eine Sequenz unmittelbar in ein Array auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="bdc79-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="bdc79-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="bdc79-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="bdc79-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdc79-110">Example</span></span>  
 <span data-ttu-id="bdc79-111">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToDictionary%2A>-Methode verwendet, um eine Sequenz und einen zugehörigen Schlüsselausdruck unmittelbar in ein Wörterbuch umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="bdc79-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="bdc79-112">ToList</span><span class="sxs-lookup"><span data-stu-id="bdc79-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="bdc79-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdc79-113">Example</span></span>  
 <span data-ttu-id="bdc79-114">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.ToList%2A>-Methode verwendet, um eine Sequenz unmittelbar in eine <xref:System.Collections.Generic.List%601> umzuwandeln, wobei `T` vom Typ <xref:System.Data.DataRow> ist.</span><span class="sxs-lookup"><span data-stu-id="bdc79-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="bdc79-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdc79-115">See also</span></span>

- [<span data-ttu-id="bdc79-116">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="bdc79-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
