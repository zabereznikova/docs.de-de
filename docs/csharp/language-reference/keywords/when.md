---
title: when (C#-Referenz)
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 9ad2eff6eb527f00ce23f463e811aa748def62d0
ms.openlocfilehash: c391c6de51d41577d61278f43d58fade5b7c139f
ms.contentlocale: de-de
ms.lasthandoff: 08/11/2017

---
 # <a name="when-c-reference"></a><span data-ttu-id="1fe75-102">when (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1fe75-102">when (C# Reference)</span></span>

<span data-ttu-id="1fe75-103">Sie können das kontextabhängige Schlüsselwort `when` verwenden, um eine Filterbedingung in zwei Kontexten anzugeben:</span><span class="sxs-lookup"><span data-stu-id="1fe75-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="1fe75-104">In der `catch`-Anweisung eines [try/catch](try-catch.md)- oder [try/catch/finally](try-catch-finally.md)-Blocks</span><span class="sxs-lookup"><span data-stu-id="1fe75-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="1fe75-105">In der `case`-Bezeichnung einer [switch](switch.md)-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1fe75-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="1fe75-106">`when` in einer `catch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1fe75-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="1fe75-107">Ab mit C# 6 kann `When` in einer `catch`-Anweisung verwendet werden, um eine Bedingung mit dem Wert „TRUE“ für den Handler anzugeben, damit eine spezifische Ausnahme ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1fe75-107">Starting with C# 6, `When` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="1fe75-108">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="1fe75-108">Its syntax is:</span></span>

```csharp
catch ExceptionType [e] when (expr)
```
<span data-ttu-id="1fe75-109">where *expr* ist ein Ausdruck, der einen booleschen Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="1fe75-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="1fe75-110">Wenn `true` zurückgegeben wird, wird der Ausnahmehandler ausgeführt; wenn `false` zurückgegeben wird, nicht.</span><span class="sxs-lookup"><span data-stu-id="1fe75-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span> 

<span data-ttu-id="1fe75-111">Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um Handler abhängig vom Text der Ausnahmemeldung für @System.Net.HttpRequestException bedingt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1fe75-111">The following example uses the `when` keyword to conditionally execute handlers for an @System.Net.HttpRequestException depending on the text of the exception message.</span></span>

 <span data-ttu-id="1fe75-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span><span class="sxs-lookup"><span data-stu-id="1fe75-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span></span>  
  
## <a name="when-in-a-switch-statement"></a><span data-ttu-id="1fe75-113">`when` in einer `switch`-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1fe75-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="1fe75-114">Ab mit C# 7 müssen sich `case`-Bezeichnungen nicht mehr gegenseitig ausschließen, und die Reihenfolge, in der `case`-Bezeichnungen in einer `switch`-Anweisung angezeigt werden, kann bestimmen, welcher Schalterblock ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1fe75-114">Starting with 7, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="1fe75-115">Das Schlüsselwort `when` kann verwendet werden, um eine Filterbedingung anzugeben, die dazu führt, dass die zugeordnete case-Bezeichnung nur TRUE ist, wenn die Filterbedingung ebenfalls TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="1fe75-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="1fe75-116">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="1fe75-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```
<span data-ttu-id="1fe75-117">Wo *expr* ein Konstantenmuster oder Typmuster ist, das mit dem match-Ausdruck verglichen wird, und wo *when-condition* ein beliebiger boolescher Ausdruck ist</span><span class="sxs-lookup"><span data-stu-id="1fe75-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span> 

<span data-ttu-id="1fe75-118">Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um auf `Shape`-Objekte zu testen, die einen Bereich von 0 haben, und um auf eine Vielzahl von `Shape`-Objekten zu testen, die einen Bereich größer als 0 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1fe75-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span> 

 <span data-ttu-id="1fe75-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="1fe75-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1fe75-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fe75-120">See also</span></span> 
  [<span data-ttu-id="1fe75-121">switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1fe75-121">switch statement</span></span>](switch.md)  
  [<span data-ttu-id="1fe75-122">Try-Catch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1fe75-122">try/catch statement</span></span>](try-catch.md)  
  [<span data-ttu-id="1fe75-123">try/catch/finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1fe75-123">try/catch/finally statement</span></span>](try-catch-finally.md) 


