---
description: ref-Schlüsselwort – C#-Referenz
title: ref-Schlüsselwort – C#-Referenz
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: d2855738c723ba6d2437257793f18349b18629dc
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877586"
---
# <a name="ref-c-reference"></a><span data-ttu-id="f9710-103">ref (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f9710-103">ref (C# Reference)</span></span>

<span data-ttu-id="f9710-104">Das `ref`-Schlüsselwort gibt einen Wert an, der als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9710-104">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="f9710-105">Es wird in vier unterschiedlichen Kontexten verwendet:</span><span class="sxs-lookup"><span data-stu-id="f9710-105">It is used in four different contexts:</span></span>

- <span data-ttu-id="f9710-106">In einer Methodensignatur und in einem Methodenaufruf, um ein Argument an eine Methode als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-106">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="f9710-107">Weitere Informationen finden Sie unter [Übergeben eines Arguments als Verweis](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="f9710-107">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="f9710-108">In einer Methodensignatur, um einen Wert an den Aufrufer als Verweis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-108">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="f9710-109">Weitere Informationen finden Sie unter [Verweisrückgabewerte](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="f9710-109">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="f9710-110">In einem Memberkörper, um anzugeben, dass ein Verweisrückgabewert, den der Aufrufer ändern möchte, lokal als Verweis gespeichert ist oder dass eine lokale Variable auf einen anderen Wert per Verweis zugreift.</span><span class="sxs-lookup"><span data-stu-id="f9710-110">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="f9710-111">Weitere Informationen finden Sie unter [Lokale ref-Variablen](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="f9710-111">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="f9710-112">In einer `struct`-Deklaration, um `ref struct` oder `readonly ref struct` zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f9710-112">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="f9710-113">Weitere Informationen finden Sie im Abschnitt zur [`ref`-Struktur](../builtin-types/struct.md#ref-struct) des Artikels [Strukturtypen](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="f9710-113">For more information, see the [`ref` struct](../builtin-types/struct.md#ref-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="f9710-114">Übergeben eines Arguments als Verweis</span><span class="sxs-lookup"><span data-stu-id="f9710-114">Passing an argument by reference</span></span>

<span data-ttu-id="f9710-115">In der Parameterliste einer Methode gibt das `ref`-Schlüsselwort an, dass ein Argument als Verweis und nicht als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9710-115">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="f9710-116">Das `ref`-Schlüsselwort stellt den formalen Parameter als Alias für das Argument dar, das eine Variable sein muss.</span><span class="sxs-lookup"><span data-stu-id="f9710-116">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="f9710-117">Anders ausgedrückt, jede Operation mit dem Parameter wird mit dem Argument durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9710-117">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="f9710-118">Wenn der Aufrufer z. B. einen lokalen Variablenausdruck oder einen Arrayelement-Zugriffsausdruck übergibt und die aufgerufene Methode das Objekt ersetzt, auf das der ref-Parameter verweist, dann verweist die lokale Variable des Aufrufers oder das Arrayelement bei Rückgabe der Methode jetzt auf das neue Objekt.</span><span class="sxs-lookup"><span data-stu-id="f9710-118">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="f9710-119">Verwechseln Sie nicht das Konzept der Übergabe durch einen Verweis mit dem Konzept der Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="f9710-119">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="f9710-120">Die beiden Konzepte sind nicht identisch.</span><span class="sxs-lookup"><span data-stu-id="f9710-120">The two concepts are not the same.</span></span> <span data-ttu-id="f9710-121">Ein Methodenparameter kann durch `ref` geändert werden, unabhängig davon, ob es sich um einen Werttyp oder ein Verweistyp handelt.</span><span class="sxs-lookup"><span data-stu-id="f9710-121">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="f9710-122">Es gibt keine Boxing-Konvertierung eines Werttyps, wenn er durch einen Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9710-122">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="f9710-123">Um einen `ref`-Parameter zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode explizit das Schlüsselwort `ref` verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9710-123">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="f9710-124">Ein Argument, das an einen `ref`- oder `in`-Parameter übergeben wird, muss vor der Übergabe initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-124">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="f9710-125">Dies unterscheidet sich von den [out](out-parameter-modifier.md)-Parametern, deren Argumente nicht explizit initialisiert werden müssen, bevor sie übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-125">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="f9710-126">Member einer Klasse können keine Signaturen haben, die sich nur durch `ref`, `in` oder `out` voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f9710-126">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="f9710-127">Es tritt ein Compilerfehler auf, wenn der einzige Unterschied zwischen beiden Member eines Typs der ist, dass einer von ihnen über einen `ref`-Parameter und der andere über einen `out`- oder `in`-Parameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="f9710-127">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="f9710-128">Der folgende Code wird z. B. nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="f9710-128">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="f9710-129">Allerdings können Methoden überladen werden, wenn eine Methode einen `ref`-, `in`- oder `out`-Parameter hat und die andere wie im folgenden Beispiel dargestellt über einen Werteparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="f9710-129">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="f9710-130">In anderen Situationen, die eine Signaturabstimmung benötigen, z.B. beim Ausblenden oder Überschreiben, sind `in`, `ref` und `out` Bestandteil der Signatur und passen nicht zueinander.</span><span class="sxs-lookup"><span data-stu-id="f9710-130">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="f9710-131">Eigenschaften sind keine Variablen.</span><span class="sxs-lookup"><span data-stu-id="f9710-131">Properties are not variables.</span></span> <span data-ttu-id="f9710-132">Sie sind Methoden und können nicht an `ref`-Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-132">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="f9710-133">Sie können keines der Schlüsselwörter `ref`, `in` und `out` für die folgenden Methodentypen verwenden:</span><span class="sxs-lookup"><span data-stu-id="f9710-133">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="f9710-134">Asynchrone Methoden, die Sie mit dem [async](async.md)-Modifizierer definieren.</span><span class="sxs-lookup"><span data-stu-id="f9710-134">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="f9710-135">Iterator-Methoden, die eine [yield return](yield.md)- oder `yield break`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9710-135">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="f9710-136">Für [Erweiterungsmethoden](../../programming-guide/classes-and-structs/extension-methods.md) gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="f9710-136">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="f9710-137">Das `out`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-137">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="f9710-138">Das `ref`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden, wenn es sich bei dem Argument nicht um eine Struktur handelt oder ein generischer Typ nicht auf eine Struktur beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="f9710-138">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="f9710-139">Das `in`-Schlüsselwort kann nur verwendet werden, wenn das erste Argument eine Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="f9710-139">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="f9710-140">Das `in`-Schlüsselwort kann nicht für einen generischen Typ verwendet werden – selbst bei einer Beschränkung auf eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="f9710-140">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="f9710-141">Übergeben eines Arguments per Verweis: Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9710-141">Passing an argument by reference: An example</span></span>

<span data-ttu-id="f9710-142">In den vorherigen Beispielen wurden Werttypen als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-142">The previous examples pass value types by reference.</span></span> <span data-ttu-id="f9710-143">Sie können das `ref`-Schlüsselwort auch verwenden, um Verweistypen als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-143">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="f9710-144">Die Übergabe eines Verweistyps als Verweis ermöglicht es der aufgerufenen Methode, das Objekt, auf die der Verweisparameter im Aufrufer verweist, zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="f9710-144">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="f9710-145">Der Speicherort des Objekts wird als Wert des Verweisparameters an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-145">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="f9710-146">Wenn Sie den Wert am Speicherort des Parameters ändern (um auf ein neues Objekt zu verweisen), ändern Sie auch den Speicherort, auf den der Aufrufer verweist.</span><span class="sxs-lookup"><span data-stu-id="f9710-146">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="f9710-147">Im folgenden Beispiel wird eine Instanz eines Verweistyps als ein `ref`-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-147">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="f9710-148">Weitere Informationen zum Übergeben von Verweistypen durch einen Wert und durch einen Verweis finden Sie unter [Übergeben von Verweistypparametern](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f9710-148">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="f9710-149">Verweisrückgabewerte</span><span class="sxs-lookup"><span data-stu-id="f9710-149">Reference return values</span></span>

<span data-ttu-id="f9710-150">Verweisrückgabewerte (auch ref-Rückgaben genannt) sind Werte, die von einer Methode an den Aufrufer als Verweis zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-150">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="f9710-151">Das bedeutet, dass der Aufrufer den von einer Methode zurückgegebenen Wert ändern kann. Diese Änderung wird im Zustand des Objekts in der aufrufenden Methode wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-151">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object in the calling method.</span></span>

<span data-ttu-id="f9710-152">Ein Verweisrückgabewert wird definiert durch Verwenden des `ref`-Schlüsselworts:</span><span class="sxs-lookup"><span data-stu-id="f9710-152">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="f9710-153">In der Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="f9710-153">In the method signature.</span></span> <span data-ttu-id="f9710-154">Die folgende Methodensignatur gibt z.B. an, dass die Methode `GetCurrentPrice` den Wert <xref:System.Decimal> nach Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f9710-154">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="f9710-155">Zwischen dem `return`-Token und der Variable, die in einer `return`-Anweisung in der Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9710-155">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="f9710-156">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f9710-156">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="f9710-157">Zum Ändern des Zustands des Objekts durch den Aufrufer muss der Verweisrückgabewert in einer Variable gespeichert werden, die explizit als [lokale ref-Variable](#ref-locals) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f9710-157">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="f9710-158">Hier ist ein vollständigeres Beispiel für die Verweisrückgabe, das sowohl die Methodensignatur als auch den Methodentext zeigt.</span><span class="sxs-lookup"><span data-stu-id="f9710-158">Here is a more complete ref return example, showing both the method signature and method body.</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="f9710-159">Die aufgerufene Methode kann den Rückgabewert auch als `ref readonly` deklarieren, um den Wert als Verweis zurückzugeben, und durchsetzen, dass der aufrufende Code den zurückgegebenen Wert nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="f9710-159">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="f9710-160">Die aufrufende Methode kann das Kopieren des Rückgabewerts verhindern, indem sie den Wert in einer lokalen [schreibgeschützten ref-Variablen](#ref-readonly-locals) speichert.</span><span class="sxs-lookup"><span data-stu-id="f9710-160">The calling method can avoid copying the returned value by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="f9710-161">Ein Beispiel finden Sie unter [Beispiel für ref-Rückgaben und lokale ref-Variablen](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="f9710-161">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="f9710-162">Lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="f9710-162">Ref locals</span></span>

<span data-ttu-id="f9710-163">Eine lokale ref-Variable wird verwendet, um auf Werte zu verweisen, die mit `return ref` zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-163">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="f9710-164">Eine lokale ref-Variable kann nicht für einen nicht ref-Rückgabewert initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-164">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="f9710-165">Das heißt, die rechte Seite der Initialisierung muss ein Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="f9710-165">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="f9710-166">Jede Änderung am Wert der lokalen ref-Variable wird im Zustand des Objekts wiedergegeben, dessen Methode den Wert als Verweis zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="f9710-166">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="f9710-167">Eine lokale ref-Variable wird mithilfe des `ref`-Schlüsselworts vor der Variablendeklaration definiert sowie unmittelbar vor dem Aufruf der Methode, die den Wert als Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f9710-167">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="f9710-168">Die folgende Anweisung definiert z.B. eine lokale ref-Variable, die von der Methode `GetEstimatedValue` zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="f9710-168">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="f9710-169">Auch auf Werte können Sie per Verweis zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9710-169">You can access a value by reference in the same way.</span></span> <span data-ttu-id="f9710-170">In einigen Fällen erhöht dies die Leistung, da ein möglicherweise aufwendiger Kopiervorgang vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="f9710-170">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="f9710-171">In der folgenden Anweisung wird z.B. gezeigt, wie ein lokaler Verweiswert definiert wird, mit dem auf einen Wert verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f9710-171">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="f9710-172">Das Schlüsselwort `ref` muss in beiden Beispielen an beiden Stellen verwendet werden. Andernfalls generiert der Compiler den Fehler CS8172 „Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden“.</span><span class="sxs-lookup"><span data-stu-id="f9710-172">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="f9710-173">Beginnend mit C# 7.3 kann die Iterationsvariable der `foreach`-Anweisung eine lokale ref-Variable oder schreibgeschützte lokale ref-Variable sein.</span><span class="sxs-lookup"><span data-stu-id="f9710-173">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="f9710-174">Weitere Informationen finden Sie im Artikel zur [foreach-Anweisung](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="f9710-174">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="f9710-175">Ebenfalls beginnend mit C# 7.3 können Sie eine lokale oder schreibgeschützte lokale ref-Variable mit dem [ref-Zuweisungsoperator](../operators/assignment-operator.md#ref-assignment-operator) neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f9710-175">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="f9710-176">Lokale schreibgeschützte ref-Variable</span><span class="sxs-lookup"><span data-stu-id="f9710-176">Ref readonly locals</span></span>

<span data-ttu-id="f9710-177">Mit einer lokalen schreibgeschützten ref-Variablen können Sie auf Werte verweisen, die von der Methode oder Eigenschaft zurückgegeben werden, die `ref readonly` in der Signatur enthält und `return ref` verwendet.</span><span class="sxs-lookup"><span data-stu-id="f9710-177">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="f9710-178">Eine `ref readonly`-Variable kombiniert die Eigenschaften einer lokalen `ref`-Variablen mit einer `readonly`-Variablen: Sie ist ein Alias für den Speicher, dem sie zugewiesen ist, und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f9710-178">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="f9710-179">Beispiel für ref-Rückgaben und lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="f9710-179">A ref returns and ref locals example</span></span>

<span data-ttu-id="f9710-180">Im folgenden Beispiel wird eine `Book`-Klasse mit zwei <xref:System.String>-Feldern definiert: `Title` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="f9710-180">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="f9710-181">Außerdem wird eine `BookCollection`-Klasse definiert, die ein privates Array von `Book`-Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="f9710-181">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="f9710-182">Einzelne Buchobjekte werden durch Aufrufen der `GetBookByTitle`-Methode als Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f9710-182">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="f9710-183">Speichert der Aufrufer den von der `GetBookByTitle`-Methode zurückgegeben Wert als lokale ref-Variable, werden Änderungen, die der Aufrufer am Rückgabewert vornimmt, im `BookCollection`-Objekt wiedergegeben. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f9710-183">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="f9710-184">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f9710-184">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9710-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9710-185">See also</span></span>

- [<span data-ttu-id="f9710-186">Schreiben von sicherem und effizientem Code</span><span class="sxs-lookup"><span data-stu-id="f9710-186">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="f9710-187">Ref-Rückgabetypen und lokale ref-Variablen</span><span class="sxs-lookup"><span data-stu-id="f9710-187">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="f9710-188">Bedingter ref-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="f9710-188">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="f9710-189">Übergeben von Parametern</span><span class="sxs-lookup"><span data-stu-id="f9710-189">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="f9710-190">Methodenparameter</span><span class="sxs-lookup"><span data-stu-id="f9710-190">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="f9710-191">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f9710-191">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f9710-192">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f9710-192">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f9710-193">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f9710-193">C# Keywords</span></span>](index.md)
