---
title: is – C#-Referenz
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398304"
---
# <a name="is-c-reference"></a><span data-ttu-id="6de39-102">is (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6de39-102">is (C# Reference)</span></span>

<span data-ttu-id="6de39-103">Der `is`-Operator überprüft, ob das Ergebnis eines Ausdrucks mit einem angegebenen Typ kompatibel ist, oder (ab C# 7.0) testet einen Ausdruck anhand eines Musters.</span><span class="sxs-lookup"><span data-stu-id="6de39-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="6de39-104">Informationen zum `is`-Operator für Typtests finden Sie im Abschnitt [is-Operator](../operators/type-testing-and-cast.md#is-operator) des Artikels [Typtest- und Umwandlungsoperatoren](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="6de39-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="6de39-105">Musterabgleich mit `is`</span><span class="sxs-lookup"><span data-stu-id="6de39-105">Pattern matching with `is`</span></span>

<span data-ttu-id="6de39-106">Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](switch.md) den Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="6de39-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="6de39-107">Das Schlüsselwort `is` unterstützt folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="6de39-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="6de39-108">Das [Typmuster](#type-pattern), das prüft, ob ein Ausdruck in einen angegebenen Typ konvertiert werden kann, und diesen, sofern die Konvertierung möglich ist, in eine Variable dieses Typs umwandelt.</span><span class="sxs-lookup"><span data-stu-id="6de39-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="6de39-109">Das [Konstantenmuster](#constant-pattern), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="6de39-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="6de39-110">Das [Variablenmuster](#var-pattern), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.</span><span class="sxs-lookup"><span data-stu-id="6de39-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="6de39-111">Typmuster</span><span class="sxs-lookup"><span data-stu-id="6de39-111">Type pattern</span></span>

<span data-ttu-id="6de39-112">Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um.</span><span class="sxs-lookup"><span data-stu-id="6de39-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="6de39-113">Dies ist eine einfach Erweiterung der `is`-Anweisung, die eine präzise Auswertung und Konvertierung des Typs ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6de39-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="6de39-114">Die allgemeine Form des Typmusters `is` ist:</span><span class="sxs-lookup"><span data-stu-id="6de39-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="6de39-115">Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.</span><span class="sxs-lookup"><span data-stu-id="6de39-115">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="6de39-116">Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="6de39-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="6de39-117">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="6de39-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="6de39-118">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="6de39-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="6de39-119">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6de39-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="6de39-120">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="6de39-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="6de39-121">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="6de39-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="6de39-122">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6de39-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="6de39-123">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="6de39-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="6de39-124">Beginnend mit C# 7.1 kann *expr* einen Kompilierzeittyp haben, der durch einen generischen Typparameter und seine Einschränkungen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6de39-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="6de39-125">Wenn *expr*`true` ist und `is` mit der `if`-Anweisung verwendet wird, wird *varname* nur innerhalb der `if`-Anweisung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6de39-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="6de39-126">Der Bereich von *varname* stammt aus dem `is`-Ausdruck am Ende des Block, der die `if`-Anweisung umschließt.</span><span class="sxs-lookup"><span data-stu-id="6de39-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="6de39-127">Bei Verwendung von *varname* an einem anderen Speicherort wird ein Kompilierzeitfehler für die Verwendung einer nicht zugewiesenen Variablen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="6de39-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="6de39-128">Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6de39-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="6de39-129">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6de39-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="6de39-130">Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.</span><span class="sxs-lookup"><span data-stu-id="6de39-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="6de39-131">Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="6de39-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="6de39-132">Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6de39-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="6de39-133">Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="6de39-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="6de39-134">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="6de39-134">Constant pattern</span></span>

<span data-ttu-id="6de39-135">Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="6de39-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="6de39-136">In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6de39-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="6de39-137">Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6de39-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="6de39-138">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="6de39-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="6de39-139">Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="6de39-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="6de39-140">*constant* kann einer der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="6de39-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="6de39-141">Ein Literalwert.</span><span class="sxs-lookup"><span data-stu-id="6de39-141">A literal value.</span></span>

- <span data-ttu-id="6de39-142">Der Name einer deklarierten `const`-Variable.</span><span class="sxs-lookup"><span data-stu-id="6de39-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="6de39-143">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="6de39-143">An enumeration constant.</span></span>

<span data-ttu-id="6de39-144">Der konstante Ausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="6de39-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="6de39-145">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6de39-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="6de39-146">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="6de39-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="6de39-147">Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.</span><span class="sxs-lookup"><span data-stu-id="6de39-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="6de39-148">Die Überprüfung auf `null` kann mithilfe des Konstantenmusters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6de39-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="6de39-149">Das Schlüsselwort `null` wird von der `is`-Anweisung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6de39-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="6de39-150">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="6de39-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="6de39-151">Das folgende Beispiel zeigt einen Vergleich von `null`-Überprüfungen:</span><span class="sxs-lookup"><span data-stu-id="6de39-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="6de39-152">var-Muster</span><span class="sxs-lookup"><span data-stu-id="6de39-152">var pattern</span></span>

<span data-ttu-id="6de39-153">Eine Musterübereinstimmung mit einem `var`-Muster wird immer erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6de39-153">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="6de39-154">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="6de39-154">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="6de39-155">Hier wird der Wert von *expr* immer einer lokalen Variablen mit dem Namen *varname* zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6de39-155">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="6de39-156">*varname* ist eine Variable desselben Typs wie der Kompilierzeittyp *expr*.</span><span class="sxs-lookup"><span data-stu-id="6de39-156">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="6de39-157">Wenn *expr* zu `null` ausgewertet wird, ergibt der `is`-Ausdruck `true` und weist `null` zu *varname* zu.</span><span class="sxs-lookup"><span data-stu-id="6de39-157">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="6de39-158">Das var-Muster ist eine der wenigen Verwendungen von `is`, die `true` für einen `null`-Wert erzeugt.</span><span class="sxs-lookup"><span data-stu-id="6de39-158">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="6de39-159">Sie können das `var`-Muster verwenden, um eine temporäre Variable innerhalb eines booleschen Ausdrucks zu erstellen, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="6de39-159">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="6de39-160">Im vorhergehenden Beispiel wird die temporäre Variable verwendet, um das Ergebnis einer aufwendigen Operation zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6de39-160">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="6de39-161">Die Variable kann dann mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6de39-161">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6de39-162">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6de39-162">C# language specification</span></span>
  
<span data-ttu-id="6de39-163">Weitere Informationen finden Sie im Abschnitt [is-Operator](~/_csharplang/spec/expressions.md#the-is-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie in den folgenden Vorschlägen für C#:</span><span class="sxs-lookup"><span data-stu-id="6de39-163">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="6de39-164">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="6de39-164">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="6de39-165">Musterabgleich mit Generics</span><span class="sxs-lookup"><span data-stu-id="6de39-165">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="6de39-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6de39-166">See also</span></span>

- [<span data-ttu-id="6de39-167">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6de39-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="6de39-168">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6de39-168">C# keywords</span></span>](index.md)
- [<span data-ttu-id="6de39-169">Typtest- und Umwandlungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="6de39-169">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
