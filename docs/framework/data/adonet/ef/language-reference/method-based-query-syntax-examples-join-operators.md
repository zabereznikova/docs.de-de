---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: a77a58d28c667e5dabf0dda4c8d2f4782ea83572
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="0e127-102">Beispiele für die methodenbasierte Abfragesyntax: Joinoperatoren</span><span class="sxs-lookup"><span data-stu-id="0e127-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="0e127-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.Join%2A> und <xref:System.Linq.Enumerable.GroupJoin%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="0e127-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="0e127-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="0e127-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0e127-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="0e127-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="0e127-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="0e127-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="0e127-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e127-107">Example</span></span>  
 <span data-ttu-id="0e127-108">Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der SalesOrderHeader-Tabelle und der SalesOrderDetail-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kunde zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0e127-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="0e127-109">Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="0e127-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="0e127-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e127-110">Example</span></span>  
 <span data-ttu-id="0e127-111">Im folgenden Beispiel wird ein <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact-Tabelle und der SalesOrderHeader-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kontakt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0e127-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="0e127-112">Die Anzahl der Aufträge und die IDs für alle Kontakte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e127-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="0e127-113">Join</span><span class="sxs-lookup"><span data-stu-id="0e127-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="0e127-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e127-114">Example</span></span>  
 <span data-ttu-id="0e127-115">Im folgenden Beispiel werden die Tabellen Contact und SalesOrderHeader miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="0e127-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="0e127-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e127-116">Example</span></span>  
 <span data-ttu-id="0e127-117">Im folgenden Beispiel werden die Tabellen Contact und SalesOrderHeader miteinander verknüpft, und die Ergebnisse werden nach der Kontakt-ID gruppiert.</span><span class="sxs-lookup"><span data-stu-id="0e127-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0e127-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e127-118">See Also</span></span>  
 [<span data-ttu-id="0e127-119">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="0e127-119">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
