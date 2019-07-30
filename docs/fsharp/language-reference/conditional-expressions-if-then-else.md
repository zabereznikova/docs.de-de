---
title: 'Bedingte Ausdrücke: If... dann... woanders'
description: Erfahren Sie, wie Sie bedingte Ausdrücke in F# zum Ausführen der unterschiedliche Codezweige geschrieben.
ms.date: 05/16/2016
ms.openlocfilehash: 825149bf296eded3cc2b4d8847ba4d82bea40cdc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630393"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="dffc5-103">Bedingte Ausdrücke:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="dffc5-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="dffc5-104">Der `if...then...else` Ausdruck führt verschiedene Code Verzweigungen aus und wird abhängig vom angegebenen booleschen Ausdruck auch zu einem anderen Wert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="dffc5-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="dffc5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dffc5-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="dffc5-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dffc5-106">Remarks</span></span>

<span data-ttu-id="dffc5-107">In der vorherigen Syntax wird *expression1* ausgeführt, wenn der boolesche Ausdruck `true`ergibt; andernfalls wird *expression2* ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="dffc5-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="dffc5-108">Anders als in anderen Sprachen ist `if...then...else` das Konstrukt ein Ausdruck, nicht eine-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dffc5-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="dffc5-109">Dies bedeutet, dass ein Wert erzeugt wird, bei dem es sich um den Wert des letzten Ausdrucks in der Verzweigung handelt, die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dffc5-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="dffc5-110">Die Typen der in den einzelnen Verzweigungen erzeugten Werte müssen mit identisch sein.</span><span class="sxs-lookup"><span data-stu-id="dffc5-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="dffc5-111">Wenn keine explizite `else` Verzweigung vorhanden ist, ist `unit`der Typ.</span><span class="sxs-lookup"><span data-stu-id="dffc5-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="dffc5-112">Wenn der Typ der `then` Verzweigung ein anderer Typ als `unit`ist, muss daher eine `else` Verzweigung mit dem gleichen Rückgabetyp vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="dffc5-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="dffc5-113">Wenn Sie `if...then...else` Ausdrücke verketten, können Sie das-Schlüssel `elif` Wort anstelle `else if`von verwenden. Sie sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="dffc5-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="dffc5-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dffc5-114">Example</span></span>

<span data-ttu-id="dffc5-115">Im folgenden Beispiel wird veranschaulicht, wie der `if...then...else` -Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dffc5-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="dffc5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dffc5-116">See also</span></span>

- [<span data-ttu-id="dffc5-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="dffc5-117">F# Language Reference</span></span>](index.md)
