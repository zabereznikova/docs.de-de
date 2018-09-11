---
title: Byte-Datentyp (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b106005ff07f55e05ae66dba94041cd8b5c24bb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266812"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="45fcd-102">Byte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45fcd-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="45fcd-103">Enthält die 8-Bit (1-Byte)-Ganzzahlen ohne Vorzeichen, die im Wert von 0 bis 255 liegen.</span><span class="sxs-lookup"><span data-stu-id="45fcd-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="45fcd-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45fcd-104">Remarks</span></span>

<span data-ttu-id="45fcd-105">Verwenden der `Byte` -Datentyp, um binäre Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="45fcd-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="45fcd-106">Der Standardwert von `Byte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="45fcd-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="45fcd-107">Zuweisung von literalen</span><span class="sxs-lookup"><span data-stu-id="45fcd-107">Literal assignments</span></span>

<span data-ttu-id="45fcd-108">Sie können deklarieren und initialisieren eine `Byte` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="45fcd-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="45fcd-109">Ganzzahlige Literal ist außerhalb des Bereichs von einer `Byte` (d. h., wenn es ist kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Byte.MaxValue?displayProperty=nameWithType>), tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="45fcd-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="45fcd-110">Im folgenden Beispiel werden Ganzzahlen wie 201 hat, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden implizit konvertiert, von [Ganzzahl](integer-data-type.md) zu `byte` Werte.</span><span class="sxs-lookup"><span data-stu-id="45fcd-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="45fcd-111">Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="45fcd-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="45fcd-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="45fcd-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="45fcd-113">Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="45fcd-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="45fcd-114">Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern.</span><span class="sxs-lookup"><span data-stu-id="45fcd-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="45fcd-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="45fcd-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="45fcd-116">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="45fcd-116">Programming tips</span></span>

-   <span data-ttu-id="45fcd-117">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="45fcd-117">**Negative Numbers.**</span></span> <span data-ttu-id="45fcd-118">Da `Byte` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen.</span><span class="sxs-lookup"><span data-stu-id="45fcd-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="45fcd-119">Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `Byte`, konvertiert den Ausdruck, der Visual Basic `Short` erste.</span><span class="sxs-lookup"><span data-stu-id="45fcd-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
-   <span data-ttu-id="45fcd-120">**Format-Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="45fcd-120">**Format Conversions.**</span></span> <span data-ttu-id="45fcd-121">Wenn Visual Basic liest oder schreibt Dateien oder beim Aufrufen von DLLs, Methoden und Eigenschaften, können sie automatisch zwischen den Datenformaten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="45fcd-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="45fcd-122">Binäre Daten, die in `Byte` Variablen und Arrays während solche Konvertierungen Format beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="45fcd-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="45fcd-123">Verwenden Sie keine `String` Variablen, um binäre Daten verwenden, da der Inhalt während der Konvertierung zwischen ANSI- und Unicode-Formaten beschädigt werden können.</span><span class="sxs-lookup"><span data-stu-id="45fcd-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

-   <span data-ttu-id="45fcd-124">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="45fcd-124">**Widening.**</span></span> <span data-ttu-id="45fcd-125">Die `Byte` -Datentyp wird zu `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="45fcd-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="45fcd-126">Dies bedeutet, Sie können konvertieren `Byte` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="45fcd-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="45fcd-127">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="45fcd-127">**Type Characters.**</span></span> <span data-ttu-id="45fcd-128">`Byte` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="45fcd-128">`Byte` has no literal type character or identifier type character.</span></span>

-   <span data-ttu-id="45fcd-129">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="45fcd-129">**Framework Type.**</span></span> <span data-ttu-id="45fcd-130">Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="45fcd-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="45fcd-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45fcd-131">Example</span></span>

 <span data-ttu-id="45fcd-132">Im folgenden Beispiel `b` ist eine `Byte` Variable.</span><span class="sxs-lookup"><span data-stu-id="45fcd-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="45fcd-133">Den Bereich der Variablen und die Anwendung von Bitschiebeoperatoren, führen Sie die Anweisungen vor.</span><span class="sxs-lookup"><span data-stu-id="45fcd-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a><span data-ttu-id="45fcd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45fcd-134">See Also</span></span>

 <xref:System.Byte?displayProperty=nameWithType>  
 [<span data-ttu-id="45fcd-135">Datentypen</span><span class="sxs-lookup"><span data-stu-id="45fcd-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="45fcd-136">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="45fcd-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="45fcd-137">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="45fcd-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="45fcd-138">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="45fcd-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
