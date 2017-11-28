---
title: let-Klausel (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 077c5178946b85d0fb85aa8da94966e4c5821736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="b4180-102">let-Klausel (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b4180-102">let clause (C# Reference)</span></span>
<span data-ttu-id="b4180-103">Bei einem Abfrageausdruck kann es manchmal nützlich sein, das Ergebnis eines Unterausdrucks zur Verwendung in nachfolgenden Klauseln zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b4180-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="b4180-104">Sie können hierzu das Schlüsselwort `let` verwenden, das eine neue Bereichsvariable erstellt und sie mit dem von Ihnen bereitgestellten Ergebnis des Ausdrucks initialisiert.</span><span class="sxs-lookup"><span data-stu-id="b4180-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="b4180-105">Sobald die Bereichsvariable mit einem Wert initialisiert wurde, kann sie nicht mehr zum Speichern eines anderen Werts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4180-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="b4180-106">Enthält die Bereichsvariable jedoch einen abfragbaren Typ, kann sie abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="b4180-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4180-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4180-107">Example</span></span>  
 <span data-ttu-id="b4180-108">Im folgenden Beispiel wird `let` auf zweierlei Weise verwendet:</span><span class="sxs-lookup"><span data-stu-id="b4180-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="b4180-109">Um einen aufzählbaren Typ zu erstellen, der selbst abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4180-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="b4180-110">Um es der Abfrage zu ermöglichen, `ToLower` nur ein Mal für die Bereichsvariable `word` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b4180-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="b4180-111">Ohne `let` müssten Sie `ToLower` in jedem Prädikat der `where`-Klausel aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b4180-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b4180-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4180-112">See Also</span></span>  
 [<span data-ttu-id="b4180-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b4180-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b4180-114">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b4180-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="b4180-115">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="b4180-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="b4180-116">Erste Schritte mit LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="b4180-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="b4180-117">Gewusst wie: Behandeln von Ausnahmen in Abfrageausdrücken</span><span class="sxs-lookup"><span data-stu-id="b4180-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
