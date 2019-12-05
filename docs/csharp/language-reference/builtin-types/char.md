---
title: char-Typ – C#-Referenz
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: ab49b8cbddac2569d6063a5f312105bef3033e84
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552303"
---
# <a name="char-c-reference"></a><span data-ttu-id="ec9d0-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ec9d0-102">char (C# reference)</span></span>

<span data-ttu-id="ec9d0-103">Das Schlüsselwort vom Typ `char` ist ein Alias für den .NET-<xref:System.Char?displayProperty=nameWithType>-Strukturtyp, der ein Unicode-UTF-16-Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="ec9d0-104">Typ</span><span class="sxs-lookup"><span data-stu-id="ec9d0-104">Type</span></span>|<span data-ttu-id="ec9d0-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="ec9d0-105">Range</span></span>|<span data-ttu-id="ec9d0-106">Größe</span><span class="sxs-lookup"><span data-stu-id="ec9d0-106">Size</span></span>|<span data-ttu-id="ec9d0-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="ec9d0-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="ec9d0-108">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="ec9d0-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="ec9d0-109">16 Bit</span><span class="sxs-lookup"><span data-stu-id="ec9d0-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="ec9d0-110">Der Standardwert des `char`-Typs ist `\0`, d. h. U+0000.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="ec9d0-111">Der [string](reference-types.md#the-string-type)-Typ stellt Text als Sequenz von `char`-Werten dar.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="ec9d0-112">Literale</span><span class="sxs-lookup"><span data-stu-id="ec9d0-112">Literals</span></span>

<span data-ttu-id="ec9d0-113">Sie können einen `char`-Wert mit Folgendem angeben:</span><span class="sxs-lookup"><span data-stu-id="ec9d0-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="ec9d0-114">einem Zeichenliteral.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-114">a character literal.</span></span>
- <span data-ttu-id="ec9d0-115">einer Escapesequenz für Unicodezeichen, d. h. `\u` gefolgt von der aus vier Symbolen bestehenden Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="ec9d0-116">einer Escapesequenz für Hexadezimalzahlen, d. h. `\x` gefolgt von der Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

<span data-ttu-id="ec9d0-117">Wie das obige Beispiel zeigt, können Sie den Wert eines Zeichencodes auch in den entsprechenden `char`-Wert umwandeln.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-117">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="ec9d0-118">Im Falle einer Escapesequenz für Unicodezeichen müssen Sie alle vier Hexadezimalziffern angeben.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="ec9d0-119">`\u006A` ist also eine gültige Escapesequenz, `\u06A` und `\u6A` sind hingegen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="ec9d0-120">Bei einer Escapesequenz für Hexadezimalzahlen können Sie die führenden Nullen weglassen.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="ec9d0-121">Die Escapesequenzen `\x006A`, `\x06A` und `\x6A` sind also gültig und entsprechen demselben Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="ec9d0-122">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ec9d0-122">Conversions</span></span>

<span data-ttu-id="ec9d0-123">Der `char`-Typ kann implizit in die folgenden [ganzzahligen](integral-numeric-types.md) Typen konvertiert werden: `ushort`, `int`, `uint`, `long` und `ulong`.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="ec9d0-124">Zudem lässt er sich auch implizit in diese integrierten numerischen [Gleitkommatypen](floating-point-numeric-types.md) konvertieren: `float`, `double` und `decimal`.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="ec9d0-125">Er kann explizit in die ganzzahligen Typen `sbyte`, `byte` und `short` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="ec9d0-126">Es gibt keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="ec9d0-127">Alle [ganzzahligen](integral-numeric-types.md) numerischen Typen oder numerischen [Gleitkommatypen](floating-point-numeric-types.md) lassen sich jedoch explizit in `char` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ec9d0-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ec9d0-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ec9d0-128">C# language specification</span></span>

<span data-ttu-id="ec9d0-129">Weitere Informationen finden Sie im Abschnitt [Integrale Typen](~/_csharplang/spec/types.md#integral-types) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="ec9d0-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec9d0-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec9d0-130">See also</span></span>

- [<span data-ttu-id="ec9d0-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ec9d0-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ec9d0-132">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="ec9d0-132">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="ec9d0-133">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ec9d0-133">Strings</span></span>](../../programming-guide/strings/index.md)
