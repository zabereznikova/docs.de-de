---
title: "Übergeben von Werttypparametern (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3377630fc4294831f6b9d66a69377aa42d973f1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="fda77-102">Übergeben von Werttypparametern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fda77-102">Passing Value-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="fda77-103">In einer [Werttypvariablen](../../../csharp/language-reference/keywords/value-types.md) sind die Daten direkt enthalten, während eine [Verweistypvariable](../../../csharp/language-reference/keywords/reference-types.md) einen Verweis auf die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="fda77-103">A [value-type](../../../csharp/language-reference/keywords/value-types.md) variable contains its data directly as opposed to a [reference-type](../../../csharp/language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="fda77-104">Wenn eine Werttypvariable als Wert an eine Methode übergeben wird, bedeutet dies die Übergabe einer Kopie der Variablen an die Methode.</span><span class="sxs-lookup"><span data-stu-id="fda77-104">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="fda77-105">Alle Änderungen am Parameter, die innerhalb der Methode erfolgen, haben keine Auswirkung auf die ursprünglichen Daten, die in der Argumentvariable gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="fda77-105">Any changes to the parameter that take place inside the method have no affect on the original data stored in the argument variable.</span></span> <span data-ttu-id="fda77-106">Wenn Sie möchten, dass mit der aufgerufenen Methode der Wert des Parameters geändert wird, müssen Sie ihn als Verweis übergeben, unter Verwendung des Schlüsselworts [ref](../../../csharp/language-reference/keywords/ref.md) oder [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="fda77-106">If you want the called method to change the value of the parameter, you must pass it by reference, using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="fda77-107">Der Einfachheit halber wird im folgenden Beispiel `ref` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fda77-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="fda77-108">Übergeben von Werttypen als Wert</span><span class="sxs-lookup"><span data-stu-id="fda77-108">Passing Value Types by Value</span></span>  
 <span data-ttu-id="fda77-109">Im folgenden Beispiel wird gezeigt, wie Werttypparameter als Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="fda77-109">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="fda77-110">Die Variable `n` wird als Wert an die `SquareIt`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="fda77-110">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="fda77-111">Alle Änderungen, die innerhalb der Methode vorgenommen werden, wirken sich nicht auf den ursprünglichen Wert der Variablen aus.</span><span class="sxs-lookup"><span data-stu-id="fda77-111">Any changes that take place inside the method have no affect on the original value of the variable.</span></span>  
  
 <span data-ttu-id="fda77-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fda77-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="fda77-113">Die Variable `n` ist eine Werttypvariable.</span><span class="sxs-lookup"><span data-stu-id="fda77-113">The variable `n` is a value type.</span></span> <span data-ttu-id="fda77-114">Sie enthält Daten, den Wert `5`.</span><span class="sxs-lookup"><span data-stu-id="fda77-114">It contains its data, the value `5`.</span></span> <span data-ttu-id="fda77-115">Beim Aufruf von `SquareIt` werden die Inhalte von `n` in den Parameter `x` kopiert, der in der Methode quadriert wird.</span><span class="sxs-lookup"><span data-stu-id="fda77-115">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="fda77-116">In `Main` ist der Wert von `n` jedoch auch nach dem Aufruf der `SquareIt`-Methode derselbe wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="fda77-116">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="fda77-117">Die Änderung, die innerhalb der Methode stattfindet, wirkt sich nur auf die lokale Variable `x` aus.</span><span class="sxs-lookup"><span data-stu-id="fda77-117">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="fda77-118">Übergeben von Werttypen als Verweis</span><span class="sxs-lookup"><span data-stu-id="fda77-118">Passing Value Types by Reference</span></span>  
 <span data-ttu-id="fda77-119">Das folgende Beispiel entspricht dem vorhergehenden Beispiel, mit dem Unterschied, dass das Argument als `ref`-Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fda77-119">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="fda77-120">Der Wert des zugrunde liegenden Arguments, `n`, wird geändert, wenn `x` in der Methode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="fda77-120">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 <span data-ttu-id="fda77-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fda77-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="fda77-122">In diesem Beispiel wird nicht der Wert von `n`, sondern ein Verweis auf `n` übergeben.</span><span class="sxs-lookup"><span data-stu-id="fda77-122">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="fda77-123">Der Parameter `x` ist kein [int](../../../csharp/language-reference/keywords/int.md), sondern ein Verweis auf `int` – in diesem Fall ein Verweis auf `n`.</span><span class="sxs-lookup"><span data-stu-id="fda77-123">The parameter `x` is not an [int](../../../csharp/language-reference/keywords/int.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="fda77-124">Beim Quadrieren von `x` innerhalb der Methode wird deshalb tatsächlich das Element quadriert, auf das `x` verweist: `n`.</span><span class="sxs-lookup"><span data-stu-id="fda77-124">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="fda77-125">Austauschen von Werttypen</span><span class="sxs-lookup"><span data-stu-id="fda77-125">Swapping Value Types</span></span>  
 <span data-ttu-id="fda77-126">Ein allgemeines Beispiel zum Ändern der Werte von Argumenten ist eine swap-Methode, bei der Sie zwei Variablen an die Methode übergeben und die Methode deren Inhalte austauscht.</span><span class="sxs-lookup"><span data-stu-id="fda77-126">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="fda77-127">Sie müssen die Argumente als Verweis an die swap-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="fda77-127">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="fda77-128">Andernfalls tauschen Sie lokale Kopien der Parameter innerhalb der Methode aus, und es erfolgt keine Änderung in der aufrufenden Methode.</span><span class="sxs-lookup"><span data-stu-id="fda77-128">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="fda77-129">Im folgenden Beispiel werden ganzzahlige Werte getauscht.</span><span class="sxs-lookup"><span data-stu-id="fda77-129">The following example swaps integer values.</span></span>  
  
 <span data-ttu-id="fda77-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fda77-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="fda77-131">Wenn Sie die `SwapByRef`-Methode aufrufen, verwenden Sie das Schlüsselwort `ref` im Aufruf, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fda77-131">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fda77-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="fda77-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda77-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fda77-133">See Also</span></span>  
 <span data-ttu-id="fda77-134">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fda77-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fda77-135">[Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="fda77-135">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 [<span data-ttu-id="fda77-136">Übergeben von Verweistypparametern</span><span class="sxs-lookup"><span data-stu-id="fda77-136">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)

