---
title: Ausdrücke in LINQ to Entities-Abfragen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: dccf3ab1a619222cdf2db54673718eb103aee2fb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422268"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="11e6d-102">Ausdrücke in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="11e6d-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="11e6d-103">Ein Ausdruck ist ein Codefragment, das als einzelner Wert, einzelnes Objekt, einzelne Methode oder einzelner Namespace ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e6d-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="11e6d-104">Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen einfachen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="11e6d-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="11e6d-105">Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein.</span><span class="sxs-lookup"><span data-stu-id="11e6d-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="11e6d-106">Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen.</span><span class="sxs-lookup"><span data-stu-id="11e6d-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="11e6d-107">Die Bandbreite der möglichen Ausdrücke reicht daher von einfach bis sehr komplex.</span><span class="sxs-lookup"><span data-stu-id="11e6d-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="11e6d-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] Abfragen Ausdrücke alles enthalten, zulässigen Typen innerhalb der <xref:System.Linq.Expressions> -Namespace, einschließlich der Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="11e6d-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="11e6d-109">Die Ausdrücke, die in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen verwendet werden können, umfassen die Ausdrücke, mit denen das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e6d-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="11e6d-110">Ausdrücke, die Teil einer Abfrage der [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind von unterstützten Vorgänge auf `ObjectQuery<T>` und der zugrunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="11e6d-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="11e6d-111">Im folgenden Beispiel ist der Vergleich in der `Where`-Klausel ein Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="11e6d-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="11e6d-112">Bestimmte Sprachkonstrukte, wie `unchecked` in C#, haben in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] keine Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="11e6d-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11e6d-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="11e6d-113">In This Section</span></span>  
 [<span data-ttu-id="11e6d-114">Constant Expressions (Konstante Ausdrücke)</span><span class="sxs-lookup"><span data-stu-id="11e6d-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="11e6d-115">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="11e6d-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="11e6d-116">NULL-Vergleiche</span><span class="sxs-lookup"><span data-stu-id="11e6d-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="11e6d-117">Initialisierungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="11e6d-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="11e6d-118">Navigationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="11e6d-118">Navigation Properties</span></span>](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a><span data-ttu-id="11e6d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11e6d-119">See Also</span></span>  
 [<span data-ttu-id="11e6d-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="11e6d-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
