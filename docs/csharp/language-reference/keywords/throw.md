---
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
ms.openlocfilehash: 04d3138e3390627355b4b2d4e25c6b00248cec1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398112"
---
# <a name="throw-c-reference"></a><span data-ttu-id="b585b-102">throw (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b585b-102">throw (C# Reference)</span></span>

<span data-ttu-id="b585b-103">Signalisiert das Auftreten einer Ausnahme während der Programmausführung.</span><span class="sxs-lookup"><span data-stu-id="b585b-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b585b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b585b-104">Remarks</span></span>

<span data-ttu-id="b585b-105">Die Syntax von `throw` lautet:</span><span class="sxs-lookup"><span data-stu-id="b585b-105">The syntax of `throw` is:</span></span>

```csharp
throw [e];
```

<span data-ttu-id="b585b-106">Wo `e` eine Instanz einer Klasse ist, die von <xref:System.Exception?displayProperty=nameWithType> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b585b-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b585b-107">Im folgenden Beispiel wird die `throw`-Anweisung verwendet, um eine <xref:System.IndexOutOfRangeException> auszulösen, wenn das Argument, das an eine Methode mit dem Namen `GetNumber` übergeben wurde, nicht auf einen gültigen Index eines internen Arrays reagiert.</span><span class="sxs-lookup"><span data-stu-id="b585b-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

<span data-ttu-id="b585b-108">Methodenaufrufer verwenden anschließend einen `try-catch`- oder `try-catch-finally`-Block, um die ausgelöste Ausnahme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b585b-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="b585b-109">Im folgenden Beispiel wird die Ausnahme behandelt, die von der Methode `GetNumber` ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="b585b-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a><span data-ttu-id="b585b-110">Erneutes Auslösen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="b585b-110">Re-throwing an exception</span></span>

<span data-ttu-id="b585b-111">`throw` kann auch in einem `catch`-Block verwendet werden, um eine Ausnahme erneut auszulösen, die in einem `catch`-Block behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b585b-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="b585b-112">In diesem Fall verwendet `throw` keinen Operanden für die Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="b585b-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="b585b-113">Es ist besonders hilfreich, wenn eine Methode ein Argument in einer aufrufenden Funktion an eine andere Bibliotheksmethode übergibt, und die Bibliotheksmethode eine Ausnahme auslöst, die an den Aufrufer übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="b585b-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="b585b-114">Im folgenden Beispiel wird z.B. eine <xref:System.NullReferenceException> erneut ausgelöst, die beim Versuch, das erste Zeichen einer deinitialisierten Zeichenfolge abzurufen, ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b585b-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span>

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> <span data-ttu-id="b585b-115">Sie können auch die `throw e`-Syntax in einem `catch`-Block verwenden, um eine neue Ausnahme zu instanziieren, die Sie an den Aufrufer übergeben.</span><span class="sxs-lookup"><span data-stu-id="b585b-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="b585b-116">In diesem Fall wird die Stapelüberwachung der ursprünglichen Ausnahme, die von der Eigenschaft <xref:System.Exception.StackTrace> abrufbar ist, nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b585b-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>

## <a name="the-throw-expression"></a><span data-ttu-id="b585b-117">Der `throw`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b585b-117">The `throw` expression</span></span>

<span data-ttu-id="b585b-118">Ab C# 7.0 kann `throw` sowohl als Ausdruck als auch als Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b585b-118">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="b585b-119">Dadurch wird eine Ausnahme in Kontexten ausgelöst, die zuvor nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="b585b-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="b585b-120">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="b585b-120">These include:</span></span>

- <span data-ttu-id="b585b-121">[Der bedingte Operator](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b585b-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="b585b-122">Im folgenden Beispiel wird ein `throw`-Ausdruck verwendet, um eine <xref:System.ArgumentException> auszulösen, wenn eine Methode an ein leeres Zeichenfolgenarray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b585b-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="b585b-123">Diese Logik müsste vor C# 7.0 in einer `if`/`else`-Anweisung erscheinen.</span><span class="sxs-lookup"><span data-stu-id="b585b-123">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- <span data-ttu-id="b585b-124">[Der NULL-Sammeloperator](../operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b585b-124">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="b585b-125">Im folgenden Beispiel wird eine `throw`-Anweisung mit einem NULL-Sammeloperator verwendet, um eine Ausnahme auszulösen, wenn die Zeichenfolge, die einer Eigenschaft `Name` zugewiesen wurde, `null` ist.</span><span class="sxs-lookup"><span data-stu-id="b585b-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- <span data-ttu-id="b585b-126">Ein Ausdruckskörper[lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) oder eine Ausdruckskörpermethode.</span><span class="sxs-lookup"><span data-stu-id="b585b-126">an expression-bodied [lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) or method.</span></span> <span data-ttu-id="b585b-127">Das folgende Beispiel veranschaulicht eine Ausdruckskörpermethode, die eine <xref:System.InvalidCastException> auslöst, da eine Konvertierung in einen <xref:System.DateTime>-Wert nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b585b-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="b585b-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b585b-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b585b-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b585b-129">See also</span></span>

- [<span data-ttu-id="b585b-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b585b-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b585b-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b585b-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b585b-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="b585b-132">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="b585b-133">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b585b-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b585b-134">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b585b-134">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
