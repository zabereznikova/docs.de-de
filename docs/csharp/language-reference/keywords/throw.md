---
description: throw – C#-Referenz
title: throw – C#-Referenz
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
ms.openlocfilehash: 4cad4810b89f976f92ce576917feb2398acce636
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142036"
---
# <a name="throw-c-reference"></a><span data-ttu-id="744c8-103">throw (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="744c8-103">throw (C# Reference)</span></span>

<span data-ttu-id="744c8-104">Signalisiert das Auftreten einer Ausnahme während der Programmausführung.</span><span class="sxs-lookup"><span data-stu-id="744c8-104">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="744c8-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="744c8-105">Remarks</span></span>

<span data-ttu-id="744c8-106">Die Syntax von `throw` lautet:</span><span class="sxs-lookup"><span data-stu-id="744c8-106">The syntax of `throw` is:</span></span>

```csharp
throw [e];
```

<span data-ttu-id="744c8-107">Wo `e` eine Instanz einer Klasse ist, die von <xref:System.Exception?displayProperty=nameWithType> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="744c8-107">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="744c8-108">Im folgenden Beispiel wird die `throw`-Anweisung verwendet, um eine <xref:System.IndexOutOfRangeException> auszulösen, wenn das Argument, das an eine Methode mit dem Namen `GetNumber` übergeben wurde, nicht auf einen gültigen Index eines internen Arrays reagiert.</span><span class="sxs-lookup"><span data-stu-id="744c8-108">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

<span data-ttu-id="744c8-109">Methodenaufrufer verwenden anschließend einen `try-catch`- oder `try-catch-finally`-Block, um die ausgelöste Ausnahme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="744c8-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="744c8-110">Im folgenden Beispiel wird die Ausnahme behandelt, die von der Methode `GetNumber` ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="744c8-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a><span data-ttu-id="744c8-111">Erneutes Auslösen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="744c8-111">Re-throwing an exception</span></span>

<span data-ttu-id="744c8-112">`throw` kann auch in einem `catch`-Block verwendet werden, um eine Ausnahme erneut auszulösen, die in einem `catch`-Block behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="744c8-112">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="744c8-113">In diesem Fall verwendet `throw` keinen Operanden für die Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="744c8-113">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="744c8-114">Es ist besonders hilfreich, wenn eine Methode ein Argument in einer aufrufenden Funktion an eine andere Bibliotheksmethode übergibt, und die Bibliotheksmethode eine Ausnahme auslöst, die an den Aufrufer übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="744c8-114">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="744c8-115">Im folgenden Beispiel wird z.B. eine <xref:System.NullReferenceException> erneut ausgelöst, die beim Versuch, das erste Zeichen einer deinitialisierten Zeichenfolge abzurufen, ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="744c8-115">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span>

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> <span data-ttu-id="744c8-116">Sie können auch die `throw e`-Syntax in einem `catch`-Block verwenden, um eine neue Ausnahme zu instanziieren, die Sie an den Aufrufer übergeben.</span><span class="sxs-lookup"><span data-stu-id="744c8-116">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="744c8-117">In diesem Fall wird die Stapelüberwachung der ursprünglichen Ausnahme, die von der Eigenschaft <xref:System.Exception.StackTrace> abrufbar ist, nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="744c8-117">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>

## <a name="the-throw-expression"></a><span data-ttu-id="744c8-118">Der `throw`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="744c8-118">The `throw` expression</span></span>

<span data-ttu-id="744c8-119">Ab C# 7.0 kann `throw` sowohl als Ausdruck als auch als Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="744c8-119">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="744c8-120">Dadurch wird eine Ausnahme in Kontexten ausgelöst, die zuvor nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="744c8-120">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="744c8-121">Dazu zählen unter anderem folgende Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="744c8-121">These include:</span></span>

- <span data-ttu-id="744c8-122">[Der bedingte Operator](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="744c8-122">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="744c8-123">Im folgenden Beispiel wird ein `throw`-Ausdruck verwendet, um eine <xref:System.ArgumentException> auszulösen, wenn eine Methode an ein leeres Zeichenfolgenarray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="744c8-123">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="744c8-124">Diese Logik müsste vor C# 7.0 in einer `if`/`else`-Anweisung erscheinen.</span><span class="sxs-lookup"><span data-stu-id="744c8-124">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- <span data-ttu-id="744c8-125">[Der NULL-Sammeloperator](../operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="744c8-125">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="744c8-126">Im folgenden Beispiel wird eine `throw`-Anweisung mit einem NULL-Sammeloperator verwendet, um eine Ausnahme auszulösen, wenn die Zeichenfolge, die einer Eigenschaft `Name` zugewiesen wurde, `null` ist.</span><span class="sxs-lookup"><span data-stu-id="744c8-126">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- <span data-ttu-id="744c8-127">Ein Ausdruckskörper[lambda](../operators/lambda-expressions.md) oder eine Ausdruckskörpermethode.</span><span class="sxs-lookup"><span data-stu-id="744c8-127">an expression-bodied [lambda](../operators/lambda-expressions.md) or method.</span></span> <span data-ttu-id="744c8-128">Das folgende Beispiel veranschaulicht eine Ausdruckskörpermethode, die eine <xref:System.InvalidCastException> auslöst, da eine Konvertierung in einen <xref:System.DateTime>-Wert nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="744c8-128">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="744c8-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="744c8-129">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="744c8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="744c8-130">See also</span></span>

- [<span data-ttu-id="744c8-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="744c8-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="744c8-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="744c8-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="744c8-133">try-catch</span><span class="sxs-lookup"><span data-stu-id="744c8-133">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="744c8-134">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="744c8-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="744c8-135">How to: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="744c8-135">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
