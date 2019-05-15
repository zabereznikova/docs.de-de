---
title: Tupel
description: Erfahren Sie mehr über die F# Tupel eine Gruppierung von unbenannter aber sortierter Werte möglicherweise von anderen Typen.
ms.date: 05/16/2016
ms.openlocfilehash: 950451ad1672e0c9fc609773f1bc32fc13636ddb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645112"
---
# <a name="tuples"></a><span data-ttu-id="13b82-103">Tupel</span><span class="sxs-lookup"><span data-stu-id="13b82-103">Tuples</span></span>

<span data-ttu-id="13b82-104">Ein *Tupel* ist eine Gruppierung von unbenannter aber sortierter Werte möglicherweise von anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="13b82-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="13b82-105">Tupel kann es sich entweder um Verweistypen oder Strukturen sein.</span><span class="sxs-lookup"><span data-stu-id="13b82-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="13b82-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="13b82-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="13b82-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13b82-107">Remarks</span></span>

<span data-ttu-id="13b82-108">Jede *Element* in der vorherigen Syntax kann eine beliebige gültige F# Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="13b82-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="13b82-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="13b82-109">Examples</span></span>

<span data-ttu-id="13b82-110">Beispiele für Tupel sind Paare-Tripeln und usw., der denselben oder unterschiedlichen Typen.</span><span class="sxs-lookup"><span data-stu-id="13b82-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="13b82-111">Beispiele sind in den folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="13b82-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="13b82-112">Abrufen von einzelnen Werten</span><span class="sxs-lookup"><span data-stu-id="13b82-112">Obtaining Individual Values</span></span>

<span data-ttu-id="13b82-113">Sie können Musterabgleich zugreifen, und weisen Sie Namen für Elemente des Tupels, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="13b82-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="13b82-114">Sie können auch dekonstruieren ein Tupels über Mustervergleich außerhalb einer `match` Ausdruck über `let` Bindung:</span><span class="sxs-lookup"><span data-stu-id="13b82-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="13b82-115">Oder Sie können Muster für Tupel als Eingaben für Funktionen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="13b82-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="13b82-116">Wenn Sie nur ein Element des Tupels benötigen, kann das Platzhalterzeichen (Unterstrich) verwendet werden, um zu vermeiden, erstellen einen neuen Namen für ein Wert, den Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="13b82-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="13b82-117">Kopieren Elemente aus einem Verweis Tupel in einer Struktur Tupel ist ebenfalls einfach:</span><span class="sxs-lookup"><span data-stu-id="13b82-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="13b82-118">Die Funktionen `fst` und `snd` (nur Tupel verweisen) die ersten und zweite Sie bzw. Elemente eines Tupels.</span><span class="sxs-lookup"><span data-stu-id="13b82-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="13b82-119">Es gibt keine integrierte Funktion, die das dritte Element der ein Tripel zurückgibt, aber Sie können ganz einfach wie folgt schreiben.</span><span class="sxs-lookup"><span data-stu-id="13b82-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="13b82-120">Im Allgemeinen ist es besser, die den Zugriff auf einzelne Tupelelemente mithilfe des musterabgleichs.</span><span class="sxs-lookup"><span data-stu-id="13b82-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="13b82-121">Verwendung von Tupeln</span><span class="sxs-lookup"><span data-stu-id="13b82-121">Using Tuples</span></span>

<span data-ttu-id="13b82-122">Tupel bieten eine bequeme Möglichkeit, mehrere Werte aus einer Funktion zurückgeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="13b82-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="13b82-123">In diesem Beispiel führt die Ganzzahldivision und gibt das gerundete Ergebnis des Vorgangs als erste Member eines Paars Tupel und den Rest als einen zweiten Members des Paares.</span><span class="sxs-lookup"><span data-stu-id="13b82-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="13b82-124">Tupel können auch als Funktionsargumente verwendet werden, wenn Sie möchten, um zu vermeiden, die implizitem currying der Argumente der Funktion, die durch die üblichen Funktionssyntax impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="13b82-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="13b82-125">Der üblichen Syntax für die Definition der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion, die die partielle Anwendung von das erste Argument der Funktion ist zu definieren, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="13b82-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="13b82-126">Currying über ein Tupel als Parameter deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="13b82-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="13b82-127">Weitere Informationen finden Sie unter "Partielle Anwendung von Argumenten" in [Funktionen](functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="13b82-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="13b82-128">Namen der Tuple-Typen</span><span class="sxs-lookup"><span data-stu-id="13b82-128">Names of Tuple Types</span></span>

<span data-ttu-id="13b82-129">Wenn Sie den Namen eines Typs, die ein Tupel ist schreiben, verwenden Sie die `*` Symbol, um Elemente zu trennen.</span><span class="sxs-lookup"><span data-stu-id="13b82-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="13b82-130">Für ein Tupel, das umfasst eine `int`, `float`, und ein `string`, z. B. `(10, 10.0, "ten")`, Typs würde wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="13b82-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="13b82-131">Interoperation mit c#-Tupel</span><span class="sxs-lookup"><span data-stu-id="13b82-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="13b82-132">C# 7.0 eingeführt Tupel für die Sprache an.</span><span class="sxs-lookup"><span data-stu-id="13b82-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="13b82-133">Tupel in C# sind Strukturen und Strukturieren von Tupeln in F# entsprechen.</span><span class="sxs-lookup"><span data-stu-id="13b82-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="13b82-134">Wenn Sie mit c# zusammenarbeiten müssen, müssen Sie Strukturieren von Tupeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="13b82-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="13b82-135">Dies ist ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="13b82-135">This is easy to do.</span></span>  <span data-ttu-id="13b82-136">Beispiel: Angenommen Sie, Sie verfügen über ein Tupel an eine C#-Klasse übergeben, und klicken Sie dann nutzen das Ergebnis, das auch ein Tupel ist:</span><span class="sxs-lookup"><span data-stu-id="13b82-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="13b82-137">In Ihrer F# Code, Sie können ein Tupel Struktur als Parameter übergibt, und nutzen Sie das Ergebnis als Struktur Tupel.</span><span class="sxs-lookup"><span data-stu-id="13b82-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="13b82-138">Konvertieren zwischen Verweis Tupel und Strukturieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="13b82-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="13b82-139">Da der Verweis Tupel und Struct-Tuples eine vollständig andere zugrunde liegende Darstellung haben, sind sie nicht implizit konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="13b82-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="13b82-140">D. h. kompiliert nicht Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="13b82-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="13b82-141">Sie müssen Muster für ein Tupel übereinstimmen, und erstellen Sie das andere hat die Bestandteile.</span><span class="sxs-lookup"><span data-stu-id="13b82-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="13b82-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="13b82-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="13b82-143">Kompilierte Form von Tupeln mit Verweis</span><span class="sxs-lookup"><span data-stu-id="13b82-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="13b82-144">Dieser Abschnitt erläutert die Form von Tupeln an, wenn sie kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="13b82-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="13b82-145">Die folgenden Informationen ist es nicht notwendig, zu lesen, wenn Sie .NET Framework 3.5 verwenden oder niedriger.</span><span class="sxs-lookup"><span data-stu-id="13b82-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="13b82-146">Tupel werden in Objekte eines von mehreren generischen Typen, die alle benannten kompiliert `System.Tuple`, für die Stelligkeit oder die Anzahl der Typparameter überladen sind.</span><span class="sxs-lookup"><span data-stu-id="13b82-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="13b82-147">Tuple-Typen werden in diesem Formular angezeigt, bei der Anzeige in einer anderen Sprache, z. B. C# oder Visual Basic, oder wenn Sie ein Tool verwenden, die F#-Konstrukte unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="13b82-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="13b82-148">Die `Tuple` Typen in .NET Framework 4 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="13b82-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="13b82-149">Wenn Sie eine frühere Version von .NET Framework Anzielen, verwendet der Compiler Versionen der [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) aus der Version 2.0 der F#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="13b82-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="13b82-150">Nur für Anwendungen, die auf der 2.0, 3.0 und 3.5 von .NET Framework-Versionen abzielen, werden die Typen in dieser Bibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="13b82-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="13b82-151">Weiterleiten von Typen wird verwendet, um sicherzustellen, dass binäre Kompatibilität zwischen .NET Framework 2.0 und .NET Framework 4 F# Komponenten.</span><span class="sxs-lookup"><span data-stu-id="13b82-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="13b82-152">Kompilierte Form von Strukturieren von Tupeln</span><span class="sxs-lookup"><span data-stu-id="13b82-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="13b82-153">Strukturieren von Tupeln (z. B. `struct (x, y)`), unterscheiden sich grundlegend von Verweis Tupel.</span><span class="sxs-lookup"><span data-stu-id="13b82-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="13b82-154">Sie kompiliert werden, in der <xref:System.ValueTuple> Typ Stelligkeit oder die Anzahl der Typparameter überladen.</span><span class="sxs-lookup"><span data-stu-id="13b82-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="13b82-155">Sie entsprechen dem [c# 7.0-Tupel](../../csharp/tuples.md) und [Visual Basic 2017 Tupel](../../visual-basic/programming-guide/language-features/data-types/tuples.md), und bidirektional zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="13b82-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="13b82-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13b82-156">See also</span></span>

- [<span data-ttu-id="13b82-157">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="13b82-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="13b82-158">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="13b82-158">F# Types</span></span>](fsharp-types.md)
