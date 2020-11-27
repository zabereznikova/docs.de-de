---
description: is – C#-Referenz
title: is – C#-Referenz
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: d30ebfa2dc47265185a96514efbddc3e4937438c
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982393"
---
# <a name="is-c-reference"></a><span data-ttu-id="897bd-103">is (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="897bd-103">is (C# Reference)</span></span>

<span data-ttu-id="897bd-104">Der `is`-Operator überprüft, ob das Ergebnis eines Ausdrucks mit einem angegebenen Typ kompatibel ist, oder (ab C# 7.0) testet einen Ausdruck anhand eines Musters.</span><span class="sxs-lookup"><span data-stu-id="897bd-104">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="897bd-105">Informationen zu Typtests des `is`-Operators finden Sie im Abschnitt [is-Operator](../operators/type-testing-and-cast.md#is-operator) des Artikels [Typtestoperatoren und Cast-Ausdrücke](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="897bd-105">For information about the type-testing `is` operator, see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="897bd-106">Musterabgleich mit `is`</span><span class="sxs-lookup"><span data-stu-id="897bd-106">Pattern matching with `is`</span></span>

<span data-ttu-id="897bd-107">Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](switch.md) den Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="897bd-107">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="897bd-108">Das Schlüsselwort `is` unterstützt folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="897bd-108">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="897bd-109">Das [Typmuster](#type-pattern), das prüft, ob ein Ausdruck in einen angegebenen Typ konvertiert werden kann, und die Variable, sofern die Konvertierung möglich ist, in eine Variable dieses Typs umwandelt.</span><span class="sxs-lookup"><span data-stu-id="897bd-109">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts the variable to a variable of that type.</span></span>
- <span data-ttu-id="897bd-110">Das [Konstantenmuster](#constant-pattern), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="897bd-110">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>
- <span data-ttu-id="897bd-111">Das [Variablenmuster](#var-pattern), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.</span><span class="sxs-lookup"><span data-stu-id="897bd-111">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="897bd-112">Typmuster</span><span class="sxs-lookup"><span data-stu-id="897bd-112">Type pattern</span></span>

<span data-ttu-id="897bd-113">Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um.</span><span class="sxs-lookup"><span data-stu-id="897bd-113">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="897bd-114">Dies ist eine einfach Erweiterung der `is`-Anweisung, die eine präzise Auswertung und Konvertierung des Typs ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="897bd-114">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="897bd-115">Die allgemeine Form des Typmusters `is` ist:</span><span class="sxs-lookup"><span data-stu-id="897bd-115">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="897bd-116">Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.</span><span class="sxs-lookup"><span data-stu-id="897bd-116">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="897bd-117">Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Bedingungen vorliegt:</span><span class="sxs-lookup"><span data-stu-id="897bd-117">The `is` expression is `true` if *expr* isn't `null`, and any of the following conditions is true:</span></span>

- <span data-ttu-id="897bd-118">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="897bd-118">*expr* is an instance of the same type as *type*.</span></span>
- <span data-ttu-id="897bd-119">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="897bd-119">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="897bd-120">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="897bd-120">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>
- <span data-ttu-id="897bd-121">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *type* ist, und *expr* hat einen Laufzeittyp,der *type* ist oder von *type* abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="897bd-121">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="897bd-122">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="897bd-122">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="897bd-123">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variable zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="897bd-123">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>
- <span data-ttu-id="897bd-124">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="897bd-124">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="897bd-125">Beginnend mit C# 7.1 kann *expr* einen Kompilierzeittyp haben, der durch einen generischen Typparameter und seine Einschränkungen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="897bd-125">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="897bd-126">Wenn *expr*`true` ist und `is` mit der `if`-Anweisung verwendet wird, wird *varname* nur innerhalb der `if`-Anweisung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="897bd-126">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="897bd-127">Der Bereich von *varname* stammt aus dem `is`-Ausdruck am Ende des Block, der die `if`-Anweisung umschließt.</span><span class="sxs-lookup"><span data-stu-id="897bd-127">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="897bd-128">Bei Verwendung von *varname* an einer anderen Stelle wird ein Kompilierzeitfehler für die Verwendung einer nicht zugewiesenen Variablen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="897bd-128">Using *varname* in any other location generates a compile-time error for use of a variable that hasn't been assigned.</span></span>

<span data-ttu-id="897bd-129">Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="897bd-129">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="897bd-130">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="897bd-130">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="897bd-131">Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.</span><span class="sxs-lookup"><span data-stu-id="897bd-131">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="897bd-132">Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="897bd-132">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="897bd-133">Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="897bd-133">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="897bd-134">Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="897bd-134">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="897bd-135">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="897bd-135">Constant pattern</span></span>

<span data-ttu-id="897bd-136">Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="897bd-136">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="897bd-137">In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="897bd-137">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="897bd-138">Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="897bd-138">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="897bd-139">Die Syntax sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="897bd-139">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="897bd-140">Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="897bd-140">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="897bd-141">*constant* kann eine der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="897bd-141">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="897bd-142">Ein Literalwert</span><span class="sxs-lookup"><span data-stu-id="897bd-142">A literal value.</span></span>

- <span data-ttu-id="897bd-143">Der Name einer deklarierten `const`-Variablen</span><span class="sxs-lookup"><span data-stu-id="897bd-143">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="897bd-144">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="897bd-144">An enumeration constant.</span></span>

<span data-ttu-id="897bd-145">Der Konstantenausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="897bd-145">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="897bd-146">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="897bd-146">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="897bd-147">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="897bd-147">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="897bd-148">Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.</span><span class="sxs-lookup"><span data-stu-id="897bd-148">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="897bd-149">Die Überprüfung auf `null` kann mithilfe des Konstantenmusters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="897bd-149">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="897bd-150">Das Schlüsselwort `null` wird von der `is`-Anweisung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="897bd-150">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="897bd-151">Die Syntax sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="897bd-151">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="897bd-152">Das folgende Beispiel zeigt einen Vergleich von `null`-Überprüfungen:</span><span class="sxs-lookup"><span data-stu-id="897bd-152">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

<span data-ttu-id="897bd-153">Der Ausdruck `x is null` wird für Referenztypen und Nullwerte zulassende Werttypen unterschiedlich berechnet.</span><span class="sxs-lookup"><span data-stu-id="897bd-153">The expression `x is null` is computed differently for reference types and nullable value types.</span></span> <span data-ttu-id="897bd-154">Für Nullwerte zulassende Werttypen wird <xref:System.Nullable%601.HasValue?displayProperty=nameWithType> verwendet.</span><span class="sxs-lookup"><span data-stu-id="897bd-154">For nullable value types, it uses <xref:System.Nullable%601.HasValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="897bd-155">Für Referenztypen wird `(object)x == null` verwendet.</span><span class="sxs-lookup"><span data-stu-id="897bd-155">For reference types, it uses `(object)x == null`.</span></span>

### <a name="var-pattern"></a><span data-ttu-id="897bd-156">var-Muster</span><span class="sxs-lookup"><span data-stu-id="897bd-156">var pattern</span></span>

<span data-ttu-id="897bd-157">Eine Musterübereinstimmung mit einem `var`-Muster wird immer erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="897bd-157">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="897bd-158">Die Syntax sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="897bd-158">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="897bd-159">Hier wird der Wert von *expr* immer einer lokalen Variablen mit dem Namen *varname* zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="897bd-159">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="897bd-160">*varname* ist eine Variable desselben Typs wie der Kompilierzeittyp *expr*.</span><span class="sxs-lookup"><span data-stu-id="897bd-160">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="897bd-161">Wenn *expr* zu `null` ausgewertet wird, ergibt der `is`-Ausdruck `true` und weist `null` zu *varname* zu.</span><span class="sxs-lookup"><span data-stu-id="897bd-161">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="897bd-162">Das var-Muster ist eine der wenigen Verwendungen von `is`, die `true` für einen `null`-Wert erzeugt.</span><span class="sxs-lookup"><span data-stu-id="897bd-162">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="897bd-163">Sie können das `var`-Muster verwenden, um eine temporäre Variable innerhalb eines booleschen Ausdrucks zu erstellen, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="897bd-163">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="897bd-164">Im vorhergehenden Beispiel wird die temporäre Variable verwendet, um das Ergebnis einer aufwendigen Operation zu speichern.</span><span class="sxs-lookup"><span data-stu-id="897bd-164">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="897bd-165">Die Variable kann dann mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="897bd-165">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="897bd-166">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="897bd-166">C# language specification</span></span>
  
<span data-ttu-id="897bd-167">Weitere Informationen finden Sie im Abschnitt [is-Operator](~/_csharplang/spec/expressions.md#the-is-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie in den folgenden Vorschlägen für C#:</span><span class="sxs-lookup"><span data-stu-id="897bd-167">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="897bd-168">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="897bd-168">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="897bd-169">Musterabgleich mit Generics</span><span class="sxs-lookup"><span data-stu-id="897bd-169">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="897bd-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="897bd-170">See also</span></span>

- [<span data-ttu-id="897bd-171">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="897bd-171">C# reference</span></span>](../index.md)
- [<span data-ttu-id="897bd-172">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="897bd-172">C# keywords</span></span>](index.md)
- [<span data-ttu-id="897bd-173">Typtest- und Umwandlungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="897bd-173">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
