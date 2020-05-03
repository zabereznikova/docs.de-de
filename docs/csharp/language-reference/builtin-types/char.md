---
title: char-Typ – C#-Referenz
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: a07cae6e607bb6cda965240c669c655207632298
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739063"
---
# <a name="char-c-reference"></a><span data-ttu-id="f2533-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f2533-102">char (C# reference)</span></span>

<span data-ttu-id="f2533-103">Das Schlüsselwort vom Typ `char` ist ein Alias für den .NET-<xref:System.Char?displayProperty=nameWithType>-Strukturtyp, der ein Unicode-UTF-16-Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="f2533-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="f2533-104">Typ</span><span class="sxs-lookup"><span data-stu-id="f2533-104">Type</span></span>|<span data-ttu-id="f2533-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="f2533-105">Range</span></span>|<span data-ttu-id="f2533-106">Größe</span><span class="sxs-lookup"><span data-stu-id="f2533-106">Size</span></span>|<span data-ttu-id="f2533-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="f2533-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="f2533-108">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="f2533-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="f2533-109">16 Bit</span><span class="sxs-lookup"><span data-stu-id="f2533-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="f2533-110">Der Standardwert des `char`-Typs ist `\0`, d. h. U+0000.</span><span class="sxs-lookup"><span data-stu-id="f2533-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="f2533-111">Der [string](reference-types.md#the-string-type)-Typ stellt Text als Sequenz von `char`-Werten dar.</span><span class="sxs-lookup"><span data-stu-id="f2533-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="f2533-112">Literale</span><span class="sxs-lookup"><span data-stu-id="f2533-112">Literals</span></span>

<span data-ttu-id="f2533-113">Sie können einen `char`-Wert mit Folgendem angeben:</span><span class="sxs-lookup"><span data-stu-id="f2533-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="f2533-114">einem Zeichenliteral.</span><span class="sxs-lookup"><span data-stu-id="f2533-114">a character literal.</span></span>
- <span data-ttu-id="f2533-115">einer Escapesequenz für Unicodezeichen, d. h. `\u` gefolgt von der aus vier Symbolen bestehenden Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="f2533-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="f2533-116">einer Escapesequenz für Hexadezimalzahlen, d. h. `\x` gefolgt von der Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="f2533-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="f2533-117">Wie das obige Beispiel zeigt, können Sie den Wert eines Zeichencodes auch in den entsprechenden `char`-Wert umwandeln.</span><span class="sxs-lookup"><span data-stu-id="f2533-117">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="f2533-118">Im Falle einer Escapesequenz für Unicodezeichen müssen Sie alle vier Hexadezimalziffern angeben.</span><span class="sxs-lookup"><span data-stu-id="f2533-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="f2533-119">`\u006A` ist also eine gültige Escapesequenz, `\u06A` und `\u6A` sind hingegen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="f2533-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="f2533-120">Bei einer Escapesequenz für Hexadezimalzahlen können Sie die führenden Nullen weglassen.</span><span class="sxs-lookup"><span data-stu-id="f2533-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="f2533-121">Die Escapesequenzen `\x006A`, `\x06A` und `\x6A` sind also gültig und entsprechen demselben Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f2533-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="f2533-122">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f2533-122">Conversions</span></span>

<span data-ttu-id="f2533-123">Der `char`-Typ kann implizit in die folgenden [ganzzahligen](integral-numeric-types.md) Typen konvertiert werden: `ushort`, `int`, `uint`, `long` und `ulong`.</span><span class="sxs-lookup"><span data-stu-id="f2533-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="f2533-124">Zudem lässt er sich auch implizit in diese integrierten numerischen [Gleitkommatypen](floating-point-numeric-types.md) konvertieren: `float`, `double` und `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f2533-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="f2533-125">Er kann explizit in die ganzzahligen Typen `sbyte`, `byte` und `short` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="f2533-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="f2533-126">Es gibt keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="f2533-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="f2533-127">Alle [ganzzahligen](integral-numeric-types.md) numerischen Typen oder numerischen [Gleitkommatypen](floating-point-numeric-types.md) lassen sich jedoch explizit in `char` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f2533-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f2533-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f2533-128">C# language specification</span></span>

<span data-ttu-id="f2533-129">Weitere Informationen finden Sie im Abschnitt [Integrale Typen](~/_csharplang/spec/types.md#integral-types) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="f2533-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2533-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2533-130">See also</span></span>

- [<span data-ttu-id="f2533-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f2533-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f2533-132">Werttypen</span><span class="sxs-lookup"><span data-stu-id="f2533-132">Value types</span></span>](value-types.md)
- [<span data-ttu-id="f2533-133">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f2533-133">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="f2533-134">Zeichencodierung in .NET</span><span class="sxs-lookup"><span data-stu-id="f2533-134">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
