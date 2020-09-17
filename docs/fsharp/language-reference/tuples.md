---
title: Tupel
description: 'Erfahren Sie mehr über das F #-Tupel, eine Gruppierung unbenannter, aber geordneter Werte, die möglicherweise unterschiedlich sind.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f4adf7e10e22d8b7a8cf697baee15962adf3630
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720360"
---
# <a name="tuples"></a><span data-ttu-id="7c7fc-103">Tupel</span><span class="sxs-lookup"><span data-stu-id="7c7fc-103">Tuples</span></span>

<span data-ttu-id="7c7fc-104">Ein *Tupel* ist eine Gruppierung unbenannter, aber geordneter Werte, die möglicherweise unterschiedliche Typen sind.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="7c7fc-105">Tupel können entweder Verweis Typen oder Strukturen sein.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c7fc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c7fc-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="7c7fc-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7c7fc-107">Remarks</span></span>

<span data-ttu-id="7c7fc-108">Jedes *Element* in der vorherigen Syntax kann ein beliebiger gültiger F #-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="7c7fc-109">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7c7fc-109">Examples</span></span>

<span data-ttu-id="7c7fc-110">Beispiele für Tupel sind Paare, Paare usw. desselben oder verschiedener Typen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="7c7fc-111">Einige Beispiele sind im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="7c7fc-112">Abrufen einzelner Werte</span><span class="sxs-lookup"><span data-stu-id="7c7fc-112">Obtaining Individual Values</span></span>

<span data-ttu-id="7c7fc-113">Sie können den Musterabgleich zum Zugreifen auf und Zuweisen von Namen für Tupelelemente verwenden, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="7c7fc-114">Sie können ein Tupel auch über einen Musterabgleich außerhalb eines `match` Ausdrucks über eine  `let` Bindung dekonstruieren:</span><span class="sxs-lookup"><span data-stu-id="7c7fc-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="7c7fc-115">Oder Sie können die Übereinstimmung von Tupeln als Eingaben für Funktionen vergleichen:</span><span class="sxs-lookup"><span data-stu-id="7c7fc-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="7c7fc-116">Wenn Sie nur ein Element des Tupels benötigen, können Sie das Platzhalter Zeichen (Unterstrich) verwenden, um zu vermeiden, dass ein neuer Name für einen Wert erstellt wird, den Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="7c7fc-117">Das Kopieren von Elementen aus einem verweistupel in ein strukturtupel ist ebenfalls einfach:</span><span class="sxs-lookup"><span data-stu-id="7c7fc-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="7c7fc-118">Die Funktionen `fst` und `snd` (nur verweistupel) geben jeweils das erste und zweite Element eines Tupels zurück.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="7c7fc-119">Es ist keine integrierte Funktion vorhanden, die das dritte Element eines Triple-Elements zurückgibt, aber Sie können es ganz einfach wie folgt schreiben.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="7c7fc-120">Im Allgemeinen ist es besser, den Musterabgleich für den Zugriff auf einzelne Tupelelemente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="7c7fc-121">Verwenden von Tupeln</span><span class="sxs-lookup"><span data-stu-id="7c7fc-121">Using Tuples</span></span>

<span data-ttu-id="7c7fc-122">Tupel stellen eine bequeme Möglichkeit dar, mehrere Werte aus einer Funktion zurückzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="7c7fc-123">Dieses Beispiel führt eine ganzzahlige Division aus und gibt das abgerundete Ergebnis des Vorgangs als ersten Member eines tupelpaars und den Rest als zweiten Member des Paars zurück.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="7c7fc-124">Tupel können auch als Funktionsargumente verwendet werden, wenn Sie die implizite Currying von Funktions Argumenten vermeiden möchten, die von der üblichen Funktions Syntax impliziert werden.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="7c7fc-125">Die übliche Syntax zum Definieren der Funktion `let sum a b = a + b` ermöglicht es Ihnen, eine Funktion zu definieren, bei der es sich um die partielle Anwendung des ersten Arguments der Funktion handelt, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="7c7fc-126">Wenn Sie ein Tupel als Parameter verwenden, wird die Currying deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="7c7fc-127">Weitere Informationen finden Sie unter "partielle Anwendung von Argumenten" in [Functions](./functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c7fc-127">For more information, see "Partial Application of Arguments" in [Functions](./functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="7c7fc-128">Namen von Tupeltypen</span><span class="sxs-lookup"><span data-stu-id="7c7fc-128">Names of Tuple Types</span></span>

<span data-ttu-id="7c7fc-129">Wenn Sie den Namen eines Typs schreiben, bei dem es sich um ein Tupel handelt, verwenden Sie das `*` Symbol zum Trennen von Elementen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="7c7fc-130">Bei einem Tupel, das aus `int` ,, `float` und besteht `string` , z `(10, 10.0, "ten")` . b., würde der Typ wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="7c7fc-131">Interoperation mit c#-Tupeln</span><span class="sxs-lookup"><span data-stu-id="7c7fc-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="7c7fc-132">In c# 7,0 wurden Tupel in die Sprache eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="7c7fc-133">Tupel in c# sind Strukturen und entsprechen strukturtupeln in F #.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="7c7fc-134">Wenn Sie mit c# interagieren müssen, müssen Sie strukturtupel verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="7c7fc-135">Dies ist einfach.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-135">This is easy to do.</span></span>  <span data-ttu-id="7c7fc-136">Stellen Sie sich beispielsweise vor, Sie müssen ein Tupel an eine c#-Klasse übergeben und dann das Ergebnis, das auch ein Tupel ist, verbrauchen:</span><span class="sxs-lookup"><span data-stu-id="7c7fc-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="7c7fc-137">Im F #-Code können Sie dann ein strukturtupel als Parameter übergeben und das Ergebnis als strukturtupel verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="7c7fc-138">Umrechnen zwischen verweistupeln und strukturtupeln</span><span class="sxs-lookup"><span data-stu-id="7c7fc-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="7c7fc-139">Da verweistupel und strukturtupel über eine völlig andere zugrunde liegende Darstellung verfügen, sind Sie nicht implizit konvertierbar.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="7c7fc-140">Das heißt, dass Code wie der folgende nicht kompiliert wird:</span><span class="sxs-lookup"><span data-stu-id="7c7fc-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="7c7fc-141">Sie müssen eine Muster Übereinstimmung für ein Tupel erstellen und das andere mit den Bestandteilen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="7c7fc-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7c7fc-142">For example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="7c7fc-143">Kompilierte Form von verweistupeln</span><span class="sxs-lookup"><span data-stu-id="7c7fc-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="7c7fc-144">In diesem Abschnitt wird die Form von Tupeln erläutert, wenn Sie kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="7c7fc-145">Die hier aufgeführten Informationen sind nur erforderlich, wenn Sie .NET Framework 3,5 oder niedriger abzielen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="7c7fc-146">Tupel werden in Objekte von einem von mehreren generischen Typen kompiliert, die alle den Namen haben, die `System.Tuple` auf die Stelligkeit überladen werden, oder die Anzahl der Typparameter.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="7c7fc-147">Tupeltypen werden in dieser Form angezeigt, wenn Sie Sie aus einer anderen Sprache anzeigen, z. b. c# oder Visual Basic, oder wenn Sie ein Tool verwenden, das keine F #-Konstrukte kennt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="7c7fc-148">Die `Tuple` Typen wurden in .NET Framework 4 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="7c7fc-149">Wenn Sie auf eine frühere Version von .NET Framework abzielen, verwendet der Compiler Versionen von `System.Tuple` aus der 2,0-Version der F #-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-149">If you are targeting an earlier version of .NET Framework, the compiler uses versions of `System.Tuple` from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="7c7fc-150">Die Typen in dieser Bibliothek werden nur für Anwendungen verwendet, die auf die Versionen 2,0, 3,0 und 3,5 von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of .NET Framework.</span></span> <span data-ttu-id="7c7fc-151">Die Typweiterleitung wird verwendet, um die binäre Kompatibilität zwischen .NET Framework 2,0-und .NET Framework 4 F #-Komponenten sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="7c7fc-152">Kompilierte Form von strukturtupeln</span><span class="sxs-lookup"><span data-stu-id="7c7fc-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="7c7fc-153">Strukturtupel (z. b. `struct (x, y)` ) unterscheiden sich grundlegend von verweistupeln.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="7c7fc-154">Sie werden in den <xref:System.ValueTuple> Typ kompiliert, überlastet durch Stelligkeit oder die Anzahl der Typparameter.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="7c7fc-155">Sie entsprechen [c# 7,0-Tupeln](../../csharp/language-reference/builtin-types/value-tuples.md) und [Visual Basic 2017-Tupeln](../../visual-basic/programming-guide/language-features/data-types/tuples.md)und interagieren bidirektional.</span><span class="sxs-lookup"><span data-stu-id="7c7fc-155">They are equivalent to [C# 7.0 Tuples](../../csharp/language-reference/builtin-types/value-tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c7fc-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c7fc-156">See also</span></span>

- [<span data-ttu-id="7c7fc-157">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7c7fc-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7c7fc-158">F#-Typen</span><span class="sxs-lookup"><span data-stu-id="7c7fc-158">F# Types</span></span>](fsharp-types.md)
