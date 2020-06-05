---
title: Byte-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 97acd1bc2ff29bac6588216b9ee4a4f187078815
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374316"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="6d93c-102">Byte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d93c-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="6d93c-103">Enthält ganzzahlige 8-Bit-Zahlen (1 Byte) ohne Vorzeichen, die einen Wert zwischen 0 und 255 enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d93c-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d93c-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6d93c-104">Remarks</span></span>

<span data-ttu-id="6d93c-105">Verwenden Sie den- `Byte` Datentyp, um Binärdaten zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d93c-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="6d93c-106">Der Standardwert von `Byte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="6d93c-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="6d93c-107">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="6d93c-107">Literal assignments</span></span>

<span data-ttu-id="6d93c-108">Sie können eine Variable deklarieren und initialisieren, `Byte` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6d93c-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="6d93c-109">Wenn sich das ganzzahlige Literale außerhalb des Bereichs von befindet (d. h `Byte` ., wenn es kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als ist <xref:System.Byte.MaxValue?displayProperty=nameWithType> ), tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="6d93c-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="6d93c-110">Im folgenden Beispiel werden ganze Zahlen gleich 201, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, implizit von [ganzzahligen](integer-data-type.md) Werten in- `byte` Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6d93c-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="6d93c-111">Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d93c-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="6d93c-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="6d93c-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="6d93c-113">Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d93c-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="6d93c-114">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d93c-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="6d93c-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6d93c-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="6d93c-116">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="6d93c-116">Programming tips</span></span>

- <span data-ttu-id="6d93c-117">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="6d93c-117">**Negative Numbers.**</span></span> <span data-ttu-id="6d93c-118">Da `Byte` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="6d93c-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="6d93c-119">Wenn Sie den unären Minus ( `-` )-Operator für einen Ausdruck verwenden, der den Typ ergibt `Byte` , konvertiert Visual Basic den Ausdruck in den `Short` ersten.</span><span class="sxs-lookup"><span data-stu-id="6d93c-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="6d93c-120">**Format Konvertierungen.**</span><span class="sxs-lookup"><span data-stu-id="6d93c-120">**Format Conversions.**</span></span> <span data-ttu-id="6d93c-121">Wenn Visual Basic Dateien liest oder schreibt oder DLLs, Methoden und Eigenschaften aufruft, kann es automatisch zwischen Datenformaten konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d93c-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="6d93c-122">Binärdaten, die in Variablen und Arrays gespeichert werden, werden `Byte` bei solchen Formatkonvertierungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6d93c-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="6d93c-123">Sie sollten keine `String` Variable für binäre Daten verwenden, da der Inhalt während der Konvertierung zwischen ANSI-und Unicode-Formaten beschädigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d93c-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="6d93c-124">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="6d93c-124">**Widening.**</span></span> <span data-ttu-id="6d93c-125">Der- `Byte` Datentyp wird zu `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` oder erweitert `Double` .</span><span class="sxs-lookup"><span data-stu-id="6d93c-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="6d93c-126">Dies bedeutet `Byte` , dass Sie in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="6d93c-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="6d93c-127">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="6d93c-127">**Type Characters.**</span></span> <span data-ttu-id="6d93c-128">`Byte`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.</span><span class="sxs-lookup"><span data-stu-id="6d93c-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="6d93c-129">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="6d93c-129">**Framework Type.**</span></span> <span data-ttu-id="6d93c-130">Der entsprechende Typ in .NET Framework ist die <xref:System.Byte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="6d93c-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="6d93c-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d93c-131">Example</span></span>

 <span data-ttu-id="6d93c-132">Im folgenden Beispiel `b` ist eine `Byte` Variable.</span><span class="sxs-lookup"><span data-stu-id="6d93c-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="6d93c-133">Die-Anweisungen veranschaulichen den Bereich der Variablen und die Anwendung von BitShift-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="6d93c-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="6d93c-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d93c-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="6d93c-135">Datentypen</span><span class="sxs-lookup"><span data-stu-id="6d93c-135">Data Types</span></span>](index.md)
- [<span data-ttu-id="6d93c-136">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="6d93c-136">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="6d93c-137">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="6d93c-137">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="6d93c-138">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="6d93c-138">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
