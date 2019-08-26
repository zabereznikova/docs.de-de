---
title: char-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 754c04bfc3b4090906420d55d55e51606b72f187
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605948"
---
# <a name="char-c-reference"></a><span data-ttu-id="71415-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="71415-102">char (C# Reference)</span></span>

<span data-ttu-id="71415-103">Das Schlüsselwort `char` wird zur Deklaration einer Instanz der <xref:System.Char?displayProperty=nameWithType>-Struktur verwendet, die das Framework zur Repräsentation eines Unicode-Zeichens verwendet.</span><span class="sxs-lookup"><span data-stu-id="71415-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="71415-104">Der Wert eines `Char`-Objekts ist ein numerischer 16-Bit-Wert (ordinal).</span><span class="sxs-lookup"><span data-stu-id="71415-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="71415-105">Unicode-Zeichen werden zur Repräsentation der meisten geschriebenen Sprachen auf der ganzen Welt verwendet.</span><span class="sxs-lookup"><span data-stu-id="71415-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="71415-106">Typ</span><span class="sxs-lookup"><span data-stu-id="71415-106">Type</span></span>|<span data-ttu-id="71415-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="71415-107">Range</span></span>|<span data-ttu-id="71415-108">Größe</span><span class="sxs-lookup"><span data-stu-id="71415-108">Size</span></span>|<span data-ttu-id="71415-109">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="71415-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="71415-110">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="71415-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="71415-111">Ein Unicode-Zeichen (16 Bit)</span><span class="sxs-lookup"><span data-stu-id="71415-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="71415-112">Literale</span><span class="sxs-lookup"><span data-stu-id="71415-112">Literals</span></span>

<span data-ttu-id="71415-113">Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="71415-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="71415-114">Sie können auch die ganzzahligen Zeichencodes umwandeln.</span><span class="sxs-lookup"><span data-stu-id="71415-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="71415-115">Im folgenden Beispiel werden vier `char`-Variablen mit dem gleichen Zeichen `X` initialisiert:</span><span class="sxs-lookup"><span data-stu-id="71415-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="71415-116">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="71415-116">Conversions</span></span>

<span data-ttu-id="71415-117">Ein `char` kann implizit in ein [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md) oder [decimal](../builtin-types/floating-point-numeric-types.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="71415-117">A `char` can be implicitly converted to [ushort](../builtin-types/integral-numeric-types.md), [int](../builtin-types/integral-numeric-types.md), [uint](../builtin-types/integral-numeric-types.md), [double](../builtin-types/floating-point-numeric-types.md), or [decimal](../builtin-types/floating-point-numeric-types.md).</span></span> <span data-ttu-id="71415-118">Es gibt allerdings keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="71415-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="71415-119">Der Typ <xref:System.Char?displayProperty=nameWithType> stellt einige statistische Methoden für das Arbeiten mit `char`-Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="71415-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="71415-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="71415-120">C# language specification</span></span>  

<span data-ttu-id="71415-121">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="71415-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="71415-122">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="71415-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="71415-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71415-123">See also</span></span>

- <xref:System.Char>
- [<span data-ttu-id="71415-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="71415-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="71415-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="71415-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="71415-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="71415-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="71415-127">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="71415-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="71415-128">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="71415-128">Built-In Types Table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="71415-129">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="71415-129">Implicit Numeric Conversions Table</span></span>](./implicit-numeric-conversions-table.md)
- [<span data-ttu-id="71415-130">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="71415-130">Explicit Numeric Conversions Table</span></span>](./explicit-numeric-conversions-table.md)
- [<span data-ttu-id="71415-131">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="71415-131">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="71415-132">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="71415-132">Strings</span></span>](../../programming-guide/strings/index.md)
