---
title: ref (C#-Referenz)
ms.date: 2017-05-30
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.assetid: b8a5e59c-907d-4065-b41d-95bf4273c0bd
caps.latest.revision: 32
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
ms.openlocfilehash: 003125ca6218d42a919d8bb592b5454a7cb387c7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ref-c-reference"></a><span data-ttu-id="c0bf6-102">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c0bf6-102">ref (C# Reference)</span></span>

<span data-ttu-id="c0bf6-103">Das `ref`-Schlüsselwort gibt einen Wert an, der als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="c0bf6-104">Es wird in drei unterschiedlichen Kontexten verwendet:</span><span class="sxs-lookup"><span data-stu-id="c0bf6-104">It is used in three different contexts:</span></span> 

- <span data-ttu-id="c0bf6-105">In einer Methodensignatur und in einem Methodenaufruf, um ein Argument an eine Methode als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="c0bf6-106">Weitere Informationen finden Sie unter [Passing an argument by reference](#passing-an-argument-by-reference) (Übergeben eines Arguments als Verweis).</span><span class="sxs-lookup"><span data-stu-id="c0bf6-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>

- <span data-ttu-id="c0bf6-107">In einer Methodensignatur, um einen Wert an den Aufrufer als Verweis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="c0bf6-108">Weitere Informationen finden Sie unter [Verweisrückgabewerte](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="c0bf6-108">See [Reference return values](#reference-return-values) for more information.</span></span>

- <span data-ttu-id="c0bf6-109">In einem Memberkörper, um anzugeben, dass ein Verweisrückgabewert lokal als Verweis, den der Aufrufer ändern möchte, gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify.</span></span> <span data-ttu-id="c0bf6-110">Weitere Informationen finden Sie unter [Lokale ref-Variablen](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="c0bf6-110">See [Ref locals](#ref-locals) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="c0bf6-111">Übergeben eines Arguments als Verweis</span><span class="sxs-lookup"><span data-stu-id="c0bf6-111">Passing an argument by reference</span></span>

<span data-ttu-id="c0bf6-112">In der Parameterliste einer Methode gibt das `ref`-Schlüsselwort an, dass ein Argument als Verweis und nicht als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-112">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="c0bf6-113">Durch das Übergeben als Verweis wird jede Änderung am Argument in der aufgerufenen Methode in der aufrufenden Methode wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-113">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="c0bf6-114">Wenn der Aufrufer z.B. einen lokalen Variablenausdruck oder einen Arrayelement-Zugriffsausdruck übergibt und die aufgerufene Methode das Objekt ersetzt, auf das der ref-Parameter verweist, dann verweist die lokale Variable des Aufrufers oder das Arrayelement jetzt auf das neue Objekt, wenn die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-114">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
>  <span data-ttu-id="c0bf6-115">Verwechseln Sie nicht das Konzept der Übergabe durch einen Verweis mit dem Konzept der Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-115">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="c0bf6-116">Die beiden Konzepte sind nicht identisch.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-116">The two concepts are not the same.</span></span> <span data-ttu-id="c0bf6-117">Ein Methodenparameter kann durch `ref` geändert werden, unabhängig davon, ob es sich um einen Werttyp oder ein Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-117">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="c0bf6-118">Es gibt keine Boxing-Konvertierung eines Werttyps, wenn er durch einen Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-118">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="c0bf6-119">Um einen `ref`-Parameter zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode explizit das Schlüsselwort `ref` verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-119">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

<span data-ttu-id="c0bf6-120">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0bf6-120">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]</span></span>

<span data-ttu-id="c0bf6-121">Ein Argument, das an einen `ref`-Parameter übergeben wird, muss vor der Übergabe initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-121">An argument that is passed to a `ref` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="c0bf6-122">Dies unterscheidet sich von den [out](out.md)-Parametern, deren Argumente nicht explizit initialisiert werden müssen, bevor sie übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-122">This differs from [out](out.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="c0bf6-123">Member einer Klasse können keine Signaturen haben, die sich nur durch `ref` und `out` voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-123">Members of a class can't have signatures that differ only by `ref` and `out`.</span></span> <span data-ttu-id="c0bf6-124">Es tritt ein Compilerfehler auf, wenn der einzige Unterschied zwischen beiden Member eines Typs der ist, dass einer von ihnen über einen `ref`-Parameter und der andere über einen `out`-Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-124">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out` parameter.</span></span> <span data-ttu-id="c0bf6-125">Der folgende Code wird z. B. nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-125">The following code, for example, doesn't compile.</span></span>  
  
 <span data-ttu-id="c0bf6-126">[!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0bf6-126">[!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]</span></span>
  
 <span data-ttu-id="c0bf6-127">Allerdings können Methoden überladen werden, wenn eine Methode einen `ref`- oder `out`-Parameter hat und die andere über einen Werteparameter verfügt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-127">However, methods can be overloaded when one method has a `ref` or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
 <span data-ttu-id="c0bf6-128">[!code-cs[Ref-und-Überladungen](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0bf6-128">[!code-cs[ref-and-overloads](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]</span></span>
  
 <span data-ttu-id="c0bf6-129">In anderen Situationen, die eine Signaturabstimmung benötigen, z. B. beim Ausblenden oder Überschreiben, sind `ref` und `out` Bestandteil der Signatur und passen nicht zueinander.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-129">In other situations that require signature matching, such as hiding or overriding, `ref` and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="c0bf6-130">Eigenschaften sind keine Variablen.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-130">Properties are not variables.</span></span> <span data-ttu-id="c0bf6-131">Sie sind Methoden und können nicht an `ref`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="c0bf6-132">Weitere Informationen zum Übergeben von Arrays finden Sie unter [Übergeben von Arrays mithilfe von „ref“ und „out“](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="c0bf6-132">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="c0bf6-133">Sie können keines der beiden Schlüsselwörter `ref` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c0bf6-133">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="c0bf6-134">Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-134">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="c0bf6-135">Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-135">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  
  
## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="c0bf6-136">Übergeben eines Arguments als Verweis: Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0bf6-136">Passing an argument by reference: An example</span></span>

<span data-ttu-id="c0bf6-137">In den vorherigen Beispielen wurden Werttypen als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-137">The previous examples pass value types by reference.</span></span> <span data-ttu-id="c0bf6-138">Sie können das `ref`-Schlüsselwort auch verwenden, um Verweistypen als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-138">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="c0bf6-139">Die Übergabe eines Verweistyps als Verweis ermöglicht es der aufgerufenen Methode, das Objekt, auf die der Verweisparameter im Aufrufer verweist, zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-139">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="c0bf6-140">Der Speicherort des Objekts wird als Wert des Verweisparameters an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-140">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="c0bf6-141">Wenn Sie den Wert am Speicherort des Parameters ändern (um auf ein neues Objekt zu verweisen), ändern Sie auch den Speicherort, auf den der Aufrufer verweist.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-141">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="c0bf6-142">Im folgenden Beispiel wird eine Instanz eines Verweistyps als ein `ref`-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-142">The following example passes an instance of a reference type as a `ref` parameter.</span></span>   
  
 <span data-ttu-id="c0bf6-143">[!code-cs[Verweise nach Verweisen](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0bf6-143">[!code-cs[ReferencesByRef](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]</span></span>  

<span data-ttu-id="c0bf6-144">Weitere Informationen zum Übergeben von Verweistypen durch einen Wert und durch einen Verweis finden Sie unter [Übergeben von Verweistypparametern](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c0bf6-144">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="c0bf6-145">Verweisrückgabewerte</span><span class="sxs-lookup"><span data-stu-id="c0bf6-145">Reference return values</span></span>

<span data-ttu-id="c0bf6-146">Verweisrückgabewerte (auch ref-Rückgaben genannt) sind Werte, die von einer Methode an den Aufrufer als Verweis zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-146">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="c0bf6-147">Das bedeutet, dass der Aufrufer den von einer Methode zurückgegebenen Wert ändern kann. Diese Änderung wird im Zustand des Objekts, das die Methode enthält, wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-147">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span> 

<span data-ttu-id="c0bf6-148">Ein Verweisrückgabewert wird definiert durch Verwenden des `ref`-Schlüsselworts:</span><span class="sxs-lookup"><span data-stu-id="c0bf6-148">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="c0bf6-149">In der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-149">In the method signature.</span></span> <span data-ttu-id="c0bf6-150">Die folgende Methodensignatur gibt z.B. an, dass die Methode `GetCurrentPrice` den Wert <xref:System.Decimal> als Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-150">For example, the following method signature inidicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- <span data-ttu-id="c0bf6-151">Vor jeder `return`-Anweisung in der Methode.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-151">Before each `return` statement in the method.</span></span> <span data-ttu-id="c0bf6-152">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c0bf6-152">For example:</span></span>
 
   ```csharp
   ref return Decimal.Zero;
   ``` 

<span data-ttu-id="c0bf6-153">Zum Ändern des Zustands des Objekts durch den Aufrufer muss der Verweisrückgabewert in einer Variable gespeichert werden, die explizit als [lokale ref-Variable](#ref-locals) definiert wird.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-153">In order for the caller to modify the an object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span> 

<span data-ttu-id="c0bf6-154">Ein Beispiel finden Sie unter [Beispiel für ref-Rückgaben und lokale ref-Variablen](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="c0bf6-154">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="c0bf6-155">Lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="c0bf6-155">Ref locals</span></span>

<span data-ttu-id="c0bf6-156">Eine lokale ref-Variable wird verwendet, um auf Werte zu verweisen, die mit `ref return` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-156">A ref local variable is used to refer to values returned using `ref return`.</span></span>  <span data-ttu-id="c0bf6-157">Eine lokale ref-Variable muss initialisiert und einem ref-Rückgabewert zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-157">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="c0bf6-158">Jede Änderung am Wert der lokalen ref-Variable wird im Zustand des Objekts wiedergegeben, dessen Methode den Wert als Verweis zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-158">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="c0bf6-159">Eine lokale ref-Variable wird mithilfe des `ref`-Schlüsselworts vor der Variablendeklaration definiert sowie unmittelbar vor dem Aufruf der Methode, die den Wert als Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-159">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span> 

<span data-ttu-id="c0bf6-160">Die folgende Anweisung definiert z.B. eine lokale ref-Variable, die von der Methode `GetEstimatedValue` zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="c0bf6-160">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="c0bf6-161">Beachten Sie, dass das `ref`-Schlüsselwort an beiden Stellen verwendet werden muss. Andernfalls generiert der Compiler den Fehler CS8172 „Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden“.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-161">Note that the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="c0bf6-162">Beispiel für ref-Rückgaben und lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="c0bf6-162">A ref returns and ref locals example</span></span>

<span data-ttu-id="c0bf6-163">Im folgenden Beispiel wird eine `Book`-Klasse mit zwei <xref:System.String>-Feldern definiert: `Title` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-163">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="c0bf6-164">Außerdem wird eine `BookCollection`-Klasse definiert, die ein privates Array von `Book`-Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-164">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="c0bf6-165">Einzelne Buchobjekte werden durch Aufrufen der `GetBookByTitle`-Methode als Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c0bf6-165">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

<span data-ttu-id="c0bf6-166">[!code-cs[csrefRückgaben](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c0bf6-166">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#1)]</span></span>  

<span data-ttu-id="c0bf6-167">Speichert der Aufrufer den von der `GetBookByTitle`-Methode zurückgegeben Wert als lokale ref-Variable, werden Änderungen, die der Aufrufer am Rückgabewert vornimmt, im `BookCollection`-Objekt wiedergegeben. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c0bf6-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

<span data-ttu-id="c0bf6-168">[!code-cs[csrefRückgaben](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="c0bf6-168">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#2)]</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="c0bf6-169">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c0bf6-169">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0bf6-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0bf6-170">See Also</span></span>  
 <span data-ttu-id="c0bf6-171">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bf6-171">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c0bf6-172">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bf6-172">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c0bf6-173">[Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c0bf6-173">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="c0bf6-174">[Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c0bf6-174">[Method Parameters](../../../csharp/language-reference/keywords/method-parameters.md) </span></span>  
 [<span data-ttu-id="c0bf6-175">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c0bf6-175">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

