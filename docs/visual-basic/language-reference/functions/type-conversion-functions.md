---
title: Funktionen für die Typkonvertierung (Visual Basic)
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: ea7cc2c7f988617de67bf0ea46aeb3396acdf4b1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980619"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="c3c0d-102">Funktionen für die Typkonvertierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3c0d-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="c3c0d-103">Diese Funktionen sind kompilierte Inline, was bedeutet, dass der Konvertierungscode Teil des Codes ist die Auswertung des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="c3c0d-104">In manchen sind Situationen kein Aufruf an eine Prozedur zum Durchführen der Konvertierung wird die Leistung verbessert.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="c3c0d-105">Jede Funktion wandelt einen Ausdruck, der einen bestimmten Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c0d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3c0d-106">Syntax</span></span>  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a><span data-ttu-id="c3c0d-107">Segment</span><span class="sxs-lookup"><span data-stu-id="c3c0d-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="c3c0d-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-108">Required.</span></span> <span data-ttu-id="c3c0d-109">Ein Ausdruck des Typs der Daten.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="c3c0d-110">Datentyp des Rückgabewerts</span><span class="sxs-lookup"><span data-stu-id="c3c0d-110">Return Value Data Type</span></span>  
 <span data-ttu-id="c3c0d-111">Den Namen der Funktion bestimmt den Datentyp des Werts, den sie zurückgibt, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c3c0d-112">Funktionsname</span><span class="sxs-lookup"><span data-stu-id="c3c0d-112">Function name</span></span>|<span data-ttu-id="c3c0d-113">Rückgabedatentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-113">Return data type</span></span>|<span data-ttu-id="c3c0d-114">Der Bereich für `expression` Argument</span><span class="sxs-lookup"><span data-stu-id="c3c0d-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="c3c0d-115">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="c3c0d-116">Eine beliebige gültige `Char` oder `String` oder numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="c3c0d-117">Byte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="c3c0d-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) über <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-119">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in bytekonvertierung mit der `CByte` funktionieren, finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-120">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="c3c0d-121">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="c3c0d-122">Eine beliebige gültige `Char` oder `String` Ausdruck; nur die ersten Zeichen der ein `String` konvertiert wird; Wert kann 0 bis 65535 (ohne Vorzeichen) sein.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="c3c0d-123">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="c3c0d-124">Jede gültige Darstellung von Datum und Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="c3c0d-125">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="c3c0d-126">-1.79769313486231570E + 308 bis - 4.94065645841246544E-324 für negative Werte; 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="c3c0d-127">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="c3c0d-128">+ / – 79.228.162.514.264.337.593.543.950.335 für die Skalierung von 0 (null) Zahlen, also ohne Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="c3c0d-129">Ist der Bereich für Zahlen mit 28 Dezimalstellen + / – 7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="c3c0d-130">Die kleinste mögliche Zahl ungleich NULL ist – 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="c3c0d-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="c3c0d-131">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="c3c0d-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) bis <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="c3c0d-133">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in ganze Zahl Konvertierung mit dem `CInt` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-134">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="c3c0d-135">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="c3c0d-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) bis <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-137">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in 64-Bit-Ganzzahl-Konvertierung mit dem `CLng` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-138">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="c3c0d-139">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="c3c0d-140">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="c3c0d-141">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="c3c0d-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) über <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-143">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in Byte mit Vorzeichen Konvertierung mit dem `CSByte` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-144">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="c3c0d-145">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="c3c0d-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) bis <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-147">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in ganze 16-Bit-Konvertierung mit den `CShort` funktionieren, finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-148">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="c3c0d-149">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="c3c0d-150">-3, 402823e + 38 bis - 1.401298E-45 für negative Werte; 1.401298E-45 bis 3, 402823e + 38 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="c3c0d-151">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="c3c0d-152">Gibt für `CStr` richten sich nach der `expression` Argument.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="c3c0d-153">Finden Sie unter [Werte zurück, für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="c3c0d-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="c3c0d-154">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="c3c0d-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) über <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-156">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in ganze Zahl ohne Vorzeichen Konvertierung mit dem `CUInt` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-157">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="c3c0d-158">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="c3c0d-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) über <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18.446.744.073.709.551.615) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-160">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in unsigned long integer-Wert-Konvertierung mit dem `CULng` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-161">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="c3c0d-162">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c3c0d-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="c3c0d-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) über <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="c3c0d-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="c3c0d-164">Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkomma, um die Konvertierung von 16-Bit-Ganzzahl ohne Vorzeichen mit der `CUShort` funktionieren, finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="c3c0d-165">Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="c3c0d-166"><sup>1</sup> Nachkommastellen können eine besondere Art der Rundung aufgerufene unterliegen *Banker rounding*.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="c3c0d-167">Weitere Informationen finden Sie unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="c3c0d-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3c0d-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3c0d-168">Remarks</span></span>  
 <span data-ttu-id="c3c0d-169">Als Faustregel gilt, sollten Sie z. B. die Typkonvertierungsfunktionen von Visual Basic .NET Framework-Methoden verwenden `ToString()`, entweder auf die <xref:System.Convert> Klasse oder auf einem einzelnen Typstruktur oder Klasse.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="c3c0d-170">Visual Basic-Funktionen sind für eine optimale Interaktion mit Visual Basic-Code vorgesehen, und sie machen auch den Quellcode kürzer und leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="c3c0d-171">Darüber hinaus die .NET Framework-Konvertierungsmethoden immer erzeugen nicht die gleichen Ergebnisse wie Visual Basic-Funktionen, z. B. bei der Konvertierung `Boolean` zu `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="c3c0d-172">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c3c0d-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  


<span data-ttu-id="c3c0d-173">Ab Visual Basic-15.8, ist die Leistung der Konvertierung von Gleitkomma-point-in Ganzzahlwerte beim übergeben optimiert die <xref:System.Single> oder <xref:System.Double> mithilfe der folgenden Methoden auf einen der die Funktionen zurückgegebene Wert (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="c3c0d-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="c3c0d-174">Diese Optimierung können Code, der eine große Anzahl von Konvertierungen von ganzzahligen auf doppelt so schnell ausgeführt werden, um.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="c3c0d-175">Das folgende Beispiel veranschaulicht diese optimierte Gleitkomma-point-in Ganzzahlwerte Konvertierungen:</span><span class="sxs-lookup"><span data-stu-id="c3c0d-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="c3c0d-176">Verhalten</span><span class="sxs-lookup"><span data-stu-id="c3c0d-176">Behavior</span></span>  
  
-   <span data-ttu-id="c3c0d-177">**Umwandlung.**</span><span class="sxs-lookup"><span data-stu-id="c3c0d-177">**Coercion.**</span></span> <span data-ttu-id="c3c0d-178">Die Funktionen für die typkonvertierung Daten können Sie in der Regel das Ergebnis eines Vorgangs auf einen bestimmten Datentyp anstelle des Standarddatentyps umgewandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="c3c0d-179">Verwenden Sie z. B. `CDec` gezwungen dezimale arithmetische Operationen in Fällen, in denen mit einfacher Genauigkeit, mit doppelter Genauigkeit oder Ganzzahlarithmetik würde normalerweise stattfinden.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="c3c0d-180">**Fehlgeschlagene Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="c3c0d-180">**Failed Conversions.**</span></span> <span data-ttu-id="c3c0d-181">Wenn die `expression` liegt außerhalb des Bereichs des Datentyps auf den er konvertiert werden, werden an die Funktion übergeben eine <xref:System.OverflowException> auftritt.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="c3c0d-182">**Nachkommastellen.**</span><span class="sxs-lookup"><span data-stu-id="c3c0d-182">**Fractional Parts.**</span></span> <span data-ttu-id="c3c0d-183">Wenn Sie einen nicht ganzzahligen Wert in eine Ganzzahlkonstante konvertieren eingeben, die Funktionen (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, und `CUShort`) entfernen Sie die Sekundenbruchteile Teil, und den Wert, der die nächste ganze Zahl gerundet.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="c3c0d-184">Wenn der Bruchteil exakt 0,5, die Konvertierungsfunktionen ganze Zahl aufgerundet auf die nächste gerade ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="c3c0d-185">0 (null) und 1.5 und 2.5, die auf 2 gerundet wird z. B. 0,5 abgerundet.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="c3c0d-186">Dies wird mitunter bezeichnet *Banker rounding*, und die darin besteht, die für ein Bias zu kompensieren, die sich ansammeln könnten, wenn Sie viele derartige Zahlen zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="c3c0d-187">`CInt` und `CLng` unterscheiden sich von der <xref:Microsoft.VisualBasic.Conversion.Int%2A> und <xref:Microsoft.VisualBasic.Conversion.Fix%2A> -Funktionen, die den Bruchteil einer Zahl zu runden, sondern abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="c3c0d-188">Darüber hinaus `Fix` und `Int` wie Sie übergeben immer den Wert des gleichen Datentyps zurück.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="c3c0d-189">**Datum/Uhrzeit-Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="c3c0d-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="c3c0d-190">Verwenden der <xref:Microsoft.VisualBasic.Information.IsDate%2A> Funktion, um zu bestimmen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="c3c0d-191">`CDate` erkennt Datums- und Uhrzeitliterale aber keine numerischen Werte.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="c3c0d-192">Konvertieren Sie eine Visual Basic 6.0 `Date` -Werts in einen `Date` Wert in Visual Basic 2005 oder höher, können Sie die <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="c3c0d-193">**Neutral Datum/Uhrzeit-Werten.**</span><span class="sxs-lookup"><span data-stu-id="c3c0d-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="c3c0d-194">Die [Date-Datentyps](../../../visual-basic/language-reference/data-types/date-data-type.md) immer sowohl Datums-und Uhrzeitinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="c3c0d-195">Für Zwecke der typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) einen neutralen Wert für die Zeit sein.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="c3c0d-196">Wenn Sie konvertieren ein `Date` Wert in eine Zeichenfolge, `CStr` enthält keine neutralen Werte in der Ergebniszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="c3c0d-197">Wenn Sie konvertieren, z. B. `#January 1, 0001 9:30:00#` in eine Zeichenfolge, das Ergebnis "9:30:00 Uhr"; die Datumsinformationen unterdrückt wird.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="c3c0d-198">Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und kann mit Funktionen wiederhergestellt werden, z. B. <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Funktion.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="c3c0d-199">**Berücksichtigung der Kultur.**</span><span class="sxs-lookup"><span data-stu-id="c3c0d-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="c3c0d-200">Die Zeichenfolgen mit Funktionen für die typkonvertierung führen Konvertierungen, die basierend auf den Einstellungen der aktuellen Kultur für die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="c3c0d-201">Z. B. `CDate` erkennt Datums-und Uhrzeitformate gemäß der gebietsschemaeinstellung des Systems.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="c3c0d-202">Sie müssen den Tag, Monat und Jahr in der richtigen Reihenfolge für Ihr Gebietsschema angeben, oder das Datum möglicherweise nicht ordnungsgemäß interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="c3c0d-203">Ein langes Datumsformat wird nicht erkannt werden, wenn es sich um einen Tag der Woche-Zeichenfolge, z. B. "Wednesday" enthält.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="c3c0d-204">Wenn Sie in oder aus einer Zeichenfolgendarstellung eines Werts in einem anderen Format als dem vom Gebietsschema angegeben konvertiert werden müssen, können nicht Sie die Funktionen für die typkonvertierung Visual Basic verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="c3c0d-205">Verwenden Sie hierzu die `ToString(IFormatProvider)` und `Parse(String, IFormatProvider)` Methoden der Typ des Werts.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="c3c0d-206">Verwenden Sie z. B. <xref:System.Double.Parse%2A?displayProperty=nameWithType> beim Konvertieren einer Zeichenfolge zu einer `Double`, und verwenden Sie <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="c3c0d-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="c3c0d-207">CType Function</span></span>  
 <span data-ttu-id="c3c0d-208">Die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) nimmt ein zweites Argument, `typename`, und wandelt `expression` zu `typename`, wobei `typename` kann-Datentyp, Struktur, Klasse oder Schnittstelle, eine gültige Konvertierung vorhanden, sein.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="c3c0d-209">Einen Vergleich der `CType` mit anderen Schlüsselwörter für die typkonvertierung, finden Sie unter [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c3c0d-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="c3c0d-210">CBool-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-210">CBool Example</span></span>  
 <span data-ttu-id="c3c0d-211">Im folgenden Beispiel wird die `CBool` Funktion, um Ausdrücke für konvertiert `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="c3c0d-212">Wenn ein Ausdruck einen Wert ungleich null ergibt `CBool` gibt `True`ist, andernfalls gibt `False`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="c3c0d-213">CByte-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-213">CByte Example</span></span>  
 <span data-ttu-id="c3c0d-214">Im folgenden Beispiel wird die `CByte` Funktion, um einen Ausdruck zum Konvertieren einer `Byte`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a><span data-ttu-id="c3c0d-215">CChar-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-215">CChar Example</span></span>  
 <span data-ttu-id="c3c0d-216">Im folgenden Beispiel wird die `CChar` Funktion konvertiert das erste Zeichen einer `String` Ausdruck, der eine `Char` Typ.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 <span data-ttu-id="c3c0d-217">Das Eingabeargument für `CChar` muss der Datentyp `Char` oder `String`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="c3c0d-218">Sie können keine `CChar` , eine Zahl in ein Zeichen zu konvertieren, da `CChar` nicht akzeptieren einen numerischen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="c3c0d-219">Im folgenden Beispiel ruft eine Zahl, die einen Codepunkt (Zeichencode) und konvertiert ihn in das entsprechende Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="c3c0d-220">Er verwendet den <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> Funktion zum Abrufen der Zeichenfolge der Ziffern, `CInt` zum Konvertieren der Zeichenfolge in den Typ `Integer`, und `ChrW` um die Anzahl in den Typ zu konvertieren `Char`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a><span data-ttu-id="c3c0d-221">CDate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-221">CDate Example</span></span>  
 <span data-ttu-id="c3c0d-222">Im folgenden Beispiel wird die `CDate` Funktion zum Konvertieren von Zeichenfolgen, die `Date` Werte.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="c3c0d-223">Im Allgemeinen wird ein hartcodieren Datums- und Uhrzeitangaben als Zeichenfolgen (wie im folgenden Beispiel gezeigt) nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="c3c0d-224">Verwenden von Datums- und Uhrzeitliterale, z. B. #Feb 12, 1969 # und # 4:45:23 Uhr #. stattdessen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="c3c0d-225">CDbl-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a><span data-ttu-id="c3c0d-226">CDec-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-226">CDec Example</span></span>  
 <span data-ttu-id="c3c0d-227">Im folgenden Beispiel wird die `CDec` Funktion, um einen numerischen Wert konvertieren `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a><span data-ttu-id="c3c0d-228">CInt-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-228">CInt Example</span></span>  
 <span data-ttu-id="c3c0d-229">Im folgenden Beispiel wird die `CInt` Funktion zum Konvertieren eines Werts zu `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a><span data-ttu-id="c3c0d-230">CLng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-230">CLng Example</span></span>
 <span data-ttu-id="c3c0d-231">Im folgenden Beispiel wird die `CLng` Funktion zum Konvertieren `Long`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a><span data-ttu-id="c3c0d-232">"CObj"-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-232">CObj Example</span></span>  
 <span data-ttu-id="c3c0d-233">Im folgenden Beispiel wird die `CObj` Funktion, um einen numerischen Wert konvertieren `Object`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="c3c0d-234">Die `Object` Variable sich selbst enthält nur einen 4-Byte-Zeiger, die auf verweist die `Double` Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="c3c0d-235">CSByte-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-235">CSByte Example</span></span>  
 <span data-ttu-id="c3c0d-236">Im folgenden Beispiel wird die `CSByte` Funktion, um einen numerischen Wert konvertieren `SByte`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a><span data-ttu-id="c3c0d-237">Beispiel für CShort</span><span class="sxs-lookup"><span data-stu-id="c3c0d-237">CShort Example</span></span>  
 <span data-ttu-id="c3c0d-238">Im folgenden Beispiel wird die `CShort` Funktion, um einen numerischen Wert konvertieren `Short`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a><span data-ttu-id="c3c0d-239">CSng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-239">CSng Example</span></span>  
 <span data-ttu-id="c3c0d-240">Im folgenden Beispiel wird die `CSng` Funktion zum Konvertieren `Single`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a><span data-ttu-id="c3c0d-241">CStr-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-241">CStr Example</span></span>  
 <span data-ttu-id="c3c0d-242">Im folgenden Beispiel wird die `CStr` Funktion, um einen numerischen Wert konvertieren `String`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 <span data-ttu-id="c3c0d-243">Im folgenden Beispiel wird die `CStr` Funktion konvertiert `Date` Werte `String` Werte.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="c3c0d-244">`CStr` stellt immer eine `Date` Wert in der standardmäßigen Kurzformat für das aktuelle Gebietsschema, z. B. "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="c3c0d-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="c3c0d-245">Allerdings `CStr` unterdrückt die *neutralen Werte* von 1/1/0001 für das Datum und die 00:00:00, für die Zeit.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="c3c0d-246">Weitere Informationen zu der vom zurückgegebenen Werte `CStr`, finden Sie unter [Werte zurückgeben, für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="c3c0d-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="c3c0d-247">CUInt-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-247">CUInt Example</span></span>  
 <span data-ttu-id="c3c0d-248">Im folgenden Beispiel wird die `CUInt` Funktion, um einen numerischen Wert konvertieren `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a><span data-ttu-id="c3c0d-249">CULng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-249">CULng Example</span></span>  
 <span data-ttu-id="c3c0d-250">Im folgenden Beispiel wird die `CULng` Funktion, um einen numerischen Wert konvertieren `ULong`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a><span data-ttu-id="c3c0d-251">CUShort-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3c0d-251">CUShort Example</span></span>  
 <span data-ttu-id="c3c0d-252">Im folgenden Beispiel wird die `CUShort` Funktion, um einen numerischen Wert konvertieren `UShort`.</span><span class="sxs-lookup"><span data-stu-id="c3c0d-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="c3c0d-253">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3c0d-253">See also</span></span>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="c3c0d-254">Konvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c3c0d-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="c3c0d-255">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c3c0d-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
