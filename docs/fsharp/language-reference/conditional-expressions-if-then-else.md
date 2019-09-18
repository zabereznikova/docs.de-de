---
title: 'Bedingte Ausdrücke: If... dann... woanders'
description: Erfahren Sie, wie Sie bedingte Ausdrücke in F# zum Ausführen der unterschiedliche Codezweige geschrieben.
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083030"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="1184c-103">Bedingte Ausdrücke:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="1184c-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="1184c-104">Der `if...then...else` Ausdruck führt verschiedene Code Verzweigungen aus und wird abhängig vom angegebenen booleschen Ausdruck auch zu einem anderen Wert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1184c-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="1184c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1184c-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="1184c-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1184c-106">Remarks</span></span>

<span data-ttu-id="1184c-107">In der vorherigen Syntax wird *expression1* ausgeführt, wenn der boolesche Ausdruck `true`ergibt; andernfalls wird *expression2* ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1184c-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="1184c-108">Anders als in anderen Sprachen ist `if...then...else` das Konstrukt ein Ausdruck, nicht eine-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1184c-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="1184c-109">Dies bedeutet, dass ein Wert erzeugt wird, bei dem es sich um den Wert des letzten Ausdrucks in der Verzweigung handelt, die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1184c-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="1184c-110">Die Typen der in den einzelnen Verzweigungen erzeugten Werte müssen mit identisch sein.</span><span class="sxs-lookup"><span data-stu-id="1184c-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="1184c-111">Wenn keine explizite `else` Verzweigung vorhanden ist, ist `unit`der Typ.</span><span class="sxs-lookup"><span data-stu-id="1184c-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="1184c-112">Wenn der Typ der `then` Verzweigung ein anderer Typ als `unit`ist, muss daher eine `else` Verzweigung mit dem gleichen Rückgabetyp vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1184c-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="1184c-113">Wenn Sie `if...then...else` Ausdrücke verketten, können Sie das-Schlüssel `elif` Wort anstelle `else if`von verwenden. Sie sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="1184c-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="1184c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1184c-114">Example</span></span>

<span data-ttu-id="1184c-115">Im folgenden Beispiel wird veranschaulicht, wie der `if...then...else` -Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1184c-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="1184c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1184c-116">See also</span></span>

- [<span data-ttu-id="1184c-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="1184c-117">F# Language Reference</span></span>](index.md)
