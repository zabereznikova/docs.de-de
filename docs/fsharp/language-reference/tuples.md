---
title: Tupel (F#)
description: Informationen Sie zu dem F#-Tupel, eine Gruppierung von unbenannter aber sortierter Werte möglicherweise von anderen Typen.
ms.date: 05/16/2016
ms.openlocfilehash: e7628e4c4b538c2fe52fca25d2597b10fec28d1c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43749222"
---
# <a name="tuples"></a><span data-ttu-id="40e52-103">Tupel</span><span class="sxs-lookup"><span data-stu-id="40e52-103">Tuples</span></span>

<span data-ttu-id="40e52-104">Ein *Tupel* ist eine Gruppierung von unbenannter aber sortierter Werte möglicherweise von anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="40e52-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="40e52-105">Tupel kann es sich entweder um Verweistypen oder Strukturen sein.</span><span class="sxs-lookup"><span data-stu-id="40e52-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="40e52-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="40e52-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="40e52-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40e52-107">Remarks</span></span>

<span data-ttu-id="40e52-108">Jede *Element* in der vorherigen Syntax können F#-ein beliebiger Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="40e52-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="40e52-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="40e52-109">Examples</span></span>

<span data-ttu-id="40e52-110">Beispiele für Tupel sind Paare-Tripeln und usw., der denselben oder unterschiedlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="40e52-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="40e52-111">Beispiele sind in den folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="40e52-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="40e52-112">Abrufen von einzelnen Werten</span><span class="sxs-lookup"><span data-stu-id="40e52-112">Obtaining Individual Values</span></span>

<span data-ttu-id="40e52-113">Sie können Musterabgleich zugreifen, und weisen Sie Namen für Elemente des Tupels, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="40e52-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="40e52-114">Sie können auch dekonstruieren ein Tupels über Mustervergleich außerhalb einer `match` Ausdruck über `let` Bindung:</span><span class="sxs-lookup"><span data-stu-id="40e52-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="40e52-115">Oder Sie können Muster für Tupel als Eingaben für Funktionen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="40e52-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="40e52-116">Wenn Sie nur ein Element des Tupels benötigen, kann das Platzhalterzeichen (Unterstrich) verwendet werden, um zu vermeiden, erstellen einen neuen Namen für ein Wert, den Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="40e52-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="40e52-117">Kopieren Elemente aus einem Verweis Tupel in einer Struktur Tupel ist ebenfalls einfach:</span><span class="sxs-lookup"><span data-stu-id="40e52-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="40e52-118">Die Funktionen `fst` und `snd` (nur Tupel verweisen) die ersten und zweite Sie bzw. Elemente eines Tupels.</span><span class="sxs-lookup"><span data-stu-id="40e52-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="40e52-119">Es gibt keine integrierte Funktion, die das dritte Element der ein Tripel zurückgibt, aber Sie können ganz einfach wie folgt schreiben.</span><span class="sxs-lookup"><span data-stu-id="40e52-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="40e52-120">Im Allgemeinen ist es besser, die den Zugriff auf einzelne Tupelelemente mithilfe des musterabgleichs.</span><span class="sxs-lookup"><span data-stu-id="40e52-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="40e52-121">Verwendung von Tupeln</span><span class="sxs-lookup"><span data-stu-id="40e52-121">Using Tuples</span></span>

<span data-ttu-id="40e52-122">Tupel bieten eine bequeme Möglichkeit, mehrere Werte aus einer Funktion zurückgeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="40e52-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="40e52-123">In diesem Beispiel führt die Ganzzahldivision und gibt das gerundete Ergebnis des Vorgangs als erste Member eines Paars Tupel und den Rest als einen zweiten Members des Paares.</span><span class="sxs-lookup"><span data-stu-id="40e52-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="40e52-124">Tupel können auch als Funktionsargumente verwendet werden, wenn Sie möchten, um zu vermeiden, die implizitem currying der Argumente der Funktion, die durch die üblichen Funktionssyntax impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="40e52-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="40e52-125">Der üblichen Syntax für die Definition der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion, die die partielle Anwendung von das erste Argument der Funktion ist zu definieren, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="40e52-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="40e52-126">Currying über ein Tupel als Parameter deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="40e52-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="40e52-127">Weitere Informationen finden Sie unter "Partielle Anwendung von Argumenten" in [Funktionen](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="40e52-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="40e52-128">Namen der Tuple-Typen</span><span class="sxs-lookup"><span data-stu-id="40e52-128">Names of Tuple Types</span></span>

<span data-ttu-id="40e52-129">Wenn Sie den Namen eines Typs, die ein Tupel ist schreiben, verwenden Sie die `*` Symbol, um Elemente zu trennen.</span><span class="sxs-lookup"><span data-stu-id="40e52-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="40e52-130">Für ein Tupel, das umfasst eine `int`, `float`, und ein `string`, z. B. `(10, 10.0, "ten")`, Typs würde wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="40e52-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="40e52-131">Interoperation mit c#-Tupel</span><span class="sxs-lookup"><span data-stu-id="40e52-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="40e52-132">C# 7.0 eingeführt Tupel für die Sprache an.</span><span class="sxs-lookup"><span data-stu-id="40e52-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="40e52-133">Tupel in c# sind Strukturen und Strukturieren von Tupeln in F# entsprechen.</span><span class="sxs-lookup"><span data-stu-id="40e52-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="40e52-134">Wenn Sie mit c# zusammenarbeiten müssen, müssen Sie Strukturieren von Tupeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="40e52-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="40e52-135">Dies ist ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="40e52-135">This is easy to do.</span></span>  <span data-ttu-id="40e52-136">Beispiel: Angenommen Sie, Sie verfügen über ein Tupel an eine C#-Klasse übergeben, und klicken Sie dann nutzen das Ergebnis, das auch ein Tupel ist:</span><span class="sxs-lookup"><span data-stu-id="40e52-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="40e52-137">Sie können in Ihre F#-Code klicken Sie dann ein Tupel Struktur als Parameter übergeben und nutzen das Ergebnis als Struktur Tupel.</span><span class="sxs-lookup"><span data-stu-id="40e52-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="40e52-138">Konvertieren zwischen Verweis Tupel und Strukturieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="40e52-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="40e52-139">Da der Verweis Tupel und Struct-Tuples eine vollständig andere zugrunde liegende Darstellung haben, sind sie nicht implizit konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="40e52-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="40e52-140">D. h. kompiliert nicht Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="40e52-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="40e52-141">Sie müssen Muster für ein Tupel übereinstimmen, und erstellen Sie das andere hat die Bestandteile.</span><span class="sxs-lookup"><span data-stu-id="40e52-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="40e52-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40e52-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="40e52-143">Kompilierte Form von Tupeln mit Verweis</span><span class="sxs-lookup"><span data-stu-id="40e52-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="40e52-144">Dieser Abschnitt erläutert die Form von Tupeln an, wenn sie kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="40e52-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="40e52-145">Die folgenden Informationen ist es nicht notwendig, zu lesen, wenn Sie .NET Framework 3.5 verwenden oder niedriger.</span><span class="sxs-lookup"><span data-stu-id="40e52-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="40e52-146">Tupel werden in Objekte eines von mehreren generischen Typen, die alle benannten kompiliert `System.Tuple`, für die Stelligkeit oder die Anzahl der Typparameter überladen sind.</span><span class="sxs-lookup"><span data-stu-id="40e52-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="40e52-147">Tuple-Typen werden in diesem Formular angezeigt, bei der Anzeige in einer anderen Sprache, z. B. c# oder Visual Basic, oder wenn Sie ein Tool verwenden, die F#-Konstrukte unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="40e52-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="40e52-148">Die `Tuple` Typen in .NET Framework 4 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="40e52-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="40e52-149">Wenn Sie eine frühere Version von .NET Framework Anzielen, verwendet der Compiler Versionen der [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) aus der Version 2.0 der F#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="40e52-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="40e52-150">Nur für Anwendungen, die auf der 2.0, 3.0 und 3.5 von .NET Framework-Versionen abzielen, werden die Typen in dieser Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="40e52-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="40e52-151">Weiterleiten von Typen wird verwendet, um sicherzustellen, dass binäre Kompatibilität zwischen .NET Framework 2.0 und .NET Framework 4 F#-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="40e52-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="40e52-152">Kompilierte Form von Strukturieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="40e52-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="40e52-153">Strukturieren von Tupeln (z. B. `struct (x, y)`), unterscheiden sich grundlegend von Verweis Tupel.</span><span class="sxs-lookup"><span data-stu-id="40e52-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="40e52-154">Sie kompiliert werden, in der <xref:System.ValueTuple> Typ Stelligkeit oder die Anzahl der Typparameter überladen.</span><span class="sxs-lookup"><span data-stu-id="40e52-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="40e52-155">Sie entsprechen dem [c# 7.0-Tupel](../../csharp/tuples.md) und [Visual Basic 2017 Tupel](../../visual-basic/programming-guide/language-features/data-types/tuples.md), und bidirektional zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="40e52-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="40e52-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40e52-156">See also</span></span>

- [<span data-ttu-id="40e52-157">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="40e52-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="40e52-158">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="40e52-158">F# Types</span></span>](fsharp-types.md)
