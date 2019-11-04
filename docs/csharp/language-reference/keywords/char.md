---
title: char-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771802"
---
# <a name="char-c-reference"></a><span data-ttu-id="b2c4b-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b2c4b-102">char (C# reference)</span></span>

<span data-ttu-id="b2c4b-103">Das Schlüsselwort vom Typ `char` ist ein Alias für den .NET-<xref:System.Char?displayProperty=nameWithType>-Strukturtyp, der ein Unicode-UTF-16-Zeichen darstellt:</span><span class="sxs-lookup"><span data-stu-id="b2c4b-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="b2c4b-104">Typ</span><span class="sxs-lookup"><span data-stu-id="b2c4b-104">Type</span></span>|<span data-ttu-id="b2c4b-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="b2c4b-105">Range</span></span>|<span data-ttu-id="b2c4b-106">Größe</span><span class="sxs-lookup"><span data-stu-id="b2c4b-106">Size</span></span>|<span data-ttu-id="b2c4b-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="b2c4b-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="b2c4b-108">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="b2c4b-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="b2c4b-109">16 Bit</span><span class="sxs-lookup"><span data-stu-id="b2c4b-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="b2c4b-110">Literale</span><span class="sxs-lookup"><span data-stu-id="b2c4b-110">Literals</span></span>

<span data-ttu-id="b2c4b-111">Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="b2c4b-112">Sie können auch einen ganzzahligen Zeichencode in den entsprechenden `char`-Wert umwandeln.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="b2c4b-113">Im folgenden Beispiel werden die vier Elemente eines `char`-Arrays mit dem gleichen Zeichen `X` initialisiert:</span><span class="sxs-lookup"><span data-stu-id="b2c4b-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="b2c4b-114">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b2c4b-114">Conversions</span></span>

<span data-ttu-id="b2c4b-115">Der `char`-Typ kann implizit in die folgenden [ganzzahligen](../builtin-types/integral-numeric-types.md) Typen konvertiert werden: `ushort`, `int`, `uint`, `long` und `ulong`.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="b2c4b-116">Zudem lässt er sich auch implizit in diese integrierten numerischen [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) konvertieren: `float`, `double` und `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="b2c4b-117">Er kann explizit in die ganzzahligen Typen `sbyte`, `byte` und `short` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="b2c4b-118">Es gibt keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="b2c4b-119">Alle [ganzzahligen](../builtin-types/integral-numeric-types.md) numerischen Typen oder numerischen [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) lassen sich jedoch explizit in `char` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b2c4b-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b2c4b-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b2c4b-120">C# language specification</span></span>

<span data-ttu-id="b2c4b-121">Weitere Informationen finden Sie im Abschnitt [Integrale Typen](~/_csharplang/spec/types.md#integral-types) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="b2c4b-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2c4b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2c4b-122">See also</span></span>

- [<span data-ttu-id="b2c4b-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b2c4b-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b2c4b-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b2c4b-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="b2c4b-125">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="b2c4b-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="b2c4b-126">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b2c4b-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
