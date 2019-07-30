---
title: 'Ausnahmen: Der try...with-Ausdruck'
description: Erfahren Sie, wie Sie F# "Try... with ' Ausdruck für die Ausnahmebehandlung.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630245"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="74661-103">Ausnahmen: Der try...with-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="74661-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="74661-104">In diesem Thema wird beschrieben, die `try...with` Ausdruck, der Ausdruck, der für die Ausnahmebehandlung in der Sprache F# verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="74661-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="74661-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74661-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="74661-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74661-106">Remarks</span></span>

<span data-ttu-id="74661-107">Der `try...with` Ausdruck wird zum Behandeln von Ausnahmen in F#verwendet.</span><span class="sxs-lookup"><span data-stu-id="74661-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="74661-108">Sie ähnelt der `try...catch` -Anweisung in. C#</span><span class="sxs-lookup"><span data-stu-id="74661-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="74661-109">In der vorangehenden Syntax generiert der Code in *expression1* möglicherweise eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="74661-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="74661-110">Der `try...with` Ausdruck gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="74661-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="74661-111">Wenn keine Ausnahme ausgelöst wird, gibt der gesamte Ausdruck den Wert von *expression1*zurück.</span><span class="sxs-lookup"><span data-stu-id="74661-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="74661-112">Wenn eine Ausnahme ausgelöst wird, wird jedes *Muster* wiederum mit der Ausnahme verglichen, und für das erste übereinstimmende Muster wird der entsprechende *Ausdruck*, der als *Ausnahmehandler*bezeichnet wird, für diesen Branch ausgeführt und der allgemeine Ausdruck Gibt den Wert des Ausdrucks in diesem Ausnahmehandler zurück.</span><span class="sxs-lookup"><span data-stu-id="74661-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="74661-113">Wenn kein Muster übereinstimmt, wird die aufrufsstapel von der Ausnahme weitergegeben, bis ein übereinstimmender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="74661-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="74661-114">Die Typen der Werte, die von jedem Ausdruck in den Ausnahme Handlern zurückgegeben werden, müssen mit dem Typ identisch sein `try` , der vom Ausdruck im-Block zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="74661-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="74661-115">Häufig bedeutet die Tatsache, dass ein Fehler aufgetreten ist, dass es keinen gültigen Wert gibt, der von den Ausdrücken in den einzelnen Ausnahme Handlern zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="74661-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="74661-116">Ein häufiges Muster ist, dass der Typ des Ausdrucks ein Optionstyp ist.</span><span class="sxs-lookup"><span data-stu-id="74661-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="74661-117">Dieses Muster wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="74661-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="74661-118">Ausnahmen können .NET-Ausnahmen oder F# Ausnahmen sein.</span><span class="sxs-lookup"><span data-stu-id="74661-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="74661-119">Ausnahmen können mithilfe F# des `exception` -Schlüssel Worts definiert werden.</span><span class="sxs-lookup"><span data-stu-id="74661-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="74661-120">Sie können eine Vielzahl von Mustern verwenden, um nach dem Ausnahmetyp und anderen Bedingungen zu filtern. die Optionen sind in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="74661-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="74661-121">Muster</span><span class="sxs-lookup"><span data-stu-id="74661-121">Pattern</span></span>|<span data-ttu-id="74661-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74661-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="74661-123">:?</span><span class="sxs-lookup"><span data-stu-id="74661-123">:?</span></span> <span data-ttu-id="74661-124">*Ausnahmetyp*</span><span class="sxs-lookup"><span data-stu-id="74661-124">*exception-type*</span></span>|<span data-ttu-id="74661-125">Entspricht dem angegebenen .net-Ausnahmetyp.</span><span class="sxs-lookup"><span data-stu-id="74661-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="74661-126">:?</span><span class="sxs-lookup"><span data-stu-id="74661-126">:?</span></span> <span data-ttu-id="74661-127">*Exception-Typ* als *Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="74661-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="74661-128">Entspricht dem angegebenen .net-Ausnahmetyp, gibt jedoch der Ausnahme einen benannten Wert.</span><span class="sxs-lookup"><span data-stu-id="74661-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="74661-129">*Ausnahme Name* (*Argumente*)</span><span class="sxs-lookup"><span data-stu-id="74661-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="74661-130">Entspricht einem F# Ausnahmetyp und bindet die Argumente.</span><span class="sxs-lookup"><span data-stu-id="74661-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="74661-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="74661-131">*identifier*</span></span>|<span data-ttu-id="74661-132">Findet eine Übereinstimmung mit jeder Ausnahme und bindet den Namen an das Ausnahme Objekt.</span><span class="sxs-lookup"><span data-stu-id="74661-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="74661-133">Äquivalent zu **:? System. Exception als**_Bezeichner_</span><span class="sxs-lookup"><span data-stu-id="74661-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="74661-134">*Bezeichner* , wenn *Bedingung*</span><span class="sxs-lookup"><span data-stu-id="74661-134">*identifier* when *condition*</span></span>|<span data-ttu-id="74661-135">Findet eine Übereinstimmung mit jeder Ausnahme, wenn die Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="74661-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="74661-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="74661-136">Examples</span></span>

<span data-ttu-id="74661-137">Die folgenden Codebeispiele veranschaulichen die Verwendung der verschiedenen Ausnahmehandler.</span><span class="sxs-lookup"><span data-stu-id="74661-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="74661-138">Das `try...with` Konstrukt ist ein separater Ausdruck aus dem `try...finally` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="74661-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="74661-139">Wenn Ihr Code also sowohl einen `with` -Block als auch einen `finally` -Block erfordert, müssen Sie die beiden Ausdrücke verschachteln.</span><span class="sxs-lookup"><span data-stu-id="74661-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="74661-140">Sie können in `try...with` asynchronen Workflows und anderen Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `try...with` des Ausdrucks verwendet.</span><span class="sxs-lookup"><span data-stu-id="74661-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="74661-141">Weitere Informationen finden Sie unter [asynchrone Workflows](../asynchronous-workflows.md)und [Berechnungs Ausdrücke](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="74661-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74661-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74661-142">See also</span></span>

- [<span data-ttu-id="74661-143">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="74661-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="74661-144">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="74661-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="74661-145">Ausnahmen: Der `try...finally` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="74661-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
