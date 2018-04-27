---
title: Vergleichsausdrücke (f#)
description: Erfahren Sie, wie die Vergleichsausdruck [F#] Verzweigen gesteuert, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.
author: cartermp
ms.author: phcart
ms.date: 04/19/2018
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f843e6fde98eae8a10235dd5cae38ffc10a4fb9f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="match-expressions"></a><span data-ttu-id="9163a-103">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="9163a-103">Match expressions</span></span>

<span data-ttu-id="9163a-104">Die `match` Ausdruck enthält, Verzweigen Steuerelement, das basierend auf den Vergleich eines Ausdrucks mit einem Satz von Mustern.</span><span class="sxs-lookup"><span data-stu-id="9163a-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="9163a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9163a-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="9163a-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9163a-106">Remarks</span></span>

<span data-ttu-id="9163a-107">Das Muster übereinstimmenden-Ausdrücke ermöglichen komplexe Verzweigung basierend auf den Vergleich eines Test-Ausdrucks mit einem Satz von Mustern.</span><span class="sxs-lookup"><span data-stu-id="9163a-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="9163a-108">In der `match` Ausdruck, der *Testausdruck* mit jedes Muster verglichen wird, wiederum, und wenn eine Übereinstimmung gefunden wird, wird das entsprechende *Ergebnisausdruck* wird ausgewertet, und der resultierende Wert als Wert des Ausdrucks Übereinstimmung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9163a-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="9163a-109">Funktion in der vorherigen Syntax für der Mustervergleich ist ein Lambda-Ausdruck, in welche, den Muster übereinstimmenden sofort für das Argument ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9163a-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="9163a-110">Funktion in der vorherigen Syntax für der Mustervergleich ist äquivalent zu folgendem.</span><span class="sxs-lookup"><span data-stu-id="9163a-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="9163a-111">Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke: das `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="9163a-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="9163a-112">Der gesamte Satz von Mustern sollten alle möglichen Übereinstimmungen der Eingabevariablen abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="9163a-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="9163a-113">In vielen Fällen verwenden Sie das Platzhaltermuster (`_`) als das letzte Muster, die zuvor nicht übereinstimmenden Eingabewerten überein.</span><span class="sxs-lookup"><span data-stu-id="9163a-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="9163a-114">Das folgende Codebeispiel veranschaulicht einige der Methoden in der die `match` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9163a-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="9163a-115">Ein Verweis und Beispiele für alle Muster, die verwendet werden können, finden Sie unter [Mustervergleich](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="9163a-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="9163a-116">Wächter für Muster</span><span class="sxs-lookup"><span data-stu-id="9163a-116">Guards on patterns</span></span>

<span data-ttu-id="9163a-117">Sie können eine `when` -Klausel, um eine weitere Bedingung angeben, die die Variable entsprechen muss, einem bestimmten Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9163a-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="9163a-118">Diese Klausel wird als bezeichnet eine *schützen*.</span><span class="sxs-lookup"><span data-stu-id="9163a-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="9163a-119">Der folgende Ausdruck den `when` Schlüsselwort wird nicht ausgewertet werden, es sei denn, eine Übereinstimmung, um das Muster, das dem Wächter zugeordnet festgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9163a-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="9163a-120">Das folgende Beispiel veranschaulicht die Verwendung von Wächter einen numerischen Bereich für ein Variablenmuster an.</span><span class="sxs-lookup"><span data-stu-id="9163a-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="9163a-121">Beachten Sie, dass mehrere Bedingungen mit booleschen Operatoren kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="9163a-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="9163a-122">Beachten Sie, weil andere Werte als Literale in das Muster nicht verwendet werden können, müssen Sie verwenden eine `when` -Klausel, wenn Sie einen Teil der Eingabe mit einem Wert vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9163a-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="9163a-123">Dies wird im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9163a-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="9163a-124">Beachten Sie, dass wenn eine union-Muster von Wächter abgedeckt wird, für der Wächter gilt **alle** der Muster, nicht nur die letzte Aktivität.</span><span class="sxs-lookup"><span data-stu-id="9163a-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="9163a-125">Angenommen, den folgenden Code, den Wächter `when a > 12` gelten für beide `A a` und `B a`:</span><span class="sxs-lookup"><span data-stu-id="9163a-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="9163a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9163a-126">See also</span></span>

[<span data-ttu-id="9163a-127">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="9163a-127">F# Language Reference</span></span>](index.md)  
[<span data-ttu-id="9163a-128">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="9163a-128">Active Patterns</span></span>](active-patterns.md)  
[<span data-ttu-id="9163a-129">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="9163a-129">Pattern Matching</span></span>](pattern-matching.md)  
