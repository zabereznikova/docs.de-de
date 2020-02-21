---
title: Umwandlung und Konvertierungen
description: Erfahren Sie, wie die Programmiersprache F# Konvertierungsoperatoren für arithmetische Konvertierungen zwischen primitiven Typen von verschiedenen bereitstellt.
ms.date: 02/20/2020
ms.openlocfilehash: 5f9727d14a7ae070e0f0f71fa0a0abe04f662071
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543585"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="58c5b-103">Umwandlung und Konvertierungen (F#)</span><span class="sxs-lookup"><span data-stu-id="58c5b-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="58c5b-104">Dieses Thema beschreibt die Unterstützung für Typumwandlungen in F#.</span><span class="sxs-lookup"><span data-stu-id="58c5b-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="58c5b-105">Arithmetische Typen</span><span class="sxs-lookup"><span data-stu-id="58c5b-105">Arithmetic Types</span></span>

<span data-ttu-id="58c5b-106">F#stellt Konvertierungs Operatoren für arithmetische Konvertierungen zwischen verschiedenen primitiven Typen bereit, z. b. zwischen Integer-und Gleit Komma Typen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="58c5b-107">Der ganzzahlige und der Char-Konvertierungs Operator haben die Formulare aktiviert und deaktiviert. die Gleit Komma Operatoren und der `enum` Konvertierungs Operator nicht.</span><span class="sxs-lookup"><span data-stu-id="58c5b-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="58c5b-108">Die nicht aktivierten Formulare werden in `Microsoft.FSharp.Core.Operators` definiert, und die überprüften Formulare werden in `Microsoft.FSharp.Core.Operators.Checked`definiert.</span><span class="sxs-lookup"><span data-stu-id="58c5b-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="58c5b-109">Die aktivierten Formulare überprüfen auf Überlauf und generieren eine Lauf Zeit Ausnahme, wenn der resultierende Wert die Begrenzungen des Zieltyps überschreitet.</span><span class="sxs-lookup"><span data-stu-id="58c5b-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="58c5b-110">Jeder dieser Operatoren hat denselben Namen wie der Name des Zieltyps.</span><span class="sxs-lookup"><span data-stu-id="58c5b-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="58c5b-111">Beispielsweise wird im folgenden Code, in dem die Typen explizit mit Anmerkungen versehen werden, `byte` mit zwei verschiedenen Bedeutungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58c5b-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="58c5b-112">Das erste Vorkommen ist der-Typ, und der zweite ist der Konvertierungs Operator.</span><span class="sxs-lookup"><span data-stu-id="58c5b-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="58c5b-113">Die folgende Tabelle zeigt die Konvertierungsoperatoren, die in F# definiert.</span><span class="sxs-lookup"><span data-stu-id="58c5b-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="58c5b-114">Operator</span><span class="sxs-lookup"><span data-stu-id="58c5b-114">Operator</span></span>|<span data-ttu-id="58c5b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58c5b-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="58c5b-116">Konvertieren in Byte, einen 8-Bit-Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="58c5b-117">In signiertes Byte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="58c5b-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="58c5b-118">Konvertieren in eine 16-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="58c5b-119">Konvertieren in eine 16-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="58c5b-120">Konvertiert in eine 32-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="58c5b-121">Konvertiert in eine 32-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="58c5b-122">Konvertiert in eine 64-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="58c5b-123">Konvertiert in eine 64-Bit-Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="58c5b-124">In eine systemeigene ganze Zahl konvertieren.</span><span class="sxs-lookup"><span data-stu-id="58c5b-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="58c5b-125">Konvertiert in eine native Ganzzahl ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="58c5b-126">Konvertieren in eine 64-Bit-IEEE-Gleit Komma Zahl mit doppelter Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="58c5b-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="58c5b-127">Konvertieren in eine 32-Bit-IEEE-Gleit Komma Zahl mit einfacher Genauigkeit.</span><span class="sxs-lookup"><span data-stu-id="58c5b-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="58c5b-128">In `System.Decimal`konvertieren.</span><span class="sxs-lookup"><span data-stu-id="58c5b-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="58c5b-129">Konvertieren Sie in `System.Char`, ein Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="58c5b-130">Konvertieren in einen enumerierten Typ.</span><span class="sxs-lookup"><span data-stu-id="58c5b-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="58c5b-131">Zusätzlich zu den integrierten primitiven Typen können Sie diese Operatoren mit Typen verwenden, die `op_Explicit` oder `op_Implicit` Methoden mit entsprechenden Signaturen implementieren.</span><span class="sxs-lookup"><span data-stu-id="58c5b-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="58c5b-132">Beispielsweise arbeitet der `int` Konvertierungs Operator mit jedem Typ, der eine statische Methoden `op_Explicit` bereitstellt, die den Typ als Parameter annimmt und `int`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="58c5b-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="58c5b-133">Als besondere Ausnahme von der allgemeinen Regel, dass Methoden nicht durch den Rückgabetyp überladen werden können, können Sie dies für `op_Explicit` und `op_Implicit`tun.</span><span class="sxs-lookup"><span data-stu-id="58c5b-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="58c5b-134">Enumerierte Typen</span><span class="sxs-lookup"><span data-stu-id="58c5b-134">Enumerated Types</span></span>

<span data-ttu-id="58c5b-135">Der `enum`-Operator ist ein generischer Operator, der einen Typparameter annimmt, der den Typ des `enum` darstellt, in den konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="58c5b-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="58c5b-136">Beim Konvertieren in einen enumerierten Typ versucht der Typrückschluss, den Typ des `enum` zu bestimmen, in den konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="58c5b-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="58c5b-137">Im folgenden Beispiel wird die Variable `col1` nicht explizit mit Anmerkungen versehen, aber der Typ wird aus dem späteren Gleichheits Test abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="58c5b-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="58c5b-138">Daher kann der Compiler ableiten, dass Sie in eine `Color` Enumeration wandeln.</span><span class="sxs-lookup"><span data-stu-id="58c5b-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="58c5b-139">Alternativ können Sie eine Typanmerkung angeben, wie `col2` im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="58c5b-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="58c5b-140">Sie können den zielenumerationstyp auch explizit als Typparameter angeben, wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="58c5b-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="58c5b-141">Beachten Sie, dass die enumerationsumwandlungen nur funktionieren, wenn der zugrunde liegende Typ der Enumeration mit dem Typ kompatibel ist, der konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="58c5b-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="58c5b-142">Im folgenden Code kann die Konvertierung aufgrund des Konflikts zwischen `int32` und `uint32`nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="58c5b-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="58c5b-143">Weitere Informationen finden Sie unter [Enumerationen](enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="58c5b-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="58c5b-144">Umwandeln von Objekttypen</span><span class="sxs-lookup"><span data-stu-id="58c5b-144">Casting Object Types</span></span>

<span data-ttu-id="58c5b-145">Die Konvertierung zwischen Typen in einer Objekthierarchie ist von grundlegender Bedeutung für objektorientierte Programmierung.</span><span class="sxs-lookup"><span data-stu-id="58c5b-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="58c5b-146">Es gibt zwei grundlegende Typen von Konvertierungen: Umwandlung (Upcasting) und Umwandlung nach unten (Downcasting).</span><span class="sxs-lookup"><span data-stu-id="58c5b-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="58c5b-147">Das Umwandeln einer Hierarchie bedeutet, dass ein abgeleiteter Objekt Verweis in einen Basisobjekt Verweis umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="58c5b-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="58c5b-148">Eine solche Umwandlung ist garantiert funktionsfähig, solange sich die Basisklasse in der Vererbungs Hierarchie der abgeleiteten Klasse befindet.</span><span class="sxs-lookup"><span data-stu-id="58c5b-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="58c5b-149">Das Umwandeln einer Hierarchie aus einem Basisobjekt Verweis in einen abgeleiteten Objekt Verweis ist nur erfolgreich, wenn das Objekt tatsächlich eine Instanz des richtigen Ziel Typs (abgeleiteter Typ) oder eines Typs ist, der vom Zieltyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="58c5b-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="58c5b-150">F#stellt Operatoren für diese Typen von Konvertierungen bereit.</span><span class="sxs-lookup"><span data-stu-id="58c5b-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="58c5b-151">Der `:>`-Operator wandelt die Hierarchie um, und der `:?>` Operator wandelt die Hierarchie um.</span><span class="sxs-lookup"><span data-stu-id="58c5b-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="58c5b-152">Umwandeln</span><span class="sxs-lookup"><span data-stu-id="58c5b-152">Upcasting</span></span>

<span data-ttu-id="58c5b-153">In vielen objektorientierten Sprachen erfolgt die Upcasting implizit. in F# sind die Regeln unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="58c5b-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="58c5b-154">Upcasting wird automatisch angewendet, wenn Sie Argumente an Methoden für einen Objekttyp übergeben.</span><span class="sxs-lookup"><span data-stu-id="58c5b-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="58c5b-155">Für Let-gebundene Funktionen in einem Modul ist umwandeln jedoch nicht automatisch, es sei denn, der Parametertyp wird als flexibler Typ deklariert.</span><span class="sxs-lookup"><span data-stu-id="58c5b-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="58c5b-156">Weitere Informationen finden Sie unter [flexible Typen](flexible-Types.md).</span><span class="sxs-lookup"><span data-stu-id="58c5b-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="58c5b-157">Der `:>`-Operator führt eine statische Umwandlung aus, was bedeutet, dass der Erfolg der Umwandlung zur Kompilierzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="58c5b-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="58c5b-158">Wenn eine Umwandlung, die `:>` verwendet, erfolgreich kompiliert wird, handelt es sich um eine gültige Umwandlung, die zur Laufzeit nicht fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="58c5b-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="58c5b-159">Sie können auch den `upcast`-Operator verwenden, um eine solche Konvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="58c5b-160">Der folgende Ausdruck gibt eine Konvertierung in der Hierarchie an:</span><span class="sxs-lookup"><span data-stu-id="58c5b-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="58c5b-161">Wenn Sie den umgewandelt-Operator verwenden, versucht der Compiler, den Typ, in den konvertiert werden soll, aus dem Kontext abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="58c5b-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="58c5b-162">Wenn der Compiler den Zieltyp nicht ermitteln kann, meldet der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="58c5b-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span> <span data-ttu-id="58c5b-163">Eine Typanmerkung ist möglicherweise erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58c5b-163">A type annotation may be required.</span></span>

### <a name="downcasting"></a><span data-ttu-id="58c5b-164">Dass</span><span class="sxs-lookup"><span data-stu-id="58c5b-164">Downcasting</span></span>

<span data-ttu-id="58c5b-165">Der `:?>`-Operator führt eine dynamische Umwandlung aus, was bedeutet, dass der Erfolg der Umwandlung zur Laufzeit bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="58c5b-165">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="58c5b-166">Eine Umwandlung, die den `:?>` Operator verwendet, wird zur Kompilierzeit nicht geprüft. zur Laufzeit wird jedoch versucht, in den angegebenen Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="58c5b-166">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="58c5b-167">Wenn das Objekt mit dem Zieltyp kompatibel ist, ist die Umwandlung erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="58c5b-167">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="58c5b-168">Wenn das Objekt nicht mit dem Zieltyp kompatibel ist, löst die Laufzeit eine `InvalidCastException`aus.</span><span class="sxs-lookup"><span data-stu-id="58c5b-168">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="58c5b-169">Sie können auch den `downcast`-Operator verwenden, um eine dynamische Typkonvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="58c5b-169">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="58c5b-170">Der folgende Ausdruck gibt eine Konvertierung der Hierarchie nach unten in einen Typ an, der aus dem Programmkontext abgeleitet wird:</span><span class="sxs-lookup"><span data-stu-id="58c5b-170">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="58c5b-171">Wie beim `upcast`-Operator meldet der Compiler einen Fehler, wenn der Compiler keinen bestimmten Zieltyp aus dem Kontext ableiten kann.</span><span class="sxs-lookup"><span data-stu-id="58c5b-171">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span> <span data-ttu-id="58c5b-172">Eine Typanmerkung ist möglicherweise erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58c5b-172">A type annotation may be required.</span></span>

<span data-ttu-id="58c5b-173">Der folgende Code veranschaulicht die Verwendung der Operatoren "`:>`" und "`:?>`".</span><span class="sxs-lookup"><span data-stu-id="58c5b-173">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="58c5b-174">Der Code veranschaulicht, dass der `:?>`-Operator am besten verwendet wird, wenn Sie wissen, dass die Konvertierung erfolgreich ist, da Sie `InvalidCastException` auslöst, wenn die Konvertierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="58c5b-174">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="58c5b-175">Wenn Sie nicht wissen, dass eine Konvertierung erfolgreich durchgeführt werden kann, ist ein Typtest, der einen `match` Ausdruck verwendet, besser, da dadurch der Aufwand für das Erzeugen einer Ausnahme vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="58c5b-175">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="58c5b-176">Da generische Operatoren `downcast` und `upcast` auf den Typrückschluss zurückgreifen, um das Argument und den Rückgabetyp zu bestimmen, können Sie im obigen Code</span><span class="sxs-lookup"><span data-stu-id="58c5b-176">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="58c5b-177">mit</span><span class="sxs-lookup"><span data-stu-id="58c5b-177">with</span></span>

```fsharp
let base1: Base1 = upcast d1
```

<span data-ttu-id="58c5b-178">Beachten Sie, dass eine Typanmerkung erforderlich ist, da die Basisklasse von `upcast` allein nicht bestimmt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="58c5b-178">Note that a type annotation is required, since `upcast` by itself could not determine the base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="58c5b-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58c5b-179">See also</span></span>

- [<span data-ttu-id="58c5b-180">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="58c5b-180">F# Language Reference</span></span>](index.md)
