---
title: Vergleichsausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
ms.openlocfilehash: d92020f353393eee683e578f4306cd4a2f214152
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197845"
---
# <a name="comparison-expressions"></a><span data-ttu-id="9e6d7-102">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="9e6d7-102">Comparison Expressions</span></span>

<span data-ttu-id="9e6d7-103">Ein Vergleichsausdruck überprüft, ob ein konstanter Wert, ein Eigenschaftswert oder das Ergebnis einer Methode gleich oder ungleich einem anderen Wert bzw. größer oder kleiner als ein anderer Wert ist.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-103">A comparison expression checks whether a constant value, property value, or method result is equal, not equal, greater than, or less than another value.</span></span> <span data-ttu-id="9e6d7-104">Wenn ein bestimmter Vergleich für LINQ to Entities nicht gültig ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-104">If a particular comparison is not valid for LINQ to Entities, an exception will be thrown.</span></span> <span data-ttu-id="9e6d7-105">Für alle Vergleiche, sowohl implizite als auch explizite, ist es erforderlich, dass alle Komponenten in der Datenquelle vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-105">All comparisons, both implicit and explicit, require that all components are comparable in the data source.</span></span> <span data-ttu-id="9e6d7-106">Vergleichsausdrücke werden oft in `Where`-Klauseln zur Einschränkung der Abfrageergebnisse verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-106">Comparison expressions are frequently used in `Where` clauses for restricting the query results.</span></span>  
  
 <span data-ttu-id="9e6d7-107">Im folgenden Beispiel von Abfrageausdruckssyntax wird eine Abfrage dargestellt, die Ergebnisse mit der Auftragsnummer "SO43663" zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9e6d7-107">The following example in query expression syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 <span data-ttu-id="9e6d7-108">Im folgenden Beispiel von methodenbasierter Abfragesyntax wird eine Abfrage dargestellt, die Ergebnisse mit der Auftragsnummer "SO43663" zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9e6d7-108">The following example in method-based query syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 <span data-ttu-id="9e6d7-109">Im folgenden Beispiel von Abfrageausdruckssyntax wird eine Abfrage dargestellt, die Auftragsinformationen zu Aufträgen mit dem Lieferdatum 8. Juli 2001 zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9e6d7-109">The following example in query expression syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 <span data-ttu-id="9e6d7-110">Im folgenden Beispiel von methodenbasierter Abfragesyntax wird eine Abfrage dargestellt, die Auftragsinformationen zu Aufträgen mit dem Lieferdatum 8. Juli 2001 zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="9e6d7-110">The following example in method-based query syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 <span data-ttu-id="9e6d7-111">Ausdrücke, die einen konstanten Wert zurückgeben, werden auf dem Server konvertiert, und es wird keine lokale Auswertung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-111">Expressions that yield a constant are converted at the server, and no attempt to do local evaluation is performed.</span></span> <span data-ttu-id="9e6d7-112">Im folgenden Beispiel wird ein Ausdruck in der `Where`-Klausel verwendet, der eine Konstante zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-112">The following example uses an expression in the `Where` clause that yields a constant.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="9e6d7-113">LINQ to Entities unterstützt nicht die Verwendung einer Benutzerklasse als Konstante.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-113">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="9e6d7-114">Ein Eigenschaftsverweis in einer Benutzerklasse wird jedoch als konstant behandelt. Er wird in einen konstanten Ausdruck der Befehlsstruktur konvertiert und für die Datenquelle ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-114">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 <span data-ttu-id="9e6d7-115">Methoden, die einen konstanten Ausdruck zurückgeben, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-115">Methods that return a constant expression are not supported.</span></span> <span data-ttu-id="9e6d7-116">Das folgende Beispiel enthält eine Methode in der `Where`-Klausel, die eine Konstante zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-116">The following example contains a method in the `Where` clause that returns a constant.</span></span> <span data-ttu-id="9e6d7-117">Dieses Beispiel löst zur Laufzeit eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="9e6d7-117">This example will throw an exception at run time.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a><span data-ttu-id="9e6d7-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e6d7-118">See also</span></span>

- [<span data-ttu-id="9e6d7-119">Ausdrücke in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="9e6d7-119">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
