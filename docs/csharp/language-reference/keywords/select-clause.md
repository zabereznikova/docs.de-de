---
description: select-Klausel – C#-Referenz
title: select-Klausel – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: d67c99cc841c08a63cc83843a07a46e80199b9d1
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136901"
---
# <a name="select-clause-c-reference"></a><span data-ttu-id="4e33f-103">select-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4e33f-103">select clause (C# Reference)</span></span>

<span data-ttu-id="4e33f-104">In einem Abfrageausdruck gibt die `select`-Klausel den Typ der Werte an, die beim Ausführen der Abfrage erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e33f-104">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="4e33f-105">Das Ergebnis basiert auf der Auswertung aller vorherigen Klauseln und auf allen Ausdrücke in der `select`-Klausel selbst.</span><span class="sxs-lookup"><span data-stu-id="4e33f-105">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="4e33f-106">Ein Abfrageausdruck muss entweder mit einer `select`-Klausel oder einer [group](group-clause.md)-Klausel enden.</span><span class="sxs-lookup"><span data-stu-id="4e33f-106">A query expression must terminate with either a `select` clause or a [group](group-clause.md) clause.</span></span>

<span data-ttu-id="4e33f-107">Im folgenden Beispiel wird eine einfache `select`-Klausel in einem Abfrageausdruck dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4e33f-107">The following example shows a simple `select` clause in a query expression.</span></span>

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

<span data-ttu-id="4e33f-108">Der Typ der mit der `select`-Klausel erstellten Sequenz bestimmt den Typ der Abfragevariable `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="4e33f-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="4e33f-109">Im einfachsten Fall gibt die `select`-Klausel nur die Bereichsvariable an.</span><span class="sxs-lookup"><span data-stu-id="4e33f-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="4e33f-110">Dadurch enthält die zurückgegebene Sequenz Elemente desselben Typs wie die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="4e33f-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="4e33f-111">Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4e33f-111">For more information, see [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="4e33f-112">Allerdings bietet die `select`-Klausel zudem ein leistungsstarkes Werkzeug, um Quelldaten in neue Typen zu transformieren (oder zu *projizieren*).</span><span class="sxs-lookup"><span data-stu-id="4e33f-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="4e33f-113">Weitere Informationen finden Sie unter [Datentransformationen mit LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="4e33f-113">For more information, see [Data Transformations with LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="4e33f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e33f-114">Example</span></span>

<span data-ttu-id="4e33f-115">Das folgende Beispiel zeigt die verschiedenen Formen, die eine `select`-Klausel annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="4e33f-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="4e33f-116">Beachten Sie in jeder Abfrage die Beziehung zwischen der `select`-Klausel und dem Typ der *Abfragevariable* (`studentQuery1`, `studentQuery2` usw.).</span><span class="sxs-lookup"><span data-stu-id="4e33f-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

<span data-ttu-id="4e33f-117">Wie in `studentQuery8` im vorherigen Beispiel kann es möglicherweise sinnvoll sein, dass die Elemente der zurückgegebenen Sequenz nur eine Teilmenge der Eigenschaften der Quellelemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e33f-117">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="4e33f-118">Indem die zurückgegebene Sequenz so klein wie möglich gehalten wird, können die Speicheranforderungen reduziert und die Geschwindigkeit der Abfrageausführung erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="4e33f-118">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="4e33f-119">Erstellen Sie hierzu einen anonymen Typ in der `select`-Klausel, und verwenden Sie einen Objektinitialisierer, um sie mit den entsprechenden Eigenschaften aus dem Quellelement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4e33f-119">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="4e33f-120">Ein Beispiel zur Vorgehensweise finden Sie unter [Objekt- und Auflistungsinitialisierer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="4e33f-120">For an example of how to do this, see [Object and Collection Initializers](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="4e33f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4e33f-121">Remarks</span></span>

<span data-ttu-id="4e33f-122">Beim Kompilieren wird die `select`-Klausel in einen Methodenaufruf des <xref:System.Linq.Enumerable.Select%2A>-Standardabfrageoperators übersetzt.</span><span class="sxs-lookup"><span data-stu-id="4e33f-122">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e33f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e33f-123">See also</span></span>

- [<span data-ttu-id="4e33f-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4e33f-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4e33f-125">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4e33f-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="4e33f-126">from-Klausel</span><span class="sxs-lookup"><span data-stu-id="4e33f-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="4e33f-127">partial (Methode) (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4e33f-127">partial (Method) (C# Reference)</span></span>](partial-method.md)
- [<span data-ttu-id="4e33f-128">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="4e33f-128">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="4e33f-129">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="4e33f-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="4e33f-130">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4e33f-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
