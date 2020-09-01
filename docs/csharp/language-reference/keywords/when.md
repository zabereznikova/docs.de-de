---
description: 'Kontextabhängiges when-Schlüsselwort: C#-Referenz'
title: 'Kontextabhängiges when-Schlüsselwort: C#-Referenz'
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: bd3a7beeb7d3c4b62d6b70e2b1c6f38ab4b6804f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138214"
---
# <a name="when-c-reference"></a><span data-ttu-id="f0985-103">when (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f0985-103">when (C# Reference)</span></span>

<span data-ttu-id="f0985-104">Sie können das kontextabhängige Schlüsselwort `when` verwenden, um in den folgenden Kontexten eine Filterbedingung anzugeben:</span><span class="sxs-lookup"><span data-stu-id="f0985-104">You can use the `when` contextual keyword to specify a filter condition in the following contexts:</span></span>

- <span data-ttu-id="f0985-105">In der `catch`-Anweisung eines [try/catch](try-catch.md)- oder [try/catch/finally](try-catch-finally.md)-Blocks</span><span class="sxs-lookup"><span data-stu-id="f0985-105">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="f0985-106">In der `case`-Bezeichnung einer [switch](switch.md)-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0985-106">In the `case` label of a [switch](switch.md) statement.</span></span>
- <span data-ttu-id="f0985-107">Im [`switch`-Ausdruck](../operators/switch-expression.md)</span><span class="sxs-lookup"><span data-stu-id="f0985-107">In the [`switch` expression](../operators/switch-expression.md).</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="f0985-108">`when` in einer `catch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0985-108">`when` in a `catch` statement</span></span>

<span data-ttu-id="f0985-109">Ab mit C# 6 kann `when` in einer `catch`-Anweisung verwendet werden, um eine Bedingung mit dem Wert „TRUE“ für den Handler anzugeben, damit eine spezifische Ausnahme ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0985-109">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="f0985-110">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="f0985-110">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="f0985-111">where *expr* ist ein Ausdruck, der einen booleschen Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="f0985-111">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="f0985-112">Wenn `true` zurückgegeben wird, wird der Ausnahmehandler ausgeführt; wenn `false` zurückgegeben wird, nicht.</span><span class="sxs-lookup"><span data-stu-id="f0985-112">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="f0985-113">Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um Handler abhängig vom Text der Ausnahmemeldung für <xref:System.Net.Http.HttpRequestException> bedingt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0985-113">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="f0985-114">`when` in einer `switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0985-114">`when` in a `switch` statement</span></span>

<span data-ttu-id="f0985-115">Ab C# 7.0 müssen sich `case`-Bezeichnungen nicht mehr gegenseitig ausschließen, und die Reihenfolge, in der `case`-Bezeichnungen in einer `switch`-Anweisung angezeigt werden, kann bestimmen, welcher Schalterblock ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0985-115">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="f0985-116">Das Schlüsselwort `when` kann verwendet werden, um eine Filterbedingung anzugeben, die dazu führt, dass die zugeordnete case-Bezeichnung nur TRUE ist, wenn die Filterbedingung ebenfalls TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="f0985-116">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="f0985-117">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="f0985-117">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="f0985-118">Wo *expr* ein Konstantenmuster oder Typmuster ist, das mit dem match-Ausdruck verglichen wird, und wo *when-condition* ein beliebiger boolescher Ausdruck ist</span><span class="sxs-lookup"><span data-stu-id="f0985-118">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="f0985-119">Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um auf `Shape`-Objekte zu testen, die einen Bereich von 0 haben, und um auf eine Vielzahl von `Shape`-Objekten zu testen, die einen Bereich größer als 0 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f0985-119">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="f0985-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0985-120">See also</span></span>

- [<span data-ttu-id="f0985-121">switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0985-121">switch statement</span></span>](switch.md)
- [<span data-ttu-id="f0985-122">Try-Catch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0985-122">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="f0985-123">try/catch/finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0985-123">try/catch/finally statement</span></span>](try-catch-finally.md)
