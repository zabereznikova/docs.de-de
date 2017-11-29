---
title: "Bedingte Ausdrücke: if... then...else (F#)"
description: "Erfahren Sie, wie bedingte Ausdrücke in f# zum Ausführen von anderen Verzweigungen von Code zu schreiben."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e1871c-4d4d-4691-9ab2-bd2c6f65589a
ms.openlocfilehash: 3531a112eb53657d5e9102d5e5f3be988360b76e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="c7e78-104">Bedingte Ausdrücke:`if...then...else`</span><span class="sxs-lookup"><span data-stu-id="c7e78-104">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="c7e78-105">Die `if...then...else` Ausdruck unterschiedliche Zweige der Code ausgeführt und wertet auch auf einen anderen Wert je nach den booleschen Ausdruck angegeben.</span><span class="sxs-lookup"><span data-stu-id="c7e78-105">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>


## <a name="syntax"></a><span data-ttu-id="c7e78-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7e78-106">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="c7e78-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7e78-107">Remarks</span></span>
<span data-ttu-id="c7e78-108">In der vorherigen Syntax *expression1* ausgeführt wird, wenn der boolesche Ausdruck ergibt `true`ist, andernfalls *expression2* ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7e78-108">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="c7e78-109">Anders als in anderen Sprachen, die `if...then...else` Konstrukt ist ein Ausdruck, der keine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c7e78-109">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="c7e78-110">Das bedeutet, dass es einen Wert erzeugt, der über den Wert des letzten Ausdrucks in der Verzweigung ist, die ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7e78-110">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="c7e78-111">Die Typen der Werte in jeder Verzweigung erzeugt müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c7e78-111">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="c7e78-112">Wenn es keine explizite ist `else` Branch, dessen Typ ist `unit`.</span><span class="sxs-lookup"><span data-stu-id="c7e78-112">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="c7e78-113">Aus diesem Grund Wenn der Typ des der `then` Verzweigung ist ein beliebiger Typ außer `unit`, muss vorhanden sein ein `else` Verzweigung mit den gleichen Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="c7e78-113">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="c7e78-114">Beim Verketten `if...then...else` Ausdrücke zusammen, verwenden Sie das Schlüsselwort `elif` anstelle von `else if`; sie gleichwertig sind.</span><span class="sxs-lookup"><span data-stu-id="c7e78-114">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="c7e78-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7e78-115">Example</span></span>
<span data-ttu-id="c7e78-116">Das folgende Beispiel zeigt, wie die `if...then...else` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c7e78-116">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
John
910 is less than 20
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="c7e78-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e78-117">See Also</span></span>
[<span data-ttu-id="c7e78-118">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c7e78-118">F# Language Reference</span></span>](index.md)

