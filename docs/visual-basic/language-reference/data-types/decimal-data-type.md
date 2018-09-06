---
title: Decimal-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: ffc1cd141ba624d2ce26e4b1c070431ff0ddd6fe
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43860323"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="7d020-102">Decimal-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d020-102">Decimal Data Type (Visual Basic)</span></span>
<span data-ttu-id="7d020-103">Speichert signierte 128-Bit (16-Byte)-Werte, die ganze Zahl (12-Byte) der 96-Bit-Zahlen mit einer Variablen Potenz von 10 skaliert darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d020-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="7d020-104">Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. Es reicht von 0 bis 28.</span><span class="sxs-lookup"><span data-stu-id="7d020-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="7d020-105">Mit einer Skala von 0 (keine Dezimalstellen) an, der der größte mögliche Wert ist + / – 79.228.162.514.264.337.593.543.950.335 (+/-7 .9228162514264337593543950335E + 28).</span><span class="sxs-lookup"><span data-stu-id="7d020-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="7d020-106">Der Höchstwert ist + / – 7,9228162514264337593543950335 mit 28 Dezimalstellen und der kleinste Wert ungleich NULL ist + / – 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="7d020-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d020-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d020-107">Remarks</span></span>  
 <span data-ttu-id="7d020-108">Die `Decimal` -Datentyp stellt die größte Anzahl von signifikanten Stellen für eine Reihe.</span><span class="sxs-lookup"><span data-stu-id="7d020-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="7d020-109">Unterstützt bis zu 29 signifikanten Stellen und können darstellen Werte oberhalb 7,9228 x 10 ^ 28.</span><span class="sxs-lookup"><span data-stu-id="7d020-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="7d020-110">Sie eignet sich besonders für Berechnungen wie Finanz-, erfordern eine große Anzahl von Ziffern, jedoch können keine Rundungsfehler tolerieren.</span><span class="sxs-lookup"><span data-stu-id="7d020-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>  
  
 <span data-ttu-id="7d020-111">Der Standardwert von `Decimal` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="7d020-111">The default value of `Decimal` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="7d020-112">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="7d020-112">Programming Tips</span></span>  
  
-   <span data-ttu-id="7d020-113">**Mit einfacher Genauigkeit.**</span><span class="sxs-lookup"><span data-stu-id="7d020-113">**Precision.**</span></span> <span data-ttu-id="7d020-114">`Decimal` ist kein Gleitkomma-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="7d020-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="7d020-115">Die `Decimal` Struktur enthält einen binäre Ganzzahl-Wert, zusammen mit einem Vorzeichenbit und eine ganze Zahl, die Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimalbruch ist.</span><span class="sxs-lookup"><span data-stu-id="7d020-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="7d020-116">Aus diesem Grund `Decimal` Zahlen haben eine genauere Darstellung im Arbeitsspeicher als Gleitkomma-Datentypen (`Single` und `Double`).</span><span class="sxs-lookup"><span data-stu-id="7d020-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>  
  
-   <span data-ttu-id="7d020-117">**Leistung:**</span><span class="sxs-lookup"><span data-stu-id="7d020-117">**Performance.**</span></span> <span data-ttu-id="7d020-118">Die `Decimal` -Datentyp ist der langsamste der alle numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="7d020-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="7d020-119">Wägen Sie die Wichtigkeit der Genauigkeit und Leistung, bevor Sie einen Datentyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="7d020-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>  
  
-   <span data-ttu-id="7d020-120">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="7d020-120">**Widening.**</span></span> <span data-ttu-id="7d020-121">Die `Decimal` -Datentyp wird zu `Single` oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="7d020-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="7d020-122">Dies bedeutet, Sie können konvertieren `Decimal` zu diesen Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="7d020-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="7d020-123">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="7d020-123">**Trailing Zeros.**</span></span> <span data-ttu-id="7d020-124">Visual Basic speichert keine nachfolgende Nullen in einer `Decimal` literal.</span><span class="sxs-lookup"><span data-stu-id="7d020-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="7d020-125">Allerdings eine `Decimal` Variablen werden beibehalten, nachfolgenden Nullen rechnerisch abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7d020-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="7d020-126">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d020-126">The following example illustrates this.</span></span>  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     <span data-ttu-id="7d020-127">Die Ausgabe des `MsgBox` im vorherigen Beispiel lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7d020-127">The output of `MsgBox` in the preceding example is as follows:</span></span>  
  
     <span data-ttu-id="7d020-128">D1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span><span class="sxs-lookup"><span data-stu-id="7d020-128">d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span></span>  
  
-   <span data-ttu-id="7d020-129">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="7d020-129">**Type Characters.**</span></span> <span data-ttu-id="7d020-130">Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="7d020-130">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="7d020-131">Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="7d020-131">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>  
  
-   <span data-ttu-id="7d020-132">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="7d020-132">**Framework Type.**</span></span> <span data-ttu-id="7d020-133">Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="7d020-133">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="7d020-134">Bereich</span><span class="sxs-lookup"><span data-stu-id="7d020-134">Range</span></span>  
 <span data-ttu-id="7d020-135">Müssen Sie möglicherweise verwenden Sie die `D` Typzeichen, weisen einen hohen Wert auf eine `Decimal` Variable oder Konstante.</span><span class="sxs-lookup"><span data-stu-id="7d020-135">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="7d020-136">Diese Anforderung ist, da der Compiler als Literal interpretiert `Long` , wenn ein literal-Typzeichen, das Literal, wie im folgenden Beispiel gezeigt folgt.</span><span class="sxs-lookup"><span data-stu-id="7d020-136">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 <span data-ttu-id="7d020-137">Die Deklaration für `bigDec1` einen Überlauf nicht erzeugt werden, da der Wert, der ihm zugewiesenen innerhalb des Bereichs für liegt `Long`.</span><span class="sxs-lookup"><span data-stu-id="7d020-137">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="7d020-138">Die `Long` Wert zugewiesen werden kann, um die `Decimal` Variable.</span><span class="sxs-lookup"><span data-stu-id="7d020-138">The `Long` value can be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="7d020-139">Die Deklaration für `bigDec2` einen Überlauffehler generiert, da der Wert, der ihm zugewiesen ist zu groß für ist `Long`.</span><span class="sxs-lookup"><span data-stu-id="7d020-139">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="7d020-140">Da die numerische Literale zuerst als interpretiert werden kann eine `Long`, er kann nicht zugewiesen werden die `Decimal` Variable.</span><span class="sxs-lookup"><span data-stu-id="7d020-140">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="7d020-141">Für `bigDec3`, des Literaltypzeichens `D` löst das Problem, da der Compiler interpretiert das Literal als ein `Decimal` anstatt als eine `Long`.</span><span class="sxs-lookup"><span data-stu-id="7d020-141">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d020-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d020-142">See Also</span></span>  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="7d020-143">Datentypen</span><span class="sxs-lookup"><span data-stu-id="7d020-143">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="7d020-144">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7d020-144">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [<span data-ttu-id="7d020-145">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7d020-145">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="7d020-146">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="7d020-146">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="7d020-147">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7d020-147">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="7d020-148">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="7d020-148">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
