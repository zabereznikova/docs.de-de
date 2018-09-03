---
title: is (C#-Referenz)
ms.date: 02/17/2017
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 974e0c3ab29da582e7b22c909650a61d179ec3f7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402882"
---
# <a name="is-c-reference"></a><span data-ttu-id="66988-102">is (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="66988-102">is (C# Reference)</span></span> #

<span data-ttu-id="66988-103">Überprüft, ob ein Objekt mit einem angegebenen Typ kompatibel ist, oder gleicht ab C# 7.0 einen Ausdruck mit einem Muster ab.</span><span class="sxs-lookup"><span data-stu-id="66988-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="66988-104">Prüfen auf Typkompatibilität</span><span class="sxs-lookup"><span data-stu-id="66988-104">Testing for type compatibility</span></span> ##

<span data-ttu-id="66988-105">Das `is`-Schlüsselwort wertet die Typkompatibilität zur Laufzeit aus.</span><span class="sxs-lookup"><span data-stu-id="66988-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="66988-106">Es bestimmt, ob eine Instanz eines Objekts oder das Ergebnis eines Ausdrucks in einen angegebenen Typen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="66988-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="66988-107">Es besitzt die Syntax</span><span class="sxs-lookup"><span data-stu-id="66988-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="66988-108">in der *expr* ein Ausdruck ist, der die Instanz eines Typs auswertet und *type* der Name des Typs, in den das Ergebnis von *expr* konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="66988-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="66988-109">Die Anweisung `is` ist `true`, wenn *expr* nicht NULL ist, und das Objekt, das beim Auswerten des Ausdrucks entsteht, kann in *Typ* konvertiert werden; andernfalls gibt es `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="66988-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="66988-110">Der folgende Code bestimmt beispielsweise, ob `obj` in eine Instanz des Typs `Person` umgewandelt werden kann:</span><span class="sxs-lookup"><span data-stu-id="66988-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="66988-111">Die Anweisung `is` ist TRUE, wenn:</span><span class="sxs-lookup"><span data-stu-id="66988-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="66988-112">*expr* eine Instanz des gleichen Typs wie *Typ* ist.</span><span class="sxs-lookup"><span data-stu-id="66988-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="66988-113">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="66988-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="66988-114">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="66988-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="66988-115">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="66988-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="66988-116">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="66988-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="66988-117">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="66988-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="66988-118">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="66988-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="66988-119">Im folgenden Beispiel wird veranschaulicht, wie der Ausdruck `is` für jede dieser Konvertierungen `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="66988-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="66988-120">Das Schlüsselwort `is` generiert eine Kompilierzeitwarnung, wenn der Ausdruck immer entweder `true` oder `false` ist.</span><span class="sxs-lookup"><span data-stu-id="66988-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="66988-121">Es berücksichtigt nur Verweis-, Boxing- und Unboxing-Konvertierungen; es berücksichtigt keine benutzerdefinierten Konvertierungen oder Konvertierungen, die von den [impliziten](implicit.md) und [expliziten](explicit.md) Operatoren eines Typs definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="66988-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="66988-122">Das folgende Beispiel generiert Warnungen, weil das Ergebnis der Konvertierung zur Kompilierzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="66988-122">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="66988-123">Bitte beachten Sie, dass der Ausdruck `is` für Konvertierungen von `int` in `long` und `double` FALSE zurückgibt, da diese Konvertierungen vom [impliziten](implicit.md) Operator verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="66988-123">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="66988-124">`expr` kann jeder beliebige Ausdruck sein, der einen Wert zurückgibt – davon ausgenommen sind anonyme Methoden und Lambdaausdrücke.</span><span class="sxs-lookup"><span data-stu-id="66988-124">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="66988-125">Im folgenden Beispiel wird `is` verwendet, um den Rückgabewert eines Methodenaufrufs auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="66988-125">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="66988-126">Ab C# 7.0 können Sie den Musterabgleich mit dem [Typmuster](#type) verwenden, um präziseren Code zu schreiben, der die Anweisung `is` verwendet.</span><span class="sxs-lookup"><span data-stu-id="66988-126">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="66988-127">Musterabgleich mit `is`</span><span class="sxs-lookup"><span data-stu-id="66988-127">Pattern matching with `is`</span></span> ##

<span data-ttu-id="66988-128">Ab C# 7.0 unterstützen die Anweisungen `is` und [switch](../../../csharp/language-reference/keywords/switch.md) den Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="66988-128">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="66988-129">Das Schlüsselwort `is` unterstützt folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="66988-129">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="66988-130">Das [Typmuster](#type), das prüft, ob ein Ausdruck in einen bestimmten Typ konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typs um.</span><span class="sxs-lookup"><span data-stu-id="66988-130">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="66988-131">Das [Konstantenmuster](#constant), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="66988-131">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="66988-132">Das [Variablenmuster](#var), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.</span><span class="sxs-lookup"><span data-stu-id="66988-132">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="66988-133"><a name="type" />Typmuster</a></span><span class="sxs-lookup"><span data-stu-id="66988-133"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="66988-134">Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um.</span><span class="sxs-lookup"><span data-stu-id="66988-134">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="66988-135">Dies ist eine einfach Erweiterung der `is`-Anweisung, der eine präzise Auswertung und Konvertierung der Typs ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="66988-135">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="66988-136">Die allgemeine Form des Typmusters `is` ist:</span><span class="sxs-lookup"><span data-stu-id="66988-136">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="66988-137">Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.</span><span class="sxs-lookup"><span data-stu-id="66988-137">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="66988-138">Der Ausdruck `is` ist `true`, wenn *expr* nicht `null` ist und eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="66988-138">The `is` expression is `true` if *expr* is not `null`, and any of the following is true:</span></span>

- <span data-ttu-id="66988-139">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="66988-139">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="66988-140">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="66988-140">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="66988-141">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="66988-141">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="66988-142">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="66988-142">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="66988-143">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="66988-143">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="66988-144">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="66988-144">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="66988-145">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="66988-145">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="66988-146">Wenn *expr* `true` ist, und `is` mit der `if`-Anweisung verwendet wird, wird *varname* zugewiesen und ist nur lokal innerhalb der Anweisung `if` gültig.</span><span class="sxs-lookup"><span data-stu-id="66988-146">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="66988-147">Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> des Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="66988-147">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="66988-148">Ohne Musterabgleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="66988-148">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="66988-149">Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.</span><span class="sxs-lookup"><span data-stu-id="66988-149">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="66988-150">Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="66988-150">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="66988-151">Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="66988-151">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="66988-152">Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="66988-152">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="66988-153"><a name="constant" /> Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="66988-153"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="66988-154">Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="66988-154">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="66988-155">In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66988-155">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="66988-156">Ab C# 7.0 wird es ebenfalls von der Anweisung `is` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="66988-156">Starting with C# 7.0, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="66988-157">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="66988-157">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="66988-158">Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="66988-158">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="66988-159">*constant* kann einer der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="66988-159">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="66988-160">Ein Literalwert.</span><span class="sxs-lookup"><span data-stu-id="66988-160">A literal value.</span></span>

- <span data-ttu-id="66988-161">Der Name einer deklarierten `const`-Variable.</span><span class="sxs-lookup"><span data-stu-id="66988-161">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="66988-162">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="66988-162">An enumeration constant.</span></span>

<span data-ttu-id="66988-163">Der konstante Ausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="66988-163">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="66988-164">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="66988-164">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="66988-165">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="66988-165">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="66988-166">Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.</span><span class="sxs-lookup"><span data-stu-id="66988-166">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]
 
### <span data-ttu-id="66988-167"><a name="var" />Variablenmuster</a></span><span class="sxs-lookup"><span data-stu-id="66988-167"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="66988-168">Eine Musterübereinstimmung mit einem Variablenmuster wird immer erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="66988-168">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="66988-169">Deren Syntax lautet</span><span class="sxs-lookup"><span data-stu-id="66988-169">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="66988-170">Hier wird der Wert von *expr* immer einer lokalen Variablen mit dem Namen *varname* zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="66988-170">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="66988-171">*varname* ist eine statische Variable des gleichen Typs wie *expr*.</span><span class="sxs-lookup"><span data-stu-id="66988-171">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="66988-172">In folgendem Beispiel wird das Variablenmuster verwendet, um einen Ausdruck einer Variablen mit dem Namen `obj` zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="66988-172">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="66988-173">Dann zeigt es den Wert und den Typ von `obj` an.</span><span class="sxs-lookup"><span data-stu-id="66988-173">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="66988-174">Bitte beachten Sie, dass der Ausdruck `is` immer noch TRUE ist und `null` *varname* zuweist, wenn *expr* `null` ist.</span><span class="sxs-lookup"><span data-stu-id="66988-174">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="66988-175">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="66988-175">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66988-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66988-176">See also</span></span>

- [<span data-ttu-id="66988-177">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="66988-177">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="66988-178">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="66988-178">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="66988-179">typeof</span><span class="sxs-lookup"><span data-stu-id="66988-179">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
- [<span data-ttu-id="66988-180">as</span><span class="sxs-lookup"><span data-stu-id="66988-180">as</span></span>](../../../csharp/language-reference/keywords/as.md)  
- [<span data-ttu-id="66988-181">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="66988-181">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
