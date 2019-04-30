---
title: Umwandlung und Konvertierungen
description: Erfahren Sie, wie die Programmiersprache F# Konvertierungsoperatoren für arithmetische Konvertierungen zwischen primitiven Typen von verschiedenen bereitstellt.
ms.date: 05/16/2016
ms.openlocfilehash: 2a12d48106a267edfc67c9e7b3d3a7bd41d8261c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966615"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="29d05-103">Umwandlung und Konvertierungen (F#)</span><span class="sxs-lookup"><span data-stu-id="29d05-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="29d05-104">Dieses Thema beschreibt die Unterstützung für Typumwandlungen in F#.</span><span class="sxs-lookup"><span data-stu-id="29d05-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="29d05-105">Arithmetische Typen</span><span class="sxs-lookup"><span data-stu-id="29d05-105">Arithmetic Types</span></span>

<span data-ttu-id="29d05-106">F#Stellt Konvertierungsoperatoren für arithmetische Konvertierungen zwischen verschiedenen primitive Typen, z. B. zwischen Ganzzahl- und Gleitkommatypen bereit.</span><span class="sxs-lookup"><span data-stu-id="29d05-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="29d05-107">Die integrale und Char-Konvertierungsoperatoren überprüft haben und die unchecked-Formulare der Gleitkommawert, Operatoren und die `enum` Konvertierungsoperator nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="29d05-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="29d05-108">Die unchecked-Formen werden in definierten `Microsoft.FSharp.Core.Operators` und die checked-Formen in definiert `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="29d05-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="29d05-109">Die checked-Formen Überlauf überprüfen und generieren eine Laufzeitausnahme aus, wenn der resultierende Wert die Grenzwerte des Zieltyps überschreitet.</span><span class="sxs-lookup"><span data-stu-id="29d05-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="29d05-110">Die einzelnen Operatoren verfügt über den gleichen Namen wie der Name des Zieltyps.</span><span class="sxs-lookup"><span data-stu-id="29d05-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="29d05-111">In den folgenden Code, in denen die Typen explizit mit Anmerkungen versehen werden, z. B. `byte` wird mit zwei unterschiedliche Bedeutungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29d05-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="29d05-112">Das erste Vorkommen ist der Typ und der zweite Operator für die Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="29d05-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="29d05-113">Die folgende Tabelle zeigt die Konvertierungsoperatoren, die in F# definiert.</span><span class="sxs-lookup"><span data-stu-id="29d05-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="29d05-114">Operator</span><span class="sxs-lookup"><span data-stu-id="29d05-114">Operator</span></span>|<span data-ttu-id="29d05-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29d05-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="29d05-116">Konvertieren Sie in Byte, ein 8-Bit-Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="29d05-117">Konvertieren Sie in Byte mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="29d05-118">Konvertieren Sie in eine 16-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="29d05-119">Konvertieren Sie in eine 16-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="29d05-120">Konvertieren Sie in eine 32-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="29d05-121">Konvertieren Sie in eine 32-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="29d05-122">Konvertieren Sie in eine 64-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="29d05-123">Konvertieren Sie in eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="29d05-124">Konvertieren Sie in eine systemeigene ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="29d05-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="29d05-125">Konvertieren Sie in eine systemeigene ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="29d05-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="29d05-126">Konvertieren Sie in eine Gleitkommazahl mit doppelter Genauigkeit-IEEE-64-Bit-Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="29d05-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="29d05-127">Konvertieren Sie in eine Gleitkommazahl mit einfacher Genauigkeit-IEEE-32-Bit.</span><span class="sxs-lookup"><span data-stu-id="29d05-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="29d05-128">Konvertieren in `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="29d05-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="29d05-129">Konvertieren in `System.Char`, ein Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="29d05-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="29d05-130">Für einen enumerierten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="29d05-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="29d05-131">Zusätzlich zur integrierten primitiven Typen können Sie diese Operatoren mit Typen, die implementieren `op_Explicit` oder `op_Implicit` Methoden mit den geeigneten Signaturen.</span><span class="sxs-lookup"><span data-stu-id="29d05-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="29d05-132">Z. B. die `int` Konvertierungsoperator funktioniert mit jeder Typ, der eine statische Methode enthält `op_Explicit` , die den Typ als Parameter akzeptiert und gibt `int`.</span><span class="sxs-lookup"><span data-stu-id="29d05-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="29d05-133">Als eine spezielle Ausnahme als allgemeine Regel, dass Methoden, durch den Rückgabetyp überladen werden, hierzu können Sie für `op_Explicit` und `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="29d05-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="29d05-134">Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="29d05-134">Enumerated Types</span></span>

<span data-ttu-id="29d05-135">Die `enum` Operator ist ein generischer Operator, der einen Typparameter verwendet, die den Typ des darstellt der `enum` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="29d05-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="29d05-136">Geben Sie beim Konvertieren in ein enumerierter Typ, Typrückschluss versucht, den Typ bestimmen die `enum` , die Sie zum konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="29d05-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="29d05-137">Im folgenden Beispiel ist die Variable `col1` ist nicht explizit mit Anmerkungen versehen, aber der Typ nicht von der höheren Gleichheitstest abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="29d05-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="29d05-138">Aus diesem Grund kann der Compiler folgern, dass Sie in das Konvertieren einer `Color` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="29d05-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="29d05-139">Alternativ können Sie eine typanmerkung angeben wie bei `col2` im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="29d05-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="29d05-140">Sie können den Zieltyp für die Enumeration auch explizit als einen Typparameter, wie im folgenden Code angeben:</span><span class="sxs-lookup"><span data-stu-id="29d05-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="29d05-141">Beachten Sie, dass die Enumeration Arbeit umgewandelt wird, nur, wenn der zugrunde liegende Typ der Enumeration mit dem konvertierten Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="29d05-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="29d05-142">Im folgenden Code wird die Konvertierung schlägt fehl, kompilieren Sie aufgrund der fehlenden Übereinstimmung zwischen `int32` und `uint32`.</span><span class="sxs-lookup"><span data-stu-id="29d05-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="29d05-143">Weitere Informationen finden Sie unter [Enumerationen](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="29d05-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="29d05-144">Umwandlung von Objekttypen</span><span class="sxs-lookup"><span data-stu-id="29d05-144">Casting Object Types</span></span>

<span data-ttu-id="29d05-145">Konvertierung zwischen Typen in einer Objekthierarchie ist elementar für objektorientierte Programmierung.</span><span class="sxs-lookup"><span data-stu-id="29d05-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="29d05-146">Es gibt zwei grundlegende Arten von Konvertierungen: Typumwandlung nach oben (umwandeln) und nach unten (Downcasting) umwandeln.</span><span class="sxs-lookup"><span data-stu-id="29d05-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="29d05-147">Typumwandlung, eine Hierarchie bedeutet, dass die Umwandlung von einer abgeleiteten Objektverweis auf ein Basisobjekt-Verweis.</span><span class="sxs-lookup"><span data-stu-id="29d05-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="29d05-148">Eine solche Umwandlung ist garantiert funktioniert nur, wenn in der Vererbungshierarchie der abgeleiteten Klasse die Basisklasse ist.</span><span class="sxs-lookup"><span data-stu-id="29d05-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="29d05-149">Umwandeln in eine Hierarchie, aus einem Basisobjekt-Verweis auf ein abgeleitetes Objekt-Verweis ist erfolgreich, nur dann, wenn das Objekt tatsächlich eine Instanz des Typs richtige Ziel (abgeleitete) oder ein Typ, der den Zieltyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="29d05-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="29d05-150">F#Stellt die Operatoren für diese Arten von Konvertierungen bereit.</span><span class="sxs-lookup"><span data-stu-id="29d05-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="29d05-151">Die `:>` -Operator wandelt der Hierarchie, und die `:?>` Operator Abwärtsumwandlung in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="29d05-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="29d05-152">Umwandeln</span><span class="sxs-lookup"><span data-stu-id="29d05-152">Upcasting</span></span>

<span data-ttu-id="29d05-153">In vielen objektorientierten Sprachen erfolgt die Upcasting implizit. in F# sind die Regeln unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="29d05-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="29d05-154">Umwandeln wird automatisch angewendet, wenn Sie auf einen Objekttyp Argumente an Methoden übergeben.</span><span class="sxs-lookup"><span data-stu-id="29d05-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="29d05-155">Allerdings erfolgt umwandeln für Let gebundenen-Funktionen in einem Modul nicht automatisch, es sei denn, der der Parametertyp als einen flexiblen Typ deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="29d05-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="29d05-156">Weitere Informationen finden Sie unter [Flexible Typen](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="29d05-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="29d05-157">Die `:>` -Operator führt eine statische Umwandlung, was bedeutet, dass der Erfolg der Umwandlung zur Kompilierzeit bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="29d05-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="29d05-158">Wenn eine Umwandlung mit `:>` erfolgreich kompiliert, es ist keine zulässige Umwandlung und zur Laufzeit kein Fehler auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="29d05-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="29d05-159">Sie können auch die `upcast` Operator, um eine solche Konvertierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="29d05-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="29d05-160">Der folgende Ausdruck gibt eine Konvertierung der Hierarchie nach oben an:</span><span class="sxs-lookup"><span data-stu-id="29d05-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="29d05-161">Wenn Sie die upcast-Operator verwenden, versucht der Compiler, den Typ abzuleiten, die, den Sie aus dem Kontext zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="29d05-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="29d05-162">Wenn der Compiler kann nicht den Zieltyp bestimmt ist, meldet der Compiler einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="29d05-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="29d05-163">Typumwandlung</span><span class="sxs-lookup"><span data-stu-id="29d05-163">Downcasting</span></span>

<span data-ttu-id="29d05-164">Die `:?>` -Operator führt eine dynamische Umwandlung, was bedeutet, dass der Erfolg der Umwandlung zur Laufzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="29d05-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="29d05-165">Eine Umwandlung mit den `:?>` Operator nicht zur Kompilierzeit; aktiviert ist, aber zur Laufzeit wird versucht, das in den angegebenen Typ umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="29d05-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="29d05-166">Wenn das Objekt mit dem Zieltyp kompatibel ist, ist die Umwandlung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="29d05-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="29d05-167">Wenn das Objekt nicht mit dem Zieltyp kompatibel ist, löst die Laufzeit eine `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="29d05-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="29d05-168">Sie können auch die `downcast` Operator beim Ausführen einer Konvertierung von Typ "dynamic".</span><span class="sxs-lookup"><span data-stu-id="29d05-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="29d05-169">Der folgende Ausdruck gibt eine Konvertierung in der Hierarchie auf einen Typ, der vom Programmkontext abgeleitet wird:</span><span class="sxs-lookup"><span data-stu-id="29d05-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="29d05-170">Wie bei der `upcast` -Operator, wenn der Compiler einen bestimmten Zieltyp aus dem Kontext ableiten kann ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="29d05-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="29d05-171">Der folgende Code veranschaulicht die Verwendung der `:>` und `:?>` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="29d05-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="29d05-172">Im Code wird veranschaulicht, die die `:?>` Operator wird am besten verwendet werden, wenn Sie wissen, dass die Konvertierung erfolgreich ausgeführt wird, da es löst `InvalidCastException` , wenn die Konvertierung schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="29d05-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="29d05-173">Wenn Sie nicht wissen, dass eine Konvertierung ist erfolgreich, einen Typtest, die verwendet eine `match` Ausdruck ist besser, da es sich um den Aufwand für das Auslösen einer Ausnahme verhindert.</span><span class="sxs-lookup"><span data-stu-id="29d05-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="29d05-174">Da generischen Operatoren `downcast` und `upcast` Typrückschluss zum Bestimmen des Typs Argument- und Rückgabetypen, im obigen Code, Sie können ersetzen</span><span class="sxs-lookup"><span data-stu-id="29d05-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="29d05-175">durch</span><span class="sxs-lookup"><span data-stu-id="29d05-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="29d05-176">Im vorherigen Code den Typ des Arguments und Rückgabetypen sind `Derived1` und `Base1`bzw.</span><span class="sxs-lookup"><span data-stu-id="29d05-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="29d05-177">Weitere Informationen zu Typtests finden Sie unter [Vergleichsausdrücke](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="29d05-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="29d05-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29d05-178">See also</span></span>

- [<span data-ttu-id="29d05-179">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="29d05-179">F# Language Reference</span></span>](index.md)
