---
title: Referenzzellen (F#)
description: "Erfahren Sie, wie f# Referenzzellen Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 09a0b221-ea21-45c4-bae8-5e4a339750c4
ms.openlocfilehash: c7470c9a36cf2cd24dd89ceffcf6e90c6dc4d2dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="reference-cells"></a><span data-ttu-id="a69d4-104">Referenzzellen</span><span class="sxs-lookup"><span data-stu-id="a69d4-104">Reference Cells</span></span>

<span data-ttu-id="a69d4-105">*Referenzzellen* sind Speicherorte, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a69d4-105">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="a69d4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a69d4-106">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="a69d4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a69d4-107">Remarks</span></span>
<span data-ttu-id="a69d4-108">Sie verwenden den Operator `ref` vor einem Wert, um eine neue Referenzzelle zu erstellen, die den Wert kapselt.</span><span class="sxs-lookup"><span data-stu-id="a69d4-108">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="a69d4-109">Anschließend können Sie den zugrunde liegenden Wert ändern, da er änderbar ist.</span><span class="sxs-lookup"><span data-stu-id="a69d4-109">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="a69d4-110">Eine Referenzzelle enthält einen tatsächlichen Wert, sie ist nicht lediglich eine Adresse.</span><span class="sxs-lookup"><span data-stu-id="a69d4-110">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="a69d4-111">Wenn Sie mit dem Operator `ref` eine Referenzzelle erstellen, erstellen Sie eine Kopie des zugrunde liegenden Werts als gekapselten änderbaren Wert.</span><span class="sxs-lookup"><span data-stu-id="a69d4-111">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="a69d4-112">Mit dem Operator `!` (Bang) können Sie eine Referenzzelle dereferenzieren.</span><span class="sxs-lookup"><span data-stu-id="a69d4-112">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="a69d4-113">Im folgenden Codebeispiel werden die Deklaration und Verwendung von Referenzzellen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a69d4-113">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="a69d4-114">Die Ausgabe lautet `50`.</span><span class="sxs-lookup"><span data-stu-id="a69d4-114">The output is `50`.</span></span>

<span data-ttu-id="a69d4-115">Referenzzellen sind Instanzen des generischen `Ref`-Datensatztyps, der wie folgt deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a69d4-115">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="a69d4-116">Der Typ `'a ref` ist ein Synonym für `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="a69d4-116">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="a69d4-117">Der Compiler und IntelliSense in der IDE zeigen erstere Version für diesen Typ an, jedoch ist letztere Version die zugrunde liegende Definition.</span><span class="sxs-lookup"><span data-stu-id="a69d4-117">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="a69d4-118">Mit dem Operator `ref` wird eine neue Referenzzelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="a69d4-118">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="a69d4-119">Der folgende Code ist die Deklaration des Operators `ref`.</span><span class="sxs-lookup"><span data-stu-id="a69d4-119">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="a69d4-120">Die folgende Tabelle enthält die Funktionen, die für die Referenzzelle verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a69d4-120">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="a69d4-121">Operator, Member oder Feld</span><span class="sxs-lookup"><span data-stu-id="a69d4-121">Operator, member, or field</span></span>|<span data-ttu-id="a69d4-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a69d4-122">Description</span></span>|<span data-ttu-id="a69d4-123">Typ</span><span class="sxs-lookup"><span data-stu-id="a69d4-123">Type</span></span>|<span data-ttu-id="a69d4-124">Definition</span><span class="sxs-lookup"><span data-stu-id="a69d4-124">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="a69d4-125">`!` (Dereferenzierungsoperator)</span><span class="sxs-lookup"><span data-stu-id="a69d4-125">`!` (dereference operator)</span></span>|<span data-ttu-id="a69d4-126">Gibt den zugrunde liegenden Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a69d4-126">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="a69d4-127">`:=` (Zuweisungsoperator)</span><span class="sxs-lookup"><span data-stu-id="a69d4-127">`:=` (assignment operator)</span></span>|<span data-ttu-id="a69d4-128">Ändert den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="a69d4-128">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="a69d4-129">`ref` (Operator)</span><span class="sxs-lookup"><span data-stu-id="a69d4-129">`ref` (operator)</span></span>|<span data-ttu-id="a69d4-130">Kapselt einen Wert in einer neuen Referenzzelle.</span><span class="sxs-lookup"><span data-stu-id="a69d4-130">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="a69d4-131">`Value` (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="a69d4-131">`Value` (property)</span></span>|<span data-ttu-id="a69d4-132">Ruft den zugrunde liegenden Wert ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="a69d4-132">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="a69d4-133">`contents` (Datensatzfeld)</span><span class="sxs-lookup"><span data-stu-id="a69d4-133">`contents` (record field)</span></span>|<span data-ttu-id="a69d4-134">Ruft den zugrunde liegenden Wert ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="a69d4-134">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="a69d4-135">Es gibt mehrere Möglichkeiten, auf den zugrunde liegenden Wert zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a69d4-135">There are several ways to access the underlying value.</span></span> <span data-ttu-id="a69d4-136">Der vom Dereferenzierungsoperator (`!`) zurückgegebene Wert ist kein zuweisbarer Wert.</span><span class="sxs-lookup"><span data-stu-id="a69d4-136">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="a69d4-137">Wenn Sie den zugrunde liegenden Wert ändern, müssen Sie daher stattdessen den Zuweisungsoperator (`:=`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a69d4-137">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="a69d4-138">Sowohl die `Value`-Eigenschaft als auch das `contents`-Feld sind zuweisbare Werte.</span><span class="sxs-lookup"><span data-stu-id="a69d4-138">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="a69d4-139">Daher können Sie diese verwenden, um auf den zugrunde liegenden Wert zuzugreifen oder diesen zu ändern, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a69d4-139">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="a69d4-140">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="a69d4-140">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="a69d4-141">Das Feld `contents` wird für die Kompatibilität mit anderen Versionen von ML bereitgestellt und gibt während der Kompilierung eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="a69d4-141">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="a69d4-142">Verwenden Sie die `--mlcompatibility`-Compileroption, um die Warnung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a69d4-142">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="a69d4-143">Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="a69d4-143">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="a69d4-144">Im folgenden Code wird die Verwendung von Referenzzellen beim Übergeben von Parametern veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a69d4-144">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="a69d4-145">Der Incrementor weist einer Methode Inkrement, die einen Parameter akzeptiert, der in den Parametertyp Byref enthält.</span><span class="sxs-lookup"><span data-stu-id="a69d4-145">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="a69d4-146">Byref im Parametertyp gibt an, dass Aufrufer eine Referenzzelle oder die Adresse einer typischen Variablen des angegebenen Typs in diesem Fall "int". übergeben müssen Im restlichen Code wird veranschaulicht, wie Inkrement mit beiden dieser Typen von Argumenten aufgerufen, und zeigt die Verwendung von Ref-Operator auf eine Variable zum Erstellen einer Referenzzelle (Ref myDelta1).</span><span class="sxs-lookup"><span data-stu-id="a69d4-146">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="a69d4-147">Anschließend wird die Verwendung des address-of-Operators (&amp;) zum Generieren eines entsprechenden Arguments veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a69d4-147">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="a69d4-148">Schließlich wird erneut Increment-Methode aufgerufen, mithilfe einer Referenzzelle, die mit einem Let-Bindung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a69d4-148">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="a69d4-149">Die letzte Codezeile veranschaulicht die Verwendung von der!</span><span class="sxs-lookup"><span data-stu-id="a69d4-149">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="a69d4-150">Operator zum Dereferenzieren der Referenzzelle für den Druck.</span><span class="sxs-lookup"><span data-stu-id="a69d4-150">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="a69d4-151">Weitere Informationen dazu, wie Sie als Verweis übergeben, finden Sie unter [Parameter und Argumente](parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="a69d4-151">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="a69d4-152">C#-Programmierer sollten wissen, dass die Ref unterschiedlich in f# funktioniert als in C# geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a69d4-152">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="a69d4-153">Beispielsweise die Verwendung von Ref beim Übergeben eines Arguments denselben Effekt in f# keine wie in c#.</span><span class="sxs-lookup"><span data-stu-id="a69d4-153">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="a69d4-154">Verarbeiten von c# `ref` zurückgibt</span><span class="sxs-lookup"><span data-stu-id="a69d4-154">Consuming C# `ref` returns</span></span>

<span data-ttu-id="a69d4-155">Ab f# 4.1, können Sie nutzen `ref` gibt, die in c# generiert.</span><span class="sxs-lookup"><span data-stu-id="a69d4-155">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="a69d4-156">Das Ergebnis der solch ein Aufruf ist eine `byref<_>` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="a69d4-156">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="a69d4-157">Die folgende C#-Methode:</span><span class="sxs-lookup"><span data-stu-id="a69d4-157">The following C# method:</span></span>

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

<span data-ttu-id="a69d4-158">Kann transparent von f# mit keine besondere Syntax aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="a69d4-158">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="a69d4-159">Sie können auch Funktionen, die Zeit dauern können deklarieren eine `ref` als Eingabe verwendet, z. B. zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="a69d4-159">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="a69d4-160">Es gibt derzeit keine Möglichkeit zum Generieren einer `ref` return in F# erläutert die in c# genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a69d4-160">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="a69d4-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a69d4-161">See Also</span></span>
[<span data-ttu-id="a69d4-162">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="a69d4-162">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="a69d4-163">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="a69d4-163">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="a69d4-164">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="a69d4-164">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
