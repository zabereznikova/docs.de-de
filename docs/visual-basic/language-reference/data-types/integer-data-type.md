---
title: Integer-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: aa7b64162308d6af2763b29034c5a7276c973876
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415608"
---
# <a name="integer-data-type-visual-basic"></a><span data-ttu-id="57867-102">Integer-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57867-102">Integer data type (Visual Basic)</span></span>

<span data-ttu-id="57867-103">Speichert 32-Bit-(4-Byte-)Ganzzahlen mit Vorzeichen, deren Werte sich im Bereich von -2.147.483.648 bis einschließlich 2.147.483.647 bewegen.</span><span class="sxs-lookup"><span data-stu-id="57867-103">Holds signed 32-bit (4-byte) integers that range in value from -2,147,483,648 through 2,147,483,647.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57867-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="57867-104">Remarks</span></span>

 <span data-ttu-id="57867-105">Der `Integer`-Datentyp bietet in Verbindung mit einem 32-Bit-Prozessor eine optimale Leistung.</span><span class="sxs-lookup"><span data-stu-id="57867-105">The `Integer` data type provides optimal performance on a 32-bit processor.</span></span> <span data-ttu-id="57867-106">Die anderen ganzzahligen Typen werden langsamer in den Arbeitsspeicher geladen und im Arbeitsspeicher gespeichert bzw. langsamer aus dem Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="57867-106">The other integral types are slower to load and store from and to memory.</span></span>  
  
 <span data-ttu-id="57867-107">Der Standardwert von `Integer` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="57867-107">The default value of `Integer` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="57867-108">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="57867-108">Literal assignments</span></span>

<span data-ttu-id="57867-109">Sie können eine-Variable deklarieren und initialisieren, `Integer` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein oktalliteralformat oder (beginnend mit Visual Basic 2017) ein binäres Literalformat zuweisen.</span><span class="sxs-lookup"><span data-stu-id="57867-109">You can declare and initialize an `Integer` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="57867-110">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Integer` befindet – sprich, wenn es kleiner als <xref:System.Int32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="57867-110">If the integer literal is outside the range of `Integer` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="57867-111">Im folgenden Beispiel werden Ganzzahlen wie 90.946, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `Integer`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="57867-111">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `Integer` values.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> <span data-ttu-id="57867-112">Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="57867-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="57867-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="57867-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="57867-114">Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="57867-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

<span data-ttu-id="57867-115">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="57867-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="57867-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="57867-116">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="57867-117">Numerische Literale können auch das `I` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Integer` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="57867-117">Numeric literals can also include the `I` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Integer` data type, as the following example shows.</span></span>

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a><span data-ttu-id="57867-118">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="57867-118">Programming tips</span></span>

- <span data-ttu-id="57867-119">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="57867-119">**Interop Considerations.**</span></span> <span data-ttu-id="57867-120">Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), denken Sie daran, dass `Integer` in anderen Umgebungen eine andere Daten Breite (16 Bits) aufweist.</span><span class="sxs-lookup"><span data-stu-id="57867-120">If you are interfacing with components not written for the .NET Framework, such as Automation or COM objects, remember that `Integer` has a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="57867-121">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic-Code als `Short` und nicht als `Integer`.</span><span class="sxs-lookup"><span data-stu-id="57867-121">If you are passing a 16-bit argument to such a component, declare it as `Short` instead of `Integer` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="57867-122">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="57867-122">**Widening.**</span></span> <span data-ttu-id="57867-123">Der `Integer`-Datentyp wird zu `Long`, `Decimal`, `Single` oder `Double` erweitert.</span><span class="sxs-lookup"><span data-stu-id="57867-123">The `Integer` data type widens to `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="57867-124">Dies bedeutet, dass Sie `Integer` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="57867-124">This means you can convert `Integer` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="57867-125">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="57867-125">**Type Characters.**</span></span> <span data-ttu-id="57867-126">Durch Anhängen des Literaltypzeichens `I` an ein Literal wird der `Integer`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="57867-126">Appending the literal type character `I` to a literal forces it to the `Integer` data type.</span></span> <span data-ttu-id="57867-127">Durch Anhängen des Typkennzeichens `%` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Integer`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="57867-127">Appending the identifier type character `%` to any identifier forces it to `Integer`.</span></span>  
  
- <span data-ttu-id="57867-128">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="57867-128">**Framework Type.**</span></span> <span data-ttu-id="57867-129">Der entsprechende Typ in .NET Framework ist die <xref:System.Int32?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="57867-129">The corresponding type in the .NET Framework is the <xref:System.Int32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="57867-130">Range</span><span class="sxs-lookup"><span data-stu-id="57867-130">Range</span></span>

<span data-ttu-id="57867-131">Wenn Sie für eine Variable mit Ganzzahltyp eine Zahl festlegen, die außerhalb des Bereichs für diesen Typ liegt, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="57867-131">If you try to set a variable of an integral type to a number outside the range for that type, an error occurs.</span></span> <span data-ttu-id="57867-132">Wenn Sie versuchen, sie auf einen Bruch festzulegen, wird die Zahl auf den nächsten ganzzahligen Wert auf- oder abgerundet.</span><span class="sxs-lookup"><span data-stu-id="57867-132">If you try to set it to a fraction, the number is rounded up or down to the nearest integer value.</span></span> <span data-ttu-id="57867-133">Wenn die Zahl zwei Ganzzahlwerten gleichermaßen nahe ist, wird der Wert auf die nächste gerade ganze Zahl gerundet.</span><span class="sxs-lookup"><span data-stu-id="57867-133">If the number is equally close to two integer values, the value is rounded to the nearest even integer.</span></span> <span data-ttu-id="57867-134">So werden Rundungsfehler reduziert, die sich beim einheitlichen Runden von in der Mitte liegenden Werten in nur eine Richtung ergeben.</span><span class="sxs-lookup"><span data-stu-id="57867-134">This behavior minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.</span></span> <span data-ttu-id="57867-135">Der folgende Code zeigt Beispiele für eine Rundung.</span><span class="sxs-lookup"><span data-stu-id="57867-135">The following code shows examples of rounding.</span></span>  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a><span data-ttu-id="57867-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57867-136">See also</span></span>

- <xref:System.Int32?displayProperty=nameWithType>
- [<span data-ttu-id="57867-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="57867-137">Data Types</span></span>](index.md)
- [<span data-ttu-id="57867-138">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="57867-138">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="57867-139">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="57867-139">Short Data Type</span></span>](short-data-type.md)
- [<span data-ttu-id="57867-140">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="57867-140">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="57867-141">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="57867-141">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="57867-142">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="57867-142">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
