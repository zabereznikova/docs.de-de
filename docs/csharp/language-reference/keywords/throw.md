---
title: throw (C#-Referenz)
ms.date: 2015-03-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 955f6d87614e0b452ace162e79e34aec9decad54
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="throw-c-reference"></a><span data-ttu-id="66e8c-102">throw (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="66e8c-102">throw (C# Reference)</span></span>
<span data-ttu-id="66e8c-103">Signalisiert das Auftreten einer Ausnahme während der Programmausführung.</span><span class="sxs-lookup"><span data-stu-id="66e8c-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66e8c-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66e8c-104">Remarks</span></span>

<span data-ttu-id="66e8c-105">Die Syntax von `throw` lautet:</span><span class="sxs-lookup"><span data-stu-id="66e8c-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="66e8c-106">Wo `e` eine Instanz einer Klasse ist, die von <xref:System.Exception?displayProperty=fullName> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="66e8c-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=fullName>.</span></span> <span data-ttu-id="66e8c-107">Im folgenden Beispiel wird die `throw`-Anweisung verwendet, um eine @System.IndexOutOfRangeException auszulösen, wenn das Argument, das an eine Methode mit dem Namen `GetNumber` übergeben wurde, nicht auf einen gültigen Index eines internen Arrays reagiert.</span><span class="sxs-lookup"><span data-stu-id="66e8c-107">The following example uses the `throw` statement to throw an @System.IndexOutOfRangeException if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

<span data-ttu-id="66e8c-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="66e8c-108">[!code-cs[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]</span></span>  

<span data-ttu-id="66e8c-109">Methodenaufrufer verwenden anschließend einen `try-catch`- oder `try-catch-finally`-Block, um die ausgelöste Ausnahme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="66e8c-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="66e8c-110">Im folgenden Beispiel wird die Ausnahme behandelt, die von der Methode `GetNumber` ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="66e8c-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

<span data-ttu-id="66e8c-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="66e8c-111">[!code-cs[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]</span></span>  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="66e8c-112">Erneutes Auslösen einer Ausnahme</span><span class="sxs-lookup"><span data-stu-id="66e8c-112">Re-throwing an exception</span></span>

<span data-ttu-id="66e8c-113">`throw` kann auch in einem `catch`-Block verwendet werden, um eine Ausnahme erneut auszulösen, die in einem `catch`-Block behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="66e8c-113">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="66e8c-114">In diesem Fall verwendet `throw` keinen Operanden für die Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="66e8c-114">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="66e8c-115">Es ist besonders hilfreich, wenn eine Methode ein Argument in einer aufrufenden Funktion an eine andere Bibliotheksmethode übergibt, und die Bibliotheksmethode eine Ausnahme auslöst, die an den Aufrufer übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="66e8c-115">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="66e8c-116">Im folgenden Beispiel wird z.B. eine @System.NullReferenceException erneut ausgelöst, die beim Versuch, das erste Zeichen einer deinitialisierten Zeichenfolge abzurufen, ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="66e8c-116">For example, the following example re-throws an @System.NullReferenceException that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

<span data-ttu-id="66e8c-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="66e8c-117">[!code-cs[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="66e8c-118">Sie können auch die `throw e`-Syntax in einem `catch`-Block verwenden, um eine neue Ausnahme zu instanziieren, die Sie an den Aufrufer übergeben.</span><span class="sxs-lookup"><span data-stu-id="66e8c-118">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="66e8c-119">In diesem Fall wird die Stapelüberwachung der ursprünglichen Ausnahme, die von der Eigenschaft @System.Exception.Stacktrace abrufbar ist, nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="66e8c-119">In this case, the stack trace of the original exception, which is available from the @System.Exception.Stacktrace property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="66e8c-120">Der `throw`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="66e8c-120">The `throw` expression</span></span>

<span data-ttu-id="66e8c-121">Ab C# 7 kann `throw` als Ausdruck sowie als Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="66e8c-121">Starting with C# 7, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="66e8c-122">Dadurch wird eine Ausnahme in Kontexten ausgelöst, die zuvor nicht unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="66e8c-122">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="66e8c-123">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="66e8c-123">These include:</span></span>

- <span data-ttu-id="66e8c-124">[Der bedingte Operator](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="66e8c-124">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="66e8c-125">Im folgenden Beispiel wird ein `throw`-Ausdruck verwendet, um eine @System.ArgumentException auszulösen, wenn eine Methode an ein leeres Zeichenfolgenarray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="66e8c-125">The following example uses a `throw` expression to throw an @System.ArgumentException if a method is passed an empty string array.</span></span> <span data-ttu-id="66e8c-126">Diese Logik müsste vor C# 7 in einer `if`/`else`-Anweisung erscheinen.</span><span class="sxs-lookup"><span data-stu-id="66e8c-126">Before C# 7, this logic would need to appear in an `if`/`else` statement.</span></span>

   <span data-ttu-id="66e8c-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="66e8c-127">[!code-cs[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]</span></span>  
  
- <span data-ttu-id="66e8c-128">[Der NULL-Sammeloperator](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="66e8c-128">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="66e8c-129">Im folgenden Beispiel wird eine `throw`-Anweisung mit einem NULL-Sammeloperator verwendet, um eine Ausnahme auszulösen, wenn die Zeichenfolge, die einer Eigenschaft `Name` zugewiesen wurde, `null` ist.</span><span class="sxs-lookup"><span data-stu-id="66e8c-129">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   <span data-ttu-id="66e8c-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="66e8c-130">[!code-cs[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]</span></span>  
 
- <span data-ttu-id="66e8c-131">Ein Ausdruckskörper[lambda](../../lambda-expressions.md) oder eine Ausdruckskörpermethode.</span><span class="sxs-lookup"><span data-stu-id="66e8c-131">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="66e8c-132">Das folgende Beispiel veranschaulicht eine Ausdruckskörpermethode, die eine @System.InvalidCastException auslöst, da eine Konvertierung in einen @System.DateTime-Wert nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="66e8c-132">The following example illustrates an expression-bodied method that throws an @System.InvalidCastException because a conversion to a @System.DateTime value is not supported.</span></span>
 
   <span data-ttu-id="66e8c-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="66e8c-133">[!code-cs[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]</span></span>  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="66e8c-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="66e8c-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66e8c-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66e8c-135">See Also</span></span>  
 <span data-ttu-id="66e8c-136">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="66e8c-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="66e8c-137">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="66e8c-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="66e8c-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="66e8c-138">[try-catch](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="66e8c-139">[Die try-, catch- und throw-Anweisung in C++](../../../csharp/language-reference/keywords/try-catch.md) </span><span class="sxs-lookup"><span data-stu-id="66e8c-139">[The try, catch, and throw Statements in C++](../../../csharp/language-reference/keywords/try-catch.md) </span></span>  
 <span data-ttu-id="66e8c-140">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="66e8c-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="66e8c-141">[Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="66e8c-141">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 [<span data-ttu-id="66e8c-142">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="66e8c-142">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

