---
title: "Vergleichsausdrücke (F#)"
description: Erfahren Sie, wie die Vergleichsausdruck [F#] Verzweigen gesteuert, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a><span data-ttu-id="67b58-104">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="67b58-104">Match Expressions</span></span>

<span data-ttu-id="67b58-105">Die `match` Ausdruck enthält, Verzweigen Steuerelement, das basierend auf den Vergleich eines Ausdrucks mit einem Satz von Mustern.</span><span class="sxs-lookup"><span data-stu-id="67b58-105">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="67b58-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="67b58-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="67b58-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67b58-107">Remarks</span></span>

<span data-ttu-id="67b58-108">Das Muster übereinstimmenden-Ausdrücke ermöglichen komplexe Verzweigung basierend auf den Vergleich eines Test-Ausdrucks mit einem Satz von Mustern.</span><span class="sxs-lookup"><span data-stu-id="67b58-108">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="67b58-109">In der `match` Ausdruck, der *Testausdruck* mit jedes Muster verglichen wird, wiederum, und wenn eine Übereinstimmung gefunden wird, wird das entsprechende *Ergebnisausdruck* wird ausgewertet, und der resultierende Wert als Wert des Ausdrucks Übereinstimmung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="67b58-109">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="67b58-110">Funktion in der vorherigen Syntax für der Mustervergleich ist ein Lambda-Ausdruck, in welche, den Muster übereinstimmenden sofort für das Argument ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="67b58-110">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="67b58-111">Funktion in der vorherigen Syntax für der Mustervergleich ist äquivalent zu folgendem.</span><span class="sxs-lookup"><span data-stu-id="67b58-111">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

<span data-ttu-id="67b58-112">Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke: das `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="67b58-112">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="67b58-113">Der gesamte Satz von Mustern sollten alle möglichen Übereinstimmungen der Eingabevariablen abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="67b58-113">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="67b58-114">In vielen Fällen verwenden Sie das Platzhaltermuster (`_`) als das letzte Muster, die zuvor nicht übereinstimmenden Eingabewerten überein.</span><span class="sxs-lookup"><span data-stu-id="67b58-114">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="67b58-115">Das folgende Codebeispiel veranschaulicht einige der Methoden in der die `match` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67b58-115">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="67b58-116">Ein Verweis und Beispiele für alle Muster, die verwendet werden können, finden Sie unter [Mustervergleich](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="67b58-116">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="67b58-117">Wächter für Muster</span><span class="sxs-lookup"><span data-stu-id="67b58-117">Guards on Patterns</span></span>

<span data-ttu-id="67b58-118">Sie können eine `when` -Klausel, um eine weitere Bedingung angeben, die die Variable entsprechen muss, einem bestimmten Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="67b58-118">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="67b58-119">Diese Klausel wird als bezeichnet eine *schützen*.</span><span class="sxs-lookup"><span data-stu-id="67b58-119">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="67b58-120">Der folgende Ausdruck den `when` Schlüsselwort wird nicht ausgewertet werden, es sei denn, eine Übereinstimmung, um das Muster, das dem Wächter zugeordnet festgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="67b58-120">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="67b58-121">Das folgende Beispiel veranschaulicht die Verwendung von Wächter einen numerischen Bereich für ein Variablenmuster an.</span><span class="sxs-lookup"><span data-stu-id="67b58-121">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="67b58-122">Beachten Sie, dass mehrere Bedingungen mit booleschen Operatoren kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="67b58-122">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="67b58-123">Beachten Sie, weil andere Werte als Literale in das Muster nicht verwendet werden können, müssen Sie verwenden eine `when` -Klausel, wenn Sie einen Teil der Eingabe mit einem Wert vergleichen.</span><span class="sxs-lookup"><span data-stu-id="67b58-123">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="67b58-124">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="67b58-124">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a><span data-ttu-id="67b58-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67b58-125">See Also</span></span>

[<span data-ttu-id="67b58-126">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="67b58-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="67b58-127">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="67b58-127">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="67b58-128">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="67b58-128">Pattern Matching</span></span>](pattern-matching.md)
