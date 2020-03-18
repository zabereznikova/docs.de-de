---
title: Behandeln von Ausnahmen in Abfrageausdrücken (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Ausnahmen in LINQ-Abfrageausdrücken in C# verarbeiten.
ms.date: 12/01/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: f900669412026e69598d3939c51ff8208b51b7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688500"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="9630e-103">Behandeln von Ausnahmen in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="9630e-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="9630e-104">Es ist möglich, jede Methode im Kontext eines Abfrageausdrucks aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9630e-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="9630e-105">Es empfiehlt sich jedoch, Methoden in einem Abfrageausdruck aufzurufen, die Nebeneffekte wie die Änderung des Inhalts der Datenquelle oder das Auslösen einer Ausnahme erzeugen können.</span><span class="sxs-lookup"><span data-stu-id="9630e-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="9630e-106">In diesem Beispiel wird veranschaulicht, wie Sie es beim Aufrufen von Methoden in Abfrageausdrücken vermeiden, Ausnahmen auszulösen, ohne gegen die allgemeinen .NET-Richtlinien für die Behandlung von Ausnahmen zu verstoßen.</span><span class="sxs-lookup"><span data-stu-id="9630e-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="9630e-107">Gemäß dieser Richtlinien dürfen Sie eine bestimmte Ausnahme abfangen, wenn Sie wissen, warum sie in einem bestimmten Kontext ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9630e-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="9630e-108">Weitere Informationen finden Sie unter [Best Practices für Ausnahmen](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="9630e-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="9630e-109">Im letzten Beispiel wird der Umgang mit diesen Fällen veranschaulicht, wenn Sie während der Ausführung einer Abfrage eine Ausnahme auslösen müssen.</span><span class="sxs-lookup"><span data-stu-id="9630e-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="9630e-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9630e-110">Example</span></span>

<span data-ttu-id="9630e-111">Im folgenden Beispiel wird veranschaulicht, wie Sie den Ausnahmebehandlungscode aus einem Abfrageausdruck verschieben.</span><span class="sxs-lookup"><span data-stu-id="9630e-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="9630e-112">Dies ist nur möglich, wenn die Methode von keiner für die Abfrage lokalen Variablen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="9630e-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="9630e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9630e-113">Example</span></span>

<span data-ttu-id="9630e-114">In einigen Fällen ist die möglicherweise beste Antwort auf eine Ausnahme, die von einer Abfrage ausgelöst wird, die Ausführung der Abfrage sofort zu beenden.</span><span class="sxs-lookup"><span data-stu-id="9630e-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="9630e-115">Im folgenden Beispiel wird der Umgang mit Ausnahmen veranschaulicht, die innerhalb eines Abfragetexts ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="9630e-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="9630e-116">Angenommen dass `SomeMethodThatMightThrow` zu einer Ausnahme führen kann, derentwegen die Ausführung der Abfrage beenden werden muss.</span><span class="sxs-lookup"><span data-stu-id="9630e-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="9630e-117">Beachten Sie, dass der `try`-Block die `foreach`-Schleife und nicht die Abfrage selbst enthält.</span><span class="sxs-lookup"><span data-stu-id="9630e-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="9630e-118">Das liegt daran, dass die `foreach`-Schleife der Punkt ist, an dem die Abfrage tatsächlich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9630e-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="9630e-119">Weitere Informationen finden Sie unter [Einführung in LINQ-Abfragen](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9630e-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="9630e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9630e-120">See also</span></span>

- [<span data-ttu-id="9630e-121">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9630e-121">Language Integrated Query (LINQ)</span></span>](index.md)
