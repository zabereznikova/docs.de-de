---
title: Ausdrücke in LINQ to Entities-Abfragen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f65759d37661271588d56965eadcccbe997623f4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166650"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="82f44-102">Ausdrücke in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="82f44-102">Expressions in LINQ to Entities Queries</span></span>

<span data-ttu-id="82f44-103">Ein Ausdruck ist ein Codefragment, das als einzelner Wert, einzelnes Objekt, einzelne Methode oder einzelner Namespace ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="82f44-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="82f44-104">Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen einfachen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="82f44-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="82f44-105">Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein.</span><span class="sxs-lookup"><span data-stu-id="82f44-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="82f44-106">Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen.</span><span class="sxs-lookup"><span data-stu-id="82f44-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="82f44-107">Die Bandbreite der möglichen Ausdrücke reicht daher von einfach bis sehr komplex.</span><span class="sxs-lookup"><span data-stu-id="82f44-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="82f44-108">In LINQ to Entities-Abfragen können Ausdrücke beliebige Elemente enthalten, die von den Typen im- <xref:System.Linq.Expressions> Namespace zugelassen werden, einschließlich Lambda-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="82f44-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="82f44-109">Die Ausdrücke, die in LINQ to Entities Abfragen verwendet werden können, sind eine supermenge der Ausdrücke, die verwendet werden können, um die Entity Framework abzufragen. Ausdrücke, die Teil von Abfragen für die Entity Framework sind, sind auf Vorgänge beschränkt, die von `ObjectQuery<T>` und der zugrunde liegenden Datenquelle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="82f44-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the Entity Framework.Expressions that are part of queries against the Entity Framework are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="82f44-110">Im folgenden Beispiel ist der Vergleich in der `Where`-Klausel ein Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="82f44-110">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="82f44-111">Bestimmte Sprachkonstrukte, wie z. b. c# `unchecked` , haben keine Bedeutung in LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="82f44-111">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82f44-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="82f44-112">In This Section</span></span>  

 [<span data-ttu-id="82f44-113">Konstante Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="82f44-113">Constant Expressions</span></span>](constant-expressions.md)  
  
 [<span data-ttu-id="82f44-114">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="82f44-114">Comparison Expressions</span></span>](comparison-expressions.md)  
  
 [<span data-ttu-id="82f44-115">NULL-Vergleiche</span><span class="sxs-lookup"><span data-stu-id="82f44-115">Null Comparisons</span></span>](null-comparisons.md)  
  
 [<span data-ttu-id="82f44-116">Initialisierungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="82f44-116">Initialization Expressions</span></span>](initialization-expressions.md)  
  
 [<span data-ttu-id="82f44-117">Beziehungen, Navigations Eigenschaften und Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="82f44-117">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="82f44-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82f44-118">See also</span></span>

- [<span data-ttu-id="82f44-119">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="82f44-119">ADO.NET Entity Framework</span></span>](../index.md)
