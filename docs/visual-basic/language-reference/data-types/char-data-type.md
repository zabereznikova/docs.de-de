---
title: Char-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344050"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="8c2d8-102">Char-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c2d8-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="8c2d8-103">Enthält nicht signierte 16-Bit-Code Punkte (2 Bytes), die den Wert von 0 bis 65535 enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="8c2d8-104">Jeder *Codepunkt*oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c2d8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c2d8-105">Remarks</span></span>

<span data-ttu-id="8c2d8-106">Verwenden Sie den `Char`-Datentyp, wenn Sie nur ein einzelnes Zeichen speichern müssen und den Aufwand `String`nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="8c2d8-107">In einigen Fällen können Sie `Char()`, ein Array von `Char` Elementen, verwenden, um mehrere Zeichen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="8c2d8-108">Der Standardwert von `Char` ist das Zeichen mit dem Codepunkt 0.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="8c2d8-109">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="8c2d8-109">Unicode Characters</span></span>

<span data-ttu-id="8c2d8-110">Die ersten 128-Code Punkte (0 – 127) von Unicode entsprechen den Buchstaben und Symbolen in einer standardmäßigen US-Tastatur.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="8c2d8-111">Diese ersten 128-Code Punkte sind identisch mit denen, die der ASCII-Zeichensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="8c2d8-112">Die zweiten 128-Code Punkte (128 – 255) stellen Sonderzeichen dar, wie z. b. lateinische, Buchstaben, Akzente, Währungssymbole und Bruchteile.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="8c2d8-113">Unicode verwendet die verbleibenden Code Punkte (256-65535) für eine Vielzahl von Symbolen, einschließlich der weltweiten Textzeichen, der Diakritik und mathematischen und technischen Symbolen.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="8c2d8-114">Sie können Methoden wie <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> für eine `Char` Variable verwenden, um die Unicode-Klassifizierung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="8c2d8-115">Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="8c2d8-115">Type Conversions</span></span>

<span data-ttu-id="8c2d8-116">Visual Basic wandelt nicht direkt zwischen `Char` und den numerischen Typen um.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="8c2d8-117">Mit der <xref:Microsoft.VisualBasic.Strings.Asc%2A>-oder <xref:Microsoft.VisualBasic.Strings.AscW%2A>-Funktion können Sie einen `Char` Wert in einen `Integer` konvertieren, der den zugehörigen Codepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="8c2d8-118">Sie können die <xref:Microsoft.VisualBasic.Strings.Chr%2A>-oder <xref:Microsoft.VisualBasic.Strings.ChrW%2A>-Funktion verwenden, um einen `Integer` Wert in ein `Char` mit diesem Codepunkt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="8c2d8-119">Wenn der Schalter für die Typüberprüfung (die [Option Strict-Anweisung) aktiviert](../../../visual-basic/language-reference/statements/option-strict-statement.md)ist, müssen Sie das Literaltypzeichen an ein einzelzeichenfolgenliteralzeichen anfügen, um es als `Char` Datentyp zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-119">If the type checking switch (the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="8c2d8-120">Das folgende Beispiel veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-120">The following example illustrates this.</span></span> <span data-ttu-id="8c2d8-121">Die erste Zuweisung zur `charVar`-Variablen generiert den Compilerfehler [BC30512](../../misc/bc30512.md) , da `Option Strict` auf ON fest liegt.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-121">The first assignment to the `charVar` variable generates compiler error [BC30512](../../misc/bc30512.md) because `Option Strict` is on.</span></span> <span data-ttu-id="8c2d8-122">Die zweite wird erfolgreich kompiliert, da das `c` Literaltypzeichens das Literale als `Char` Wert identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-122">The second compiles successfully because the `c` literal type character identifies the literal as a `Char` value.</span></span>

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a><span data-ttu-id="8c2d8-123">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="8c2d8-123">Programming Tips</span></span>

- <span data-ttu-id="8c2d8-124">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="8c2d8-124">**Negative Numbers.**</span></span> <span data-ttu-id="8c2d8-125">`Char` ist ein unsignierter Typ und kann keinen negativen Wert darstellen.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-125">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="8c2d8-126">In jedem Fall sollten Sie `Char` nicht verwenden, um numerische Werte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-126">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="8c2d8-127">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="8c2d8-127">**Interop Considerations.**</span></span> <span data-ttu-id="8c2d8-128">Wenn Sie eine Schnittstelle mit Komponenten, die nicht für die .NET Framework geschrieben wurden, z. b. Automatisierungs-oder COM-Objekte, beachten Sie, dass die Zeichen Typen in anderen Umgebungen eine andere Daten Breite (8 Bits) aufweisen</span><span class="sxs-lookup"><span data-stu-id="8c2d8-128">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="8c2d8-129">Wenn Sie ein 8-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `Byte`, anstatt `Char` im neuen Visual Basic Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-129">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="8c2d8-130">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="8c2d8-130">**Widening.**</span></span> <span data-ttu-id="8c2d8-131">Der `Char`-Datentyp wird zu `String`erweitert.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-131">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="8c2d8-132">Dies bedeutet, dass Sie `Char` in `String` konvertieren können und dass keine <xref:System.OverflowException?displayProperty=nameWithType>auftritt.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-132">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="8c2d8-133">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="8c2d8-133">**Type Characters.**</span></span> <span data-ttu-id="8c2d8-134">Das Anfügen des Literals `C` an eine Zeichenfolge mit einem einzelnen Zeichen erzwingt den Datentyp `Char`.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-134">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="8c2d8-135">`Char` hat kein Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-135">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="8c2d8-136">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="8c2d8-136">**Framework Type.**</span></span> <span data-ttu-id="8c2d8-137">Der entsprechende Typ in .NET Framework ist die <xref:System.Char?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="8c2d8-137">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c2d8-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c2d8-138">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="8c2d8-139">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8c2d8-139">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8c2d8-140">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c2d8-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="8c2d8-141">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="8c2d8-141">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8c2d8-142">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8c2d8-142">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8c2d8-143">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="8c2d8-143">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="8c2d8-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="8c2d8-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
