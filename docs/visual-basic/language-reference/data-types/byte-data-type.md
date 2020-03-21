---
title: Byte-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401352"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="df68f-102">Byte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df68f-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="df68f-103">Enthält ganze Ganzzahlen mit nicht signierten 8-Bit-Dateien (1 Byte), die einen Wert von 0 bis 255 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="df68f-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="df68f-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="df68f-104">Remarks</span></span>

<span data-ttu-id="df68f-105">Verwenden `Byte` Sie den Datentyp, um Binärdaten zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="df68f-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="df68f-106">Der Standardwert von `Byte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="df68f-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="df68f-107">Literale Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="df68f-107">Literal assignments</span></span>

<span data-ttu-id="df68f-108">Sie können eine `Byte` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="df68f-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="df68f-109">Wenn sich das integrale Literal `Byte` außerhalb des Bereichs von <xref:System.Byte.MinValue?displayProperty=nameWithType> a <xref:System.Byte.MaxValue?displayProperty=nameWithType>befindet (d. h., wenn es kleiner oder größer als ist ), tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="df68f-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="df68f-110">Im folgenden Beispiel werden ganzzahlige Zahlen gleich 201, die als Dezimal-, Hexadezimal- und `byte` Binärliterale dargestellt werden, implizit von [Ganzzahl](integer-data-type.md) in Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="df68f-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="df68f-111">Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="df68f-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="df68f-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="df68f-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="df68f-113">Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="df68f-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="df68f-114">Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="df68f-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="df68f-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df68f-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="df68f-116">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="df68f-116">Programming tips</span></span>

- <span data-ttu-id="df68f-117">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="df68f-117">**Negative Numbers.**</span></span> <span data-ttu-id="df68f-118">Da `Byte` es sich um einen nicht signierten Typ handelt, kann er keine negative Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="df68f-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="df68f-119">Wenn Sie den Operator`-`unary minus ( ) für `Byte`einen Ausdruck verwenden, `Short` der als Typ ausgewertet wird, konvertiert Visual Basic den Ausdruck in den ersten.</span><span class="sxs-lookup"><span data-stu-id="df68f-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="df68f-120">**Formatkonvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="df68f-120">**Format Conversions.**</span></span> <span data-ttu-id="df68f-121">Wenn Visual Basic Dateien liest oder schreibt oder DLLs, Methoden und Eigenschaften aufruft, kann es automatisch zwischen Datenformaten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="df68f-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="df68f-122">Binäre Daten, die in `Byte` Variablen und Arrays gespeichert sind, werden während solcher Formatkonvertierungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="df68f-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="df68f-123">Sie sollten keine `String` Variable für Binärdaten verwenden, da derInhalt während der Konvertierung zwischen ANSI- und Unicode-Formaten beschädigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="df68f-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="df68f-124">**Erweiterung.**</span><span class="sxs-lookup"><span data-stu-id="df68f-124">**Widening.**</span></span> <span data-ttu-id="df68f-125">Der `Byte` Datentyp wird `Short` `UShort`auf `Integer` `UInteger`, `Long` `ULong`, `Decimal` `Single`, `Double`, , , , , , oder erweitert.</span><span class="sxs-lookup"><span data-stu-id="df68f-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="df68f-126">Dies bedeutet, `Byte` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.</span><span class="sxs-lookup"><span data-stu-id="df68f-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="df68f-127">**Typ Zeichen.**</span><span class="sxs-lookup"><span data-stu-id="df68f-127">**Type Characters.**</span></span> <span data-ttu-id="df68f-128">`Byte`hat kein Literaltypzeichen oder Bezeichnertypzeichen.</span><span class="sxs-lookup"><span data-stu-id="df68f-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="df68f-129">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="df68f-129">**Framework Type.**</span></span> <span data-ttu-id="df68f-130">Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="df68f-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="df68f-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df68f-131">Example</span></span>

 <span data-ttu-id="df68f-132">Im folgenden Beispiel `b` ist `Byte` eine Variable.</span><span class="sxs-lookup"><span data-stu-id="df68f-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="df68f-133">Die Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung von Bitshift-Operatoren darauf.</span><span class="sxs-lookup"><span data-stu-id="df68f-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="df68f-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df68f-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="df68f-135">Datentypen</span><span class="sxs-lookup"><span data-stu-id="df68f-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="df68f-136">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="df68f-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="df68f-137">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="df68f-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="df68f-138">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="df68f-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
