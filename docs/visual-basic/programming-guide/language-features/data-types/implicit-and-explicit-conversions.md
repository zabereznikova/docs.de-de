---
title: Implizite und explizite Konvertierungen
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 2858dafd2531bd846ad89672348d103f385c4511
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393830"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="f8a39-102">Implizite und explizite Konvertierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8a39-102">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="f8a39-103">Eine *implizite Konvertierung* erfordert keine besondere Syntax im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="f8a39-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="f8a39-104">Im folgenden Beispiel konvertiert Visual Basic den Wert von implizit `k` in einen Gleit Komma Wert mit einfacher Genauigkeit, bevor er dem zugewiesen wird `q` .</span><span class="sxs-lookup"><span data-stu-id="f8a39-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="f8a39-105">Eine *explizite Konvertierung* verwendet ein Typkonvertierungs Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f8a39-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="f8a39-106">Visual Basic stellt mehrere solche Schlüsselwörter bereit, die einen Ausdruck in Klammern in den gewünschten Datentyp umwandeln.</span><span class="sxs-lookup"><span data-stu-id="f8a39-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="f8a39-107">Diese Schlüsselwörter fungieren wie Funktionen, aber der Compiler generiert den Code Inline, sodass die Ausführung etwas schneller ist als bei einem Funktions Aufruf.</span><span class="sxs-lookup"><span data-stu-id="f8a39-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="f8a39-108">In der folgenden Erweiterung des vorherigen Beispiels konvertiert das- `CInt` Schlüsselwort den Wert von `q` zurück in eine ganze Zahl, bevor Sie diesem zugewiesen wird `k` .</span><span class="sxs-lookup"><span data-stu-id="f8a39-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="f8a39-109">Konvertierungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f8a39-109">Conversion Keywords</span></span>

<span data-ttu-id="f8a39-110">Die folgende Tabelle zeigt die verfügbaren Konvertierungs Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="f8a39-110">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="f8a39-111">Schlüsselwort für Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="f8a39-111">Type conversion keyword</span></span>|<span data-ttu-id="f8a39-112">Konvertiert einen Ausdruck in einen-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="f8a39-112">Converts an expression to data type</span></span>|<span data-ttu-id="f8a39-113">Zulässige Datentypen von zu konvertierenden Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="f8a39-113">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="f8a39-114">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-114">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="f8a39-115">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="f8a39-116">Byte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-116">Byte Data Type</span></span>](../../../language-reference/data-types/byte-data-type.md)|<span data-ttu-id="f8a39-117">Ein beliebiger numerischer Typ (einschließlich `SByte` und enumerierten Typen),, `Boolean` `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="f8a39-118">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-118">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)|<span data-ttu-id="f8a39-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-119">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="f8a39-120">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-120">Date Data Type</span></span>](../../../language-reference/data-types/date-data-type.md)|<span data-ttu-id="f8a39-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-121">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="f8a39-122">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-122">Double Data Type</span></span>](../../../language-reference/data-types/double-data-type.md)|<span data-ttu-id="f8a39-123">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="f8a39-124">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-124">Decimal Data Type</span></span>](../../../language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="f8a39-125">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="f8a39-126">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-126">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)|<span data-ttu-id="f8a39-127">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="f8a39-128">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-128">Long Data Type</span></span>](../../../language-reference/data-types/long-data-type.md)|<span data-ttu-id="f8a39-129">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="f8a39-130">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="f8a39-130">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)|<span data-ttu-id="f8a39-131">Beliebiger Typ</span><span class="sxs-lookup"><span data-stu-id="f8a39-131">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="f8a39-132">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-132">SByte Data Type</span></span>](../../../language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="f8a39-133">Ein beliebiger numerischer Typ (einschließlich `Byte` und enumerierten Typen),, `Boolean` `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="f8a39-134">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-134">Short Data Type</span></span>](../../../language-reference/data-types/short-data-type.md)|<span data-ttu-id="f8a39-135">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="f8a39-136">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-136">Single Data Type</span></span>](../../../language-reference/data-types/single-data-type.md)|<span data-ttu-id="f8a39-137">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="f8a39-138">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-138">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)|<span data-ttu-id="f8a39-139">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `Char` ,, `Char` `Date` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="f8a39-140">Nach dem Komma () angegebener Typ `,`</span><span class="sxs-lookup"><span data-stu-id="f8a39-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="f8a39-141">Beim Konvertieren in einen *elementaren Datentyp* (einschließlich eines Arrays eines elementaren Typs) werden dieselben Typen wie für das entsprechende Konvertierungs Schlüsselwort zulässig.</span><span class="sxs-lookup"><span data-stu-id="f8a39-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="f8a39-142">Beim umstellen in einen zusammen *gesetzten Datentyp*werden die Schnittstellen implementiert, die implementiert werden, und die Klassen, von denen Sie erbt.</span><span class="sxs-lookup"><span data-stu-id="f8a39-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="f8a39-143">Beim umstellen in eine Klasse oder Struktur, für die Sie überladen haben `CType` , diese Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="f8a39-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="f8a39-144">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-144">UInteger Data Type</span></span>](../../../language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="f8a39-145">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="f8a39-146">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-146">ULong Data Type</span></span>](../../../language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="f8a39-147">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="f8a39-148">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f8a39-148">UShort Data Type</span></span>](../../../language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="f8a39-149">Alle numerischen Typen (einschließlich `Byte` , `SByte` und enumerierten Typen), `Boolean` , `String` ,`Object`</span><span class="sxs-lookup"><span data-stu-id="f8a39-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="f8a39-150">Die CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="f8a39-150">The CType Function</span></span>

<span data-ttu-id="f8a39-151">Die [CType-Funktion](../../../language-reference/functions/ctype-function.md) arbeitet mit zwei Argumenten.</span><span class="sxs-lookup"><span data-stu-id="f8a39-151">The [CType Function](../../../language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="f8a39-152">Der erste ist der Ausdruck, der konvertiert werden soll, und der zweite ist der Ziel Datentyp oder die Objektklasse.</span><span class="sxs-lookup"><span data-stu-id="f8a39-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="f8a39-153">Beachten Sie, dass das erste Argument ein Ausdruck und kein Typ sein muss.</span><span class="sxs-lookup"><span data-stu-id="f8a39-153">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="f8a39-154">`CType`ist eine *Inline Funktion*, d. h., der kompilierte Code führt die Konvertierung aus, oft ohne einen Funktions aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f8a39-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="f8a39-155">Dadurch wird die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="f8a39-155">This improves performance.</span></span>

<span data-ttu-id="f8a39-156">Einen Vergleich von `CType` mit den anderen Schlüsselwörtern für die Typkonvertierung finden Sie unter [DirectCast-Operator](../../../language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f8a39-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="f8a39-157">Elementare Typen</span><span class="sxs-lookup"><span data-stu-id="f8a39-157">Elementary Types</span></span>

<span data-ttu-id="f8a39-158">Das folgende Beispiel veranschaulicht die Verwendung von `CType`.</span><span class="sxs-lookup"><span data-stu-id="f8a39-158">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="f8a39-159">Zusammengesetzte Typen</span><span class="sxs-lookup"><span data-stu-id="f8a39-159">Composite Types</span></span>

<span data-ttu-id="f8a39-160">Sie können verwenden `CType` , um Werte in zusammengesetzte Datentypen sowie in elementare Typen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f8a39-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="f8a39-161">Sie können es auch verwenden, um eine Objektklasse in den Typ einer ihrer Schnittstellen umzuwandeln, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8a39-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="f8a39-162">Array Typen</span><span class="sxs-lookup"><span data-stu-id="f8a39-162">Array Types</span></span>

<span data-ttu-id="f8a39-163">`CType`kann auch Array Datentypen konvertieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8a39-163">`CType` can also convert array data types, as in the following example.</span></span>

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

<span data-ttu-id="f8a39-164">Weitere Informationen und ein Beispiel finden Sie unter [Array Konvertierungen](array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="f8a39-164">For more information and an example, see [Array Conversions](array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="f8a39-165">Typen, die CType definieren</span><span class="sxs-lookup"><span data-stu-id="f8a39-165">Types Defining CType</span></span>

<span data-ttu-id="f8a39-166">Sie können `CType` für eine von Ihnen definierte Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="f8a39-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="f8a39-167">Dies ermöglicht es Ihnen, Werte in den und aus dem Typ der Klasse oder Struktur zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f8a39-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="f8a39-168">Weitere Informationen und ein Beispiel finden Sie unter Gewusst [wie: Definieren eines Konvertierungs Operators](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f8a39-168">For more information and an example, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f8a39-169">Die mit einem Konvertierungs Schlüsselwort verwendeten Werte müssen für den Ziel Datentyp gültig sein, oder es tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="f8a39-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="f8a39-170">Wenn Sie z. b. versuchen, eine `Long` in eine zu konvertieren `Integer` , muss der Wert von `Long` innerhalb des gültigen Bereichs für den- `Integer` Datentyp liegen.</span><span class="sxs-lookup"><span data-stu-id="f8a39-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="f8a39-171">`CType`Die Angabe von für die Konvertierung von einem Klassentyp in einen anderen schlägt zur Laufzeit fehl, wenn der Quelltyp nicht vom Zieltyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f8a39-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="f8a39-172">Bei einem solchen Fehler wird eine <xref:System.InvalidCastException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f8a39-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="f8a39-173">Wenn einer der Typen jedoch eine Struktur oder Klasse ist, die Sie definiert haben, und wenn Sie `CType` für diese Struktur oder Klasse definiert haben, kann eine Konvertierung erfolgreich durchgeführt werden, wenn Sie die Anforderungen Ihres erfüllt `CType` .</span><span class="sxs-lookup"><span data-stu-id="f8a39-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="f8a39-174">Weitere Informationen finden [Sie unter Gewusst wie: Definieren eines Konvertierungs Operators](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f8a39-174">See [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="f8a39-175">Das Ausführen einer expliziten Konvertierung wird auch *als Umwandlung* eines Ausdrucks in einen bestimmten Datentyp oder eine bestimmte Objektklasse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f8a39-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a39-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8a39-176">See also</span></span>

- [<span data-ttu-id="f8a39-177">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8a39-177">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="f8a39-178">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="f8a39-178">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="f8a39-179">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8a39-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="f8a39-180">Strukturen</span><span class="sxs-lookup"><span data-stu-id="f8a39-180">Structures</span></span>](structures.md)
- [<span data-ttu-id="f8a39-181">Datentypen</span><span class="sxs-lookup"><span data-stu-id="f8a39-181">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="f8a39-182">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="f8a39-182">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f8a39-183">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="f8a39-183">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
