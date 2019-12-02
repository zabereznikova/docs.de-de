---
title: char-Typ – C#-Referenz
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 3b2eec4f0e17aa329fe3865fb3ef453ee030c6a7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450841"
---
# <a name="char-c-reference"></a><span data-ttu-id="225a2-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="225a2-102">char (C# reference)</span></span>

<span data-ttu-id="225a2-103">Das Schlüsselwort vom Typ `char` ist ein Alias für den .NET-<xref:System.Char?displayProperty=nameWithType>-Strukturtyp, der ein Unicode-UTF-16-Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="225a2-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="225a2-104">Typ</span><span class="sxs-lookup"><span data-stu-id="225a2-104">Type</span></span>|<span data-ttu-id="225a2-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="225a2-105">Range</span></span>|<span data-ttu-id="225a2-106">Größe</span><span class="sxs-lookup"><span data-stu-id="225a2-106">Size</span></span>|<span data-ttu-id="225a2-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="225a2-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="225a2-108">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="225a2-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="225a2-109">16 Bit</span><span class="sxs-lookup"><span data-stu-id="225a2-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="225a2-110">Der [string](reference-types.md#the-string-type)-Typ stellt Text als Sequenz von `char`-Werten dar.</span><span class="sxs-lookup"><span data-stu-id="225a2-110">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="225a2-111">Literale</span><span class="sxs-lookup"><span data-stu-id="225a2-111">Literals</span></span>

<span data-ttu-id="225a2-112">Sie können einen `char`-Wert mit Folgendem angeben:</span><span class="sxs-lookup"><span data-stu-id="225a2-112">You can specify a `char` value with:</span></span>

- <span data-ttu-id="225a2-113">einem Zeichenliteral.</span><span class="sxs-lookup"><span data-stu-id="225a2-113">a character literal.</span></span>
- <span data-ttu-id="225a2-114">einer Escapesequenz für Unicodezeichen, d. h. `\u` gefolgt von der aus vier Symbolen bestehenden Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="225a2-114">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="225a2-115">einer Escapesequenz für Hexadezimalzahlen, d. h. `\x` gefolgt von der Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="225a2-115">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

<span data-ttu-id="225a2-116">Wie das obige Beispiel zeigt, können Sie den Wert eines Zeichencodes auch in den entsprechenden `char`-Wert umwandeln.</span><span class="sxs-lookup"><span data-stu-id="225a2-116">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="225a2-117">Im Falle einer Escapesequenz für Unicodezeichen müssen Sie alle vier Hexadezimalziffern angeben.</span><span class="sxs-lookup"><span data-stu-id="225a2-117">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="225a2-118">`\u006A` ist also eine gültige Escapesequenz, `\u06A` und `\u6A` sind hingegen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="225a2-118">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="225a2-119">Bei einer Escapesequenz für Hexadezimalzahlen können Sie die führenden Nullen weglassen.</span><span class="sxs-lookup"><span data-stu-id="225a2-119">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="225a2-120">Die Escapesequenzen `\x006A`, `\x06A` und `\x6A` sind also gültig und entsprechen demselben Zeichen.</span><span class="sxs-lookup"><span data-stu-id="225a2-120">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="225a2-121">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="225a2-121">Conversions</span></span>

<span data-ttu-id="225a2-122">Der `char`-Typ kann implizit in die folgenden [ganzzahligen](integral-numeric-types.md) Typen konvertiert werden: `ushort`, `int`, `uint`, `long` und `ulong`.</span><span class="sxs-lookup"><span data-stu-id="225a2-122">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="225a2-123">Zudem lässt er sich auch implizit in diese integrierten numerischen [Gleitkommatypen](floating-point-numeric-types.md) konvertieren: `float`, `double` und `decimal`.</span><span class="sxs-lookup"><span data-stu-id="225a2-123">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="225a2-124">Er kann explizit in die ganzzahligen Typen `sbyte`, `byte` und `short` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="225a2-124">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="225a2-125">Es gibt keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="225a2-125">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="225a2-126">Alle [ganzzahligen](integral-numeric-types.md) numerischen Typen oder numerischen [Gleitkommatypen](floating-point-numeric-types.md) lassen sich jedoch explizit in `char` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="225a2-126">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="225a2-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="225a2-127">C# language specification</span></span>

<span data-ttu-id="225a2-128">Weitere Informationen finden Sie im Abschnitt [Integrale Typen](~/_csharplang/spec/types.md#integral-types) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="225a2-128">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="225a2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="225a2-129">See also</span></span>

- [<span data-ttu-id="225a2-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="225a2-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="225a2-131">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="225a2-131">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="225a2-132">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="225a2-132">Strings</span></span>](../../programming-guide/strings/index.md)
