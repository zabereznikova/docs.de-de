---
title: Short-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 176d27c86127dac1d9c9c0231790f7a5c2a2fefc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415556"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="09a90-102">Short-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09a90-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="09a90-103">Enthält ganze 16-Bit-Zahlen (2 Bytes) mit Vorzeichen, die den Wert von-32.768 bis 32.767 über liegen.</span><span class="sxs-lookup"><span data-stu-id="09a90-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09a90-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="09a90-104">Remarks</span></span>  

 <span data-ttu-id="09a90-105">Verwenden Sie den- `Short` Datentyp, um ganzzahlige Werte zu enthalten, die nicht die vollständige Daten Breite von erfordern `Integer` .</span><span class="sxs-lookup"><span data-stu-id="09a90-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="09a90-106">In einigen Fällen können die Common Language Runtime die `Short` Variablen eng zusammenpacken und den Speicherverbrauch verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="09a90-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="09a90-107">Der Standardwert von `Short` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="09a90-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="09a90-108">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="09a90-108">Literal assignments</span></span>

<span data-ttu-id="09a90-109">Sie können eine Variable deklarieren und initialisieren, `Short` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="09a90-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="09a90-110">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="09a90-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="09a90-111">Im folgenden Beispiel werden ganze Zahlen gleich 1.034, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, implizit von [ganzzahligen](integer-data-type.md) Werten in- `Short` Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="09a90-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="09a90-112">Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="09a90-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="09a90-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="09a90-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="09a90-114">Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="09a90-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="09a90-115">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="09a90-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="09a90-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="09a90-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="09a90-117">Numerische Literale können auch das `S` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Short` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="09a90-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="09a90-118">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="09a90-118">Programming tips</span></span>

- <span data-ttu-id="09a90-119">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="09a90-119">**Widening.**</span></span> <span data-ttu-id="09a90-120">Der- `Short` Datentyp wird zu `Integer` , `Long` , `Decimal` , `Single` oder erweitert `Double` .</span><span class="sxs-lookup"><span data-stu-id="09a90-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="09a90-121">Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="09a90-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="09a90-122">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="09a90-122">**Type Characters.**</span></span> <span data-ttu-id="09a90-123">Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="09a90-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="09a90-124">`Short`hat kein Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="09a90-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="09a90-125">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="09a90-125">**Framework Type.**</span></span> <span data-ttu-id="09a90-126">Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="09a90-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a90-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09a90-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="09a90-128">Datentypen</span><span class="sxs-lookup"><span data-stu-id="09a90-128">Data Types</span></span>](index.md)
- [<span data-ttu-id="09a90-129">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="09a90-129">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="09a90-130">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="09a90-130">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="09a90-131">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="09a90-131">Integer Data Type</span></span>](integer-data-type.md)
- [<span data-ttu-id="09a90-132">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="09a90-132">Long Data Type</span></span>](long-data-type.md)
- [<span data-ttu-id="09a90-133">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="09a90-133">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
