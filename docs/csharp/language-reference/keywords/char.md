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
ms.openlocfilehash: 6acb40117c4f59deb084965cb3db9e4a96f7f61a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242346"
---
# <a name="char-c-reference"></a><span data-ttu-id="6e520-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6e520-102">char (C# Reference)</span></span>

<span data-ttu-id="6e520-103">Das Schlüsselwort `char` wird zur Deklaration einer Instanz der <xref:System.Char?displayProperty=nameWithType>-Struktur verwendet, die das Framework zur Repräsentation eines Unicode-Zeichens verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e520-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="6e520-104">Der Wert eines `Char`-Objekts ist ein numerischer 16-Bit-Wert (ordinal).</span><span class="sxs-lookup"><span data-stu-id="6e520-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>

 <span data-ttu-id="6e520-105">Unicode-Zeichen werden zur Repräsentation der meisten geschriebenen Sprachen auf der ganzen Welt verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e520-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>

|<span data-ttu-id="6e520-106">Typ</span><span class="sxs-lookup"><span data-stu-id="6e520-106">Type</span></span>|<span data-ttu-id="6e520-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="6e520-107">Range</span></span>|<span data-ttu-id="6e520-108">Größe</span><span class="sxs-lookup"><span data-stu-id="6e520-108">Size</span></span>|<span data-ttu-id="6e520-109">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="6e520-109">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="6e520-110">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="6e520-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="6e520-111">Ein Unicode-Zeichen (16 Bit)</span><span class="sxs-lookup"><span data-stu-id="6e520-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="6e520-112">Literale</span><span class="sxs-lookup"><span data-stu-id="6e520-112">Literals</span></span>

<span data-ttu-id="6e520-113">Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6e520-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="6e520-114">Sie können auch die ganzzahligen Zeichencodes umwandeln.</span><span class="sxs-lookup"><span data-stu-id="6e520-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="6e520-115">Im folgenden Beispiel werden vier `char`-Variablen mit dem gleichen Zeichen `X` initialisiert:</span><span class="sxs-lookup"><span data-stu-id="6e520-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="6e520-116">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="6e520-116">Conversions</span></span>

<span data-ttu-id="6e520-117">Ein `char` kann implizit in ein [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e520-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="6e520-118">Es gibt allerdings keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="6e520-118">However, there are no implicit conversions from other types to the `char` type.</span></span>

<span data-ttu-id="6e520-119">Der Typ <xref:System.Char?displayProperty=nameWithType> stellt einige statistische Methoden für das Arbeiten mit `char`-Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="6e520-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6e520-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6e520-120">C# language specification</span></span>  

<span data-ttu-id="6e520-121">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6e520-121">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="6e520-122">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="6e520-122">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e520-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e520-123">See also</span></span>

- <xref:System.Char>  
- [<span data-ttu-id="6e520-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6e520-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6e520-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6e520-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6e520-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6e520-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="6e520-127">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="6e520-127">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="6e520-128">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="6e520-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="6e520-129">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="6e520-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="6e520-130">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="6e520-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="6e520-131">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="6e520-131">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
- [<span data-ttu-id="6e520-132">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6e520-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)