---
title: Unterscheidungs-Union (F#)
description: Informationen zum Verwenden von F#-Unterscheidungs-Unions.
ms.date: 05/16/2016
ms.openlocfilehash: 617c659e26df52819a98294bcbfa081ab82fed03
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2018
ms.locfileid: "34149074"
---
# <a name="discriminated-unions"></a><span data-ttu-id="47c1a-103">Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="47c1a-103">Discriminated Unions</span></span>

<span data-ttu-id="47c1a-104">Unterscheidungs-Unions bieten Unterstützung für Werte, bei denen es sich um einen Fall aus einer Anzahl verschiedener benannter Fälle handeln kann, mit jeweils potenziell unterschiedlichen Werten und Typen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="47c1a-105">Unterscheidungs-Unions sind für heterogene Daten nützlich: Daten, die besondere Fälle enthalten können, einschließlich gültiger und fehlerhafter Fälle, Daten, die sich im Typ von einer Instanz zur nächsten unterscheiden und als Alternative für kleine Objekthierarchien.</span><span class="sxs-lookup"><span data-stu-id="47c1a-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="47c1a-106">Außerdem werden rekursive Unterscheidungs-Unions verwendet, um Strukturdatenstrukturen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="47c1a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="47c1a-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a><span data-ttu-id="47c1a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47c1a-108">Remarks</span></span>
<span data-ttu-id="47c1a-109">Unterscheidungs-Unions ähneln Union-Typen in anderen Sprachen, aber es gibt Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="47c1a-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="47c1a-110">Wie bei einem Union-Typ in C++ oder einem Variantentyp in Visual Basic werden die im Wert gespeicherten Daten nicht korrigiert. Der Typ kann eine von mehreren unterschiedlichen Optionen sein.</span><span class="sxs-lookup"><span data-stu-id="47c1a-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="47c1a-111">Im Gegensatz zu Unions in diesen anderen Sprachen, jedoch der möglichen Optionen wird jeweils ein *Fallbezeichner*.</span><span class="sxs-lookup"><span data-stu-id="47c1a-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="47c1a-112">Die Fallbezeichner sind Namen für die verschiedenen möglichen Typen von Werten, die Objekte dieses Typs aufweisen können. Die Werte sind optional.</span><span class="sxs-lookup"><span data-stu-id="47c1a-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="47c1a-113">Wenn keine Werte vorhanden sind, entspricht der Fall einem Enumerationsfall.</span><span class="sxs-lookup"><span data-stu-id="47c1a-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="47c1a-114">Wenn Werte vorhanden sind, kann jeder Wert entweder ein einzelner Wert eines angegebenen Typs oder ein Tupel sein, das mehrere Felder gleicher oder unterschiedlicher Typen aggregiert.</span><span class="sxs-lookup"><span data-stu-id="47c1a-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="47c1a-115">Sie können einem einzelnen Feld einen Namen zuweisen, der Name ist jedoch optional, selbst wenn andere Felder im gleichen Fall benannt sind.</span><span class="sxs-lookup"><span data-stu-id="47c1a-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="47c1a-116">Eingabehilfen für diskriminierte Unions standardmäßig `public`.</span><span class="sxs-lookup"><span data-stu-id="47c1a-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="47c1a-117">Betrachten Sie zum Beispiel die folgende Deklaration eines Formtyps:</span><span class="sxs-lookup"><span data-stu-id="47c1a-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="47c1a-118">Der vorangehende Code deklariert eine Unterscheidungs-Union-Form, die Werte der folgenden drei Fälle haben kann: Rechteck, Kreis und Prisma.</span><span class="sxs-lookup"><span data-stu-id="47c1a-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="47c1a-119">Jeder Fall hat einen anderen Satz von Feldern.</span><span class="sxs-lookup"><span data-stu-id="47c1a-119">Each case has a different set of fields.</span></span> <span data-ttu-id="47c1a-120">Der Rechteckfall hat zwei benannte Felder, beide vom Typ `float` mit den Namen Breite und Länge.</span><span class="sxs-lookup"><span data-stu-id="47c1a-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="47c1a-121">Der Kreisfall hat nur ein benanntes Feld, nämlich Radius.</span><span class="sxs-lookup"><span data-stu-id="47c1a-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="47c1a-122">Der prismafall hat drei Felder zwei welche (Breite und Höhe) sind benannte Felder.</span><span class="sxs-lookup"><span data-stu-id="47c1a-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="47c1a-123">Unbenannte Felder werden als anonyme Felder bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="47c1a-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="47c1a-124">Sie erstellen Objekte, indem Sie Werte für die benannten und anonymen Felder bereitstellen, wie in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="47c1a-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="47c1a-125">Dieser Code zeigt, dass Sie entweder die benannten Felder in der Initialisierung verwenden können, oder Sie können die Reihenfolge der Felder in der Deklaration erstellen und nur die Werte für jedes Feld bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="47c1a-126">Der Konstruktoraufruf für `rect` im vorherigen Code verwendet benannte Felder, der Konstruktoraufruf für `circ` hingegen die Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="47c1a-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="47c1a-127">Sie können die angeordneten Felder und benannten Felder wie in der Konstruktion von `prism` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="47c1a-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="47c1a-128">Der `option`-Typ ist eine einfache Unterscheidungs-Union in der F#-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="47c1a-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="47c1a-129">Der `option`-Typ wird folgendermaßen deklariert.</span><span class="sxs-lookup"><span data-stu-id="47c1a-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="47c1a-130">Der vorherige Code gibt an, dass der `Option`-Typ eine Unterscheidungs-Union mit den beiden Fällen `Some` und `None` ist.</span><span class="sxs-lookup"><span data-stu-id="47c1a-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="47c1a-131">Der `Some`-Fall verfügt über einen zugeordneten Wert, der aus einem anonymen Feld besteht, dessen Typ durch den Typparameter `'a` dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="47c1a-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="47c1a-132">Der `None`-Fall verfügt über keinen zugeordneten Wert.</span><span class="sxs-lookup"><span data-stu-id="47c1a-132">The `None` case has no associated value.</span></span> <span data-ttu-id="47c1a-133">Der `option`-Typ gibt also einen generischen Typ an, der entweder einen Wert eines Typs oder keinen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="47c1a-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="47c1a-134">Der `Option`-Typ weist außerdem ein kleingeschriebenes Typalias auf, `option`, das häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="47c1a-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="47c1a-135">Die Fallbezeichner können für den Unterscheidungs-Union-Typ als Konstruktoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47c1a-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="47c1a-136">Der folgende Code wird z. B. verwendet, um Werte des `option`-Typs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="47c1a-137">Die Fallbezeichner werden auch in Musterabgleichsausdrücken verwendet.</span><span class="sxs-lookup"><span data-stu-id="47c1a-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="47c1a-138">In einem Musterabgleichsausdruck werden Bezeichner für die Werte bereitgestellt, die den einzelnen Fällen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="47c1a-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="47c1a-139">Im folgenden Code ist `x` z. B. der Bezeichner, dem der Wert des `Some`-Falls des `option`-Typs zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="47c1a-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="47c1a-140">In Musterabgleichsausdrücken können Sie benannte Felder verwenden, um Unterscheidungs-Union-Übereinstimmungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="47c1a-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="47c1a-141">Für den zuvor deklarierten Formtyp können Sie die benannten Felder verwenden, um die Werte von Feldern zu extrahieren, wie der folgende Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="47c1a-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="47c1a-142">Normalerweise können die Fallbezeichner verwendet werden, ohne sie durch den Namen der Union zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="47c1a-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="47c1a-143">Wenn Sie soll, dass der Name immer mit dem Namen der Union qualifiziert werden, können Sie anwenden der [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) -Attribut auf die union-Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="47c1a-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="47c1a-144">Entpacken Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="47c1a-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="47c1a-145">In f# Unterscheidungs-Unions werden häufig zum in der Domäne Modellierung Umschließen eines einzelnen Typs.</span><span class="sxs-lookup"><span data-stu-id="47c1a-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="47c1a-146">Es ist einfach, um den zugrunde liegenden Wert über einen Musterabgleich sowie zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="47c1a-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="47c1a-147">Sie müssen nicht für einen einzelnen Fall einen Vergleichsausdruck verwenden:</span><span class="sxs-lookup"><span data-stu-id="47c1a-147">You don't need to use a match expression for a single case:</span></span>
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="47c1a-148">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="47c1a-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="47c1a-149">Struktur Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="47c1a-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="47c1a-150">Ab f# 4.1, können Sie auch Unterscheidungs-Unions als Strukturen darstellen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="47c1a-151">Dies erfolgt mit der `[<Struct>]` Attribut.</span><span class="sxs-lookup"><span data-stu-id="47c1a-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="47c1a-152">Da diese sind Werttypen und nicht auf Typen verweisen, sind zusätzliche Überlegungen, die im Vergleich mit dem Verweis Unterscheidungs-Unions:</span><span class="sxs-lookup"><span data-stu-id="47c1a-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="47c1a-153">Sie werden als Werttypen kopiert und Werttypsemantik haben.</span><span class="sxs-lookup"><span data-stu-id="47c1a-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="47c1a-154">Eine rekursive Definition können keine mit einer multicase Discriminated-Union-Struktur.</span><span class="sxs-lookup"><span data-stu-id="47c1a-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="47c1a-155">Sie müssen eine multicase Struktur Discriminated Union Groß-/Kleinschreibung eindeutige Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="47c1a-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="47c1a-156">Verwenden von Unterscheidungs-Unions statt Objekthierarchien</span><span class="sxs-lookup"><span data-stu-id="47c1a-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>
<span data-ttu-id="47c1a-157">Sie können oft eine Unterscheidungs-Union als einfachere Alternative zu einer kleinen Objekthierarchie verwenden.</span><span class="sxs-lookup"><span data-stu-id="47c1a-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="47c1a-158">Die folgende Unterscheidungs-Union könnte z. B. statt einer `Shape`-Basisklasse verwendet werden, die abgeleitete Typen für Kreis, Quadrat usw. aufweist.</span><span class="sxs-lookup"><span data-stu-id="47c1a-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="47c1a-159">Statt einer virtuellen Methode zur Berechnung eines Bereich oder eines Umkreises, wie sie in einer objektorientierten Implementierung verwendet werden würde, können Sie mithilfe des Mustervergleichs die entsprechenden Formeln branchen, um die Mengen zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="47c1a-160">Im folgenden Beispiel werden andere Formeln verwendet, um den Bereich abhängig von der Form zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="47c1a-161">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="47c1a-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="47c1a-162">Verwenden von Unterscheidungs-Unions für Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="47c1a-162">Using Discriminated Unions for Tree Data Structures</span></span>
<span data-ttu-id="47c1a-163">Unterscheidungs-Unions können rekursiv sein, d. h., dass die Union selbst im Typ eines Falles oder mehrerer Fälle enthalten sein kann.</span><span class="sxs-lookup"><span data-stu-id="47c1a-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="47c1a-164">Rekursive Unterscheidungs-Unions können verwendet werden, um Strukturen zur Gestaltung von Ausdrücken in Programmiersprachen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="47c1a-165">Im folgenden Code wird eine rekursive Unterscheidungs-Union verwendet, um eine binäre Strukturdatenstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47c1a-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="47c1a-166">Die Union besteht aus zwei Fällen: `Node`, der ein Knoten mit einem ganzzahligen Wert und linken und rechten Teilstrukturen ist, und `Tip`, der die Struktur beendet.</span><span class="sxs-lookup"><span data-stu-id="47c1a-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="47c1a-167">Im vorherigen Code verfügt `resultSumTree` über den Wert 10.</span><span class="sxs-lookup"><span data-stu-id="47c1a-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="47c1a-168">Die folgende Abbildung zeigt die Struktur für `myTree` an.</span><span class="sxs-lookup"><span data-stu-id="47c1a-168">The following illustration shows the tree structure for `myTree`.</span></span>

![Struktur für myTree](../media/TreeStructureDiagram.png)

<span data-ttu-id="47c1a-170">Unterscheidungs-Unions funktionieren gut, wenn die Knoten in der Struktur heterogen sind.</span><span class="sxs-lookup"><span data-stu-id="47c1a-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="47c1a-171">Im folgenden Code stellt der `Expression`-Typ die abstrakte Syntaxstruktur eines Ausdrucks in einer einfachen Programmiersprache dar, die Addition und Multiplikation von Zahlen und Variablen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="47c1a-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="47c1a-172">Einige der Union-Fälle sind nicht rekursiv und stellen entweder Zahlen (`Number`) oder Variablen (`Variable`) dar.</span><span class="sxs-lookup"><span data-stu-id="47c1a-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="47c1a-173">Andere Fälle sind rekursiv und stellen Operationen (`Add` und `Multiply`) dar, wobei die Operanden auch Ausdrücke sind.</span><span class="sxs-lookup"><span data-stu-id="47c1a-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="47c1a-174">Die `Evaluate`-Funktion verwendet einen Vergleichsausdruck, um den Syntaxbaum rekursiv zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="47c1a-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="47c1a-175">Wenn dieser Code ausgeführt wird, beträgt der Wert von `result` 5.</span><span class="sxs-lookup"><span data-stu-id="47c1a-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="47c1a-176">Allgemeine Attribute</span><span class="sxs-lookup"><span data-stu-id="47c1a-176">Common Attributes</span></span>

<span data-ttu-id="47c1a-177">Die folgenden Attribute werden häufig im Unterscheidungs-Unions angezeigt:</span><span class="sxs-lookup"><span data-stu-id="47c1a-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* <span data-ttu-id="47c1a-178">`[Struct]` (F# 4.1 und höher)</span><span class="sxs-lookup"><span data-stu-id="47c1a-178">`[Struct]` (F# 4.1 and higher)</span></span>

## <a name="see-also"></a><span data-ttu-id="47c1a-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47c1a-179">See Also</span></span>
[<span data-ttu-id="47c1a-180">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="47c1a-180">F# Language Reference</span></span>](index.md)
