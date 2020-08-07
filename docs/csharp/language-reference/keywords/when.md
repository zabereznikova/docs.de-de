---
title: 'Kontextabhängiges when-Schlüsselwort: C#-Referenz'
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 2b041ca3a821f45dd63ce3f6bee7a920eb495651
ms.sourcegitcommit: 32f0d6f4c01ddc6ca78767c3a30e3305f8cd032c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "87426994"
---
# <a name="when-c-reference"></a><span data-ttu-id="45246-102">when (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="45246-102">when (C# Reference)</span></span>

<span data-ttu-id="45246-103">Sie können das kontextabhängige Schlüsselwort `when` verwenden, um in den folgenden Kontexten eine Filterbedingung anzugeben:</span><span class="sxs-lookup"><span data-stu-id="45246-103">You can use the `when` contextual keyword to specify a filter condition in the following contexts:</span></span>

- <span data-ttu-id="45246-104">In der `catch`-Anweisung eines [try/catch](try-catch.md)- oder [try/catch/finally](try-catch-finally.md)-Blocks</span><span class="sxs-lookup"><span data-stu-id="45246-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="45246-105">In der `case`-Bezeichnung einer [switch](switch.md)-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45246-105">In the `case` label of a [switch](switch.md) statement.</span></span>
- <span data-ttu-id="45246-106">Im [`switch`-Ausdruck](../operators/switch-expression.md)</span><span class="sxs-lookup"><span data-stu-id="45246-106">In the [`switch` expression](../operators/switch-expression.md).</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="45246-107">`when` in einer `catch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45246-107">`when` in a `catch` statement</span></span>

<span data-ttu-id="45246-108">Ab mit C# 6 kann `when` in einer `catch`-Anweisung verwendet werden, um eine Bedingung mit dem Wert „TRUE“ für den Handler anzugeben, damit eine spezifische Ausnahme ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="45246-108">Starting with C# 6, `when` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="45246-109">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="45246-109">Its syntax is:</span></span>

```csharp
catch (ExceptionType [e]) when (expr)
```

<span data-ttu-id="45246-110">where *expr* ist ein Ausdruck, der einen booleschen Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="45246-110">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="45246-111">Wenn `true` zurückgegeben wird, wird der Ausnahmehandler ausgeführt; wenn `false` zurückgegeben wird, nicht.</span><span class="sxs-lookup"><span data-stu-id="45246-111">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span>

<span data-ttu-id="45246-112">Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um Handler abhängig vom Text der Ausnahmemeldung für <xref:System.Net.Http.HttpRequestException> bedingt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="45246-112">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

[!code-csharp[when-with-catch](~/samples/snippets/csharp/language-reference/keywords/when/catch.cs)]

## <a name="when-in-a-switch-statement"></a><span data-ttu-id="45246-113">`when` in einer `switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45246-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="45246-114">Ab C# 7.0 müssen sich `case`-Bezeichnungen nicht mehr gegenseitig ausschließen, und die Reihenfolge, in der `case`-Bezeichnungen in einer `switch`-Anweisung angezeigt werden, kann bestimmen, welcher Schalterblock ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45246-114">Starting with C# 7.0, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="45246-115">Das Schlüsselwort `when` kann verwendet werden, um eine Filterbedingung anzugeben, die dazu führt, dass die zugeordnete case-Bezeichnung nur TRUE ist, wenn die Filterbedingung ebenfalls TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="45246-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="45246-116">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="45246-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```

<span data-ttu-id="45246-117">Wo *expr* ein Konstantenmuster oder Typmuster ist, das mit dem match-Ausdruck verglichen wird, und wo *when-condition* ein beliebiger boolescher Ausdruck ist</span><span class="sxs-lookup"><span data-stu-id="45246-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span>

<span data-ttu-id="45246-118">Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um auf `Shape`-Objekte zu testen, die einen Bereich von 0 haben, und um auf eine Vielzahl von `Shape`-Objekten zu testen, die einen Bereich größer als 0 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="45246-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span>

[!code-csharp[when-with-case#1](~/samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]

## <a name="see-also"></a><span data-ttu-id="45246-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45246-119">See also</span></span>

- [<span data-ttu-id="45246-120">switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45246-120">switch statement</span></span>](switch.md)
- [<span data-ttu-id="45246-121">Try-Catch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45246-121">try/catch statement</span></span>](try-catch.md)
- [<span data-ttu-id="45246-122">try/catch/finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45246-122">try/catch/finally statement</span></span>](try-catch-finally.md)
