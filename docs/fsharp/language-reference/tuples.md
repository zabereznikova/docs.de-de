---
title: Tupel (F#)
description: Informationen Sie zu F#-Tupel, eine Gruppierung von unbenannte jedoch geordnete Werte möglicherweise von anderen Typen.
ms.date: 05/16/2016
ms.openlocfilehash: d017a2ce8a6ad9b3cec8dfa2ee15b47f06d8f67c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564775"
---
# <a name="tuples"></a><span data-ttu-id="f5387-103">Tupel</span><span class="sxs-lookup"><span data-stu-id="f5387-103">Tuples</span></span>

<span data-ttu-id="f5387-104">Ein *Tupel* ist eine Gruppierung von unbenannte jedoch geordnete Werte möglicherweise von anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="f5387-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="f5387-105">Tupel kann entweder Verweistypen oder Strukturen sein.</span><span class="sxs-lookup"><span data-stu-id="f5387-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5387-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5387-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```
## <a name="remarks"></a><span data-ttu-id="f5387-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5387-107">Remarks</span></span>
<span data-ttu-id="f5387-108">Jede *Element* in der vorherigen Syntax kann jeder gültiger F#-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="f5387-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="f5387-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f5387-109">Examples</span></span>
<span data-ttu-id="f5387-110">Beispiele für Tupel sind Paare, Tripel, usw., der gleichen oder unterschiedliche Typen.</span><span class="sxs-lookup"><span data-stu-id="f5387-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="f5387-111">Einige Beispiele sind in den folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f5387-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]
    
## <a name="obtaining-individual-values"></a><span data-ttu-id="f5387-112">Abrufen einzelner Werte</span><span class="sxs-lookup"><span data-stu-id="f5387-112">Obtaining Individual Values</span></span>
<span data-ttu-id="f5387-113">Sie können mithilfe des Mustervergleichs zugreifen, und weisen Sie Aliasnamen für Tupelelemente, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5387-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="f5387-114">Sie können auch ein Tupel über Mustervergleich außerhalb von Löschen einer `match` Ausdruck über `let` Bindung:</span><span class="sxs-lookup"><span data-stu-id="f5387-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="f5387-115">Oder Sie können Muster, die als Eingaben für Funktionen auf Tupel übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="f5387-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="f5387-116">Wenn Sie nur ein Element des Tupels benötigen, kann das Platzhalterzeichen (Unterstrich) verwendet werden, um zu vermeiden, erstellen einen neuen Namen für einen Wert an, dem Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="f5387-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="f5387-117">Kopieren Elemente aus einem Verweis Tupel in einer Struktur Tupel ist einfach:</span><span class="sxs-lookup"><span data-stu-id="f5387-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="f5387-118">Die Funktionen `fst` und `snd` (nur Tupel verweisen) die ersten und zweiten Sie Elemente eines Tupels bzw.</span><span class="sxs-lookup"><span data-stu-id="f5387-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="f5387-119">Keine integrierte Funktion, die das dritte Element der Tripel zurückgibt vorhanden ist, aber Sie können problemlos wie folgt schreiben.</span><span class="sxs-lookup"><span data-stu-id="f5387-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="f5387-120">Im Allgemeinen ist es besser, die mithilfe des Mustervergleichs Zugriff auf Tupelelemente der einzelnen.</span><span class="sxs-lookup"><span data-stu-id="f5387-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="f5387-121">Verwenden von Tupeln</span><span class="sxs-lookup"><span data-stu-id="f5387-121">Using Tuples</span></span>
<span data-ttu-id="f5387-122">Tupel bieten eine einfache Möglichkeit, mehrere Werte aus einer Funktion zurückgeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5387-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="f5387-123">In diesem Beispiel führt die Ganzzahldivision und gibt das gerundete Ergebnis des Vorgangs als erste Member eines Paars Tupel und den Rest als zweite Element des Paars.</span><span class="sxs-lookup"><span data-stu-id="f5387-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="f5387-124">Tupel können auch als Funktionsargumente verwendet werden, wenn sollten vermieden werden die implizitem currying von Funktionsargumenten, die durch die üblichen Funktionssyntax impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="f5387-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="f5387-125">Der üblichen Syntax zum Definieren der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion, ist der partiellen Anwendung von das erste Argument der Funktion, zu definieren, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5387-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="f5387-126">Verwenden Sie ein Tupel als Parameter wird currying deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5387-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="f5387-127">Weitere Informationen finden Sie unter "Partielle Anwendung von Argumenten" im [Funktionen](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5387-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="f5387-128">Namen von Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="f5387-128">Names of Tuple Types</span></span>
<span data-ttu-id="f5387-129">Wenn Sie den Namen eines Typs, die ein Tupel ist schreiben, verwenden Sie die `*` Symbol, um Elemente zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f5387-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="f5387-130">Für ein Tupel, aus denen besteht eine `int`, `float`, und ein `string`, wie z. B. `(10, 10.0, "ten")`, Typs würde wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f5387-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="f5387-131">Interoperation mit c# Tupel</span><span class="sxs-lookup"><span data-stu-id="f5387-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="f5387-132">C#-7.0 eingeführt Tupel in der Sprache.</span><span class="sxs-lookup"><span data-stu-id="f5387-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="f5387-133">Tupel in C# geschrieben sind Strukturen und Struktur Tupel in f# entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f5387-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="f5387-134">Wenn Sie mit c# zusammenarbeiten müssen, müssen Sie die Struktur Tupel verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5387-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="f5387-135">Dies ist einfach.</span><span class="sxs-lookup"><span data-stu-id="f5387-135">This is easy to do.</span></span>  <span data-ttu-id="f5387-136">Angenommen Sie, Sie verfügen über ein Tupel an eine C#-Klasse übergeben und dann verwenden das Ergebnis, das auch ein Tupel ist:</span><span class="sxs-lookup"><span data-stu-id="f5387-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="f5387-137">Sie können in Ihrem f#-Code dann ein Tupel Struktur als Parameter übergeben und nutzen das Ergebnis als Struktur Tupel.</span><span class="sxs-lookup"><span data-stu-id="f5387-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="f5387-138">Konvertieren zwischen Verweis Tupel und Tupel-Struktur</span><span class="sxs-lookup"><span data-stu-id="f5387-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="f5387-139">Da Verweis Tupel und Struct-Tuples eine ganz andere zugrunde liegenden Darstellung haben, sind sie nicht implizit konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f5387-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="f5387-140">D. h. kompiliert nicht dem folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f5387-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="f5387-141">Sie müssen das Muster auf ein Tupel übereinstimmen und die andere die Bestandteile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5387-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="f5387-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f5387-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="f5387-143">Kompilierte Form der Verweis Tupel</span><span class="sxs-lookup"><span data-stu-id="f5387-143">Compiled Form of Reference Tuples</span></span>
<span data-ttu-id="f5387-144">Dieser Abschnitt erklärt die Form der Tupel bei der Prozedur-sind.</span><span class="sxs-lookup"><span data-stu-id="f5387-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="f5387-145">Die Informationen hier nicht lesen, es sei denn, Sie .NET Framework 3.5 abzielen notwendig oder niedriger.</span><span class="sxs-lookup"><span data-stu-id="f5387-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="f5387-146">Tupel werden in Objekte eines von mehreren generischen Typen, die alle benannten kompiliert `System.Tuple`, für die Stelligkeit oder die Anzahl von Typparametern überladen sind.</span><span class="sxs-lookup"><span data-stu-id="f5387-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="f5387-147">Tuple-Typen werden in dieser Form angezeigt, bei der Anzeige in einer anderen Sprache, z. B. c# oder Visual Basic, oder wenn Sie ein Tool verwenden, die f#-Konstrukte nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="f5387-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="f5387-148">Die `Tuple` Typen in .NET Framework 4 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f5387-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="f5387-149">Wenn Sie eine frühere Version von .NET Framework abzielen, verwendet der Compiler-Versionen [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) aus der Version 2.0 der f#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="f5387-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="f5387-150">Die Typen in dieser Bibliothek dienen nur für Anwendungen, die auf dem 2.0, 3.0 und 3.5 Versionen von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="f5387-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="f5387-151">Typweiterleitung wird verwendet, um sicherzustellen, dass binäre Kompatibilität zwischen .NET Framework 2.0 und .NET Framework 4 F#-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="f5387-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="f5387-152">Kompilierte Form der Tupel-Struktur</span><span class="sxs-lookup"><span data-stu-id="f5387-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="f5387-153">Struct-Tupel (z. B. `struct (x, y)`), unterscheiden sich grundlegend von Verweis Tupel.</span><span class="sxs-lookup"><span data-stu-id="f5387-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="f5387-154">Sie werden in kompiliert die <xref:System.ValueTuple> Typ, durch Stelligkeit oder die Anzahl von Typparametern überlastet.</span><span class="sxs-lookup"><span data-stu-id="f5387-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="f5387-155">Gleichwertig zu [c# 7.0 Tupel](../../csharp/tuples.md) und [Visual Basic 2017 Tupel](../../visual-basic/programming-guide/language-features/data-types/tuples.md), und bietet Interoperabilität bidirektional.</span><span class="sxs-lookup"><span data-stu-id="f5387-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5387-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5387-156">See Also</span></span>
[<span data-ttu-id="f5387-157">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="f5387-157">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="f5387-158">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="f5387-158">F# Types</span></span>](fsharp-types.md)
