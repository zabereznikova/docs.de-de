---
title: "Behandeln von Ausnahmen in Abfrageausdrücken"
description: "So behandeln Sie Ausnahmen in Abfrageausdrücken"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9ce4a4ca62bb476b2414ec8b93d5633faca53b59
ms.contentlocale: de-de
ms.lasthandoff: 08/11/2017

---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="2aa3b-104">Behandeln von Ausnahmen in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="2aa3b-104">Handle exceptions in query expressions</span></span>

<span data-ttu-id="2aa3b-105">Es ist möglich, jede Methode im Kontext eines Abfrageausdrucks aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-105">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="2aa3b-106">Es empfiehlt sich jedoch, Methoden in einem Abfrageausdruck aufzurufen, die Nebeneffekte wie die Änderung des Inhalts der Datenquelle oder das Auslösen einer Ausnahme erzeugen können.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-106">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="2aa3b-107">In diesem Beispiel wird veranschaulicht, wie Sie es beim Aufrufen von Methoden in Abfrageausdrücken vermeiden, Ausnahmen auszulösen, ohne gegen die allgemeinen .NET Framework-Richtlinien für die Behandlung von Ausnahmen zu verstoßen.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-107">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="2aa3b-108">Diesen Richtlinien gemäß dürfen Sie eine bestimmte Ausnahme abfangen, wenn Sie wissen, warum sie in einem bestimmten Kontext ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-108">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="2aa3b-109">Weitere Informationen finden Sie unter [Best Practices für Ausnahmen](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2aa3b-109">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="2aa3b-110">Im letzten Beispiel wird der Umgang mit diesen Fällen veranschaulicht, wenn Sie während der Ausführung einer Abfrage eine Ausnahme auslösen müssen.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-110">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa3b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aa3b-111">Example</span></span>  

 <span data-ttu-id="2aa3b-112">Im folgenden Beispiel wird veranschaulicht, wie Sie den Ausnahmebehandlungscode aus einem Abfrageausdruck verschieben.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-112">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="2aa3b-113">Dies ist nur möglich, wenn die Methode von keiner für die Abfrage lokalen Variablen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-113">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 <span data-ttu-id="2aa3b-114">[!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2aa3b-114">[!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa3b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aa3b-115">Example</span></span> 

 <span data-ttu-id="2aa3b-116">In einigen Fällen ist die möglicherweise beste Antwort auf eine Ausnahme, die von einer Abfrage ausgelöst wird, die Ausführung der Abfrage sofort zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-116">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="2aa3b-117">Im folgenden Beispiel wird der Umgang mit Ausnahmen veranschaulicht, die innerhalb eines Abfragetexts ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-117">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="2aa3b-118">Angenommen dass `SomeMethodThatMightThrow` zu einer Ausnahme führen kann, derentwegen die Ausführung der Abfrage beenden werden muss.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-118">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="2aa3b-119">Beachten Sie, dass der `try`-Block die `foreach`-Schleife und nicht die Abfrage selbst enthält.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-119">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="2aa3b-120">Das liegt daran, dass die `foreach`-Schleife der Punkt ist, an dem die Abfrage tatsächlich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2aa3b-120">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="2aa3b-121">Weitere Informationen finden Sie unter [Introduction to LINQ queries (Einführung in LINQ-Abfragen)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2aa3b-121">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="2aa3b-122">[!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2aa3b-122">[!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="2aa3b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa3b-123">See Also</span></span>  
 [<span data-ttu-id="2aa3b-124">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="2aa3b-124">LINQ query expressions</span></span>](index.md)

