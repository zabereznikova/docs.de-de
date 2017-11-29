---
title: "Funktionen für die Typkonvertierung (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 117cd4ce038a533715bbc86558545f0f223dd149
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="c00a5-102">Funktionen für die Typkonvertierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c00a5-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="c00a5-103">Diese Funktionen sind Inline kompiliert, was bedeutet, dass der Konvertierungscode Bestandteil des Codes ist die Auswertung des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="c00a5-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="c00a5-104">Manchmal ist kein Aufruf einer Prozedur zum Durchführen der Konvertierung zur Verbesserung, die Leistung beiträgt.</span><span class="sxs-lookup"><span data-stu-id="c00a5-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="c00a5-105">Jede Funktion wandelt einen Ausdruck in einen bestimmten Datentyp.</span><span class="sxs-lookup"><span data-stu-id="c00a5-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00a5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c00a5-106">Syntax</span></span>  
  
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
  
## <a name="part"></a><span data-ttu-id="c00a5-107">Segment</span><span class="sxs-lookup"><span data-stu-id="c00a5-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="c00a5-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c00a5-108">Required.</span></span> <span data-ttu-id="c00a5-109">Jeder Ausdruck mit dem Quelldatentyp.</span><span class="sxs-lookup"><span data-stu-id="c00a5-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="c00a5-110">Datentyp des Rückgabewerts</span><span class="sxs-lookup"><span data-stu-id="c00a5-110">Return Value Data Type</span></span>  
 <span data-ttu-id="c00a5-111">Der Funktionsname bestimmt den Datentyp des Werts, den sie zurückgibt, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c00a5-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="c00a5-112">Funktionsname</span><span class="sxs-lookup"><span data-stu-id="c00a5-112">Function name</span></span>|<span data-ttu-id="c00a5-113">Rückgabedatentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-113">Return data type</span></span>|<span data-ttu-id="c00a5-114">Der Bereich für `expression` Argument</span><span class="sxs-lookup"><span data-stu-id="c00a5-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="c00a5-115">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="c00a5-116">Jeder gültige `Char` oder `String` oder numerische Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c00a5-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="c00a5-117">Byte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="c00a5-118">0 bis 255 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-118">0 through 255 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CChar`|[<span data-ttu-id="c00a5-119">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-119">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="c00a5-120">Jeder gültige `Char` oder `String` Ausdruck; nur die ersten Zeichen des eine `String` konvertiert; Wert kann zwischen 0 und 65535 (ohne Vorzeichen) liegen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-120">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="c00a5-121">Date-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-121">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="c00a5-122">Jede gültige Darstellung einer Datums- und Uhrzeitangabe.</span><span class="sxs-lookup"><span data-stu-id="c00a5-122">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="c00a5-123">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-123">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="c00a5-124">-1.79769313486231570E + 308 bis - 4.94065645841246544E-324 für negative Werte; 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="c00a5-124">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="c00a5-125">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-125">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="c00a5-126">+/-Wert 79,228,162,514,264,337,593,543,950,335 für Skalierung von 0 (null) Zahlen, also ohne Dezimalstellen an.</span><span class="sxs-lookup"><span data-stu-id="c00a5-126">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="c00a5-127">Für Zahlen mit 28 Dezimalstellen wird der Bereich +/-7,9228162514264337593543950335 ist.</span><span class="sxs-lookup"><span data-stu-id="c00a5-127">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="c00a5-128">Die kleinstmögliche Zahl ungleich 0 (null) ist 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="c00a5-128">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="c00a5-129">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="c00a5-130">2.147.483.648 bis 2.147.483.647; werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-130">-2,147,483,648 through 2,147,483,647; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CLng`|[<span data-ttu-id="c00a5-131">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-131">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="c00a5-132">-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807; werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-132">-9,223,372,036,854,775,808 through 9,223,372,036,854,775,807; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CObj`|[<span data-ttu-id="c00a5-133">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-133">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="c00a5-134">Jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c00a5-134">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="c00a5-135">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-135">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="c00a5-136">-128 bis 127; werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-136">-128 through 127; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CShort`|[<span data-ttu-id="c00a5-137">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-137">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="c00a5-138">32.768 bis 32.767; werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-138">-32,768 through 32,767; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CSng`|[<span data-ttu-id="c00a5-139">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-139">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="c00a5-140">-3, 402823e + 38 bis - 1.401298E-45 für negative Werte; 1.401298E-45 bis 3, 402823e + 38 für positive Werte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="c00a5-140">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="c00a5-141">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="c00a5-142">Gibt für `CStr` richten sich nach der `expression` Argument.</span><span class="sxs-lookup"><span data-stu-id="c00a5-142">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="c00a5-143">Finden Sie unter [Rückgabewerte für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="c00a5-143">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="c00a5-144">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-144">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="c00a5-145">0 bis 4.294.967.295 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-145">0 through 4,294,967,295 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CULng`|[<span data-ttu-id="c00a5-146">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-146">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="c00a5-147">0 bis 18.446.744.073.709.551.615 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-147">0 through 18,446,744,073,709,551,615 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CUShort`|[<span data-ttu-id="c00a5-148">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c00a5-148">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="c00a5-149">0 bis 65.535 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c00a5-149">0 through 65,535 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
  
 <span data-ttu-id="c00a5-150"><sup>1</sup> Bruchteile unterliegen eine besondere Art von Rundung aufgerufen werden können *Banker rounding*.</span><span class="sxs-lookup"><span data-stu-id="c00a5-150"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="c00a5-151">Weitere Informationen finden Sie unter "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="c00a5-151">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c00a5-152">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c00a5-152">Remarks</span></span>  
 <span data-ttu-id="c00a5-153">In der Regel sollten Sie z. B. die Typkonvertierungsfunktionen von Visual Basic .NET Framework-Methoden verwenden `ToString()`, entweder auf die <xref:System.Convert> Klasse oder eine Struktur vom Typ einzeln oder -Klasse.</span><span class="sxs-lookup"><span data-stu-id="c00a5-153">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="c00a5-154">Visual Basic-Funktionen sind für eine optimale Interaktion mit Visual Basic-Code vorgesehen, und diese bilden auch des Quellcodes kürzer und leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-154">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="c00a5-155">Darüber hinaus die .NET Framework-Konvertierungsmethoden nicht immer erzeugen die gleichen Ergebnisse wie die Visual Basic-Funktionen, z. B. beim Konvertieren von `Boolean` auf `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-155">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="c00a5-156">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="c00a5-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c00a5-157">Verhalten</span><span class="sxs-lookup"><span data-stu-id="c00a5-157">Behavior</span></span>  
  
-   <span data-ttu-id="c00a5-158">**Umwandlung.**</span><span class="sxs-lookup"><span data-stu-id="c00a5-158">**Coercion.**</span></span> <span data-ttu-id="c00a5-159">Die Datentypkonvertierungsfunktionen können Sie im Allgemeinen das Ergebnis eines Vorgangs an einen bestimmten Datentyp anstelle des Standarddatentyps umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c00a5-159">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="c00a5-160">Verwenden Sie z. B. `CDec` gezwungen dezimale arithmetische Operationen in Fällen, in denen mit einfacher Genauigkeit, mit doppelter Genauigkeit oder Ganzzahlarithmetik würde normalerweise stattfinden.</span><span class="sxs-lookup"><span data-stu-id="c00a5-160">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="c00a5-161">**Fehlgeschlagene Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="c00a5-161">**Failed Conversions.**</span></span> <span data-ttu-id="c00a5-162">Wenn die `expression` liegt außerhalb des Bereichs des Datentyps auf das konvertiert werden, werden an die Funktion übergebene ein <xref:System.OverflowException> auftritt.</span><span class="sxs-lookup"><span data-stu-id="c00a5-162">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="c00a5-163">**Bruchteile.**</span><span class="sxs-lookup"><span data-stu-id="c00a5-163">**Fractional Parts.**</span></span> <span data-ttu-id="c00a5-164">Wenn Sie einen nicht ganzzahligen Wert in eine ganze Zahl konvertieren Typkonvertierungsfunktionen, die ganze Zahl (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, und `CUShort`) entfernen Sie die Sekundenbruchteile Teil und den Wert auf die nächste Ganzzahl gerundet.</span><span class="sxs-lookup"><span data-stu-id="c00a5-164">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="c00a5-165">Wenn der Bruchteil exakt 0,5 die Konvertierungsfunktionen ganze Zahl gerundet wird, damit die nächste gerade ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="c00a5-165">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="c00a5-166">Rundet z. B. 0,5 auf 0 (null) und 1,5 und 2.5 auf 2 gerundet.</span><span class="sxs-lookup"><span data-stu-id="c00a5-166">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="c00a5-167">Dies wird manchmal als bezeichnet *Banker rounding*, und der Zweck eines Bias zu kompensieren, die sich ansammeln könnten, wenn Sie viele diese Zahlen zusammenführen ist.</span><span class="sxs-lookup"><span data-stu-id="c00a5-167">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="c00a5-168">`CInt`und `CLng` unterscheiden sich von der <xref:Microsoft.VisualBasic.Conversion.Int%2A> und <xref:Microsoft.VisualBasic.Conversion.Fix%2A> -Funktionen, die den Bruchteil einer Zahl zu runden, sondern abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="c00a5-168">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="c00a5-169">Darüber hinaus `Fix` und `Int` wie Sie übergeben immer den Wert des gleichen Datentyps zurück.</span><span class="sxs-lookup"><span data-stu-id="c00a5-169">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="c00a5-170">**Datum/Uhrzeit-Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="c00a5-170">**Date/Time Conversions.**</span></span> <span data-ttu-id="c00a5-171">Verwenden der <xref:Microsoft.VisualBasic.Information.IsDate%2A> Funktion, um zu bestimmen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c00a5-171">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="c00a5-172">`CDate`erkennt Datumsliterale und Zeitliterale, aber keine numerischen Werte.</span><span class="sxs-lookup"><span data-stu-id="c00a5-172">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="c00a5-173">Konvertieren Sie eine Visual Basic 6.0 `Date` -Wert in einen `Date` Wert in Visual Basic 2005 oder höher können Sie die <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="c00a5-173">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="c00a5-174">**Neutrale Datum/Uhrzeit-Werte.**</span><span class="sxs-lookup"><span data-stu-id="c00a5-174">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="c00a5-175">Die [Datumsdatentyp](../../../visual-basic/language-reference/data-types/date-data-type.md) enthält immer die Datums-und Uhrzeitinformationen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-175">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="c00a5-176">Zwecken Typumwandlung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) für die Zeit ein neutrale Wert sein.</span><span class="sxs-lookup"><span data-stu-id="c00a5-176">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="c00a5-177">Konvertieren einer `Date` Wert in eine Zeichenfolge `CStr` neutralen Werte nicht in der Ergebniszeichenfolge enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c00a5-177">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="c00a5-178">Angenommen, Sie konvertieren `#January 1, 0001 9:30:00#` in eine Zeichenfolge das Ergebnis "9:30:00 AM"; die Datumsinformationen unterdrückt wird.</span><span class="sxs-lookup"><span data-stu-id="c00a5-178">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="c00a5-179">Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und können mit Funktionen wie z. B. wiederhergestellt werden <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Funktion.</span><span class="sxs-lookup"><span data-stu-id="c00a5-179">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="c00a5-180">**Berücksichtigung der Kultur.**</span><span class="sxs-lookup"><span data-stu-id="c00a5-180">**Culture Sensitivity.**</span></span> <span data-ttu-id="c00a5-181">Typkonvertierungsfunktionen, die im Zusammenhang mit Zeichenfolgen führen Konvertierungen, die auf Grundlage der aktuellen kultureinstellungen für die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="c00a5-181">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="c00a5-182">Beispielsweise `CDate` erkennt Datumsformate gemäß dem Gebietsschema Ihres Systems.</span><span class="sxs-lookup"><span data-stu-id="c00a5-182">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="c00a5-183">Sie müssen den Tag, Monat und Jahr in der richtigen Reihenfolge für Ihr Gebietsschema angeben, oder das Datum möglicherweise nicht ordnungsgemäß interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="c00a5-183">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="c00a5-184">Ein langes Datumsformat wird nicht erkannt, wenn sie eine Day of Week-Zeichenfolge, z. B. "Mittwoch" enthält.</span><span class="sxs-lookup"><span data-stu-id="c00a5-184">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="c00a5-185">Wenn Sie in oder aus einer Zeichenfolgendarstellung eines Werts in einem anderen Format als dem vom Gebietsschema angegeben konvertiert werden müssen, können nicht Sie die Visual Basic-Typkonvertierungsfunktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c00a5-185">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="c00a5-186">Verwenden Sie hierzu die `ToString(IFormatProvider)` und `Parse(String, IFormatProvider)` Methoden vom Typ des Werts.</span><span class="sxs-lookup"><span data-stu-id="c00a5-186">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="c00a5-187">Verwenden Sie z. B. <xref:System.Double.Parse%2A?displayProperty=nameWithType> beim Konvertieren einer Zeichenfolge zu einer `Double`, und verwenden Sie <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c00a5-187">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="c00a5-188">CType Function</span><span class="sxs-lookup"><span data-stu-id="c00a5-188">CType Function</span></span>  
 <span data-ttu-id="c00a5-189">Die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) nimmt ein zweites Argument `typename`, und wandelt `expression` auf `typename`, wobei `typename` kann-Datentyp, Struktur, Klasse oder Schnittstelle, eine gültige Konvertierung vorhanden, sein.</span><span class="sxs-lookup"><span data-stu-id="c00a5-189">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="c00a5-190">Einen Vergleich der `CType` mit anderen Schlüsselwörter für die typkonvertierung, finden Sie unter [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c00a5-190">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="c00a5-191">CBool-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-191">CBool Example</span></span>  
 <span data-ttu-id="c00a5-192">Im folgenden Beispiel wird die `CBool` Funktion, um Ausdrücke, die zu konvertierende `Boolean` Werte.</span><span class="sxs-lookup"><span data-stu-id="c00a5-192">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="c00a5-193">Wenn ein Ausdruck einen Wert ungleich null ergibt `CBool` gibt `True`ist, andernfalls gibt `False`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-193">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="c00a5-194">CByte-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-194">CByte Example</span></span>  
 <span data-ttu-id="c00a5-195">Im folgenden Beispiel wird die `CByte` Funktion, um einen Ausdruck zum Konvertieren einer `Byte`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-195">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="c00a5-196">CChar-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-196">CChar Example</span></span>  
 <span data-ttu-id="c00a5-197">Im folgenden Beispiel wird die `CChar` Funktion konvertiert das erste Zeichen einer `String` Ausdruck, der eine `Char` Typ.</span><span class="sxs-lookup"><span data-stu-id="c00a5-197">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="c00a5-198">Das Eingabeargument für `CChar` muss der Datentyp `Char` oder `String`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-198">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="c00a5-199">Sie können keine `CChar` , eine Zahl in ein Zeichen zu konvertieren, da `CChar` kann keine akzeptieren einen numerischen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-199">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="c00a5-200">Im folgenden Beispiel wird eine Zahl, die einen Codepunkt (Zeichencode) abgerufen und in das entsprechende Zeichen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c00a5-200">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="c00a5-201">Er verwendet die <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> -Funktion abrufen die Zeichenfolge aus Ziffern, `CInt` zum Konvertieren der Zeichenfolge in den Typ `Integer`, und `ChrW` zu konvertieren `Char`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-201">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="c00a5-202">CDate-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-202">CDate Example</span></span>  
 <span data-ttu-id="c00a5-203">Im folgenden Beispiel wird die `CDate` Funktion zum Konvertieren von Zeichenfolgen in `Date` Werte.</span><span class="sxs-lookup"><span data-stu-id="c00a5-203">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="c00a5-204">Im Allgemeinen wird ein Hardcodieren Datumsangaben und Uhrzeiten als Zeichenfolgen (wie im folgenden Beispiel gezeigt) nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-204">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="c00a5-205">Verwenden von Datums- und Zeitliterale, z. B. #Feb 12, &#1969; und # 4:45:23 Uhr # stattdessen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-205">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="c00a5-206">CDbl-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-206">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="c00a5-207">CDec-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-207">CDec Example</span></span>  
 <span data-ttu-id="c00a5-208">Im folgenden Beispiel wird die `CDec` Funktion, um einen numerischen Wert konvertieren `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-208">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="c00a5-209">CInt-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-209">CInt Example</span></span>  
 <span data-ttu-id="c00a5-210">Im folgenden Beispiel wird die `CInt` Funktion, um einen Wert zu konvertieren `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-210">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a><span data-ttu-id="c00a5-211">CLng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-211">CLng Example</span></span>  
 <span data-ttu-id="c00a5-212">Im folgenden Beispiel wird die `CLng` Funktion, um Werte zu konvertieren `Long`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-212">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="c00a5-213">CObj-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-213">CObj Example</span></span>  
 <span data-ttu-id="c00a5-214">Im folgenden Beispiel wird die `CObj` Funktion, um einen numerischen Wert konvertieren `Object`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-214">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="c00a5-215">Die `Object` Variable selbst enthält nur einen 4-Byte-Zeiger, die auf verweist die `Double` Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c00a5-215">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="c00a5-216">CSByte-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-216">CSByte Example</span></span>  
 <span data-ttu-id="c00a5-217">Im folgenden Beispiel wird die `CSByte` Funktion, um einen numerischen Wert konvertieren `SByte`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-217">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="c00a5-218">Beispiel für CShort</span><span class="sxs-lookup"><span data-stu-id="c00a5-218">CShort Example</span></span>  
 <span data-ttu-id="c00a5-219">Im folgenden Beispiel wird die `CShort` Funktion, um einen numerischen Wert konvertieren `Short`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-219">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="c00a5-220">CSng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-220">CSng Example</span></span>  
 <span data-ttu-id="c00a5-221">Im folgenden Beispiel wird die `CSng` Funktion, um Werte zu konvertieren `Single`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-221">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="c00a5-222">CStr-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-222">CStr Example</span></span>  
 <span data-ttu-id="c00a5-223">Im folgenden Beispiel wird die `CStr` Funktion, um einen numerischen Wert konvertieren `String`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-223">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="c00a5-224">Im folgenden Beispiel wird die `CStr` Funktion konvertiert `Date` Werte `String` Werte.</span><span class="sxs-lookup"><span data-stu-id="c00a5-224">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="c00a5-225">`CStr`Rendert immer eine `Date` Wert in der standardmäßigen Kurzformat für das aktuelle Gebietsschema, z. B. "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="c00a5-225">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="c00a5-226">Allerdings `CStr` unterdrückt die *neutralen Werte* von 1/1/0001 für das Datum und die 00:00:00 für die Zeit.</span><span class="sxs-lookup"><span data-stu-id="c00a5-226">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="c00a5-227">Weitere Informationen über die Rückgabewerte `CStr`, finden Sie unter [Rückgabewerte für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="c00a5-227">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="c00a5-228">CUInt-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-228">CUInt Example</span></span>  
 <span data-ttu-id="c00a5-229">Im folgenden Beispiel wird die `CUInt` Funktion, um einen numerischen Wert konvertieren `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-229">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="c00a5-230">CULng-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-230">CULng Example</span></span>  
 <span data-ttu-id="c00a5-231">Im folgenden Beispiel wird die `CULng` Funktion, um einen numerischen Wert konvertieren `ULong`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-231">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="c00a5-232">CUShort-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00a5-232">CUShort Example</span></span>  
 <span data-ttu-id="c00a5-233">Im folgenden Beispiel wird die `CUShort` Funktion, um einen numerischen Wert konvertieren `UShort`.</span><span class="sxs-lookup"><span data-stu-id="c00a5-233">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c00a5-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c00a5-234">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="c00a5-235">Konvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c00a5-235">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="c00a5-236">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c00a5-236">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
