---
title: Type Conversion Functions
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
ms.openlocfilehash: 3924da6ccbfea00668370f2fbcf4baf289be80db
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349971"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="f35e9-102">Funktionen für die Typkonvertierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f35e9-102">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="f35e9-103">Diese Funktionen werden Inline kompiliert. Dies bedeutet, dass der Konvertierungs Code Teil des Codes ist, der den Ausdruck auswertet.</span><span class="sxs-lookup"><span data-stu-id="f35e9-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="f35e9-104">Manchmal gibt es keinen aufzurufenden Vorgang zum Durchführen der Konvertierung, wodurch die Leistung verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="f35e9-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="f35e9-105">Jede Funktion wandelt einen Ausdruck in einen bestimmten Datentyp um.</span><span class="sxs-lookup"><span data-stu-id="f35e9-105">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="f35e9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f35e9-106">Syntax</span></span>

```vb
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

## <a name="part"></a><span data-ttu-id="f35e9-107">-Komponente</span><span class="sxs-lookup"><span data-stu-id="f35e9-107">Part</span></span>

`expression`  
<span data-ttu-id="f35e9-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="f35e9-108">Required.</span></span> <span data-ttu-id="f35e9-109">Ein beliebiger Ausdruck des Quell Datentyps.</span><span class="sxs-lookup"><span data-stu-id="f35e9-109">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="f35e9-110">Rückgabewert Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-110">Return Value Data Type</span></span>

<span data-ttu-id="f35e9-111">Der Funktionsname bestimmt den Datentyp des zurückgegebenen Werts, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f35e9-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="f35e9-112">Funktionsname</span><span class="sxs-lookup"><span data-stu-id="f35e9-112">Function name</span></span>|<span data-ttu-id="f35e9-113">Rückgabe Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-113">Return data type</span></span>|<span data-ttu-id="f35e9-114">Bereich für `expression` Argument</span><span class="sxs-lookup"><span data-stu-id="f35e9-114">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="f35e9-115">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="f35e9-116">Ein beliebiger gültiger `Char` oder `String` oder ein numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f35e9-116">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="f35e9-117">Byte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="f35e9-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) bis <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigniert); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-119">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Gleit Komma-zu-Byte-Konvertierung mit der `CByte`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-120">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-120">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="f35e9-121">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="f35e9-122">Jeder gültige `Char` oder `String` Ausdruck. nur das erste Zeichen einer `String` wird konvertiert. der Wert kann zwischen 0 und 65535 (ohne Vorzeichen) liegen.</span><span class="sxs-lookup"><span data-stu-id="f35e9-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="f35e9-123">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="f35e9-124">Eine beliebige gültige Darstellung eines Datums und einer Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="f35e9-124">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="f35e9-125">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="f35e9-126">-1.79769313486231570 e + 308 bis-4.94065645841246544 e-324 für negative Werte; 4.94065645841246544 e-324 bis 1.79769313486231570 e + 308 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="f35e9-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="f35e9-127">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="f35e9-128">+/-337 für Zahlen mit NULL Skalierung, d. h. Zahlen ohne Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="f35e9-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="f35e9-129">Für Zahlen mit 28 Dezimalstellen beträgt der Bereich +/-7.9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="f35e9-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="f35e9-130">Die kleinstmögliche Zahl ungleich 0 (null) ist 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="f35e9-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="f35e9-131">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="f35e9-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) bis <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="f35e9-133">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Konvertierung von Gleit Komma-zu ganzzahligen Daten mit der `CInt`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-134">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-134">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="f35e9-135">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="f35e9-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) bis <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-137">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Konvertierung von Gleit Komma-zu 64-Bit-ganzzahligen Daten mit der `CLng`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-138">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-138">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="f35e9-139">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="f35e9-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="f35e9-140">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f35e9-140">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="f35e9-141">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="f35e9-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) bis <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-143">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Konvertierung von Gleit Komma-und signierten Bytes mit der `CSByte`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-144">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-144">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="f35e9-145">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="f35e9-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) bis <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-147">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma-zu-16-Bit-ganzzahligen Konvertierungen mit der `CShort`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-148">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-148">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="f35e9-149">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="f35e9-150">-3.402823 e + 38 bis- -1 401298E e-45 für negative Werte; -1 401298E e-45 bis 3.402823 e + 38 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="f35e9-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="f35e9-151">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="f35e9-152">Gibt für `CStr` abhängig vom `expression`-Argument zurück.</span><span class="sxs-lookup"><span data-stu-id="f35e9-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="f35e9-153">Weitere Informationen finden Sie [unter Rückgabewerte für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="f35e9-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="f35e9-154">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="f35e9-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) bis <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (unsigniert); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-156">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma Zahlen in ganz Zahl Konvertierungen ohne Vorzeichen mit der `CUInt`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-157">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-157">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="f35e9-158">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="f35e9-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) bis <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (unsigniert); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-160">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma Zahlen in eine lange ganzzahlige Konvertierung ohne Vorzeichen mit der `CULng`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-161">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-161">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="f35e9-162">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="f35e9-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="f35e9-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) bis <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (unsigniert); Bruchteile werden gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f35e9-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="f35e9-164">Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma Zahlen in eine 16-Bit-Ganzzahl ohne Vorzeichen mit der `CUShort`-Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="f35e9-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="f35e9-165">Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="f35e9-165">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="f35e9-166"><sup>1</sup> Bruchteile können einer besonderen Art von Rundung unterliegen, die als " *Banker Rundung*" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f35e9-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="f35e9-167">Weitere Informationen finden Sie unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="f35e9-167">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="f35e9-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f35e9-168">Remarks</span></span>

<span data-ttu-id="f35e9-169">Als Regel sollten Sie die Visual Basic Typkonvertierungs Funktionen für die .NET Framework Methoden wie `ToString()`verwenden, entweder für die <xref:System.Convert> Klasse oder für eine einzelne Typstruktur oder-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f35e9-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="f35e9-170">Die Visual Basic Funktionen sind für eine optimale Interaktion mit Visual Basic Code konzipiert. Außerdem wird der Quellcode kürzer und leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="f35e9-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="f35e9-171">Außerdem erzielen die .NET Framework Konvertierungs Methoden nicht immer dieselben Ergebnisse wie die Visual Basic Funktionen, z. b. beim Konvertieren `Boolean` in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f35e9-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="f35e9-172">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f35e9-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="f35e9-173">Ab Visual Basic 15,8 wird die Leistung der Konvertierung von Gleit Komma-zu-ganzzahligen Daten optimiert, wenn Sie die <xref:System.Single> oder <xref:System.Double> Wert, der von den folgenden Methoden zurückgegeben wird, an eine der ganzzahligen Konvertierungs Funktionen (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`) übergeben:</span><span class="sxs-lookup"><span data-stu-id="f35e9-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

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

<span data-ttu-id="f35e9-174">Diese Optimierung ermöglicht, dass Code, der eine große Anzahl von ganzzahligen Konvertierungen durchführt, bis zu doppelt so schnell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f35e9-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="f35e9-175">Das folgende Beispiel veranschaulicht diese optimierten Konvertierungen von Gleit Komma-und ganzzahligen Zeichen folgen:</span><span class="sxs-lookup"><span data-stu-id="f35e9-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="f35e9-176">Verhalten</span><span class="sxs-lookup"><span data-stu-id="f35e9-176">Behavior</span></span>

- <span data-ttu-id="f35e9-177">**Nötigung.**</span><span class="sxs-lookup"><span data-stu-id="f35e9-177">**Coercion.**</span></span> <span data-ttu-id="f35e9-178">Im Allgemeinen können Sie die Datentyp-Konvertierungs Funktionen verwenden, um das Ergebnis eines Vorgangs in einen bestimmten Datentyp und nicht in den Standard Datentyp umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="f35e9-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="f35e9-179">Verwenden Sie z. b. `CDec`, um die Dezimal Arithmetik in Fällen zu erzwingen, in denen normalerweise eine einzelne Genauigkeit, eine doppelte Genauigkeit oder eine ganzzahlige Arithmetik stattfindet</span><span class="sxs-lookup"><span data-stu-id="f35e9-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="f35e9-180">**Fehlerhafte Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="f35e9-180">**Failed Conversions.**</span></span> <span data-ttu-id="f35e9-181">Wenn die an die Funktion über gegebene `expression` außerhalb des Bereichs des Datentyps liegt, in den Sie konvertiert werden soll, tritt ein <xref:System.OverflowException> auf.</span><span class="sxs-lookup"><span data-stu-id="f35e9-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="f35e9-182">**Bruchteile.**</span><span class="sxs-lookup"><span data-stu-id="f35e9-182">**Fractional Parts.**</span></span> <span data-ttu-id="f35e9-183">Wenn Sie einen nicht ganzzahligen Wert in einen ganzzahligen Typ konvertieren, entfernen die ganzzahligen Konvertierungs Funktionen (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`und `CUShort`) den Bruch Teil und runden den Wert auf die nächste ganze Zahl ab.</span><span class="sxs-lookup"><span data-stu-id="f35e9-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="f35e9-184">Wenn der Bruchteil der Dezimalstellen genau 0,5 ist, runden die ganzzahligen Konvertierungs Funktionen diese auf die nächste gerade ganze Zahl auf.</span><span class="sxs-lookup"><span data-stu-id="f35e9-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="f35e9-185">0,5 rundet beispielsweise auf 0 und 1,5 und 2,5 beide Runden auf 2.</span><span class="sxs-lookup"><span data-stu-id="f35e9-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="f35e9-186">Dies wird auch als *die Rundung von Bankiers*bezeichnet, und der Zweck besteht darin, einen Bias auszugleichen, der sich beim Hinzufügen von zahlreichen derartigen Zahlen ansammeln könnte.</span><span class="sxs-lookup"><span data-stu-id="f35e9-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="f35e9-187">`CInt` und `CLng` unterscheiden sich von den Funktionen <xref:Microsoft.VisualBasic.Conversion.Int%2A> und <xref:Microsoft.VisualBasic.Conversion.Fix%2A>, die den Bruchteil einer Zahl abschneiden, anstatt Sie zu runden.</span><span class="sxs-lookup"><span data-stu-id="f35e9-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="f35e9-188">Außerdem geben `Fix` und `Int` immer einen Wert desselben Datentyps zurück, den Sie übergeben.</span><span class="sxs-lookup"><span data-stu-id="f35e9-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="f35e9-189">**Datums-/Uhrzeit-Konvertierungen**</span><span class="sxs-lookup"><span data-stu-id="f35e9-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="f35e9-190">Verwenden Sie die <xref:Microsoft.VisualBasic.Information.IsDate%2A>-Funktion, um zu bestimmen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f35e9-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="f35e9-191">`CDate` erkennt Datums Literale und Zeit Literale, aber keine numerischen Werte.</span><span class="sxs-lookup"><span data-stu-id="f35e9-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="f35e9-192">Wenn Sie einen Visual Basic 6,0 `Date`-Wert in Visual Basic 2005 oder höhere Versionen in einen `Date` Wert konvertieren möchten, können Sie die <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="f35e9-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="f35e9-193">**Neutrale Datums-/Uhrzeitwerte.**</span><span class="sxs-lookup"><span data-stu-id="f35e9-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="f35e9-194">Der [Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md) enthält immer Datums-und Uhrzeit Informationen.</span><span class="sxs-lookup"><span data-stu-id="f35e9-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="f35e9-195">Für den Zweck der Typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1) als *neutralen Wert* für das Datum und 00:00:00 (Mitternacht) als neutralen Wert für die Zeit.</span><span class="sxs-lookup"><span data-stu-id="f35e9-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="f35e9-196">Wenn Sie einen `Date` Wert in eine Zeichenfolge konvertieren, enthält `CStr` keine neutralen Werte in die resultierende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f35e9-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="f35e9-197">Wenn Sie `#January 1, 0001 9:30:00#` z. b. in eine Zeichenfolge konvertieren, ist das Ergebnis "9:30:00 am"; die Datumsinformationen werden unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="f35e9-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="f35e9-198">Die Datumsinformationen sind jedoch weiterhin im ursprünglichen `Date` Wert vorhanden und können mit Funktionen wie <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Funktion wieder hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f35e9-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="f35e9-199">**Kultur Sensitivität.**</span><span class="sxs-lookup"><span data-stu-id="f35e9-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="f35e9-200">Die Typkonvertierungs Funktionen, die Zeichen folgen einschließen, führen Konvertierungen auf Grundlage der aktuellen Kultur Einstellungen für die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="f35e9-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="f35e9-201">`CDate` erkennt z. b. Datumsformate gemäß der Gebiets Schema Einstellung Ihres Systems.</span><span class="sxs-lookup"><span data-stu-id="f35e9-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="f35e9-202">Sie müssen den Tag, den Monat und das Jahr in der richtigen Reihenfolge für Ihr Gebiets Schema angeben, oder das Datum wird möglicherweise nicht richtig interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f35e9-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="f35e9-203">Ein langes Datumsformat wird nicht erkannt, wenn es eine Wochentag-Zeichenfolge, z. b. "Mittwoch", enthält.</span><span class="sxs-lookup"><span data-stu-id="f35e9-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="f35e9-204">Wenn Sie in eine oder aus einer Zeichen folgen Darstellung eines Werts in einem anderen Format als dem durch das Gebiets Schema angegebenen Format konvertieren müssen, können Sie die Visual Basic Typkonvertierungs Funktionen nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="f35e9-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="f35e9-205">Verwenden Sie hierzu die Methoden `ToString(IFormatProvider)` und `Parse(String, IFormatProvider)` dieses Werttyps.</span><span class="sxs-lookup"><span data-stu-id="f35e9-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="f35e9-206">Verwenden Sie z. b. <xref:System.Double.Parse%2A?displayProperty=nameWithType>, wenn Sie eine Zeichenfolge in einen `Double`und <xref:System.Double.ToString%2A?displayProperty=nameWithType> verwenden, wenn Sie einen Wert vom Typ `Double` in eine Zeichenfolge umwandelt.</span><span class="sxs-lookup"><span data-stu-id="f35e9-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="f35e9-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="f35e9-207">CType Function</span></span>

<span data-ttu-id="f35e9-208">Die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) nimmt ein zweites Argument, `typename`und wandelt `expression`, um `typename`, wobei `typename` jeder Datentyp, jede Struktur, Klasse oder Schnittstelle sein kann, auf die eine gültige Konvertierung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f35e9-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="f35e9-209">Einen Vergleich von `CType` mit den anderen Schlüsselwörtern für die Typkonvertierung finden Sie unter [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f35e9-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="f35e9-210">CBool-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-210">CBool Example</span></span>

<span data-ttu-id="f35e9-211">Im folgenden Beispiel wird die `CBool`-Funktion verwendet, um Ausdrücke in `Boolean` Werte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="f35e9-212">Wenn ein Ausdruck zu einem Wert ungleich 0 (null) ausgewertet wird, gibt `CBool` `True`zurück. Andernfalls wird `False`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f35e9-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="f35e9-213">CByte-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-213">CByte Example</span></span>

<span data-ttu-id="f35e9-214">Im folgenden Beispiel wird die `CByte`-Funktion verwendet, um einen Ausdruck in eine `Byte`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="f35e9-215">CChar-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-215">CChar Example</span></span>

<span data-ttu-id="f35e9-216">Im folgenden Beispiel wird die `CChar`-Funktion verwendet, um das erste Zeichen eines `String` Ausdrucks in einen `Char`-Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="f35e9-217">Das Eingabe Argument für `CChar` muss vom Datentyp `Char` oder `String`sein.</span><span class="sxs-lookup"><span data-stu-id="f35e9-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="f35e9-218">Sie können `CChar` nicht verwenden, um eine Zahl in ein Zeichen zu konvertieren, da `CChar` keinen numerischen Datentyp annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="f35e9-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="f35e9-219">Im folgenden Beispiel wird eine Zahl abgerufen, die einen Codepunkt darstellt (Zeichencode) und in das entsprechende Zeichen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f35e9-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="f35e9-220">Er verwendet die <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>-Funktion, um die Zeichenfolge zu erhalten, `CInt`, die Zeichenfolge in den Typ `Integer`zu konvertieren, und `ChrW`, um die Zahl in den Typ `Char`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="f35e9-221">CDate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-221">CDate Example</span></span>

<span data-ttu-id="f35e9-222">Im folgenden Beispiel wird die `CDate`-Funktion verwendet, um Zeichen folgen in `Date` Werte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="f35e9-223">Im Allgemeinen wird das hart codieren von Datums-und Uhrzeitangaben als Zeichen folgen (wie in diesem Beispiel gezeigt) nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f35e9-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="f35e9-224">Verwenden Sie stattdessen Datums Literale und Zeit Literale, wie z. b. #Feb 12, 1969 # und #4:45:23 pm #.</span><span class="sxs-lookup"><span data-stu-id="f35e9-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="f35e9-225">CDbl-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-225">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="f35e9-226">CDec-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-226">CDec Example</span></span>

<span data-ttu-id="f35e9-227">Im folgenden Beispiel wird die `CDec`-Funktion verwendet, um einen numerischen Wert in `Decimal`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="f35e9-228">CInt-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-228">CInt Example</span></span>

<span data-ttu-id="f35e9-229">Im folgenden Beispiel wird die `CInt`-Funktion verwendet, um einen-Wert in `Integer`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="f35e9-230">CLng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-230">CLng Example</span></span>

<span data-ttu-id="f35e9-231">Im folgenden Beispiel wird die `CLng`-Funktion verwendet, um Werte in `Long`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="f35e9-232">CObj-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-232">CObj Example</span></span>

<span data-ttu-id="f35e9-233">Im folgenden Beispiel wird die `CObj`-Funktion verwendet, um einen numerischen Wert in `Object`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="f35e9-234">Die `Object` Variable selbst enthält nur einen vier-Byte-Zeiger, der auf den zugewiesenen `Double` Wert zeigt.</span><span class="sxs-lookup"><span data-stu-id="f35e9-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="f35e9-235">CSByte-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-235">CSByte Example</span></span>

<span data-ttu-id="f35e9-236">Im folgenden Beispiel wird die `CSByte`-Funktion verwendet, um einen numerischen Wert in `SByte`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="f35e9-237">CShort-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-237">CShort Example</span></span>

<span data-ttu-id="f35e9-238">Im folgenden Beispiel wird die `CShort`-Funktion verwendet, um einen numerischen Wert in `Short`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="f35e9-239">CSng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-239">CSng Example</span></span>

<span data-ttu-id="f35e9-240">Im folgenden Beispiel wird die `CSng`-Funktion verwendet, um Werte in `Single`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="f35e9-241">CStr-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-241">CStr Example</span></span>

<span data-ttu-id="f35e9-242">Im folgenden Beispiel wird die `CStr`-Funktion verwendet, um einen numerischen Wert in `String`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="f35e9-243">Im folgenden Beispiel wird die `CStr`-Funktion verwendet, um `Date` Werte in `String` Werte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="f35e9-244">`CStr` rendert immer einen `Date`-Wert im Standard Kurzformat für das aktuelle Gebiets Schema, z. b. "6/15/2003 4:35:47 pm".</span><span class="sxs-lookup"><span data-stu-id="f35e9-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="f35e9-245">`CStr` unterdrückt jedoch die *neutralen Werte* von 1/1/0001 für das Datum und 00:00:00 für die Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="f35e9-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="f35e9-246">Weitere Details zu den Werten, die von `CStr`zurückgegeben werden, finden Sie unter [Rückgabewerte für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="f35e9-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="f35e9-247">CUInt-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-247">CUInt Example</span></span>

<span data-ttu-id="f35e9-248">Im folgenden Beispiel wird die `CUInt`-Funktion verwendet, um einen numerischen Wert in `UInteger`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="f35e9-249">CULng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-249">CULng Example</span></span>

<span data-ttu-id="f35e9-250">Im folgenden Beispiel wird die `CULng`-Funktion verwendet, um einen numerischen Wert in `ULong`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="f35e9-251">CUShort-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35e9-251">CUShort Example</span></span>

<span data-ttu-id="f35e9-252">Im folgenden Beispiel wird die `CUShort`-Funktion verwendet, um einen numerischen Wert in `UShort`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f35e9-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="f35e9-253">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f35e9-253">See also</span></span>

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
- [<span data-ttu-id="f35e9-254">Konvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="f35e9-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="f35e9-255">Typkonvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f35e9-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
