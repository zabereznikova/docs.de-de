---
title: 'Ausnahmen: Der try...with-Ausdruck (F#)'
description: Erfahren Sie, wie der F#-"try...with-" Ausdruck für die Ausnahmebehandlung zu verwenden.
ms.date: 05/16/2016
ms.openlocfilehash: 588960c0f8ccedb431c37d0f1314bf1a293b638c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042165"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="e4543-103">Ausnahmen: Der try...with-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e4543-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="e4543-104">In diesem Thema wird beschrieben, die `try...with` Ausdruck, der Ausdruck, der für die Ausnahmebehandlung in der Sprache f# verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4543-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4543-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4543-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="e4543-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4543-106">Remarks</span></span>

<span data-ttu-id="e4543-107">Die `try...with` Ausdruck wird verwendet, um die Behandlung von Ausnahmen in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="e4543-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="e4543-108">Es ähnelt der `try...catch` -Anweisung in c#.</span><span class="sxs-lookup"><span data-stu-id="e4543-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="e4543-109">In der vorherigen Syntax wird der Code in *expression1* möglicherweise eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="e4543-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="e4543-110">Die `try...with` Ausdruck gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="e4543-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="e4543-111">Wenn keine Ausnahme ausgelöst wird, wird der gesamte Ausdruck gibt den Wert der *expression1*.</span><span class="sxs-lookup"><span data-stu-id="e4543-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="e4543-112">Wenn eine Ausnahme ausgelöst wird, jede *Muster* wiederum verglichen wird, mit der Ausnahme und für das erste übereinstimmende Muster, die den entsprechenden *Ausdruck*, bekannt als die *Ausnahmehandler*für diesen Branch ausgeführt wird und der gesamte Ausdruck den Wert des Ausdrucks, in dieser Ausnahmehandler gibt.</span><span class="sxs-lookup"><span data-stu-id="e4543-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="e4543-113">Wenn keine übereinstimmt, wird die Ausnahme der Aufrufliste nach oben weitergegeben, bis ein entsprechender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e4543-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="e4543-114">Die Typen der von jeder Ausdruck in die Ausnahmehandler zurückgegebenen Werte müssen der Rückgabetyp der Ausdruck in übereinstimmen der `try` Block.</span><span class="sxs-lookup"><span data-stu-id="e4543-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="e4543-115">In vielen Fällen bedeutet die Tatsache, dass Fehler auch, dass es keinen gültiger Wert, der die Ausdrücke in jeder Ausnahmehandler zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4543-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="e4543-116">Ein häufig verwendetes Muster ist der Typ des Ausdrucks ein Optionstyp werden.</span><span class="sxs-lookup"><span data-stu-id="e4543-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="e4543-117">Das folgende Codebeispiel veranschaulicht dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="e4543-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="e4543-118">Ausnahmen können .NET Ausnahmen sein, oder sie können die F#-Ausnahmen werden.</span><span class="sxs-lookup"><span data-stu-id="e4543-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="e4543-119">Sie können die F#-Ausnahmen definieren, mit der `exception` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e4543-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="e4543-120">Eine Vielzahl von Mustern können Sie den Ausnahmetyp und andere Bedingungen filtern; die Optionen werden in der folgenden Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="e4543-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="e4543-121">Muster</span><span class="sxs-lookup"><span data-stu-id="e4543-121">Pattern</span></span>|<span data-ttu-id="e4543-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4543-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="e4543-123">:?</span><span class="sxs-lookup"><span data-stu-id="e4543-123">:?</span></span> <span data-ttu-id="e4543-124">*Typ der Ausnahme*</span><span class="sxs-lookup"><span data-stu-id="e4543-124">*exception-type*</span></span>|<span data-ttu-id="e4543-125">Entspricht den angegebenen Ausnahmetyp von .NET.</span><span class="sxs-lookup"><span data-stu-id="e4543-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="e4543-126">:?</span><span class="sxs-lookup"><span data-stu-id="e4543-126">:?</span></span> <span data-ttu-id="e4543-127">*Typ der Ausnahme* als *Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="e4543-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="e4543-128">Mit der angegebenen Ausnahme .NET Typ übereinstimmt, doch bieten der Ausnahme einen benannten Wert.</span><span class="sxs-lookup"><span data-stu-id="e4543-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="e4543-129">*Ausnahme-Name*(*Argumente*)</span><span class="sxs-lookup"><span data-stu-id="e4543-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="e4543-130">Einen F#-Ausnahmetyp entspricht, und bindet die Argumente.</span><span class="sxs-lookup"><span data-stu-id="e4543-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="e4543-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="e4543-131">*identifier*</span></span>|<span data-ttu-id="e4543-132">Entspricht einer beliebigen Ausnahme aus, und bindet den Namen an das Ausnahmeobjekt.</span><span class="sxs-lookup"><span data-stu-id="e4543-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="e4543-133">Äquivalent zu \**:? System.Exception als \*\*\* Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="e4543-133">Equivalent to \**:? System.Exception as\*\*\*identifier*</span></span>|
|<span data-ttu-id="e4543-134">*Bezeichner* beim *Bedingung*</span><span class="sxs-lookup"><span data-stu-id="e4543-134">*identifier* when *condition*</span></span>|<span data-ttu-id="e4543-135">Entspricht einer beliebigen Ausnahme aus, wenn die Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="e4543-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="e4543-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e4543-136">Examples</span></span>

<span data-ttu-id="e4543-137">Die folgenden Codebeispiele veranschaulichen die Verwendung der verschiedenen Ausnahme-Handler-Muster.</span><span class="sxs-lookup"><span data-stu-id="e4543-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

>[!NOTE]
<span data-ttu-id="e4543-138">Die `try...with` Konstrukt ist ein separater Ausdruck aus der `try...finally` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e4543-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="e4543-139">Aus diesem Grund Wenn der Code sowohl erfordert eine `with` Block und ein `finally` blockieren, müssen Sie die beiden Ausdrücke schachteln.</span><span class="sxs-lookup"><span data-stu-id="e4543-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE]
<span data-ttu-id="e4543-140">Sie können `try...with` in asynchronen Workflows und anderen Berechnungsausdrücken, in dem Fall einer angepassten Version von der `try...with` Ausdruck wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4543-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="e4543-141">Weitere Informationen finden Sie unter [asynchrone Workflows](../asynchronous-workflows.md), und [Berechnungsausdrücke](../computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e4543-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4543-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4543-142">See also</span></span>

- [<span data-ttu-id="e4543-143">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="e4543-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="e4543-144">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="e4543-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="e4543-145">Ausnahmen: Der `try...finally`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e4543-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
