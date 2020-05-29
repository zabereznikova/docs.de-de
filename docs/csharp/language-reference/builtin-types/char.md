---
title: char-Typ – C#-Referenz
ms.date: 05/11/2020
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: f771626e9777deab30e798559d847615d6124e6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205782"
---
# <a name="char-c-reference"></a><span data-ttu-id="d5116-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d5116-102">char (C# reference)</span></span>

<span data-ttu-id="d5116-103">Das Schlüsselwort vom Typ `char` ist ein Alias für den .NET-<xref:System.Char?displayProperty=nameWithType>-Strukturtyp, der ein Unicode-UTF-16-Zeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5116-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="d5116-104">Typ</span><span class="sxs-lookup"><span data-stu-id="d5116-104">Type</span></span>|<span data-ttu-id="d5116-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="d5116-105">Range</span></span>|<span data-ttu-id="d5116-106">Größe</span><span class="sxs-lookup"><span data-stu-id="d5116-106">Size</span></span>|<span data-ttu-id="d5116-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="d5116-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="d5116-108">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="d5116-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="d5116-109">16 Bit</span><span class="sxs-lookup"><span data-stu-id="d5116-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="d5116-110">Der Standardwert des `char`-Typs ist `\0`, d. h. U+0000.</span><span class="sxs-lookup"><span data-stu-id="d5116-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="d5116-111">Der `char`-Typ unterstützt [Vergleichs](../operators/comparison-operators.md)-, [Gleichheits](../operators/equality-operators.md)-, [Inkrement](../operators/arithmetic-operators.md#increment-operator-)- und [Dekrement](../operators/arithmetic-operators.md#decrement-operator---)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d5116-111">The `char` type supports [comparison](../operators/comparison-operators.md), [equality](../operators/equality-operators.md), [increment](../operators/arithmetic-operators.md#increment-operator-), and [decrement](../operators/arithmetic-operators.md#decrement-operator---) operators.</span></span> <span data-ttu-id="d5116-112">Außerdem wird für `char`-Operanden, [arithmetische](../operators/arithmetic-operators.md) und [bitweise logische](../operators/bitwise-and-shift-operators.md) Operatoren ein Vorgang für die entsprechenden Zeichencodes durchgeführt und ein Ergebnis des `int`-Typs erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d5116-112">Moreover, for `char` operands, [arithmetic](../operators/arithmetic-operators.md) and [bitwise logical](../operators/bitwise-and-shift-operators.md) operators perform an operation on the corresponding character codes and produce the result of the `int` type.</span></span>

<span data-ttu-id="d5116-113">Der [string](reference-types.md#the-string-type)-Typ stellt Text als Sequenz von `char`-Werten dar.</span><span class="sxs-lookup"><span data-stu-id="d5116-113">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="d5116-114">Literale</span><span class="sxs-lookup"><span data-stu-id="d5116-114">Literals</span></span>

<span data-ttu-id="d5116-115">Sie können einen `char`-Wert mit Folgendem angeben:</span><span class="sxs-lookup"><span data-stu-id="d5116-115">You can specify a `char` value with:</span></span>

- <span data-ttu-id="d5116-116">einem Zeichenliteral.</span><span class="sxs-lookup"><span data-stu-id="d5116-116">a character literal.</span></span>
- <span data-ttu-id="d5116-117">einer Escapesequenz für Unicodezeichen, d. h. `\u` gefolgt von der aus vier Symbolen bestehenden Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="d5116-117">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="d5116-118">einer Escapesequenz für Hexadezimalzahlen, d. h. `\x` gefolgt von der Hexadezimaldarstellung eines Zeichencodes.</span><span class="sxs-lookup"><span data-stu-id="d5116-118">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](snippets/CharType.cs#Literals)]

<span data-ttu-id="d5116-119">Wie das obige Beispiel zeigt, können Sie den Wert eines Zeichencodes auch in den entsprechenden `char`-Wert umwandeln.</span><span class="sxs-lookup"><span data-stu-id="d5116-119">As the preceding example shows, you can also cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="d5116-120">Im Falle einer Escapesequenz für Unicodezeichen müssen Sie alle vier Hexadezimalziffern angeben.</span><span class="sxs-lookup"><span data-stu-id="d5116-120">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="d5116-121">`\u006A` ist also eine gültige Escapesequenz, `\u06A` und `\u6A` sind hingegen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="d5116-121">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="d5116-122">Bei einer Escapesequenz für Hexadezimalzahlen können Sie die führenden Nullen weglassen.</span><span class="sxs-lookup"><span data-stu-id="d5116-122">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="d5116-123">Die Escapesequenzen `\x006A`, `\x06A` und `\x6A` sind also gültig und entsprechen demselben Zeichen.</span><span class="sxs-lookup"><span data-stu-id="d5116-123">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="d5116-124">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d5116-124">Conversions</span></span>

<span data-ttu-id="d5116-125">Der `char`-Typ kann implizit in die folgenden [ganzzahligen](integral-numeric-types.md) Typen konvertiert werden: `ushort`, `int`, `uint`, `long` und `ulong`.</span><span class="sxs-lookup"><span data-stu-id="d5116-125">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="d5116-126">Zudem lässt er sich auch implizit in diese integrierten numerischen [Gleitkommatypen](floating-point-numeric-types.md) konvertieren: `float`, `double` und `decimal`.</span><span class="sxs-lookup"><span data-stu-id="d5116-126">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="d5116-127">Er kann explizit in die ganzzahligen Typen `sbyte`, `byte` und `short` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="d5116-127">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="d5116-128">Es gibt keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="d5116-128">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="d5116-129">Alle [ganzzahligen](integral-numeric-types.md) numerischen Typen oder numerischen [Gleitkommatypen](floating-point-numeric-types.md) lassen sich jedoch explizit in `char` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d5116-129">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d5116-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d5116-130">C# language specification</span></span>

<span data-ttu-id="d5116-131">Weitere Informationen finden Sie im Abschnitt [Integrale Typen](~/_csharplang/spec/types.md#integral-types) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d5116-131">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5116-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5116-132">See also</span></span>

- [<span data-ttu-id="d5116-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d5116-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d5116-134">Werttypen</span><span class="sxs-lookup"><span data-stu-id="d5116-134">Value types</span></span>](value-types.md)
- [<span data-ttu-id="d5116-135">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="d5116-135">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Text.Rune?displayProperty=nameWithType>
- [<span data-ttu-id="d5116-136">Zeichencodierung in .NET</span><span class="sxs-lookup"><span data-stu-id="d5116-136">Character encoding in .NET</span></span>](../../../standard/base-types/character-encoding-introduction.md)
