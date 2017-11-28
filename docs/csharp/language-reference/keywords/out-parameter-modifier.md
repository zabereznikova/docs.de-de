---
title: "Modifizierer für out-Parameter (C#-Verweis)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 68ef554f95fe71f925cfa22cc49758cec3da237e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="ed5f1-102">Modifizierer für out-Parameter (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="ed5f1-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="ed5f1-103">Das Schlüsselwort `out` bewirkt, dass Argumente per Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="ed5f1-104">Dies entspricht dem Schlüsselwort [ref](../../../csharp/language-reference/keywords/ref.md), mit Ausnahme davon, dass bei `ref` die Variable initialisiert sein muss, bevor sie übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="ed5f1-105">Um einen Parameter `out` zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode das Schlüsselwort `out` explizit verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="ed5f1-106">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ed5f1-106">For example:</span></span>  
  
 [!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> <span data-ttu-id="ed5f1-107">Das Schlüsselwort `out` kann auch mit einem generischen Typparameter verwendet werden, um anzugeben, dass der Typparameter kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-107">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="ed5f1-108">Weitere Informationen zur Verwendung des Schlüsselworts `out` in diesem Kontext finden Sie unter [out (generischer Modifizierer)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="ed5f1-108">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="ed5f1-109">Variablen, die als `out`-Argumente übergeben wurden, müssen nicht initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-109">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="ed5f1-110">Die aufgerufene Methode ist jedoch erforderlich, um einen Wert zuzuweisen, bevor die Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-110">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="ed5f1-111">Obwohl die Schlüsselwörter `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-111">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="ed5f1-112">Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`-Argument übernimmt und die andere ein `out`-Argument.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="ed5f1-113">Der folgende Code wird z. B. nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="ed5f1-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="ed5f1-114">Überladen ist legal; wenn jedoch eine Methode ein `ref`- oder `out`-Argument übernimmt und die andere keines der beiden, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ed5f1-114">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 <span data-ttu-id="ed5f1-115">Eigenschaften sind keine Variablen und können daher nicht als `out`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-115">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="ed5f1-116">Weitere Informationen zum Übergeben von Arrays finden Sie unter [Übergeben von Arrays mit „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="ed5f1-116">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="ed5f1-117">Sie können keines der beiden Schlüsselwörter `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ed5f1-117">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="ed5f1-118">Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-118">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="ed5f1-119">Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-119">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="ed5f1-120">Deklarieren von `out`-Argumenten</span><span class="sxs-lookup"><span data-stu-id="ed5f1-120">Declaring `out` arguments</span></span>   

 <span data-ttu-id="ed5f1-121">Das Deklarieren einer Methode mit `out`-Argumenten ist nützlich, wenn eine Methode mehrere Werte zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-121">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="ed5f1-122">Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-122">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="ed5f1-123">Beachten Sie, dass das dritte Argument Null zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-123">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="ed5f1-124">Dadurch können Methoden Werte optional zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-124">This enables methods to return values optionally.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 <span data-ttu-id="ed5f1-125">Das [Try-Muster](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) umfasst die Rückgabe eines `bool`, um anzugeben, ob ein Vorgang erfolgreich war oder fehlschlug, und die Rückgabe des Werts, der durch den Vorgang in einem `out`-Argument erzeugt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-125">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="ed5f1-126">Eine Reihe von Analysemethoden, z.B. [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@))), verwendet dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-126">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="ed5f1-127">Aufrufen einer Methode mit einem `out`-Argument</span><span class="sxs-lookup"><span data-stu-id="ed5f1-127">Calling a method with an `out` argument</span></span>

<span data-ttu-id="ed5f1-128">In C# 6 und früheren Versionen müssen Sie eine Variable in einer separaten Anweisung deklarieren, bevor Sie es als ein `out`-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-128">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="ed5f1-129">Das folgende Beispiel deklariert eine Variable namens `number`, bevor sie an die Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) übergeben wird, die versucht, eine Zeichenfolge in eine Zahl umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-129">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

<span data-ttu-id="ed5f1-130">Ab C# 7 können Sie in der Argumentliste des Methodenaufrufs anstatt in einer separaten Variablendeklaration die `out`-Variable deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-130">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="ed5f1-131">Dies erzeugt kompakteren, lesbaren Code und verhindert auch, dass Sie versehentlich der Variable vor dem Aufruf der Methode einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-131">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="ed5f1-132">Das folgende Beispiel ähnelt dem vorherigen Beispiel, außer dass es die `number`-Variable im Aufruf der Methode [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@))) definiert.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-132">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
<span data-ttu-id="ed5f1-133">Im vorherigen Beispiel ist die `number`-Variable stark als `int` typisiert.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-133">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="ed5f1-134">Sie können auch eine implizit typisierte lokale Variable deklarieren, wie es im folgenden Beispiel getan wird.</span><span class="sxs-lookup"><span data-stu-id="ed5f1-134">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 [!code-csharp[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a><span data-ttu-id="ed5f1-135">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ed5f1-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed5f1-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed5f1-136">See Also</span></span>  
 [<span data-ttu-id="ed5f1-137">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ed5f1-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ed5f1-138">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed5f1-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ed5f1-139">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ed5f1-139">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ed5f1-140">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="ed5f1-140">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
