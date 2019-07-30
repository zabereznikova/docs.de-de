---
title: Ausdrücke vergleichen
description: Erfahren Sie, F# wie der Übereinstimmungs Ausdruck eine Verzweigungs Steuerung bereitstellt, die auf dem Vergleich eines Ausdrucks mit einer Reihe von Mustern basiert.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627605"
---
# <a name="match-expressions"></a><span data-ttu-id="d58ef-103">Ausdrücke vergleichen</span><span class="sxs-lookup"><span data-stu-id="d58ef-103">Match expressions</span></span>

<span data-ttu-id="d58ef-104">Der `match` Ausdruck stellt ein Verzweigungs Steuerelement bereit, das auf dem Vergleich eines Ausdrucks mit einer Reihe von Mustern basiert.</span><span class="sxs-lookup"><span data-stu-id="d58ef-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="d58ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d58ef-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d58ef-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d58ef-106">Remarks</span></span>

<span data-ttu-id="d58ef-107">Die Muster Vergleichsausdrücke ermöglichen eine komplexe Verzweigung basierend auf dem Vergleich eines Test Ausdrucks mit einer Reihe von Mustern.</span><span class="sxs-lookup"><span data-stu-id="d58ef-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="d58ef-108">Im Ausdruck wird der *Test Ausdruck* mit den einzelnen Mustern verglichen. Wenn eine Übereinstimmung gefunden wird, wird der entsprechende *Ergebnis Ausdruck* ausgewertet, und der resultierende Wert wird als Wert des Vergleichs Ausdrucks zurückgegeben. `match`</span><span class="sxs-lookup"><span data-stu-id="d58ef-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="d58ef-109">Die in der vorherigen Syntax gezeigte Muster Vergleichsfunktion ist ein Lambda Ausdruck, in dem der Musterabgleich sofort auf dem Argument ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d58ef-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="d58ef-110">Die in der vorherigen Syntax gezeigte Muster Vergleichsfunktion entspricht der folgenden.</span><span class="sxs-lookup"><span data-stu-id="d58ef-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="d58ef-111">Weitere Informationen zu Lambda-Ausdrücken finden [Sie unter Lambda-Ausdrücke: Das `fun` Schlüssel](./functions/lambda-expressions-the-fun-keyword.md)Wort.</span><span class="sxs-lookup"><span data-stu-id="d58ef-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="d58ef-112">Der gesamte Satz von Mustern sollte alle möglichen Übereinstimmungen der Eingabevariablen abdecken.</span><span class="sxs-lookup"><span data-stu-id="d58ef-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="d58ef-113">Häufig verwenden Sie das Platzhalter Muster (`_`) als letztes Muster, um alle zuvor nicht übereinstimmenden Eingabewerte abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="d58ef-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="d58ef-114">Der folgende Code veranschaulicht einige der Methoden, mit denen der `match` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d58ef-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="d58ef-115">Einen Verweis und Beispiele für alle möglichen Muster, die verwendet werden können, finden Sie unter [Muster](pattern-matching.md)Abgleich.</span><span class="sxs-lookup"><span data-stu-id="d58ef-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="d58ef-116">Wächter bei Mustern</span><span class="sxs-lookup"><span data-stu-id="d58ef-116">Guards on patterns</span></span>

<span data-ttu-id="d58ef-117">Sie können eine `when` -Klausel verwenden, um eine zusätzliche Bedingung anzugeben, die die Variable erfüllen muss, damit Sie einem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="d58ef-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="d58ef-118">Eine solche Klausel wird als *Wächter*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d58ef-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="d58ef-119">Der Ausdruck, der `when` auf das-Schlüsselwort folgt, wird nur ausgewertet, wenn eine Entsprechung für das diesem Guard zugeordnete Muster vorliegt.</span><span class="sxs-lookup"><span data-stu-id="d58ef-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="d58ef-120">Das folgende Beispiel veranschaulicht die Verwendung eines-Schutzes, um einen numerischen Bereich für ein Variablen Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d58ef-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="d58ef-121">Beachten Sie, dass mehrere Bedingungen mithilfe von booleschen Operatoren kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d58ef-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="d58ef-122">Beachten Sie, dass Sie eine `when` -Klausel verwenden müssen, wenn Sie einen Teil der Eingabe mit einem Wert vergleichen müssen, weil andere Werte als Literale nicht im Muster verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d58ef-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="d58ef-123">Dies wird im folgenden Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="d58ef-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="d58ef-124">Beachten Sie Folgendes: Wenn ein Union-Muster durch einen Wächter abgedeckt wird, gilt der Wächter für **alle** Muster, nicht nur für den letzten.</span><span class="sxs-lookup"><span data-stu-id="d58ef-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="d58ef-125">Beispielsweise gilt für den folgenden Code, dass der `when a > 12` Wächter sowohl `A a` für als `B a`auch für gilt:</span><span class="sxs-lookup"><span data-stu-id="d58ef-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d58ef-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d58ef-126">See also</span></span>

- [<span data-ttu-id="d58ef-127">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d58ef-127">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d58ef-128">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="d58ef-128">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="d58ef-129">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="d58ef-129">Pattern Matching</span></span>](pattern-matching.md)
