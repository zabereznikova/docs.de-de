---
title: is – C#-Referenz
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 1a1f539e80f8d843f40640fa798cf6122f316a9f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715237"
---
# <a name="is-c-reference"></a><span data-ttu-id="e574d-102">is (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e574d-102">is (C# Reference)</span></span>

<span data-ttu-id="e574d-103">Der `is`-Operator überprüft, ob das Ergebnis eines Ausdrucks mit einem angegebenen Typ kompatibel ist, oder (ab C# 7.0) testet einen Ausdruck anhand eines Musters.</span><span class="sxs-lookup"><span data-stu-id="e574d-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="e574d-104">Informationen zum `is`-Operator für Typtests finden Sie im Abschnitt [is-Operator](../operators/type-testing-and-cast.md#is-operator) des Artikels [Typtest- und Umwandlungsoperatoren](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="e574d-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="e574d-105">Musterabgleich mit `is`</span><span class="sxs-lookup"><span data-stu-id="e574d-105">Pattern matching with `is`</span></span>

<span data-ttu-id="e574d-106">Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](switch.md) den Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="e574d-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="e574d-107">Das Schlüsselwort `is` unterstützt folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="e574d-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="e574d-108">Das [Typmuster](#type-pattern), das prüft, ob ein Ausdruck in einen angegebenen Typ konvertiert werden kann, und diesen, sofern die Konvertierung möglich ist, in eine Variable dieses Typs umwandelt.</span><span class="sxs-lookup"><span data-stu-id="e574d-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="e574d-109">Das [Konstantenmuster](#constant-pattern), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="e574d-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="e574d-110">Das [Variablenmuster](#var-pattern), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.</span><span class="sxs-lookup"><span data-stu-id="e574d-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="e574d-111">Typmuster</span><span class="sxs-lookup"><span data-stu-id="e574d-111">Type pattern</span></span>

<span data-ttu-id="e574d-112">Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um.</span><span class="sxs-lookup"><span data-stu-id="e574d-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="e574d-113">Dies ist eine einfach Erweiterung der `is`-Anweisung, die eine präzise Auswertung und Konvertierung des Typs ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e574d-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="e574d-114">Die allgemeine Form des Typmusters `is` ist:</span><span class="sxs-lookup"><span data-stu-id="e574d-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="e574d-115">Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.</span><span class="sxs-lookup"><span data-stu-id="e574d-115">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="e574d-116">Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="e574d-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="e574d-117">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="e574d-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="e574d-118">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e574d-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="e574d-119">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e574d-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="e574d-120">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e574d-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="e574d-121">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="e574d-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="e574d-122">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e574d-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="e574d-123">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="e574d-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="e574d-124">Beginnend mit C# 7.1 kann *expr* einen Kompilierzeittyp haben, der durch einen generischen Typparameter und seine Einschränkungen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e574d-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="e574d-125">Wenn *expr*`true` ist und `is` mit der `if`-Anweisung verwendet wird, wird *varname* nur innerhalb der `if`-Anweisung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e574d-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="e574d-126">Der Bereich von *varname* stammt aus dem `is`-Ausdruck am Ende des Block, der die `if`-Anweisung umschließt.</span><span class="sxs-lookup"><span data-stu-id="e574d-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="e574d-127">Bei Verwendung von *varname* an einem anderen Speicherort wird ein Kompilierzeitfehler für die Verwendung einer nicht zugewiesenen Variablen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e574d-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="e574d-128">Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e574d-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="e574d-129">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e574d-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="e574d-130">Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.</span><span class="sxs-lookup"><span data-stu-id="e574d-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="e574d-131">Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="e574d-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="e574d-132">Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e574d-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="e574d-133">Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="e574d-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="e574d-134">Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="e574d-134">Constant pattern</span></span>

<span data-ttu-id="e574d-135">Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="e574d-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="e574d-136">In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e574d-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="e574d-137">Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e574d-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="e574d-138">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="e574d-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="e574d-139">Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="e574d-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="e574d-140">*constant* kann einer der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="e574d-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="e574d-141">Ein Literalwert.</span><span class="sxs-lookup"><span data-stu-id="e574d-141">A literal value.</span></span>

- <span data-ttu-id="e574d-142">Der Name einer deklarierten `const`-Variable.</span><span class="sxs-lookup"><span data-stu-id="e574d-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="e574d-143">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="e574d-143">An enumeration constant.</span></span>

<span data-ttu-id="e574d-144">Der konstante Ausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="e574d-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="e574d-145">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e574d-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="e574d-146">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e574d-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="e574d-147">Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.</span><span class="sxs-lookup"><span data-stu-id="e574d-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="e574d-148">Die Überprüfung auf `null` kann mithilfe des Konstantenmusters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="e574d-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="e574d-149">Das Schlüsselwort `null` wird von der `is`-Anweisung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e574d-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="e574d-150">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="e574d-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="e574d-151">Das folgende Beispiel zeigt einen Vergleich von `null`-Überprüfungen:</span><span class="sxs-lookup"><span data-stu-id="e574d-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="e574d-152">var-Muster</span><span class="sxs-lookup"><span data-stu-id="e574d-152">var pattern</span></span>

<span data-ttu-id="e574d-153">Das `var`-Muster ist ein Catch-All-Muster für jeden Typ bzw. jeden Wert.</span><span class="sxs-lookup"><span data-stu-id="e574d-153">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="e574d-154">Der Wert von *expr* wird immer einer lokalen Variablen zugewiesen, deren Typ dem Kompilierzeittyp von *expr* entspricht.</span><span class="sxs-lookup"><span data-stu-id="e574d-154">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="e574d-155">Das Ergebnis des `is`-Ausdrucks lautet immer `true`.</span><span class="sxs-lookup"><span data-stu-id="e574d-155">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="e574d-156">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="e574d-156">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="e574d-157">In folgendem Beispiel wird das Variablenmuster verwendet, um einen Ausdruck einer Variablen mit dem Namen `obj` zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e574d-157">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="e574d-158">Dann zeigt es den Wert und den Typ von `obj` an.</span><span class="sxs-lookup"><span data-stu-id="e574d-158">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="e574d-159">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e574d-159">C# language specification</span></span>
  
<span data-ttu-id="e574d-160">Weitere Informationen finden Sie im Abschnitt [is-Operator](~/_csharplang/spec/expressions.md#the-is-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie in den folgenden Vorschlägen für C#:</span><span class="sxs-lookup"><span data-stu-id="e574d-160">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="e574d-161">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="e574d-161">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="e574d-162">Musterabgleich mit Generics</span><span class="sxs-lookup"><span data-stu-id="e574d-162">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="e574d-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e574d-163">See also</span></span>

- [<span data-ttu-id="e574d-164">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e574d-164">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e574d-165">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e574d-165">C# keywords</span></span>](index.md)
- [<span data-ttu-id="e574d-166">Typtest- und Umwandlungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e574d-166">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
