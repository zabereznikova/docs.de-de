---
description: orderby-Klausel – C#-Referenz
title: orderby-Klausel – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142348"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="81a64-103">orderby-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="81a64-103">orderby clause (C# Reference)</span></span>

<span data-ttu-id="81a64-104">In einem Abfrageausdruck bewirkt die `orderby`-Klausel, dass die zurückgegebene Sequenz oder Untersequenz (Gruppe) entweder in aufsteigender oder absteigender Reihenfolge sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="81a64-104">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="81a64-105">Es können mehrere Schlüssel angegeben werden, um eine oder mehrere sekundäre Sortiervorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="81a64-105">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="81a64-106">Die Sortierung erfolgt mit dem Standardvergleich für den Typ des Elements.</span><span class="sxs-lookup"><span data-stu-id="81a64-106">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="81a64-107">Standardmäßig wird die Sortierung in aufsteigender Reihenfolge vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="81a64-107">The default sort order is ascending.</span></span> <span data-ttu-id="81a64-108">Sie können auch einen benutzerdefinierten Vergleich angeben.</span><span class="sxs-lookup"><span data-stu-id="81a64-108">You can also specify a custom comparer.</span></span> <span data-ttu-id="81a64-109">Der ist jedoch nur mit der methodenbasierten Syntax verfügbar.</span><span class="sxs-lookup"><span data-stu-id="81a64-109">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="81a64-110">Weitere Informationen finden Sie unter [Sortieren von Daten](../../programming-guide/concepts/linq/sorting-data.md).</span><span class="sxs-lookup"><span data-stu-id="81a64-110">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="81a64-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81a64-111">Example</span></span>

<span data-ttu-id="81a64-112">Im folgenden Beispiel sortiert die erste Abfrage die Wörter in alphabetischer Reihenfolge, beginnend mit A, und die zweite Abfrage die gleichen Wörter in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="81a64-112">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="81a64-113">(Das Schlüsselwort `ascending` ist der Standardwert für das Sortieren und kann ausgelassen werden.)</span><span class="sxs-lookup"><span data-stu-id="81a64-113">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="81a64-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81a64-114">Example</span></span>

<span data-ttu-id="81a64-115">Im folgenden Beispiel wird eine primäre Sortierung der Nachnamen von Studenten und dann eine sekundäre Sortierung auf ihre Vornamen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="81a64-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="81a64-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="81a64-116">Remarks</span></span>

<span data-ttu-id="81a64-117">Zur Kompilierzeit wird die `orderby`-Klausel in einen Aufruf der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode übersetzt.</span><span class="sxs-lookup"><span data-stu-id="81a64-117">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="81a64-118">Mehrere Schlüssel in der `orderby`-Klausel werden in <xref:System.Linq.Enumerable.ThenBy%2A>-Methodenaufrufe übersetzt.</span><span class="sxs-lookup"><span data-stu-id="81a64-118">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="81a64-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81a64-119">See also</span></span>

- [<span data-ttu-id="81a64-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="81a64-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="81a64-121">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="81a64-121">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="81a64-122">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="81a64-122">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="81a64-123">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="81a64-123">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="81a64-124">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="81a64-124">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
