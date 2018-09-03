---
title: throw (C#-Referenz)
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 831c4cce14e902697d84129e54cc54f07d26b9f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43417357"
---
# <a name="throw-c-reference"></a><span data-ttu-id="fd3af-102">throw (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fd3af-102">throw (C# Reference)</span></span>
<span data-ttu-id="fd3af-103">Signalisiert das Auftreten einer Ausnahme während der Programmausführung.</span><span class="sxs-lookup"><span data-stu-id="fd3af-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd3af-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd3af-104">Remarks</span></span>

<span data-ttu-id="fd3af-105">Die Syntax von `throw` lautet:</span><span class="sxs-lookup"><span data-stu-id="fd3af-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="fd3af-106">Wo `e` eine Instanz einer Klasse ist, die von <xref:System.Exception?displayProperty=nameWithType> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="fd3af-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fd3af-107">Im folgenden Beispiel wird die `throw`-Anweisung verwendet, um eine <xref:System.IndexOutOfRangeException> auszulösen, wenn das Argument, das an eine Methode mit dem Namen `GetNumber` übergeben wurde, nicht auf einen gültigen Index eines internen Arrays reagiert.</span><span class="sxs-lookup"><span data-stu-id="fd3af-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

<span data-ttu-id="fd3af-108">Methodenaufrufer verwenden anschließend einen `try-catch`- oder `try-catch-finally`-Block, um die ausgelöste Ausnahme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="fd3af-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="fd3af-109">Im folgenden Beispiel wird die Ausnahme behandelt, die von der Methode `GetNumber` ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="fd3af-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="fd3af-110">Erneutes Auslösen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="fd3af-110">Re-throwing an exception</span></span>

<span data-ttu-id="fd3af-111">`throw` kann auch in einem `catch`-Block verwendet werden, um eine Ausnahme erneut auszulösen, die in einem `catch`-Block behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="fd3af-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="fd3af-112">In diesem Fall verwendet `throw` keinen Operanden für die Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="fd3af-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="fd3af-113">Es ist besonders hilfreich, wenn eine Methode ein Argument in einer aufrufenden Funktion an eine andere Bibliotheksmethode übergibt, und die Bibliotheksmethode eine Ausnahme auslöst, die an den Aufrufer übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="fd3af-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="fd3af-114">Im folgenden Beispiel wird z.B. eine <xref:System.NullReferenceException> erneut ausgelöst, die beim Versuch, das erste Zeichen einer deinitialisierten Zeichenfolge abzurufen, ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="fd3af-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> <span data-ttu-id="fd3af-115">Sie können auch die `throw e`-Syntax in einem `catch`-Block verwenden, um eine neue Ausnahme zu instanziieren, die Sie an den Aufrufer übergeben.</span><span class="sxs-lookup"><span data-stu-id="fd3af-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="fd3af-116">In diesem Fall wird die Stapelüberwachung der ursprünglichen Ausnahme, die von der Eigenschaft <xref:System.Exception.StackTrace> abrufbar ist, nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fd3af-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="fd3af-117">Der `throw`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="fd3af-117">The `throw` expression</span></span>

<span data-ttu-id="fd3af-118">Ab C# 7.0 kann `throw` sowohl als Ausdruck als auch als Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd3af-118">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="fd3af-119">Dadurch wird eine Ausnahme in Kontexten ausgelöst, die zuvor nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="fd3af-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="fd3af-120">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="fd3af-120">These include:</span></span>

- <span data-ttu-id="fd3af-121">[Der bedingte Operator](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fd3af-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="fd3af-122">Im folgenden Beispiel wird ein `throw`-Ausdruck verwendet, um eine <xref:System.ArgumentException> auszulösen, wenn eine Methode an ein leeres Zeichenfolgenarray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fd3af-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="fd3af-123">Diese Logik müsste vor C# 7.0 in einer `if`/`else`-Anweisung erscheinen.</span><span class="sxs-lookup"><span data-stu-id="fd3af-123">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- <span data-ttu-id="fd3af-124">[Der NULL-Sammeloperator](../operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fd3af-124">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="fd3af-125">Im folgenden Beispiel wird eine `throw`-Anweisung mit einem NULL-Sammeloperator verwendet, um eine Ausnahme auszulösen, wenn die Zeichenfolge, die einer Eigenschaft `Name` zugewiesen wurde, `null` ist.</span><span class="sxs-lookup"><span data-stu-id="fd3af-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- <span data-ttu-id="fd3af-126">Ein Ausdruckskörper[lambda](../../lambda-expressions.md) oder eine Ausdruckskörpermethode.</span><span class="sxs-lookup"><span data-stu-id="fd3af-126">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="fd3af-127">Das folgende Beispiel veranschaulicht eine Ausdruckskörpermethode, die eine <xref:System.InvalidCastException> auslöst, da eine Konvertierung in einen <xref:System.DateTime>-Wert nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="fd3af-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="fd3af-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="fd3af-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fd3af-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd3af-129">See Also</span></span>

- [<span data-ttu-id="fd3af-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fd3af-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="fd3af-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fd3af-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="fd3af-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="fd3af-132">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
- [<span data-ttu-id="fd3af-133">The try, catch, and throw Statements in C++ (Die Anweisungen „try“, „catch“ und „throw“ in C++)</span><span class="sxs-lookup"><span data-stu-id="fd3af-133">The try, catch, and throw Statements in C++</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
- [<span data-ttu-id="fd3af-134">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fd3af-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="fd3af-135">Ausnahmebehandlungsanweisungen</span><span class="sxs-lookup"><span data-stu-id="fd3af-135">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
- [<span data-ttu-id="fd3af-136">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="fd3af-136">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
