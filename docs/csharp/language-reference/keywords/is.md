---
title: is (C#-Referenz)
keywords: "is-Schlüsselwort (C#), is (C#)"
ms.date: 2017-02-17
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- is_CSharpKeyword
- is
dev_langs:
- CSharp
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58b18284b12ca0c636ed3fa923c43d94f202597f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="is-c-reference"></a><span data-ttu-id="c1869-103">is (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c1869-103">is (C# Reference)</span></span> #

<span data-ttu-id="c1869-104">Überprüft, ob ein Objekt mit einem angegebenen Typ kompatibel ist; gleicht ab C# 7 einen Ausdruck mit einem Muster ab.</span><span class="sxs-lookup"><span data-stu-id="c1869-104">Checks if an object is compatible with a given type, or (starting with C# 7) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="c1869-105">Prüfen auf Typkompatibilität</span><span class="sxs-lookup"><span data-stu-id="c1869-105">Testing for type compatibility</span></span> ##

<span data-ttu-id="c1869-106">Das `is`-Schlüsselwort wertet die Typkompatibilität zur Laufzeit aus.</span><span class="sxs-lookup"><span data-stu-id="c1869-106">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="c1869-107">Es bestimmt, ob eine Instanz eines Objekts oder das Ergebnis eines Ausdrucks in einen angegebenen Typen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c1869-107">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="c1869-108">Es besitzt die Syntax</span><span class="sxs-lookup"><span data-stu-id="c1869-108">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="c1869-109">in der *expr* ein Ausdruck ist, der die Instanz eines Typs auswertet und *type* der Name des Typs, in den das Ergebnis von *expr* konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1869-109">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="c1869-110">Die Anweisung `is` ist `true`, wenn *expr* nicht NULL ist, und das Objekt, das beim Auswerten des Ausdrucks entsteht, kann in *Typ* konvertiert werden; andernfalls gibt es `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="c1869-110">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="c1869-111">Der folgende Code bestimmt beispielsweise, ob `obj` in eine Instanz des Typs `Person` umgewandelt werden kann:</span><span class="sxs-lookup"><span data-stu-id="c1869-111">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

<span data-ttu-id="c1869-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c1869-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span></span>

<span data-ttu-id="c1869-113">Die Anweisung `is` ist TRUE, wenn:</span><span class="sxs-lookup"><span data-stu-id="c1869-113">The `is` statement is true if:</span></span>

- <span data-ttu-id="c1869-114">*expr* eine Instanz des gleichen Typs wie *Typ* ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-114">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c1869-115">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-115">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c1869-116">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c1869-116">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c1869-117">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-117">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c1869-118">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="c1869-118">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="c1869-119">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-119">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c1869-120">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="c1869-120">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c1869-121">Im folgenden Beispiel wird veranschaulicht, wie der Ausdruck `is` für jede dieser Konvertierungen `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="c1869-121">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

<span data-ttu-id="c1869-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="c1869-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span></span>

<span data-ttu-id="c1869-123">Das Schlüsselwort `is` generiert eine Kompilierzeitwarnung, wenn der Ausdruck immer entweder `true` oder `false` ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-123">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="c1869-124">Es berücksichtigt nur Verweis-, Boxing- und Unboxing-Konvertierungen; es berücksichtigt keine benutzerdefinierten Konvertierungen oder Konvertierungen, die von den [impliziten](implicit.md) und [expliziten](explicit.md) Operatoren eines Typs definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c1869-124">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="c1869-125">Das folgende Beispiel generiert Warnungen, weil das Ergebnis der Konvertierung zur Kompilierzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-125">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="c1869-126">Bitte beachten Sie, dass der Ausdruck `is` für Konvertierungen von `int` in `long` und `double` FALSE zurückgibt, da diese Konvertierungen vom [impliziten](implicit.md) Operator verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c1869-126">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

<span data-ttu-id="c1869-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="c1869-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span></span>

<span data-ttu-id="c1869-128">`expr` kann jeder beliebige Ausdruck sein, der einen Wert zurückgibt – davon ausgenommen sind anonyme Methoden und Lambdaausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c1869-128">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="c1869-129">Im folgenden Beispiel wird `is` verwendet, um den Rückgabewert eines Methodenaufrufs auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="c1869-129">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
<span data-ttu-id="c1869-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span><span class="sxs-lookup"><span data-stu-id="c1869-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span></span>

<span data-ttu-id="c1869-131">Ab C# 7 können Sie den Musterabgleich mit dem [Typmuster](#type) verwenden, um präziseren Code zu schreiben, der die Anweisung `is` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c1869-131">Starting with C# 7, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="c1869-132">Musterabgleich mit `is`</span><span class="sxs-lookup"><span data-stu-id="c1869-132">Pattern matching with `is`</span></span> ##

<span data-ttu-id="c1869-133">Ab C# 7 unterstützen die Auszüge `is` und [switch](../../../csharp/language-reference/keywords/switch.md) den Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="c1869-133">Starting with C# 7, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="c1869-134">Das Schlüsselwort `is` unterstützt folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="c1869-134">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="c1869-135">Das [Typmuster](#type), das prüft, ob ein Ausdruck in einen bestimmten Typ konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typs um.</span><span class="sxs-lookup"><span data-stu-id="c1869-135">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="c1869-136">Das [Konstantenmuster](#constant), das prüft, ob ein Ausdruck einen angegebenen konstanten Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="c1869-136">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="c1869-137">Das [Variablenmuster](#var), eine Übereinstimmung, die immer erfolgreich ausführt wird und den Wert eines Ausdrucks an eine neue lokale Variable bindet.</span><span class="sxs-lookup"><span data-stu-id="c1869-137">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="c1869-138"><a name="type" />Typmuster</a></span><span class="sxs-lookup"><span data-stu-id="c1869-138"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="c1869-139">Wenn Sie das Typmuster verwenden, um einen Musterabgleich durchzuführen, prüft `is`, ob ein Ausdruck in einen angegebenen Typen konvertiert werden kann; sofern dies möglich ist, wandelt es diesen in eine Variable dieses Typ um.</span><span class="sxs-lookup"><span data-stu-id="c1869-139">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="c1869-140">Dies ist eine einfach Erweiterung der `is`-Anweisung, der eine präzise Auswertung und Konvertierung der Typs ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c1869-140">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="c1869-141">Die allgemeine Form des Typmusters `is` ist:</span><span class="sxs-lookup"><span data-stu-id="c1869-141">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="c1869-142">Hier ist *expr* ein Ausdruck, der eine Instanz eines beliebigen Typen ergibt, *Typ* ist der Name des Typen, in den das Ergebnis von *expr* konvertiert werden soll, und *varname* ist das Objekt, in das das Ergebnis von *expr* konvertiert wird, wenn der `is`-Test `true` ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-142">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="c1869-143">Der Ausdruck `is` ist `true`, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="c1869-143">The `is` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="c1869-144">*expr* ist eine Instanz des gleichen Typs wie *Typ*.</span><span class="sxs-lookup"><span data-stu-id="c1869-144">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c1869-145">*expr* ist eine Instanz eines Typs, der von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-145">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c1869-146">Das Ergebnis von *expr* kann, in anderen Worten, in eine Instanz von *Typ* umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c1869-146">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c1869-147">*expr* hat einen Kompilierzeittyp, der eine Basisklasse von *Typ* ist, und *expr* hat einen Runtime-Typ,der *Typ* ist oder von *Typ* abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-147">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c1869-148">Der *Kompilierzeittyp* einer Variablen ist der Typ der Variablen, wie in der Deklaration des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="c1869-148">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="c1869-149">Der *Laufzeittyp* einer Variablen ist der Typ der Instanz, die dieser Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-149">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c1869-150">*expr* ist eine Instanz eines Typs, der die Schnittstelle *Typ* implementiert.</span><span class="sxs-lookup"><span data-stu-id="c1869-150">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c1869-151">Wenn *expr* `true` ist, und `is` mit der `if`-Anweisung verwendet wird, wird *varname* zugewiesen und ist nur lokal innerhalb der Anweisung `if` gültig.</span><span class="sxs-lookup"><span data-stu-id="c1869-151">If *exp* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="c1869-152">Im folgenden Beispiel wird das `is`-Typmuster verwendet, um die Implementierung der Methode <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> des Typs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c1869-152">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> method.</span></span>

<span data-ttu-id="c1869-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span><span class="sxs-lookup"><span data-stu-id="c1869-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span></span>

<span data-ttu-id="c1869-154">Ohne Mustervergleich könnte dieser Code wie folgt geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c1869-154">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="c1869-155">Die Verwendung des Typenmusterabgleichs erzeugt einen kompakteren, lesbaren Code, da nicht mehr geprüft werden muss, ob das Ergebnis einer Umwandlung `null` ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-155">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

<span data-ttu-id="c1869-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span><span class="sxs-lookup"><span data-stu-id="c1869-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span></span>

<span data-ttu-id="c1869-157">Das Typmuster `is` erstellt zusätzlich kompakteren Code, wenn der Typ eines Werttyps bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-157">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="c1869-158">Im folgenden Beispiel wird das Typmuster `is` verwendet, um zu bestimmen, ob ein Objekt eine Instanz von `Person` oder `Dog` ist, bevor der Wert einer passenden Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c1869-158">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

<span data-ttu-id="c1869-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span><span class="sxs-lookup"><span data-stu-id="c1869-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span></span>

<span data-ttu-id="c1869-160">Der gleichwertige Code erfordert ohne einen Musterabgleich eine gesonderte Zuweisung, die eine explizite Umwandlung beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="c1869-160">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

<span data-ttu-id="c1869-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span><span class="sxs-lookup"><span data-stu-id="c1869-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span></span>

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="c1869-162"><a name="constant" /> Konstantenmuster</span><span class="sxs-lookup"><span data-stu-id="c1869-162"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="c1869-163">Beim Durchführen eines Musterabgleichs mit einem Konstantenmuster prüft `is`, ob ein Ausdruck einer angegebenen Konstanten entspricht.</span><span class="sxs-lookup"><span data-stu-id="c1869-163">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="c1869-164">In C# 6 und früheren Versionen wird das Konstantenmuster von der Anweisung [switch](switch.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1869-164">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="c1869-165">Ab C# 7 wird es ebenfalls von der Anweisung `is` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1869-165">Starting with C# 7, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="c1869-166">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="c1869-166">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="c1869-167">Hier ist *expr* der auszuwertende Ausdruck, und *constant* ist der Wert, auf den geprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1869-167">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="c1869-168">*constant* kann einer der folgenden konstanten Ausdrücke sein:</span><span class="sxs-lookup"><span data-stu-id="c1869-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="c1869-169">Ein Literalwert.</span><span class="sxs-lookup"><span data-stu-id="c1869-169">A literal value.</span></span>

- <span data-ttu-id="c1869-170">Der Name einer deklarierten `const`-Variable.</span><span class="sxs-lookup"><span data-stu-id="c1869-170">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="c1869-171">Eine Enumerationskonstante.</span><span class="sxs-lookup"><span data-stu-id="c1869-171">An enumeration constant.</span></span>

<span data-ttu-id="c1869-172">Der konstante Ausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="c1869-172">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="c1869-173">Wenn *expr* und *constant* integrale Typen sind, bestimmt der C#-Gleichheitsoperator, ob der Ausdruck `true` (d.h., ob `expr == constant`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c1869-173">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="c1869-174">Andernfalls wird der Wert des Ausdrucks durch einen Aufruf der statischen Methode [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="c1869-174">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="c1869-175">Im folgenden Beispiel werden Typ- und Konstantenmuster miteinander vereint, um zu prüfen, ob ein Objekt eine `Dice`-Instanz ist; ist dem so, wird geprüft, ob der Wert eines Würfelvorgangs 6 ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-175">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

<span data-ttu-id="c1869-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span><span class="sxs-lookup"><span data-stu-id="c1869-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span></span>
 
### <span data-ttu-id="c1869-177"><a name="var" />Variablenmuster</a></span><span class="sxs-lookup"><span data-stu-id="c1869-177"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="c1869-178">Eine Musterübereinstimmung mit einem Variablenmuster wird immer erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1869-178">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="c1869-179">Deren Syntax lautet</span><span class="sxs-lookup"><span data-stu-id="c1869-179">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="c1869-180">Hier wird der Wert von *expr* immer einer lokalen Variablen mit dem Namen *varname* zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c1869-180">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="c1869-181">*varname* ist eine statische Variable des gleichen Typs wie *expr*.</span><span class="sxs-lookup"><span data-stu-id="c1869-181">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="c1869-182">In folgendem Beispiel wird das Variablenmuster verwendet, um einen Ausdruck einer Variablen mit dem Namen `obj` zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c1869-182">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="c1869-183">Dann zeigt es den Wert und den Typ von `obj` an.</span><span class="sxs-lookup"><span data-stu-id="c1869-183">It then displays the value and the type of `obj`.</span></span>

<span data-ttu-id="c1869-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span><span class="sxs-lookup"><span data-stu-id="c1869-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span></span>

<span data-ttu-id="c1869-185">Bitte beachten Sie, dass der Ausdruck `is` immer noch TRUE ist und `null` *varname* zuweist, wenn *expr* `null` ist.</span><span class="sxs-lookup"><span data-stu-id="c1869-185">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="c1869-186">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c1869-186">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1869-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1869-187">See also</span></span>  
 <span data-ttu-id="c1869-188">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1869-188">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c1869-189">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1869-189">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c1869-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="c1869-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="c1869-191">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="c1869-191">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 [<span data-ttu-id="c1869-192">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c1869-192">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

