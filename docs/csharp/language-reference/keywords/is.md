---
title: is – C#-Referenz
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: ac1ec7da7da465f4290000ac9c7254e9492c3c81
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421816"
---
# <a name="is-c-reference"></a><span data-ttu-id="ae6fb-102">is (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ae6fb-102">is (C# Reference)</span></span>

<span data-ttu-id="ae6fb-103">Überprüft, ob ein Objekt mit einem angegebenen Typ kompatibel ist, oder gleicht ab C# 7.0 einen Ausdruck mit einem Muster ab.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="ae6fb-104">Prüfen auf Typkompatibilität</span><span class="sxs-lookup"><span data-stu-id="ae6fb-104">Testing for type compatibility</span></span>

<span data-ttu-id="ae6fb-105">Das `is`-Schlüsselwort wertet die Typkompatibilität zur Laufzeit aus.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="ae6fb-106">Es bestimmt, ob eine Instanz eines Objekts oder das Ergebnis eines Ausdrucks in einen angegebenen Typen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="ae6fb-107">Es besitzt die Syntax</span><span class="sxs-lookup"><span data-stu-id="ae6fb-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="ae6fb-108">in der *expr* ein Ausdruck ist, der die Instanz eines Typs auswertet und *type* der Name des Typs, in den das Ergebnis von *expr* konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="ae6fb-109">Die Anweisung `is` ist `true`, wenn *expr* nicht NULL ist, und das Objekt, das beim Auswerten des Ausdrucks entsteht, kann in *Typ* konvertiert werden; andernfalls gibt es `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="ae6fb-110">Der folgende Code bestimmt beispielsweise, ob `obj` in eine Instanz des Typs `Person` umgewandelt werden kann:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="ae6fb-111">Die Anweisung `is` ist TRUE, wenn:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="ae6fb-112">*expr* eine Instanz des gleichen Typs wie *Typ* ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="ae6fb-113">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="ae6fb-114">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="ae6fb-115">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="ae6fb-116">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="ae6fb-117">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="ae6fb-118">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="ae6fb-119">Im folgenden Beispiel wird veranschaulicht, wie der Ausdruck `is` für jede dieser Konvertierungen `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="ae6fb-120">Das Schlüsselwort `is` generiert eine Kompilierzeitwarnung, wenn der Ausdruck immer entweder `true` oder `false` ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="ae6fb-121">Es berücksichtigt nur Verweis-, Boxing- und Unboxing-Konvertierungen; es berücksichtigt keine benutzerdefinierten Konvertierungen oder Konvertierungen, die von den [impliziten](implicit.md) und [expliziten](explicit.md) Operatoren eines Typs definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="ae6fb-122">Das folgende Beispiel generiert Warnungen, weil das Ergebnis der Konvertierung zur Kompilierzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="ae6fb-123">Der Ausdruck `is` für Konvertierungen von `int` in `long` und `double` gibt FALSE zurück, da diese Konvertierungen vom [impliziten](implicit.md) Operator verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="ae6fb-124">`expr` kann weder eine anonyme Methode noch ein Lambdaausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-124">`expr` cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="ae6fb-125">Es kann ein anderer Ausdruck sein, der einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="ae6fb-126">Im folgenden Beispiel wird `is` verwendet, um den Rückgabewert eines Methodenaufrufs auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="ae6fb-127">Ab C# 7.0 können Sie den Musterabgleich mit dem [Typmuster](#type) verwenden, um präziseren Code zu schreiben, der die Anweisung `is` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="ae6fb-128">Musterabgleich mit `is`</span><span class="sxs-lookup"><span data-stu-id="ae6fb-128">Pattern matching with `is`</span></span>

<span data-ttu-id="ae6fb-129">Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](../../../csharp/language-reference/keywords/switch.md) den Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="ae6fb-130">Das Schlüsselwort `is` unterstützt folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="ae6fb-131">Das [Typmuster](#type), das prüft, ob ein Ausdruck in einen bestimmten Typ konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typs um.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="ae6fb-132">Das [Konstantenmuster](#constant), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="ae6fb-133">Das [Variablenmuster](#var), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="ae6fb-134"><a name="type" />Typmuster</span><span class="sxs-lookup"><span data-stu-id="ae6fb-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="ae6fb-135">Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="ae6fb-136">Dies ist eine einfach Erweiterung der `is`-Anweisung, die eine präzise Auswertung und Konvertierung des Typs ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="ae6fb-137">Die allgemeine Form des Typmusters `is` ist:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="ae6fb-138">Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="ae6fb-139">Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="ae6fb-140">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="ae6fb-141">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="ae6fb-142">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="ae6fb-143">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="ae6fb-144">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="ae6fb-145">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="ae6fb-146">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="ae6fb-147">Beginnend mit C# 7.1 kann *expr* einen Kompilierzeittyp haben, der durch einen generischen Typparameter und seine Einschränkungen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="ae6fb-148">Wenn *expr* `true` ist und `is` mit der `if`-Anweisung verwendet wird, wird *varname* nur innerhalb der `if`-Anweisung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="ae6fb-149">Der Bereich von *varname* stammt aus dem `is`-Ausdruck am Ende des Block, der die `if`-Anweisung umschließt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-149">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="ae6fb-150">Bei Verwendung von *varname* an einem anderen Speicherort wird ein Kompilierzeitfehler für die Verwendung einer nicht zugewiesenen Variablen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-150">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="ae6fb-151">Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-151">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="ae6fb-152">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-152">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="ae6fb-153">Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-153">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="ae6fb-154">Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-154">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="ae6fb-155">Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-155">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="ae6fb-156">Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-156">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="ae6fb-157"><a name="constant" /> Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="ae6fb-157"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="ae6fb-158">Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-158">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="ae6fb-159">In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-159">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="ae6fb-160">Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-160">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="ae6fb-161">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-161">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="ae6fb-162">Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-162">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="ae6fb-163">*constant* kann einer der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-163">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="ae6fb-164">Ein Literalwert.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-164">A literal value.</span></span>

- <span data-ttu-id="ae6fb-165">Der Name einer deklarierten `const`-Variable.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-165">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="ae6fb-166">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-166">An enumeration constant.</span></span>

<span data-ttu-id="ae6fb-167">Der konstante Ausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-167">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="ae6fb-168">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-168">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="ae6fb-169">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-169">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="ae6fb-170">Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-170">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="ae6fb-171">Die Überprüfung auf `null` kann mithilfe des Konstantenmusters erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-171">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="ae6fb-172">Das Schlüsselwort `null` wird von der `is`-Anweisung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-172">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="ae6fb-173">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-173">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="ae6fb-174">Das folgende Beispiel zeigt einen Vergleich von `null`-Überprüfungen:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-174">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="ae6fb-175"><a name="var" />Variablenmuster</a></span><span class="sxs-lookup"><span data-stu-id="ae6fb-175"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="ae6fb-176">Das `var`-Muster ist ein Catch-All-Muster für jeden Typ bzw. jeden Wert.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-176">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="ae6fb-177">Der Wert von *expr* wird immer einer lokalen Variablen zugewiesen, deren Typ dem Kompilierzeittyp von *expr* entspricht.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-177">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="ae6fb-178">Das Ergebnis des `is`-Ausdrucks lautet immer `true`.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-178">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="ae6fb-179">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="ae6fb-179">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="ae6fb-180">In folgendem Beispiel wird das Variablenmuster verwendet, um einen Ausdruck einer Variablen mit dem Namen `obj` zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-180">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="ae6fb-181">Dann zeigt es den Wert und den Typ von `obj` an.</span><span class="sxs-lookup"><span data-stu-id="ae6fb-181">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="ae6fb-182">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ae6fb-182">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ae6fb-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae6fb-183">See also</span></span>

- [<span data-ttu-id="ae6fb-184">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ae6fb-184">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="ae6fb-185">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ae6fb-185">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="ae6fb-186">typeof</span><span class="sxs-lookup"><span data-stu-id="ae6fb-186">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="ae6fb-187">as</span><span class="sxs-lookup"><span data-stu-id="ae6fb-187">as</span></span>](../../../csharp/language-reference/keywords/as.md)
