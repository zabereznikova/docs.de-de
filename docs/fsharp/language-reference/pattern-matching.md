---
title: Musterabgleich
description: 'Erfahren Sie, wie Muster in F # verwendet werden, um Daten mit logischen Strukturen zu vergleichen, Daten in Bestandteile zu zerlegen oder Informationen aus Daten zu extrahieren.'
ms.date: 11/12/2020
ms.openlocfilehash: e167712b082b7f587e41a78edcaf0a0db9c7294b
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687804"
---
# <a name="pattern-matching"></a><span data-ttu-id="01d97-103">Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="01d97-103">Pattern Matching</span></span>

<span data-ttu-id="01d97-104">Muster sind Regeln zum Transformieren von Eingabedaten.</span><span class="sxs-lookup"><span data-stu-id="01d97-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="01d97-105">Sie werden in F# stets verwendet, um Daten mit logischen Strukturen zu vergleichen, Daten in einzelne Bestandteile zu zerlegen oder auf unterschiedliche Weise Informationen aus Daten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="01d97-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="01d97-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01d97-106">Remarks</span></span>

<span data-ttu-id="01d97-107">Muster werden in vielen Sprachkonstrukten verwendet, z. B. im `match`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="01d97-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="01d97-108">Sie werden verwendet, wenn Argumente für Funktionen in `let`-Bindungen oder Lambda-Ausdrücken verarbeitet werden, sowie in den dem `try...with`-Ausdruck zugeordneten Ausnahmehandlern.</span><span class="sxs-lookup"><span data-stu-id="01d97-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="01d97-109">Weitere Informationen finden Sie unter [Match Expressions](match-expressions.md), [let-Bindungen](./functions/let-bindings.md), [Lambda-Ausdrücke: das `fun` Schlüsselwort](./functions/lambda-expressions-the-fun-keyword.md)und [Ausnahmen: der `try...with` Ausdruck](./exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="01d97-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="01d97-110">Im `match` Ausdruck ist das *Muster* z. b. das, was dem Pipe-Symbol folgt.</span><span class="sxs-lookup"><span data-stu-id="01d97-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="01d97-111">Jedes Muster fungiert als Regel zum Transformieren von Eingaben.</span><span class="sxs-lookup"><span data-stu-id="01d97-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="01d97-112">Im `match`-Ausdruck wird jedes Muster einzeln untersucht, um zu ermitteln, ob die Eingabedaten mit dem Muster kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="01d97-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="01d97-113">Wenn eine Übereinstimmung gefunden wird, wird der Ergebnisausdruck ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="01d97-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="01d97-114">Wenn keine Übereinstimmung gefunden wird, wird die nächste Musterregel getestet.</span><span class="sxs-lookup"><span data-stu-id="01d97-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="01d97-115">Der *optionale when-* Bedingungs Teil wird in [Match-Ausdrücken](match-expressions.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="01d97-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="01d97-116">In der folgenden Tabelle werden unterstützte Muster aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="01d97-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="01d97-117">Zur Laufzeit wird die Eingabe anhand jedes der folgenden Muster in der in der Tabelle aufgeführten Reihenfolge überprüft. Die Muster werden rekursiv vom ersten bis zum letzten Muster im Code und von links nach rechts in den einzelnen Zeilen angewendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="01d97-118">Name</span><span class="sxs-lookup"><span data-stu-id="01d97-118">Name</span></span>|<span data-ttu-id="01d97-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="01d97-119">Description</span></span>|<span data-ttu-id="01d97-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01d97-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="01d97-121">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-121">Constant pattern</span></span>|<span data-ttu-id="01d97-122">Ein beliebiges numerisches Literal, Zeichenliteral oder Zeichenfolgenliteral, eine Enumerationskonstante oder ein definierter Literalbezeichner.</span><span class="sxs-lookup"><span data-stu-id="01d97-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="01d97-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="01d97-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="01d97-124">Bezeichnermuster</span><span class="sxs-lookup"><span data-stu-id="01d97-124">Identifier pattern</span></span>|<span data-ttu-id="01d97-125">Der Wert eines Falls einer Unterscheidungs-Union, eine Ausnahmebezeichnung oder ein Fall eines aktiven Musters.</span><span class="sxs-lookup"><span data-stu-id="01d97-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="01d97-126">Variablenmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-126">Variable pattern</span></span>|<span data-ttu-id="01d97-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="01d97-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="01d97-128">`as`-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-128">`as` pattern</span></span>|<span data-ttu-id="01d97-129">*Muster* als *Bezeichner*</span><span class="sxs-lookup"><span data-stu-id="01d97-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="01d97-130">OR-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-130">OR pattern</span></span>|<span data-ttu-id="01d97-131">*muster1* &#124; *muster2*</span><span class="sxs-lookup"><span data-stu-id="01d97-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="01d97-132">AND-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-132">AND pattern</span></span>|<span data-ttu-id="01d97-133">*muster1* &amp; *muster2*</span><span class="sxs-lookup"><span data-stu-id="01d97-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="01d97-134">Cons-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-134">Cons pattern</span></span>|<span data-ttu-id="01d97-135">*identifier* *Bezeichner:: List-Identifier*</span><span class="sxs-lookup"><span data-stu-id="01d97-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="01d97-136">Listenmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-136">List pattern</span></span>|<span data-ttu-id="01d97-137">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="01d97-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="01d97-138">Arraymuster</span><span class="sxs-lookup"><span data-stu-id="01d97-138">Array pattern</span></span>|<span data-ttu-id="01d97-139">[&#124; *pattern_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="01d97-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="01d97-140">Muster in Klammern</span><span class="sxs-lookup"><span data-stu-id="01d97-140">Parenthesized pattern</span></span>|<span data-ttu-id="01d97-141">( *Muster* )</span><span class="sxs-lookup"><span data-stu-id="01d97-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="01d97-142">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-142">Tuple pattern</span></span>|<span data-ttu-id="01d97-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="01d97-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="01d97-144">Datensatzmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-144">Record pattern</span></span>|<span data-ttu-id="01d97-145">{ *Bezeichner1*  =  *pattern_1*; ... ; *identifier_n*  =  *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="01d97-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="01d97-146">Platzhaltermuster</span><span class="sxs-lookup"><span data-stu-id="01d97-146">Wildcard pattern</span></span>|<span data-ttu-id="01d97-147">_</span><span class="sxs-lookup"><span data-stu-id="01d97-147">_</span></span>|`_`|
|<span data-ttu-id="01d97-148">Muster zusammen mit Typanmerkung</span><span class="sxs-lookup"><span data-stu-id="01d97-148">Pattern together with type annotation</span></span>|<span data-ttu-id="01d97-149">*Pattern* : *Type*</span><span class="sxs-lookup"><span data-stu-id="01d97-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="01d97-150">Typtestmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-150">Type test pattern</span></span>|<span data-ttu-id="01d97-151">:?</span><span class="sxs-lookup"><span data-stu-id="01d97-151">:?</span></span> <span data-ttu-id="01d97-152">*Type* [as *Identifier* ]</span><span class="sxs-lookup"><span data-stu-id="01d97-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="01d97-153">NULL-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-153">Null pattern</span></span>|<span data-ttu-id="01d97-154">NULL</span><span class="sxs-lookup"><span data-stu-id="01d97-154">null</span></span>|`null`|
|<span data-ttu-id="01d97-155">Nameof-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-155">Nameof pattern</span></span>|<span data-ttu-id="01d97-156">*nameof-expr*</span><span class="sxs-lookup"><span data-stu-id="01d97-156">*nameof expr*</span></span>|`nameof str`|

## <a name="constant-patterns"></a><span data-ttu-id="01d97-157">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-157">Constant Patterns</span></span>

<span data-ttu-id="01d97-158">Konstantenmuster sind numerische Literale, Zeichenliterale und Zeichenfolgenliterale, Enumerationskonstanten (einschließlich Enumerationstypnamen).</span><span class="sxs-lookup"><span data-stu-id="01d97-158">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="01d97-159">Ein `match`-Ausdruck, der nur über Konstantenmuster verfügt, ist mit case-Anweisungen in anderen Sprachen vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="01d97-159">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="01d97-160">Die Eingabe wird mit dem Literalwert verglichen, und das Muster stimmt überein, wenn die Werte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="01d97-160">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="01d97-161">Der Typ des Literals muss mit dem Typ der Eingabe kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="01d97-161">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="01d97-162">Im folgenden Beispiel wird die Verwendung von Literalmustern veranschaulicht, und es werden außerdem ein Variablenmuster und ein OR-Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-162">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="01d97-163">Ein weiteres Beispiel für ein Literalmuster ist ein auf Enumerationskonstanten basierendes Muster.</span><span class="sxs-lookup"><span data-stu-id="01d97-163">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="01d97-164">Wenn Sie Enumerationskonstanten verwenden, müssen Sie den Enumerationstypnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="01d97-164">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="01d97-165">Bezeichnermuster</span><span class="sxs-lookup"><span data-stu-id="01d97-165">Identifier Patterns</span></span>

<span data-ttu-id="01d97-166">Wenn das Muster eine Zeichenfolge ist, die einen gültigen Bezeichner bildet, bestimmt die Form des Bezeichners, wie das Muster verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="01d97-166">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="01d97-167">Wenn der Bezeichner länger als ein einzelnes Zeichen ist und mit einem Großbuchstaben beginnt, versucht der Compiler, eine Übereinstimmung mit dem Bezeichnermuster zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="01d97-167">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="01d97-168">Der Bezeichner für dieses Muster kann ein Wert sein, der mit dem Literal-Attribut, einem Unterscheidungs-Union-Fall, einem Ausnahmebezeichner oder einem Fall eines aktiven Musters markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="01d97-168">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="01d97-169">Wenn kein übereinstimmender Bezeichner gefunden wird, schlägt der Vergleich fehl, und die nächste Musterregel, das Variablenmuster, wird mit der Eingabe verglichen.</span><span class="sxs-lookup"><span data-stu-id="01d97-169">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="01d97-170">Unterscheidungs-Union-Muster können einfache benannte Fälle sein oder über einen Wert bzw. über ein mehrere Werte enthaltendes Tupel verfügen.</span><span class="sxs-lookup"><span data-stu-id="01d97-170">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="01d97-171">Wenn ein Wert vorhanden ist, müssen Sie einen Bezeichner für den Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="01d97-171">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="01d97-172">Im Fall eines Tupels müssen Sie ein Tupelmuster mit einem Bezeichner für jedes Element des Tupels oder einen Bezeichner mit einem Feldnamen für eine oder mehrere benannte Union-Felder angeben.</span><span class="sxs-lookup"><span data-stu-id="01d97-172">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="01d97-173">Entsprechende Beispiele finden Sie in den Codebeispielen dieses Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="01d97-173">See the code examples in this section for examples.</span></span>

<span data-ttu-id="01d97-174">Der `option`-Typ ist eine Unterscheidungs-Union mit den beiden Fällen `Some` und `None`.</span><span class="sxs-lookup"><span data-stu-id="01d97-174">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="01d97-175">Ein Fall (`Some`) verfügt über einen Wert, der andere Fall (`None`) ist jedoch lediglich ein benannter Fall.</span><span class="sxs-lookup"><span data-stu-id="01d97-175">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="01d97-176">Daher muss `Some` über eine Variable für den dem Fall `Some` zugeordneten Wert verfügen, `None` muss jedoch als None angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-176">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="01d97-177">Im folgenden Code wird der Variablen `var1` der Wert zugewiesen, der durch den Vergleich mit dem Fall `Some` ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="01d97-177">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="01d97-178">Im folgenden Beispiel enthält die Unterscheidungs-Union `PersonName` eine Kombination von Zeichenfolgen und Zeichen, die mögliche Formen von Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="01d97-178">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="01d97-179">Die Fälle der Unterscheidungs-Union lauten `FirstOnly`, `LastOnly` und `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="01d97-179">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="01d97-180">Für Unterscheidungs-Unions, die über benannte Felder verfügen, verwenden Sie das Gleichheitszeichen (=), um den Wert eines benannten Felds zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="01d97-180">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="01d97-181">Betrachten Sie zum Beispiel eine Unterscheidungs-Union mit einer Deklaration wie der folgenden.</span><span class="sxs-lookup"><span data-stu-id="01d97-181">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="01d97-182">Sie können die benannten Felder in einem Musterabgleichsausdruck wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="01d97-182">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="01d97-183">Die Verwendung des benannten Felds ist optional. Im vorherigen Beispiel haben `Circle(r)` und `Circle(radius = r)` die gleiche Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="01d97-183">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="01d97-184">Wenn Sie mehrere Felder angeben, verwenden Sie das Semikolon (;) als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="01d97-184">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="01d97-185">Mit aktiven Mustern können Sie komplexere benutzerdefinierte Musterabgleiche definieren.</span><span class="sxs-lookup"><span data-stu-id="01d97-185">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="01d97-186">Weitere Informationen zu aktiven Mustern finden Sie unter [aktive Muster](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="01d97-186">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="01d97-187">Der Fall, in dem der Bezeichner eine Ausnahme ist, wird beim Mustervergleich im Kontext von Ausnahmehandlern verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-187">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="01d97-188">Weitere Informationen zum Musterabgleich bei der Ausnahmebehandlung finden Sie unter [Ausnahmen: der `try...with` Ausdruck](./exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="01d97-188">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="01d97-189">Variablenmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-189">Variable Patterns</span></span>

<span data-ttu-id="01d97-190">Im Variablenmuster wird dem zu vergleichenden Wert ein Variablenname zugewiesen, der dann im Ausführungsausdruck auf der rechten Seite des Symbols `->` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="01d97-190">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="01d97-191">Ein Variablenmuster an sich stimmt mit jeder Eingabe überein, jedoch sind Variablenmuster häufig in anderen Mustern enthalten und ermöglichen somit komplexere Strukturen, z. B. Tupel und Arrays, die in Variablen zerlegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="01d97-191">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="01d97-192">Im folgenden Beispiel wird ein Variablenmuster in einem Tupelmuster veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="01d97-192">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="01d97-193">as-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-193">as Pattern</span></span>

<span data-ttu-id="01d97-194">Das `as`-Muster ist ein Muster, an das eine `as`-Klausel angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="01d97-194">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="01d97-195">Die `as`-Klausel bindet den übereinstimmenden Wert an einen Namen, der im Ausführungsausdruck eines `match`-Ausdrucks verwendet werden kann. Falls das Muster in einer `let`-Bindung verwendet wird, wird stattdessen der Name dem lokalen Bereich als Bindung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="01d97-195">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="01d97-196">Im folgenden Beispiel wird ein `as`-Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-196">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="01d97-197">OR-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-197">OR Pattern</span></span>

<span data-ttu-id="01d97-198">Das OR-Muster wird verwendet, wenn Eingabedaten mit mehreren Mustern übereinstimmen können und als Ergebnis der gleiche Code ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="01d97-198">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="01d97-199">Die Typen beider Seiten des OR-Musters müssen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="01d97-199">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="01d97-200">Das OR-Muster wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="01d97-200">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="01d97-201">AND-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-201">AND Pattern</span></span>

<span data-ttu-id="01d97-202">Das AND-Muster erfordert, dass die Eingabe mit zwei Mustern übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="01d97-202">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="01d97-203">Die Typen beider Seiten des AND-Musters müssen kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="01d97-203">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="01d97-204">Das folgende Beispiel ist ähnlich wie `detectZeroTuple` im Abschnitt tupelmuster weiter unten in diesem Thema dargestellt. hier werden jedoch sowohl `var1` `var2` als auch Werte mithilfe des-Musters und des-Musters abgerufen.</span><span class="sxs-lookup"><span data-stu-id="01d97-204">The following example is like `detectZeroTuple` shown in the Tuple Pattern section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="01d97-205">Cons-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-205">Cons Pattern</span></span>

<span data-ttu-id="01d97-206">Das Cons-Muster wird verwendet, um eine Liste in das erste Element, den *Kopf* und eine Liste *mit den restlichen* Elementen, dem Ende, zu zerlegen.</span><span class="sxs-lookup"><span data-stu-id="01d97-206">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="01d97-207">Listenmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-207">List Pattern</span></span>

<span data-ttu-id="01d97-208">Mit dem Listenmuster können Listen in eine Reihe von Elementen zerlegt werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-208">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="01d97-209">Das Listenmuster selbst darf nur mit Listen einer bestimmten Anzahl von Elementen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="01d97-209">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="01d97-210">Arraymuster</span><span class="sxs-lookup"><span data-stu-id="01d97-210">Array Pattern</span></span>

<span data-ttu-id="01d97-211">Das Arraymuster ähnelt dem Listenmuster, und es kann zum Zerlegen von Arrays einer bestimmten Länge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-211">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="01d97-212">Muster in Klammern</span><span class="sxs-lookup"><span data-stu-id="01d97-212">Parenthesized Pattern</span></span>

<span data-ttu-id="01d97-213">Muster können in Klammern eingeschlossen werden, um die gewünschte Assoziativität zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="01d97-213">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="01d97-214">Im folgenden Beispiel werden Klammern verwendet, um die Assoziativität zwischen einem AND-Muster und einem Cons-Muster zu steuern.</span><span class="sxs-lookup"><span data-stu-id="01d97-214">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="01d97-215">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-215">Tuple Pattern</span></span>

<span data-ttu-id="01d97-216">Mithilfe des Tupelmusters werden Eingabe in Tupelform verglichen. Es ermöglicht das Zerlegen des Tupels in seine Bestandteile mithilfe von Musterabgleichsvariablen für die einzelnen Positionen im Tupel.</span><span class="sxs-lookup"><span data-stu-id="01d97-216">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="01d97-217">Im folgenden Beispiel wird die Verwendung des Tupelmusters veranschaulicht, und es werden außerdem Literalmuster, Variablenmuster und das Platzhaltermuster verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-217">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="01d97-218">Datensatzmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-218">Record Pattern</span></span>

<span data-ttu-id="01d97-219">Mit dem Datensatzmuster werden Datensätze zerlegt, um die Werte von Feldern zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="01d97-219">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="01d97-220">Das Muster muss nicht auf alle Felder des Datensatzes verweisen. Weggelassene Felder werden nicht verglichen und nicht extrahiert.</span><span class="sxs-lookup"><span data-stu-id="01d97-220">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="01d97-221">Platzhaltermuster</span><span class="sxs-lookup"><span data-stu-id="01d97-221">Wildcard Pattern</span></span>

<span data-ttu-id="01d97-222">Das Platzhaltermuster wird durch den Unterstrich (`_`) dargestellt und stimmt wie das Variablenmuster mit jeder Eingabe überein, außer dass die Eingabe verworfen wird, anstatt einer Variablen zugewiesen zu werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-222">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="01d97-223">Das Platzhaltermuster wird oft innerhalb anderer Muster als Platzhalter für Werte verwendet, die im Ausdruck auf der rechten Seite des Symbols `->` nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-223">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="01d97-224">Das Platzhaltermuster wird außerdem häufig am Ende einer Liste von Mustern als Übereinstimmung für jede nicht übereinstimmende Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-224">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="01d97-225">Das Platzhaltermuster wird in vielen Codebeispielen dieses Themas veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="01d97-225">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="01d97-226">Ein Beispiel finden Sie im vorangehenden Code.</span><span class="sxs-lookup"><span data-stu-id="01d97-226">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="01d97-227">Muster mit Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="01d97-227">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="01d97-228">Muster können Typanmerkungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="01d97-228">Patterns can have type annotations.</span></span> <span data-ttu-id="01d97-229">Diese verhalten sich wie andere Typanmerkungen und steuern Typrückschluss wie diese.</span><span class="sxs-lookup"><span data-stu-id="01d97-229">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="01d97-230">Typanmerkungen in Mustern müssen in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-230">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="01d97-231">Im folgenden Code wird ein Muster veranschaulicht, das eine Typanmerkung aufweist.</span><span class="sxs-lookup"><span data-stu-id="01d97-231">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="01d97-232">Typtestmuster</span><span class="sxs-lookup"><span data-stu-id="01d97-232">Type Test Pattern</span></span>

<span data-ttu-id="01d97-233">Das Typtestmuster wird verwendet, um die Eingabe anhand eines Typs zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="01d97-233">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="01d97-234">Wenn der Eingabetyp mit dem im Muster angegebenen Typ oder einem von diesem abgeleiteten Typ übereinstimmt, ist der Vergleich erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="01d97-234">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="01d97-235">Das Typtestmuster wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="01d97-235">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

<span data-ttu-id="01d97-236">Wenn Sie nur überprüfen, ob es sich bei einem Bezeichner um einen bestimmten abgeleiteten Typ handelt, benötigen Sie den `as identifier` Teil des Musters nicht, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="01d97-236">If you're only checking if an identifier is of a particular derived type, you don't need the `as identifier` part of the pattern, as shown in the following example:</span></span>

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a><span data-ttu-id="01d97-237">NULL-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-237">Null Pattern</span></span>

<span data-ttu-id="01d97-238">Das NULL-Muster wird mit dem NULL-Wert verglichen, der beim Arbeiten mit Typen, die NULL-Werte zulassen, vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="01d97-238">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="01d97-239">NULL-Muster werden häufig verwendet, wenn Sie mit .NET Framework Code interagieren.</span><span class="sxs-lookup"><span data-stu-id="01d97-239">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="01d97-240">Beispielsweise kann der Rückgabewert einer .NET-API die Eingabe für einen `match`-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="01d97-240">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="01d97-241">Die Steuerung des Programmablaufs kann von Eigenschaften des Rückgabewerts abhängig gemacht werden, beispielsweise davon, ob der Rückgabewert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="01d97-241">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="01d97-242">Mithilfe des NULL-Musters können Sie verhindern, dass NULL-Werte an den Rest des Programms weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="01d97-242">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="01d97-243">Im folgenden Beispiel werden das NULL-Muster und das Variablenmuster verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d97-243">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="nameof-pattern"></a><span data-ttu-id="01d97-244">Nameof-Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-244">Nameof pattern</span></span>

<span data-ttu-id="01d97-245">Das `nameof` Muster entspricht einer Zeichenfolge, wenn sein Wert gleich dem Ausdruck ist, der dem `nameof` Schlüsselwort folgt.</span><span class="sxs-lookup"><span data-stu-id="01d97-245">The `nameof` pattern matches against a string when its value is equal to the expression that follows the `nameof` keyword.</span></span> <span data-ttu-id="01d97-246">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="01d97-246">for example:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```

<span data-ttu-id="01d97-247">[`nameof`](nameof.md)Informationen dazu, wie Sie einen Namen verwenden können, finden Sie unter dem-Operator.</span><span class="sxs-lookup"><span data-stu-id="01d97-247">See the [`nameof`](nameof.md) operator for information on what you can take a name of.</span></span>

## <a name="see-also"></a><span data-ttu-id="01d97-248">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01d97-248">See also</span></span>

- [<span data-ttu-id="01d97-249">Vergleichsausdrücke</span><span class="sxs-lookup"><span data-stu-id="01d97-249">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="01d97-250">Aktive Muster</span><span class="sxs-lookup"><span data-stu-id="01d97-250">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="01d97-251">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="01d97-251">F# Language Reference</span></span>](index.md)
