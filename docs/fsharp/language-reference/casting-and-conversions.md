---
title: Umwandlung und Konvertierungen (F#)
description: "Hier erfahren Sie, wie der Programmiersprache f# Konvertierungsoperatoren für arithmetische Konvertierungen zwischen verschiedenen primitiven Typen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: db30db67-da21-4206-bf0c-9211bd3cb22f
ms.openlocfilehash: f17d3919c59c5881213d28a59cea7ae184493949
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="47984-104">Umwandlung und Konvertierungen (F#)</span><span class="sxs-lookup"><span data-stu-id="47984-104">Casting and Conversions (F#)</span></span>

<span data-ttu-id="47984-105">Dieses Thema beschreibt die Unterstützung für Konvertierungen in F# erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="47984-105">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="47984-106">Arithmetische Typen</span><span class="sxs-lookup"><span data-stu-id="47984-106">Arithmetic Types</span></span>
<span data-ttu-id="47984-107">F# bietet Konvertierungsoperatoren für arithmetische Konvertierungen zwischen verschiedenen primitive Typen, z. B. zwischen Ganzzahl- und Gleitkommatypen.</span><span class="sxs-lookup"><span data-stu-id="47984-107">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="47984-108">Konvertierungsoperatoren integrale und Char überprüft haben und die unchecked-Formulare der Gleitkommawert Operatoren und die `enum` Konvertierungsoperator nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="47984-108">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="47984-109">Die unchecked-Formen werden in definiert `Microsoft.FSharp.Core.Operators` und die aktivierten Formularen werden im definiert `Microsoft.FSharp.Core.Operators.Checked`.</span><span class="sxs-lookup"><span data-stu-id="47984-109">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="47984-110">Die überprüften Formulare auf Überläufe überprüfen und generieren eine Laufzeitausnahme, wenn der resultierende Wert die Grenzen des Zieltyps überschreitet.</span><span class="sxs-lookup"><span data-stu-id="47984-110">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="47984-111">Jede dieser Operatoren verfügt über den gleichen Namen wie der Name des Zieltyps.</span><span class="sxs-lookup"><span data-stu-id="47984-111">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="47984-112">In den folgenden Code, in denen die Typen explizit mit Anmerkungen versehen werden, z. B. `byte` mit zwei verschiedenen Bedeutungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47984-112">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="47984-113">Das erste Vorkommen ist der Typ und der zweite Operator für die Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="47984-113">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="47984-114">Die folgende Tabelle zeigt die Konvertierungsoperatoren, die in f# definiert.</span><span class="sxs-lookup"><span data-stu-id="47984-114">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="47984-115">Operator</span><span class="sxs-lookup"><span data-stu-id="47984-115">Operator</span></span>|<span data-ttu-id="47984-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47984-116">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="47984-117">Konvertieren Sie in Byte, ein 8-Bit-Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-117">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="47984-118">Konvertieren Sie in einen Bytewert mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-118">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="47984-119">Konvertieren Sie in eine 16-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-119">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="47984-120">Konvertieren Sie in eine 16-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-120">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="47984-121">Konvertieren Sie in eine 32-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-121">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="47984-122">Konvertieren Sie in eine 32-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-122">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="47984-123">Konvertieren Sie in eine 64-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-123">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="47984-124">Konvertieren Sie in eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-124">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="47984-125">Konvertieren Sie in eine systemeigene ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="47984-125">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="47984-126">Konvertieren Sie in eine systemeigene Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-126">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="47984-127">Konvertieren Sie in eine mit doppelter Genauigkeit IEEE-64-Bit-Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="47984-127">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="47984-128">Konvertieren Sie in eine 32-Bit mit einfacher Genauigkeit IEEE-Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="47984-128">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="47984-129">Konvertieren in `System.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="47984-129">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="47984-130">Konvertieren in `System.Char`, ein Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="47984-130">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="47984-131">Für einen enumerierten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="47984-131">Convert to an enumerated type.</span></span>|
<span data-ttu-id="47984-132">Zusätzlich zu den integrierten Grundtypen, können Sie diese Operatoren mit Typen, die implementieren `op_Explicit` oder `op_Implicit` Methoden mit den entsprechenden Signaturen.</span><span class="sxs-lookup"><span data-stu-id="47984-132">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="47984-133">Z. B. die `int` Konvertierungsoperator funktioniert mit jeder Typ, der eine statische Methode bietet `op_Explicit` , die den Typ als Parameter akzeptiert und gibt `int`.</span><span class="sxs-lookup"><span data-stu-id="47984-133">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="47984-134">Als eine besondere Ausnahme, die allgemeine Regel, durch den Rückgabetyp Methoden nicht überladen werden können, Sie hierzu für `op_Explicit` und `op_Implicit`.</span><span class="sxs-lookup"><span data-stu-id="47984-134">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="47984-135">Enumerationstypen</span><span class="sxs-lookup"><span data-stu-id="47984-135">Enumerated Types</span></span>
<span data-ttu-id="47984-136">Die `enum` Operator ist ein generischer Operator, der einen Typparameter ausgeführt wird, die den Typ des darstellt der `enum` zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="47984-136">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="47984-137">Wenn für einen enumerierten Typ konvertiert werden, geben Sie mithilfe eines Rückschlusses versucht zu ermitteln, welche die `enum` , die Sie zum konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47984-137">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="47984-138">Im folgenden Beispiel wird die Variable `col1` nicht explizit kommentiert, aber der Typ nicht von der höheren Gleichheitstest abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="47984-138">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="47984-139">Aus diesem Grund kann der Compiler folgern, dass Sie zum Konvertieren einer `Color` Enumeration.</span><span class="sxs-lookup"><span data-stu-id="47984-139">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="47984-140">Alternativ können Sie eine typanmerkung angeben wie bei `col2` im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="47984-140">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]
    
<span data-ttu-id="47984-141">Sie können den Zieltyp für die Enumeration auch explizit wie ein Typparameter, wie im folgenden Code gezeigt angeben:</span><span class="sxs-lookup"><span data-stu-id="47984-141">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="47984-142">Beachten Sie, dass die Enumeration Arbeit wandelt nur, wenn der zugrunde liegende Typ der Enumeration mit dem konvertierten Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="47984-142">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="47984-143">Im folgenden Code wird die Konvertierung schlägt fehl, aufgrund des Konflikts zwischen Kompilieren `int32` und `uint32`.</span><span class="sxs-lookup"><span data-stu-id="47984-143">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="47984-144">Weitere Informationen finden Sie unter [Enumerationen](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="47984-144">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="47984-145">Umwandeln von Objekttypen</span><span class="sxs-lookup"><span data-stu-id="47984-145">Casting Object Types</span></span>
<span data-ttu-id="47984-146">Konvertierung zwischen Typen in einer Objekthierarchie ist grundlegend für objektorientiertes Programmieren.</span><span class="sxs-lookup"><span data-stu-id="47984-146">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="47984-147">Es gibt zwei grundlegende Typen von Konvertierungen: die Umwandlung (Upcasting) und nach unten (Downcasting) umwandeln.</span><span class="sxs-lookup"><span data-stu-id="47984-147">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="47984-148">Umwandlung einer Hierarchie bedeutet das Umwandeln von einer abgeleiteten Objektverweis auf ein Basisobjekt Verweis.</span><span class="sxs-lookup"><span data-stu-id="47984-148">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="47984-149">Eine solche Umwandlung funktioniert auf alle Fälle als in der Vererbungshierarchie der abgeleiteten Klasse die Basisklasse ist.</span><span class="sxs-lookup"><span data-stu-id="47984-149">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="47984-150">Umwandeln in eine Hierarchie, aus einem Basisobjekt-Verweis auf einen abgeleiteten Objektverweis erfolgreich ist, nur dann, wenn das Objekt tatsächlich eine Instanz des Typs richtige Ziel (abgeleitet) oder ein Typ, der den Zieltyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="47984-150">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="47984-151">F# stellt Operatoren für diese Typen von Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="47984-151">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="47984-152">Die `:>` -Operator wandelt der Hierarchie nach oben und der `:?>` -Operator wandelt innerhalb der Hierarchie nach unten.</span><span class="sxs-lookup"><span data-stu-id="47984-152">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="47984-153">Umwandeln</span><span class="sxs-lookup"><span data-stu-id="47984-153">Upcasting</span></span>
<span data-ttu-id="47984-154">In vielen objektorientierten Sprachen erfolgt Upcasting implizit. in F# erläutert werden sind die Regeln etwas anders.</span><span class="sxs-lookup"><span data-stu-id="47984-154">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="47984-155">Upcasting wird automatisch angewendet werden, wenn Sie Argumente auf einen Objekttyp an Methoden übergeben.</span><span class="sxs-lookup"><span data-stu-id="47984-155">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="47984-156">Allerdings wird für gebundene Let-Funktionen in einem Modul Upcasting nicht automatisch wiederhergestellt, wenn der Parametertyp als einen flexiblen Typ deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="47984-156">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="47984-157">Weitere Informationen finden Sie unter [Flexible Typen](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="47984-157">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="47984-158">Die `:>` -Operator führt eine statische umgewandelt, was bedeutet, dass der Erfolg der Umwandlung zur Kompilierzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="47984-158">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="47984-159">Wenn eine Umwandlung mit `:>` erfolgreich kompiliert, es ist keine zulässige Umwandlung und verfügt über keine Chance Fehler zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="47984-159">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="47984-160">Sie können auch die `upcast` Operator, um eine solche Konvertierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="47984-160">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="47984-161">Der folgende Ausdruck gibt eine Konvertierung der Hierarchie nach oben an:</span><span class="sxs-lookup"><span data-stu-id="47984-161">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="47984-162">Wenn Sie die upcast-Operator verwenden, versucht der Compiler den Typ abzuleiten, den Sie aus dem Kontext konvertieren sind.</span><span class="sxs-lookup"><span data-stu-id="47984-162">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="47984-163">Wenn der Compiler kann nicht den Zieltyp bestimmt ist, meldet der Compiler einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="47984-163">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="47984-164">Downcasting</span><span class="sxs-lookup"><span data-stu-id="47984-164">Downcasting</span></span>
<span data-ttu-id="47984-165">Die `:?>` -Operator führt eine dynamische Umwandlung, was bedeutet, dass der Erfolg der Umwandlung zur Laufzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="47984-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="47984-166">Eine Umwandlung mit den `:?>` Operator nicht zur Kompilierzeit; aktiviert ist, aber zur Laufzeit wird versucht, auf den angegebenen Typ umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="47984-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="47984-167">Wenn das Objekt mit dem Zieltyp kompatibel ist, ist die Umwandlung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="47984-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="47984-168">Wenn das Objekt nicht mit dem Zieltyp kompatibel ist, löst die Laufzeit eine `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="47984-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="47984-169">Sie können auch die `downcast` Operator, um eine dynamische typkonvertierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="47984-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="47984-170">Der folgende Ausdruck gibt eine Konvertierung in der Hierarchie auf einen Typ, der vom Programmkontext abgeleitet wird:</span><span class="sxs-lookup"><span data-stu-id="47984-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="47984-171">Wie bei der `upcast` -Operator, wenn der Compiler einen bestimmten Zieltyp aus dem Kontext ableiten kann meldet einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="47984-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="47984-172">Der folgende Code veranschaulicht die Verwendung der `:>` und `:?>` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="47984-172">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="47984-173">Im Code wird veranschaulicht, die die `:?>` Operator wird am besten verwendet werden, wenn Sie wissen, dass die Konvertierung erfolgreich ausgeführt wird, da löst `InvalidCastException` , wenn die Konvertierung schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="47984-173">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="47984-174">Wenn Sie nicht wissen, dass eine Konvertierung ist erfolgreich, einen Typtest, die verwendet eine `match` Ausdruck ist besser, da der Aufwand für das Auslösen einer Ausnahme vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="47984-174">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="47984-175">Da generischen Operatoren `downcast` und `upcast` Typrückschluss zum Bestimmen des Typs Argument- und Rückgabetypen, im obigen Code, ersetzen Sie</span><span class="sxs-lookup"><span data-stu-id="47984-175">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="47984-176">with</span><span class="sxs-lookup"><span data-stu-id="47984-176">with</span></span>

```fsharp
base1 = upcast d1
```

<span data-ttu-id="47984-177">Im vorherigen Code den Argumenttyp und Rückgabetypen sind `Derived1` und `Base1`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="47984-177">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="47984-178">Weitere Informationen zu Typtests finden Sie unter [Übereinstimmungsausdrücken](match-Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="47984-178">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47984-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47984-179">See Also</span></span>
[<span data-ttu-id="47984-180">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="47984-180">F# Language Reference</span></span>](index.md)
