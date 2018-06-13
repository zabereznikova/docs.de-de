---
title: 'Ausnahmen: Der try...with-Ausdruck (F#)'
description: Erfahren Sie, wie der F#-"try...with" Ausdruck für die Ausnahmebehandlung zu verwenden.
ms.date: 05/16/2016
ms.openlocfilehash: 5e6e16d5fba88841d567512ba7e08a2e8d17bdba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565287"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="01022-103">Ausnahmen: Der try...with-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="01022-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="01022-104">In diesem Thema wird beschrieben, die `try...with` Ausdruck, der Ausdruck, der für die Ausnahmebehandlung in der Programmiersprache f# verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01022-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="01022-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="01022-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="01022-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01022-106">Remarks</span></span>
<span data-ttu-id="01022-107">Die `try...with` Ausdruck wird verwendet, um die Behandlung von Ausnahmen in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="01022-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="01022-108">Ähnliches gilt für die `try...catch` -Anweisung in c#.</span><span class="sxs-lookup"><span data-stu-id="01022-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="01022-109">In der vorherigen Syntax wird der Code in *expression1* möglicherweise eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="01022-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="01022-110">Die `try...with` Ausdruck gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="01022-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="01022-111">Wenn keine Ausnahme ausgelöst wird, wird der gesamte Ausdruck gibt den Wert der *expression1*.</span><span class="sxs-lookup"><span data-stu-id="01022-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="01022-112">Wenn eine Ausnahme ausgelöst wird, jede *Muster* wiederum verglichen wird, mit der Ausnahme und für das erste übereinstimmende Muster für den entsprechenden *Ausdruck*, bekannt als die *Ausnahmehandler*für die Verzweigung wird ausgeführt, und der gesamte Ausdruck den Wert des Ausdrucks in dieser Ausnahmehandler gibt.</span><span class="sxs-lookup"><span data-stu-id="01022-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="01022-113">Wenn keine Muster übereinstimmt, wird die Ausnahme der Aufrufliste weitergegeben, bis ein entsprechender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="01022-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="01022-114">Die Typen der von jeder Ausdruck in der Ausnahmehandler zurückgegebenen Werte übereinstimmen der Rückgabetyp der Ausdruck in der `try` Block.</span><span class="sxs-lookup"><span data-stu-id="01022-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="01022-115">In vielen Fällen bedeutet die Tatsache, dass auch ein Fehler aufgetreten ist, dass es keinen gültiger Wert, der die Ausdrücke in jeder Ausnahmehandler zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="01022-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="01022-116">Ein häufig verwendetes Muster ist die Angabe des Ausdrucks ein Optionstyp werden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="01022-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="01022-117">Im folgenden Codebeispiel wird veranschaulicht, dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="01022-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="01022-118">Ausnahmen können Ausnahmen von .NET sein, oder es F#-Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="01022-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="01022-119">Sie können mit F#-Ausnahmen definieren die `exception` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="01022-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="01022-120">Eine Vielzahl von Mustern können Sie den Ausnahmetyp und andere Bedingungen gefiltert; in der folgenden Tabelle werden die Optionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="01022-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="01022-121">Muster</span><span class="sxs-lookup"><span data-stu-id="01022-121">Pattern</span></span>|<span data-ttu-id="01022-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01022-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="01022-123">:?</span><span class="sxs-lookup"><span data-stu-id="01022-123">:?</span></span> <span data-ttu-id="01022-124">*Typ der Ausnahme*</span><span class="sxs-lookup"><span data-stu-id="01022-124">*exception-type*</span></span>|<span data-ttu-id="01022-125">Entspricht den angegebenen .NET Ausnahmetyp an.</span><span class="sxs-lookup"><span data-stu-id="01022-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="01022-126">:?</span><span class="sxs-lookup"><span data-stu-id="01022-126">:?</span></span> <span data-ttu-id="01022-127">*Ausnahmetyp* als *Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="01022-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="01022-128">Entspricht den angegebenen .NET Ausnahmetyp, aber bietet der Ausnahme einen benannten Wert.</span><span class="sxs-lookup"><span data-stu-id="01022-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="01022-129">*Name des Ausnahmefehlers*(*Argumente*)</span><span class="sxs-lookup"><span data-stu-id="01022-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="01022-130">Einen f#-Ausnahmetyp entspricht, und bindet die Argumente.</span><span class="sxs-lookup"><span data-stu-id="01022-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="01022-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="01022-131">*identifier*</span></span>|<span data-ttu-id="01022-132">Entspricht einer beliebigen Ausnahme und bindet den Namen an das Ausnahmeobjekt.</span><span class="sxs-lookup"><span data-stu-id="01022-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="01022-133">Entspricht **:? System.Exception als *** Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="01022-133">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="01022-134">*Bezeichner* Wenn *Bedingung*</span><span class="sxs-lookup"><span data-stu-id="01022-134">*identifier* when *condition*</span></span>|<span data-ttu-id="01022-135">Entspricht einer beliebigen Ausnahme aus, wenn die Bedingung "true" ergibt.</span><span class="sxs-lookup"><span data-stu-id="01022-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="01022-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="01022-136">Examples</span></span>
<span data-ttu-id="01022-137">Die folgenden Codebeispiele veranschaulichen die Verwendung der verschiedenen Ausnahme-Handler-Muster.</span><span class="sxs-lookup"><span data-stu-id="01022-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="01022-138">Die `try...with` Konstrukt ist ein separater Ausdruck aus der `try...finally` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="01022-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="01022-139">Aus diesem Grund Wenn Code sowohl erfordert eine `with` Block und ein `finally` blockieren, müssen die beiden Ausdrücke schachteln.</span><span class="sxs-lookup"><span data-stu-id="01022-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="01022-140">Sie können `try...with` in asynchronen Workflows und anderen Berechnungsausdrücken, in dem Fall wird einer angepassten Version von der `try...with` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01022-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="01022-141">Weitere Informationen finden Sie unter [asynchrone Workflows](../asynchronous-workflows.md), und [Berechnungsausdrücke](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="01022-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="01022-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01022-142">See Also</span></span>
[<span data-ttu-id="01022-143">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="01022-143">Exception Handling</span></span>](index.md)

[<span data-ttu-id="01022-144">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="01022-144">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="01022-145">Ausnahmen: Der `try...finally`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="01022-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
