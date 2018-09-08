---
title: Vergleichsausdrücke (f#)
description: Erfahren Sie, wie der F#-Vergleichsausdruck verzweigungssteuerung bereitstellt, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.
ms.date: 04/19/2018
ms.openlocfilehash: e4cb82f20fe82bff562736557c2346562c557f59
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132038"
---
# <a name="match-expressions"></a><span data-ttu-id="44e9d-103">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="44e9d-103">Match expressions</span></span>

<span data-ttu-id="44e9d-104">Die `match` Ausdruck liefert verzweigungssteuerung, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.</span><span class="sxs-lookup"><span data-stu-id="44e9d-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="44e9d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="44e9d-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="44e9d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44e9d-106">Remarks</span></span>

<span data-ttu-id="44e9d-107">Die mustervergleichsausdrücke ermöglichen Verzweigungen durch komplexe auf Basis des Vergleichs eines Test-Ausdrucks mit einem Satz von Mustern.</span><span class="sxs-lookup"><span data-stu-id="44e9d-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="44e9d-108">In der `match` Ausdruck, der *Testausdruck* mit jedes Muster verglichen wird, nacheinander, und wenn eine Übereinstimmung gefunden wird, wird das entsprechende *Ergebnisausdruck* wird ausgewertet, und der resultierende Wert als der Wert des Ausdrucks Übereinstimmung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44e9d-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="44e9d-109">Mustervergleich in der vorherigen Syntax gezeigt Funktion ist ein Lambda-Ausdruck, in welches, den Muster übereinstimmende sofort für das Argument ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44e9d-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="44e9d-110">Der Musterabgleich-Funktion in der vorherigen Syntax ist äquivalent zu folgendem.</span><span class="sxs-lookup"><span data-stu-id="44e9d-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="44e9d-111">Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda-Ausdrücke: der `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="44e9d-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="44e9d-112">Die gesamte Gruppe von Mustern sollten alle möglichen Übereinstimmungen der Eingabevariablen abdecken.</span><span class="sxs-lookup"><span data-stu-id="44e9d-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="44e9d-113">In vielen Fällen verwenden Sie das Platzhaltermuster (`_`) als das letzte Muster entsprechend alle zuvor nicht übereinstimmende Eingabewerte.</span><span class="sxs-lookup"><span data-stu-id="44e9d-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="44e9d-114">Der folgende Code zeigt einige der Methoden in der die `match` Ausdruck wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="44e9d-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="44e9d-115">Eine Referenz und Beispiele für alle Muster, die verwendet werden können, finden Sie unter [Musterabgleich](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="44e9d-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="44e9d-116">Wächter für Muster</span><span class="sxs-lookup"><span data-stu-id="44e9d-116">Guards on patterns</span></span>

<span data-ttu-id="44e9d-117">Sie können eine `when` -Klausel, um eine zusätzliche Bedingung anzugeben, die die Variable ein Muster erfüllen müssen.</span><span class="sxs-lookup"><span data-stu-id="44e9d-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="44e9d-118">Diese Klausel wird als bezeichnet ein *schützen*.</span><span class="sxs-lookup"><span data-stu-id="44e9d-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="44e9d-119">Der Ausdruck nach den `when` Schlüsselwort wird nicht ausgewertet, wenn eine Übereinstimmung für das Muster, die dem Wächter zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="44e9d-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="44e9d-120">Das folgende Beispiel veranschaulicht die Verwendung von Wächter einen numerischen Bereich für ein Variablenmuster an.</span><span class="sxs-lookup"><span data-stu-id="44e9d-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="44e9d-121">Beachten Sie, dass mehrere Bedingungen mit booleschen Operatoren kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="44e9d-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="44e9d-122">Beachten Sie, dass da andere Werte als Literale in das Muster verwendet werden können, müssen Sie verwenden eine `when` -Klausel, wenn einen Teil der Eingabe mit einem Wert zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="44e9d-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="44e9d-123">Dies wird im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="44e9d-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="44e9d-124">Beachten Sie, dass bei einem union-Muster durch eine Guard abgedeckt ist, um der Wächter gilt **alle** der Muster, nicht nur die letzte Aktivität.</span><span class="sxs-lookup"><span data-stu-id="44e9d-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="44e9d-125">Betrachten Sie den folgenden Code, den Wächter `when a > 12` gilt für `A a` und `B a`:</span><span class="sxs-lookup"><span data-stu-id="44e9d-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="44e9d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44e9d-126">See also</span></span>

- [<span data-ttu-id="44e9d-127">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="44e9d-127">F# Language Reference</span></span>](index.md)  
- [<span data-ttu-id="44e9d-128">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="44e9d-128">Active Patterns</span></span>](active-patterns.md)  
- [<span data-ttu-id="44e9d-129">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="44e9d-129">Pattern Matching</span></span>](pattern-matching.md)  
