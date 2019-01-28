---
title: ref-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 10/24/2018
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: dc19638dc3753132be01235466a98f87bdce4569
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726649"
---
# <a name="ref-c-reference"></a><span data-ttu-id="e83d8-102">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e83d8-102">ref (C# Reference)</span></span>

<span data-ttu-id="e83d8-103">Das `ref`-Schlüsselwort gibt einen Wert an, der als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e83d8-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="e83d8-104">Es wird in vier unterschiedlichen Kontexten verwendet:</span><span class="sxs-lookup"><span data-stu-id="e83d8-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="e83d8-105">In einer Methodensignatur und in einem Methodenaufruf, um ein Argument an eine Methode als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="e83d8-106">Weitere Informationen finden Sie unter [Übergeben eines Arguments als Verweis](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="e83d8-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="e83d8-107">In einer Methodensignatur, um einen Wert an den Aufrufer als Verweis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="e83d8-108">Weitere Informationen finden Sie unter [Verweisrückgabewerte](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="e83d8-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="e83d8-109">In einem Memberkörper, um anzugeben, dass ein Verweisrückgabewert, den der Aufrufer ändern möchte, lokal als Verweis gespeichert ist oder dass eine lokale Variable auf einen anderen Wert per Verweis zugreift.</span><span class="sxs-lookup"><span data-stu-id="e83d8-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="e83d8-110">Weitere Informationen finden Sie unter [Lokale ref-Variablen](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="e83d8-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="e83d8-111">In einer `struct`-Deklaration, um `ref struct` oder `ref readonly struct` zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e83d8-111">In a `struct` declaration to declare a `ref struct` or a `ref readonly struct`.</span></span> <span data-ttu-id="e83d8-112">Weitere Informationen finden Sie unter [ref-Strukturtypen](#ref-struct-types).</span><span class="sxs-lookup"><span data-stu-id="e83d8-112">For more information, see [ref struct types](#ref-struct-types).</span></span>


## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="e83d8-113">Übergeben eines Arguments als Verweis</span><span class="sxs-lookup"><span data-stu-id="e83d8-113">Passing an argument by reference</span></span>

<span data-ttu-id="e83d8-114">In der Parameterliste einer Methode gibt das `ref`-Schlüsselwort an, dass ein Argument als Verweis und nicht als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e83d8-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="e83d8-115">Durch das Übergeben als Verweis wird jede Änderung am Argument in der aufgerufenen Methode in der aufrufenden Methode wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-115">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="e83d8-116">Wenn der Aufrufer z.B. einen lokalen Variablenausdruck oder einen Arrayelement-Zugriffsausdruck übergibt und die aufgerufene Methode das Objekt ersetzt, auf das der ref-Parameter verweist, dann verweist die lokale Variable des Aufrufers oder das Arrayelement jetzt auf das neue Objekt, wenn die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-116">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="e83d8-117">Verwechseln Sie nicht das Konzept der Übergabe durch einen Verweis mit dem Konzept der Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-117">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="e83d8-118">Die beiden Konzepte sind nicht identisch.</span><span class="sxs-lookup"><span data-stu-id="e83d8-118">The two concepts are not the same.</span></span> <span data-ttu-id="e83d8-119">Ein Methodenparameter kann durch `ref` geändert werden, unabhängig davon, ob es sich um einen Werttyp oder ein Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-119">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="e83d8-120">Es gibt keine Boxing-Konvertierung eines Werttyps, wenn er durch einen Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e83d8-120">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="e83d8-121">Um einen `ref`-Parameter zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode explizit das Schlüsselwort `ref` verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-121">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="e83d8-122">Ein Argument, das an einen `ref`- oder `in`-Parameter übergeben wird, muss vor der Übergabe initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-122">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="e83d8-123">Dies unterscheidet sich von den [out](out-parameter-modifier.md)-Parametern, deren Argumente nicht explizit initialisiert werden müssen, bevor sie übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-123">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="e83d8-124">Member einer Klasse können keine Signaturen haben, die sich nur durch `ref`, `in` oder `out` voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-124">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="e83d8-125">Es tritt ein Compilerfehler auf, wenn der einzige Unterschied zwischen beiden Member eines Typs der ist, dass einer von ihnen über einen `ref`-Parameter und der andere über einen `out`- oder `in`-Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-125">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="e83d8-126">Der folgende Code wird z. B. nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="e83d8-126">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="e83d8-127">Allerdings können Methoden überladen werden, wenn eine Methode einen `ref`-, `in`- oder `out`-Parameter hat und die andere wie im folgenden Beispiel dargestellt über einen Werteparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-127">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="e83d8-128">In anderen Situationen, die eine Signaturabstimmung benötigen, z.B. beim Ausblenden oder Überschreiben, sind `in`, `ref` und `out` Bestandteil der Signatur und passen nicht zueinander.</span><span class="sxs-lookup"><span data-stu-id="e83d8-128">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="e83d8-129">Eigenschaften sind keine Variablen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-129">Properties are not variables.</span></span> <span data-ttu-id="e83d8-130">Sie sind Methoden und können nicht an `ref`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-130">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="e83d8-131">Sie können keines der Schlüsselwörter `ref`, `in` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e83d8-131">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="e83d8-132">Asynchrone Methoden, die Sie mit dem [async](async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="e83d8-132">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="e83d8-133">Iterator-Methoden, die eine [yield return](yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="e83d8-133">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="e83d8-134">Übergeben eines Arguments per Verweis: Beispiel</span><span class="sxs-lookup"><span data-stu-id="e83d8-134">Passing an argument by reference: An example</span></span>

<span data-ttu-id="e83d8-135">In den vorherigen Beispielen wurden Werttypen als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-135">The previous examples pass value types by reference.</span></span> <span data-ttu-id="e83d8-136">Sie können das `ref`-Schlüsselwort auch verwenden, um Verweistypen als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-136">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="e83d8-137">Die Übergabe eines Verweistyps als Verweis ermöglicht es der aufgerufenen Methode, das Objekt, auf die der Verweisparameter im Aufrufer verweist, zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-137">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="e83d8-138">Der Speicherort des Objekts wird als Wert des Verweisparameters an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-138">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="e83d8-139">Wenn Sie den Wert am Speicherort des Parameters ändern (um auf ein neues Objekt zu verweisen), ändern Sie auch den Speicherort, auf den der Aufrufer verweist.</span><span class="sxs-lookup"><span data-stu-id="e83d8-139">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="e83d8-140">Im folgenden Beispiel wird eine Instanz eines Verweistyps als ein `ref`-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-140">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="e83d8-141">Weitere Informationen zum Übergeben von Verweistypen durch einen Wert und durch einen Verweis finden Sie unter [Übergeben von Verweistypparametern](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e83d8-141">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="e83d8-142">Verweisrückgabewerte</span><span class="sxs-lookup"><span data-stu-id="e83d8-142">Reference return values</span></span>

<span data-ttu-id="e83d8-143">Verweisrückgabewerte (auch ref-Rückgaben genannt) sind Werte, die von einer Methode an den Aufrufer als Verweis zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-143">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="e83d8-144">Das bedeutet, dass der Aufrufer den von einer Methode zurückgegebenen Wert ändern kann. Diese Änderung wird im Zustand des Objekts, das die Methode enthält, wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-144">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="e83d8-145">Ein Verweisrückgabewert wird definiert durch Verwenden des `ref`-Schlüsselworts:</span><span class="sxs-lookup"><span data-stu-id="e83d8-145">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="e83d8-146">In der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="e83d8-146">In the method signature.</span></span> <span data-ttu-id="e83d8-147">Die folgende Methodensignatur gibt z.B. an, dass die Methode `GetCurrentPrice` den Wert <xref:System.Decimal> nach Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-147">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="e83d8-148">Zwischen dem `return`-Token und der Variable, die in einer `return`-Anweisung in der Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e83d8-148">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="e83d8-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e83d8-149">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="e83d8-150">Zum Ändern des Zustands des Objekts durch den Aufrufer muss der Verweisrückgabewert in einer Variable gespeichert werden, die explizit als [lokale ref-Variable](#ref-locals) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e83d8-150">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="e83d8-151">Die aufgerufene Methode kann den Rückgabewert auch als `ref readonly` deklarieren, um den Wert als Verweis zurückzugeben, und durchsetzen, dass der aufrufende Code den zurückgegebenen Wert nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="e83d8-151">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="e83d8-152">Die aufrufende Methode kann das Kopieren des zurückgegebenen Werts vermeiden, indem sie den Wert in einer lokalen [schreibgeschützten ref-Variablen](#ref-readonly-locals) speichert.</span><span class="sxs-lookup"><span data-stu-id="e83d8-152">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="e83d8-153">Ein Beispiel finden Sie unter [Beispiel für ref-Rückgaben und lokale ref-Variablen](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="e83d8-153">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="e83d8-154">Lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="e83d8-154">Ref locals</span></span>

<span data-ttu-id="e83d8-155">Eine lokale ref-Variable wird verwendet, um auf Werte zu verweisen, die mit `return ref` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-155">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="e83d8-156">Eine lokale ref-Variable kann nicht für einen nicht ref-Rückgabewert initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-156">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="e83d8-157">Das heißt, die rechte Seite der Initialisierung muss ein Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="e83d8-157">In other words, the right hand side of the initialization must be a reference.</span></span> <span data-ttu-id="e83d8-158">Jede Änderung am Wert der lokalen ref-Variable wird im Zustand des Objekts wiedergegeben, dessen Methode den Wert als Verweis zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="e83d8-158">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="e83d8-159">Eine lokale ref-Variable wird mithilfe des `ref`-Schlüsselworts vor der Variablendeklaration definiert sowie unmittelbar vor dem Aufruf der Methode, die den Wert als Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-159">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="e83d8-160">Die folgende Anweisung definiert z.B. eine lokale ref-Variable, die von der Methode `GetEstimatedValue` zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="e83d8-160">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="e83d8-161">Auch auf Werte können Sie per Verweis zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-161">You can access a value by reference in the same way.</span></span> <span data-ttu-id="e83d8-162">In einigen Fällen erhöht dies die Leistung, da ein möglicherweise aufwendiger Kopiervorgang vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="e83d8-162">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="e83d8-163">In der folgenden Anweisung wird z.B. gezeigt, wie ein lokaler Verweiswert definiert wird, mit dem auf einen Wert verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e83d8-163">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="e83d8-164">Beachten Sie, dass das `ref`-Schlüsselwort in beiden Beispielen an beiden Stellen verwendet werden muss. Andernfalls generiert der Compiler den Fehler CS8172 "Cannot initialize a by-reference variable with a value." (Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden).</span><span class="sxs-lookup"><span data-stu-id="e83d8-164">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="e83d8-165">Beginnend mit C# 7.3 kann die Iterationsvariable der `foreach`-Anweisung eine lokale ref-Variable oder schreibgeschützte lokale ref-Variable sein.</span><span class="sxs-lookup"><span data-stu-id="e83d8-165">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="e83d8-166">Weitere Informationen finden Sie im Artikel zur [foreach-Anweisung](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="e83d8-166">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="e83d8-167">Lokale schreibgeschützte ref-Variable</span><span class="sxs-lookup"><span data-stu-id="e83d8-167">Ref readonly locals</span></span>

<span data-ttu-id="e83d8-168">Mit einer lokalen schreibgeschützten ref-Variablen können Sie auf Werte verweisen, die von der Methode oder Eigenschaft zurückgegeben werden, die `ref readonly` in der Signatur enthält und `return ref` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e83d8-168">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="e83d8-169">Eine `ref readonly`-Variable kombiniert die Eigenschaften einer lokalen `ref`-Variablen mit einer `readonly`-Variablen: Sie ist ein Alias für den Speicher, dem sie zugewiesen ist, und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-169">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span> 

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="e83d8-170">Beispiel für ref-Rückgaben und lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="e83d8-170">A ref returns and ref locals example</span></span>

<span data-ttu-id="e83d8-171">Im folgenden Beispiel wird eine `Book`-Klasse mit zwei <xref:System.String>-Feldern definiert: `Title` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="e83d8-171">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="e83d8-172">Außerdem wird eine `BookCollection`-Klasse definiert, die ein privates Array von `Book`-Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="e83d8-172">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="e83d8-173">Einzelne Buchobjekte werden durch Aufrufen der `GetBookByTitle`-Methode als Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-173">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="e83d8-174">Speichert der Aufrufer den von der `GetBookByTitle`-Methode zurückgegeben Wert als lokale ref-Variable, werden Änderungen, die der Aufrufer am Rückgabewert vornimmt, im `BookCollection`-Objekt wiedergegeben. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e83d8-174">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a><span data-ttu-id="e83d8-175">ref-Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="e83d8-175">Ref struct types</span></span>

<span data-ttu-id="e83d8-176">Das Hinzufügen des `ref`-Modifizierers zu einer `struct`-Deklaration definiert, dass Instanzen dieses Typs stapelzugeordnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-176">Adding the `ref` modifier to a `struct` declaration defines that instances of that type must be stack allocated.</span></span> <span data-ttu-id="e83d8-177">Das bedeutet, Instanzen dieses Typs können nie im Heap als Member einer anderen Klasse erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e83d8-177">In other words, instances of these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="e83d8-178">Der primäre Beweggrund für dieses Feature waren <xref:System.Span%601> und zugehörige Strukturen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-178">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span>

<span data-ttu-id="e83d8-179">Das Ziel, einen `ref struct`-Typ als im Stapel zugewiesene Variable zu behalten, führt zu verschiedenen Regeln, die der Compiler für alle `ref struct`-Typen erzwingt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-179">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="e83d8-180">Sie können für `ref struct` kein Boxing durchführen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-180">You can't box a `ref struct`.</span></span> <span data-ttu-id="e83d8-181">Sie können einen `ref struct`-Typ nicht einer Variablen vom Typ `object`, `dynamic` oder einem Schnittstellentyp zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-181">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="e83d8-182">`ref struct`-Typen können keine Schnittstellen implementieren.</span><span class="sxs-lookup"><span data-stu-id="e83d8-182">`ref struct` types cannot implement interfaces.</span></span>
- <span data-ttu-id="e83d8-183">Sie können `ref struct` nicht als Member einer Klasse oder einer normalen Struktur deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e83d8-183">You can't declare a `ref struct` as a member of a class or a normal struct.</span></span>
- <span data-ttu-id="e83d8-184">Sie können keine lokalen Variablen deklarieren, bei denen es sich um `ref struct`-Typen in asynchronen Methoden handelt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-184">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="e83d8-185">Sie können sie in synchronen Methoden deklarieren, die <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> oder `Task`-ähnliche Typen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e83d8-185">You can declare them in synchronous methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> or `Task`-like types.</span></span>
- <span data-ttu-id="e83d8-186">Sie können lokale `ref struct`-Variablen nicht in Iteratoren deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e83d8-186">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="e83d8-187">Sie können `ref struct`-Variablen nicht in Lambda-Ausdrücken oder lokalen Funktionen erfassen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-187">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="e83d8-188">Diese Einschränkungen stellen sicher, dass Sie `ref struct` nicht versehentlich in einer Weise verwenden, die zu einer Höherstufung in den verwalteten Heap führt.</span><span class="sxs-lookup"><span data-stu-id="e83d8-188">These restrictions ensure you don't accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

<span data-ttu-id="e83d8-189">Sie können Modifizierer zum Deklarieren einer Struktur als `readonly ref` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e83d8-189">You can combine modifiers to declare a struct as `readonly ref`.</span></span> <span data-ttu-id="e83d8-190">`readonly ref struct` vereint die Vorteile und Einschränkungen der `ref struct`- und `readonly struct`-Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="e83d8-190">A `readonly ref struct` combines the benefits and restrictions of `ref struct` and `readonly struct` declarations.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e83d8-191">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e83d8-191">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e83d8-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e83d8-192">See also</span></span>

- [<span data-ttu-id="e83d8-193">Schreiben von sicherem und effizientem Code</span><span class="sxs-lookup"><span data-stu-id="e83d8-193">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="e83d8-194">Ref-Rückgabetypen und lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="e83d8-194">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="e83d8-195">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e83d8-195">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="e83d8-196">ref-Zuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="e83d8-196">ref assignment operator</span></span>](../operators/assignment-operator.md#ref-assignment-operator)
- [<span data-ttu-id="e83d8-197">Übergeben von Parametern</span><span class="sxs-lookup"><span data-stu-id="e83d8-197">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="e83d8-198">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="e83d8-198">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="e83d8-199">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e83d8-199">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e83d8-200">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e83d8-200">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e83d8-201">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e83d8-201">C# Keywords</span></span>](index.md)
