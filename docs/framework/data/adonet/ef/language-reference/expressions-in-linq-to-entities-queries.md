---
title: Ausdrücke in LINQ to Entities-Abfragen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 5262d2bca07525aba6db5303e730c8b358641d52
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250975"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="db92d-102">Ausdrücke in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="db92d-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="db92d-103">Ein Ausdruck ist ein Codefragment, das als einzelner Wert, einzelnes Objekt, einzelne Methode oder einzelner Namespace ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="db92d-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="db92d-104">Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen einfachen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="db92d-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="db92d-105">Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein.</span><span class="sxs-lookup"><span data-stu-id="db92d-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="db92d-106">Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen.</span><span class="sxs-lookup"><span data-stu-id="db92d-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="db92d-107">Die Bandbreite der möglichen Ausdrücke reicht daher von einfach bis sehr komplex.</span><span class="sxs-lookup"><span data-stu-id="db92d-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="db92d-108">In LINQ to Entities-Abfragen können Ausdrücke beliebige Elemente enthalten, die von den Typen <xref:System.Linq.Expressions> im-Namespace zugelassen werden, einschließlich Lambda-Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="db92d-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="db92d-109">Die Ausdrücke, die in LINQ to Entities Abfragen verwendet werden können, sind eine übergeordnete Menge der Ausdrücke, die zum Abfragen [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]von verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="db92d-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="db92d-110">Ausdrücke, die Teil von Abfragen [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] für sind, sind auf Vorgänge beschränkt, die von `ObjectQuery<T>` und der zugrunde liegenden Datenquelle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="db92d-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="db92d-111">Im folgenden Beispiel ist der Vergleich in der `Where`-Klausel ein Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="db92d-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="db92d-112">Bestimmte Sprachkonstrukte, wie C# `unchecked`z. b., haben keine Bedeutung in LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="db92d-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db92d-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="db92d-113">In This Section</span></span>  
 [<span data-ttu-id="db92d-114">Constant Expressions (Konstante Ausdrücke)</span><span class="sxs-lookup"><span data-stu-id="db92d-114">Constant Expressions</span></span>](constant-expressions.md)  
  
 [<span data-ttu-id="db92d-115">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="db92d-115">Comparison Expressions</span></span>](comparison-expressions.md)  
  
 [<span data-ttu-id="db92d-116">NULL-Vergleiche</span><span class="sxs-lookup"><span data-stu-id="db92d-116">Null Comparisons</span></span>](null-comparisons.md)  
  
 [<span data-ttu-id="db92d-117">Initialisierungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="db92d-117">Initialization Expressions</span></span>](initialization-expressions.md)  
  
 [<span data-ttu-id="db92d-118">Beziehungen, Navigations Eigenschaften und Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="db92d-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="db92d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db92d-119">See also</span></span>

- [<span data-ttu-id="db92d-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="db92d-120">ADO.NET Entity Framework</span></span>](../index.md)
