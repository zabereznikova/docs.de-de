---
description: let-Klausel – C#-Referenz
title: let-Klausel – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 3767b9745cccd9802374a8100de19f286c9b55ea
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139592"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="cb447-103">let-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cb447-103">let clause (C# Reference)</span></span>

<span data-ttu-id="cb447-104">Bei einem Abfrageausdruck kann es manchmal nützlich sein, das Ergebnis eines Unterausdrucks zur Verwendung in nachfolgenden Klauseln zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cb447-104">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="cb447-105">Sie können hierzu das Schlüsselwort `let` verwenden, das eine neue Bereichsvariable erstellt und sie mit dem von Ihnen bereitgestellten Ergebnis des Ausdrucks initialisiert.</span><span class="sxs-lookup"><span data-stu-id="cb447-105">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="cb447-106">Sobald die Bereichsvariable mit einem Wert initialisiert wurde, kann sie nicht mehr zum Speichern eines anderen Werts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb447-106">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="cb447-107">Enthält die Bereichsvariable jedoch einen abfragbaren Typ, kann sie abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="cb447-107">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="cb447-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb447-108">Example</span></span>

<span data-ttu-id="cb447-109">Im folgenden Beispiel wird `let` auf zweierlei Weise verwendet:</span><span class="sxs-lookup"><span data-stu-id="cb447-109">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="cb447-110">Um einen aufzählbaren Typ zu erstellen, der selbst abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb447-110">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="cb447-111">Um es der Abfrage zu ermöglichen, `ToLower` nur ein Mal für die Bereichsvariable `word` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="cb447-111">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="cb447-112">Ohne `let` müssten Sie `ToLower` in jedem Prädikat der `where`-Klausel aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cb447-112">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="cb447-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb447-113">See also</span></span>

- [<span data-ttu-id="cb447-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cb447-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cb447-115">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cb447-115">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="cb447-116">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="cb447-116">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="cb447-117">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cb447-117">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="cb447-118">Behandeln von Ausnahmen in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="cb447-118">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)
