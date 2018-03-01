---
title: char (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 41f672e9b12481fa5cce78015e95d2c5245a26db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="char-c-reference"></a><span data-ttu-id="a6bf7-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a6bf7-102">char (C# Reference)</span></span>
<span data-ttu-id="a6bf7-103">Das Schlüsselwort `char` wird zur Deklaration einer Instanz der <xref:System.Char?displayProperty=nameWithType>-Struktur verwendet, die das Framework zur Repräsentation eines Unicode-Zeichens verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="a6bf7-104">Der Wert eines `Char`-Objekts ist ein numerischer 16-Bit-Wert (ordinal).</span><span class="sxs-lookup"><span data-stu-id="a6bf7-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="a6bf7-105">Unicode-Zeichen werden zur Repräsentation der meisten geschriebenen Sprachen auf der ganzen Welt verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="a6bf7-106">Typ</span><span class="sxs-lookup"><span data-stu-id="a6bf7-106">Type</span></span>|<span data-ttu-id="a6bf7-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="a6bf7-107">Range</span></span>|<span data-ttu-id="a6bf7-108">Größe</span><span class="sxs-lookup"><span data-stu-id="a6bf7-108">Size</span></span>|<span data-ttu-id="a6bf7-109">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="a6bf7-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="a6bf7-110">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="a6bf7-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="a6bf7-111">Ein Unicode-Zeichen (16 Bit)</span><span class="sxs-lookup"><span data-stu-id="a6bf7-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="a6bf7-112">Literale</span><span class="sxs-lookup"><span data-stu-id="a6bf7-112">Literals</span></span>  
 <span data-ttu-id="a6bf7-113">Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="a6bf7-114">Sie können auch die ganzzahligen Zeichencodes umwandeln.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="a6bf7-115">Im folgenden Beispiel werden vier `char`-Variablen mit dem gleichen Zeichen `X` initialisiert:</span><span class="sxs-lookup"><span data-stu-id="a6bf7-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a><span data-ttu-id="a6bf7-116">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="a6bf7-116">Conversions</span></span>  
 <span data-ttu-id="a6bf7-117">Ein `char` kann implizit in ein [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="a6bf7-118">Es gibt allerdings keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-118">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="a6bf7-119">Der Typ <xref:System.Char?displayProperty=nameWithType> stellt einige statistische Methoden für das Arbeiten mit `char`-Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="a6bf7-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a6bf7-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="a6bf7-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6bf7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6bf7-121">See Also</span></span>  
 <xref:System.Char>  
 [<span data-ttu-id="a6bf7-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a6bf7-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a6bf7-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a6bf7-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a6bf7-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a6bf7-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a6bf7-125">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="a6bf7-125">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="a6bf7-126">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="a6bf7-126">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="a6bf7-127">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="a6bf7-127">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="a6bf7-128">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="a6bf7-128">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="a6bf7-129">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="a6bf7-129">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="a6bf7-130">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a6bf7-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
