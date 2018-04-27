---
title: Implizite und explizite Konvertierungen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9827cecce0a15d37d2ffe3ccf691404149b156fb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="18914-102">Implizite und explizite Konvertierungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18914-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="18914-103">Ein *implizite Konvertierung* erfordert keine spezielle Syntax im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="18914-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="18914-104">Im folgenden Beispiel Visual Basic implizit konvertiert den Wert der `k` in einen Gleitkommawert mit einfacher Genauigkeit-Wert vor der Zuweisung zu `q`.</span><span class="sxs-lookup"><span data-stu-id="18914-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="18914-105">Ein *explizite Konvertierung* einen Typkonvertierungsschlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="18914-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="18914-106">Visual Basic bietet mehrere solcher Schlüsselwörter, die einen Ausdruck in Klammern einschließen, um den gewünschten Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="18914-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="18914-107">Diese Schlüsselwörter Verhalten sich wie Funktionen, aber damit Ausführung etwas schneller als bei einem Funktionsaufruf ist, generiert der Compiler den Code Inline.</span><span class="sxs-lookup"><span data-stu-id="18914-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="18914-108">In der folgenden Erweiterung des vorhergehenden Beispiels die `CInt` Schlüsselwort konvertiert den Wert der `q` wieder in eine ganze Zahl vor der Zuweisung zu `k`.</span><span class="sxs-lookup"><span data-stu-id="18914-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="18914-109">Konvertierungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="18914-109">Conversion Keywords</span></span>  
 <span data-ttu-id="18914-110">Die folgende Tabelle zeigt die verfügbaren Konvertierungsschlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="18914-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="18914-111">Typkonvertierungsschlüsselwort</span><span class="sxs-lookup"><span data-stu-id="18914-111">Type conversion keyword</span></span>|<span data-ttu-id="18914-112">Konvertiert einen Ausdruck in den Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-112">Converts an expression to data type</span></span>|<span data-ttu-id="18914-113">Zulässige Datentypen des Ausdrucks, der konvertiert werden</span><span class="sxs-lookup"><span data-stu-id="18914-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="18914-114">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="18914-115">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="18914-116">Byte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="18914-117">Alle numerischen Typen (einschließlich `SByte` und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="18914-118">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="18914-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="18914-120">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="18914-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="18914-122">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="18914-123">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="18914-124">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="18914-125">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="18914-126">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="18914-127">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="18914-128">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="18914-129">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="18914-130">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="18914-131">Beliebiger Typ</span><span class="sxs-lookup"><span data-stu-id="18914-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="18914-132">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="18914-133">Alle numerischen Typen (einschließlich `Byte` und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="18914-134">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="18914-135">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="18914-136">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="18914-137">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="18914-138">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="18914-139">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `Char`, `Char` Array `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="18914-140">Nach dem Komma angegeben Typ (`,`)</span><span class="sxs-lookup"><span data-stu-id="18914-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="18914-141">Beim Konvertieren in ein *elementaren Datentyp* (einschließlich ein Array von ein elementarer Typ), die gleiche Typen für das entsprechende Konvertierungsschlüsselwort zulässig sind</span><span class="sxs-lookup"><span data-stu-id="18914-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="18914-142">Beim Konvertieren in eine *zusammengesetzten Datentyp*, er implementiert, Schnittstellen und Klassen, die von der geerbt</span><span class="sxs-lookup"><span data-stu-id="18914-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="18914-143">Wenn eine Konvertierung in eine Klasse oder Struktur, auf denen Sie überladene haben `CType`, diese Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="18914-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="18914-144">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="18914-145">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="18914-146">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="18914-147">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="18914-148">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="18914-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="18914-149">Alle numerischen Typen (einschließlich `Byte`, `SByte`, und Enumerationstypen), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="18914-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="18914-150">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="18914-150">The CType Function</span></span>  
 <span data-ttu-id="18914-151">Die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) arbeitet mit zwei Argumente.</span><span class="sxs-lookup"><span data-stu-id="18914-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="18914-152">Der erste ist der Ausdruck konvertiert werden, und das zweite ist das Ziel Daten oder die Objektklasse.</span><span class="sxs-lookup"><span data-stu-id="18914-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="18914-153">Beachten Sie, dass das erste Argument einen Ausdruck, der nicht für einen Typ sein muss.</span><span class="sxs-lookup"><span data-stu-id="18914-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="18914-154">`CType` ist ein *Inlinefunktion*, d. h. den kompilierten Code ist die Konvertierung, die häufigsten aufrufen, ohne eine Funktion generieren.</span><span class="sxs-lookup"><span data-stu-id="18914-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="18914-155">Dies verbessert die Leistung.</span><span class="sxs-lookup"><span data-stu-id="18914-155">This improves performance.</span></span>  
  
 <span data-ttu-id="18914-156">Einen Vergleich der `CType` mit anderen Schlüsselwörter für die typkonvertierung, finden Sie unter [DirectCast-Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="18914-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="18914-157">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="18914-157">Elementary Types</span></span>  
 <span data-ttu-id="18914-158">Das folgende Beispiel veranschaulicht die Verwendung von `CType`.</span><span class="sxs-lookup"><span data-stu-id="18914-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="18914-159">Zusammengesetzte Typen</span><span class="sxs-lookup"><span data-stu-id="18914-159">Composite Types</span></span>  
 <span data-ttu-id="18914-160">Sie können `CType` Werte in zusammengesetzten Datentypen als auch in elementare Typen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="18914-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="18914-161">Sie können es verwenden, um zu erzwingende eine Objektklasse in den Typ einer der Schnittstellen, wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="18914-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="18914-162">Arraytypen</span><span class="sxs-lookup"><span data-stu-id="18914-162">Array Types</span></span>  
 <span data-ttu-id="18914-163">`CType` Array-Datentypen, wie im folgenden Beispiel können auch konvertieren.</span><span class="sxs-lookup"><span data-stu-id="18914-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 <span data-ttu-id="18914-164">Weitere Informationen und ein Beispiel finden Sie unter [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="18914-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="18914-165">Typen, die CType definieren</span><span class="sxs-lookup"><span data-stu-id="18914-165">Types Defining CType</span></span>  
 <span data-ttu-id="18914-166">Sie können definieren, `CType` auf eine Klasse oder Struktur, die Sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="18914-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="18914-167">Dadurch können Sie zum Konvertieren von Werten in und aus dem Typ der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="18914-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="18914-168">Weitere Informationen und ein Beispiel finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="18914-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18914-169">Werte, die mit einem Konvertierungsschlüsselwort verwendet, müssen für den Zieldatentyp gültig sein, oder ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="18914-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="18914-170">Z. B., wenn Sie versuchen, konvertieren Sie eine `Long` auf eine `Integer`, den Wert des der `Long` muss innerhalb des gültigen Bereichs für die `Integer` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="18914-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="18914-171">Angeben von `CType` von einem Klassentyp nach einem anderen fehlschlägt, zur Laufzeit konvertiert werden, wenn der Quelltyp nicht aus dem Zieltyp abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="18914-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="18914-172">Solche Fehler löst eine <xref:System.InvalidCastException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="18914-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="18914-173">Jedoch, wenn einer der Typen wird eine Struktur oder Klasse, die Sie definiert haben, und Sie definiert haben `CType` für diese Struktur oder Klasse, eine Konvertierung kann erfolgreich ausgeführt werden, wenn es sich um die Anforderungen erfüllt die `CType`.</span><span class="sxs-lookup"><span data-stu-id="18914-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="18914-174">Finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="18914-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="18914-175">Eine explizite Konvertierung ist auch bekannt als *Umwandlung* ein Ausdruck auf eine angegebene Typ oder ein Objekt der Klasse.</span><span class="sxs-lookup"><span data-stu-id="18914-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18914-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18914-176">See Also</span></span>  
 [<span data-ttu-id="18914-177">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18914-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="18914-178">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="18914-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="18914-179">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18914-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="18914-180">Strukturen</span><span class="sxs-lookup"><span data-stu-id="18914-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="18914-181">Datentypen</span><span class="sxs-lookup"><span data-stu-id="18914-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="18914-182">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="18914-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="18914-183">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="18914-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
