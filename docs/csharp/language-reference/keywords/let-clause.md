---
title: let-Klausel (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 62294df7f0f2ebb3249dffd72ba4910fbae984c8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47230709"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="2c9c1-102">let-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2c9c1-102">let clause (C# Reference)</span></span>

<span data-ttu-id="2c9c1-103">Bei einem Abfrageausdruck kann es manchmal nützlich sein, das Ergebnis eines Unterausdrucks zur Verwendung in nachfolgenden Klauseln zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="2c9c1-104">Sie können hierzu das Schlüsselwort `let` verwenden, das eine neue Bereichsvariable erstellt und sie mit dem von Ihnen bereitgestellten Ergebnis des Ausdrucks initialisiert.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="2c9c1-105">Sobald die Bereichsvariable mit einem Wert initialisiert wurde, kann sie nicht mehr zum Speichern eines anderen Werts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="2c9c1-106">Enthält die Bereichsvariable jedoch einen abfragbaren Typ, kann sie abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="2c9c1-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c9c1-107">Example</span></span>

<span data-ttu-id="2c9c1-108">Im folgenden Beispiel wird `let` auf zweierlei Weise verwendet:</span><span class="sxs-lookup"><span data-stu-id="2c9c1-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="2c9c1-109">Um einen aufzählbaren Typ zu erstellen, der selbst abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="2c9c1-110">Um es der Abfrage zu ermöglichen, `ToLower` nur ein Mal für die Bereichsvariable `word` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="2c9c1-111">Ohne `let` müssten Sie `ToLower` in jedem Prädikat der `where`-Klausel aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2c9c1-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="2c9c1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c9c1-112">See also</span></span>

- [<span data-ttu-id="2c9c1-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2c9c1-113">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="2c9c1-114">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="2c9c1-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="2c9c1-115">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="2c9c1-115">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="2c9c1-116">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="2c9c1-116">Getting Started with LINQ in C#</span></span>](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="2c9c1-117">Behandeln von Ausnahmen in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="2c9c1-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)