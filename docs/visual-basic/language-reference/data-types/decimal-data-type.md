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
ms.openlocfilehash: bab5a0bd7e0a85d550362bc3c1166566f6dcb81b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512770"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="82aa0-102">Decimal-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82aa0-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="82aa0-103">Enthält signierte 128-Bit-Werte (16 Byte), die 96-Bit (12-Byte)-ganzzahlige Zahlen darstellen, die durch eine Variablen Potenz von 10 skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="82aa0-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="82aa0-104">Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. der Bereich reicht von 0 bis 28.</span><span class="sxs-lookup"><span data-stu-id="82aa0-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="82aa0-105">Bei einer Skala von 0 (keine Dezimalstellen) ist der größte mögliche Wert +/-337 (+/-7.9228162514264337593543950335E + 28).</span><span class="sxs-lookup"><span data-stu-id="82aa0-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="82aa0-106">Bei 28 Dezimalstellen ist der größte Wert +/-7.9228162514264337593543950335, und der kleinste Wert ungleich 0 (null) ist +/-0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="82aa0-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="82aa0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82aa0-107">Remarks</span></span>

<span data-ttu-id="82aa0-108">Der `Decimal` -Datentyp bietet die größte Anzahl von signifikanten Ziffern für eine Zahl.</span><span class="sxs-lookup"><span data-stu-id="82aa0-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="82aa0-109">Sie unterstützt bis zu 29 signifikante Ziffern und kann Werte über 7,9228 x 10 ^ 28 darstellen.</span><span class="sxs-lookup"><span data-stu-id="82aa0-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="82aa0-110">Sie eignet sich besonders für Berechnungen, z. b. Finanz Weise, die eine große Anzahl von Ziffern erfordern, aber keine Rundungsfehler tolerieren können.</span><span class="sxs-lookup"><span data-stu-id="82aa0-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="82aa0-111">Der Standardwert von `Decimal` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="82aa0-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="82aa0-112">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="82aa0-112">Programming Tips</span></span>

- <span data-ttu-id="82aa0-113">**Präziser.**</span><span class="sxs-lookup"><span data-stu-id="82aa0-113">**Precision.**</span></span> <span data-ttu-id="82aa0-114">`Decimal`ist kein Gleit Komma Datentyp.</span><span class="sxs-lookup"><span data-stu-id="82aa0-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="82aa0-115">Die `Decimal` -Struktur enthält einen binären ganzzahligen Wert, sowie ein Vorzeichen-Bit und einen ganzzahligen Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimal Bruch ist.</span><span class="sxs-lookup"><span data-stu-id="82aa0-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="82aa0-116">Aus diesem `Decimal` Grund weisen Zahlen eine präzisere Darstellung im Arbeitsspeicher auf als Gleit Komma Typen (`Single` und `Double`).</span><span class="sxs-lookup"><span data-stu-id="82aa0-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="82aa0-117">**Leistung:**</span><span class="sxs-lookup"><span data-stu-id="82aa0-117">**Performance.**</span></span> <span data-ttu-id="82aa0-118">Der `Decimal` -Datentyp ist der langsamste Wert aller numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="82aa0-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="82aa0-119">Vor dem Auswählen eines Datentyps sollten Sie die Wichtigkeit der Genauigkeit vor der Leistung abwägen.</span><span class="sxs-lookup"><span data-stu-id="82aa0-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="82aa0-120">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="82aa0-120">**Widening.**</span></span> <span data-ttu-id="82aa0-121">Der `Decimal` -Datentyp wird zu `Single` oder `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="82aa0-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="82aa0-122">Dies bedeutet, dass Sie `Decimal` in einen dieser Typen konvertieren können, ohne <xref:System.OverflowException?displayProperty=nameWithType> dass ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="82aa0-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="82aa0-123">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="82aa0-123">**Trailing Zeros.**</span></span> <span data-ttu-id="82aa0-124">In Visual Basic werden nachfolgende Nullen nicht in `Decimal` einem Literalformat gespeichert.</span><span class="sxs-lookup"><span data-stu-id="82aa0-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="82aa0-125">Allerdings behält `Decimal` eine Variable alle nachfolgenden Nullen bei, die rechnerisch abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="82aa0-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="82aa0-126">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="82aa0-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="82aa0-127">Die Ausgabe von `MsgBox` im vorherigen Beispiel lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="82aa0-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="82aa0-128">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="82aa0-128">**Type Characters.**</span></span> <span data-ttu-id="82aa0-129">Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="82aa0-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="82aa0-130">Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="82aa0-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="82aa0-131">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="82aa0-131">**Framework Type.**</span></span> <span data-ttu-id="82aa0-132">Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="82aa0-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="82aa0-133">Bereich</span><span class="sxs-lookup"><span data-stu-id="82aa0-133">Range</span></span>
 <span data-ttu-id="82aa0-134">Möglicherweise müssen Sie das `D` Typzeichen verwenden, um einer `Decimal` Variablen oder Konstanten einen großen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="82aa0-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="82aa0-135">Diese Anforderung liegt daran, dass der Compiler ein Literalzeichen als `Long` interpretiert, es sei denn, ein Literaltypzeichen folgt dem Literalen, wie im folgenden Beispiel gezeigt</span><span class="sxs-lookup"><span data-stu-id="82aa0-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="82aa0-136">Die Deklaration `bigDec1` für erzeugt keinen Überlauf, da der zugewiesene Wert innerhalb des Bereichs für `Long`liegt.</span><span class="sxs-lookup"><span data-stu-id="82aa0-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="82aa0-137">Der `Long` Wert kann der `Decimal` Variablen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="82aa0-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="82aa0-138">Die-Deklaration für `bigDec2` generiert einen Überlauf Fehler, da der zugewiesene Wert für `Long`zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="82aa0-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="82aa0-139">Da das numerische Literale nicht als `Long`erstes interpretiert werden kann, kann es der `Decimal` Variablen nicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="82aa0-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="82aa0-140">Für `bigDec3`löst das Literaltypzeichen `D` das Problem, indem der Compiler gezwungen wird, das Literale `Decimal` als anstelle von als `Long`zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="82aa0-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="82aa0-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82aa0-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="82aa0-142">Datentypen</span><span class="sxs-lookup"><span data-stu-id="82aa0-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="82aa0-143">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="82aa0-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="82aa0-144">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="82aa0-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="82aa0-145">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="82aa0-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="82aa0-146">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="82aa0-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="82aa0-147">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="82aa0-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
