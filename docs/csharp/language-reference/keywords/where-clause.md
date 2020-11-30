---
description: where-Klausel – C#-Referenz
title: where-Klausel – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 58a8dc226bb2720b6a8251f028712a80f74e893c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89141685"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="06161-103">where-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="06161-103">where clause (C# Reference)</span></span>

<span data-ttu-id="06161-104">Die `where`-Klausel wird in einem Abfrageausdruck verwendet, um anzugeben, welche Elemente aus der Datenquelle im Abfrageausdruck zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06161-104">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="06161-105">Sie wendet eine boolesche Bedingung (*Prädikat*) auf jedes Quellelement an, auf das durch die Bereichsvariable verwiesen wird, und gibt die Elemente zurück, bei denen die angegebene Bedingung wahr ist.</span><span class="sxs-lookup"><span data-stu-id="06161-105">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="06161-106">Ein einzelner Abfrageausdruck enthält möglicherweise mehrere `where`-Klauseln, und eine einzelne Klausel kann mehrere Teilausdrücke des Prädikats enthalten.</span><span class="sxs-lookup"><span data-stu-id="06161-106">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="06161-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06161-107">Example</span></span>

<span data-ttu-id="06161-108">Im folgenden Beispiel filtert die `where`-Klausel alle Zahlen mit Ausnahme derjenigen heraus, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="06161-108">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="06161-109">Wenn Sie die `where`-Klausel entfernen, werden alle Zahlen aus der Datenquelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06161-109">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="06161-110">Der Ausdruck `num < 5` ist das Prädikat, das auf jedes Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="06161-110">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="06161-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06161-111">Example</span></span>

<span data-ttu-id="06161-112">Innerhalb einer einzelnen `where`-Klausel können Sie so viele Prädikate wie nötig angeben, indem Sie die Operatoren [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) und [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) verwenden.</span><span class="sxs-lookup"><span data-stu-id="06161-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="06161-113">Im folgenden Beispiel gibt die Abfrage zwei Prädikate an, um nur die geraden Zahlen auszuwählen, die niedriger als fünf sind.</span><span class="sxs-lookup"><span data-stu-id="06161-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="06161-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06161-114">Example</span></span>

<span data-ttu-id="06161-115">Eine `where`-Klausel kann eine oder mehrere Methoden enthalten, die boolesche Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="06161-115">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="06161-116">Im folgenden Beispiel verwendet die `where`-Klausel eine Methode, um zu bestimmen, ob der aktuelle Wert der Bereichsvariable gerade oder ungerade ist.</span><span class="sxs-lookup"><span data-stu-id="06161-116">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="06161-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="06161-117">Remarks</span></span>

<span data-ttu-id="06161-118">Die `where`-Klausel ist ein Filtermechanismus.</span><span class="sxs-lookup"><span data-stu-id="06161-118">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="06161-119">Sie kann praktisch überall in einem Abfrageausdruck positioniert werden; sie kann allerdings nicht die erste oder letzte Klausel sein.</span><span class="sxs-lookup"><span data-stu-id="06161-119">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="06161-120">Eine `where`-Klausel kann entweder vor oder nach der [group](group-clause.md)-Klausel angezeigt werden, abhängig davon, ob Sie die Quellelemente vor oder nach deren Gruppierung filtern müssen.</span><span class="sxs-lookup"><span data-stu-id="06161-120">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="06161-121">Wenn ein angegebenes Prädikat nicht für die Elemente in der Datenquelle gültig ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="06161-121">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="06161-122">Dies ist ein Vorteil der von LINQ bereitgestellten starken Typprüfung.</span><span class="sxs-lookup"><span data-stu-id="06161-122">This is one benefit of the strong type-checking provided by LINQ.</span></span>

<span data-ttu-id="06161-123">Zur Kompilierzeit wird das Schlüsselwort `where` in einen Aufruf der Standardabfrageoperator-Methode <xref:System.Linq.Enumerable.Where%2A> konvertiert.</span><span class="sxs-lookup"><span data-stu-id="06161-123">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="06161-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06161-124">See also</span></span>

- [<span data-ttu-id="06161-125">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="06161-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="06161-126">from-Klausel</span><span class="sxs-lookup"><span data-stu-id="06161-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="06161-127">select-Klausel</span><span class="sxs-lookup"><span data-stu-id="06161-127">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="06161-128">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="06161-128">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="06161-129">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="06161-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="06161-130">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="06161-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
