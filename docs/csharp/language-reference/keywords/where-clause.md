---
title: where-Klausel – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 15df6339cec9eabadf5aa4c184d7504c4e065032
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73421934"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="a388b-102">where-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a388b-102">where clause (C# Reference)</span></span>

<span data-ttu-id="a388b-103">Die `where`-Klausel wird in einem Abfrageausdruck verwendet, um anzugeben, welche Elemente aus der Datenquelle im Abfrageausdruck zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a388b-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="a388b-104">Sie wendet eine boolesche Bedingung (*Prädikat*) auf jedes Quellelement an, auf das durch die Bereichsvariable verwiesen wird, und gibt die Elemente zurück, bei denen die angegebene Bedingung wahr ist.</span><span class="sxs-lookup"><span data-stu-id="a388b-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="a388b-105">Ein einzelner Abfrageausdruck enthält möglicherweise mehrere `where`-Klauseln, und eine einzelne Klausel kann mehrere Teilausdrücke des Prädikats enthalten.</span><span class="sxs-lookup"><span data-stu-id="a388b-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="a388b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a388b-106">Example</span></span>

<span data-ttu-id="a388b-107">Im folgenden Beispiel filtert die `where`-Klausel alle Zahlen mit Ausnahme derjenigen heraus, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="a388b-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="a388b-108">Wenn Sie die `where`-Klausel entfernen, werden alle Zahlen aus der Datenquelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a388b-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="a388b-109">Der Ausdruck `num < 5` ist das Prädikat, das auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a388b-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="a388b-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a388b-110">Example</span></span>

<span data-ttu-id="a388b-111">Innerhalb einer einzelnen `where`-Klausel können Sie so viele Prädikate wie nötig angeben, indem Sie die Operatoren [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) und [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a388b-111">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="a388b-112">Im folgenden Beispiel gibt die Abfrage zwei Prädikate an, um nur die geraden Zahlen auszuwählen, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="a388b-112">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="a388b-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a388b-113">Example</span></span>

<span data-ttu-id="a388b-114">Eine `where`-Klausel kann eine oder mehrere Methoden enthalten, die boolesche Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a388b-114">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="a388b-115">Im folgenden Beispiel verwendet die `where`-Klausel eine Methode, um zu bestimmen, ob der aktuelle Wert der Bereichsvariable gerade oder ungerade ist.</span><span class="sxs-lookup"><span data-stu-id="a388b-115">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="a388b-116">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a388b-116">Remarks</span></span>

<span data-ttu-id="a388b-117">Die `where`-Klausel ist ein Filtermechanismus.</span><span class="sxs-lookup"><span data-stu-id="a388b-117">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="a388b-118">Sie kann praktisch überall in einem Abfrageausdruck positioniert werden; sie kann allerdings nicht die erste oder letzte Klausel sein.</span><span class="sxs-lookup"><span data-stu-id="a388b-118">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="a388b-119">Eine `where`-Klausel kann entweder vor oder nach der [group](group-clause.md)-Klausel angezeigt werden, abhängig davon, ob Sie die Quellelemente vor oder nach deren Gruppierung filtern müssen.</span><span class="sxs-lookup"><span data-stu-id="a388b-119">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="a388b-120">Wenn ein angegebenes Prädikat nicht für die Elemente in der Datenquelle gültig ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="a388b-120">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="a388b-121">Dies ist ein Vorteil der von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] bereitgestellten starken Typprüfung.</span><span class="sxs-lookup"><span data-stu-id="a388b-121">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>

<span data-ttu-id="a388b-122">Zur Kompilierzeit wird das Schlüsselwort `where` in einen Aufruf der Standardabfrageoperator-Methode <xref:System.Linq.Enumerable.Where%2A> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a388b-122">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="a388b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a388b-123">See also</span></span>

- [<span data-ttu-id="a388b-124">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a388b-124">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="a388b-125">from-Klausel</span><span class="sxs-lookup"><span data-stu-id="a388b-125">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="a388b-126">select-Klausel</span><span class="sxs-lookup"><span data-stu-id="a388b-126">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="a388b-127">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="a388b-127">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="a388b-128">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="a388b-128">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="a388b-129">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="a388b-129">Getting Started with LINQ in C#</span></span>](/dotnet/csharp/programming-guide/concepts/linq/)
