---
title: 'Beispiele für die Abfrageausdruckssyntax: Joinoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: af7bea7c9fda7a3c1eb1e419c50dcd61df8c63d1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="4685e-102">Beispiele für die Abfrageausdruckssyntax: Joinoperatoren</span><span class="sxs-lookup"><span data-stu-id="4685e-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="4685e-103">Das Verknüpfen (JOIN) ist eine wichtige Operation bei Abfragen von Daten aus Datenquellen, bei denen es untereinander keine navigierbaren Beziehungen, wie Tabellen in relationalen Datenbanken, gibt.</span><span class="sxs-lookup"><span data-stu-id="4685e-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="4685e-104">Bei einer JOIN-Operation für zwei Datenquellen werden Objekte in einer Datenquelle mit Objekten in der anderen Datenquelle, die über ein gemeinsames Attribut verfügen, miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="4685e-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="4685e-105">Weitere Informationen finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="4685e-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="4685e-106">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.GroupJoin%2A> und <xref:System.Linq.Enumerable.Join%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="4685e-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="4685e-107">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="4685e-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4685e-108">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="4685e-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="4685e-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="4685e-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="4685e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4685e-110">Example</span></span>  
 <span data-ttu-id="4685e-111">Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der SalesOrderHeader-Tabelle und der SalesOrderDetail-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kunde zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4685e-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="4685e-112">Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="4685e-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="4685e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4685e-113">Example</span></span>  
 <span data-ttu-id="4685e-114">Im folgenden Beispiel wird ein <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact-Tabelle und der SalesOrderHeader-Tabelle durchgeführt, um nach der Anzahl der Aufträge pro Kontakt zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4685e-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="4685e-115">Die Anzahl der Aufträge und die IDs für alle Kontakte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4685e-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
### <a name="example"></a><span data-ttu-id="4685e-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4685e-116">Example</span></span>  
 <span data-ttu-id="4685e-117">Im folgenden Beispiel wird eine <xref:System.Linq.Enumerable.GroupJoin%2A> zwischen der Contact-Tabelle und der SalesOrderHeader-Tabelle durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4685e-117">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables.</span></span> <span data-ttu-id="4685e-118">Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten (linken) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="4685e-118">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="4685e-119">Join</span><span class="sxs-lookup"><span data-stu-id="4685e-119">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="4685e-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4685e-120">Example</span></span>  
 <span data-ttu-id="4685e-121">Im folgenden Beispiel werden die SalesOrderHeader-Tabelle und die SalesOrderDetail-Tabelle miteinander verknüpft, um die Onlinebestellungen für den Monat August abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4685e-121">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="4685e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4685e-122">See Also</span></span>  
 [<span data-ttu-id="4685e-123">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4685e-123">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
