---
title: char (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c6601a58804d6ecfcbedbc19da09560884e54e7f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="char-c-reference"></a><span data-ttu-id="b26ea-102">char (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b26ea-102">char (C# Reference)</span></span>
<span data-ttu-id="b26ea-103">Das Schlüsselwort `char` wird zur Deklaration einer Instanz der <xref:System.Char?displayProperty=fullName>-Struktur verwendet, die das Framework zur Repräsentation eines Unicode-Zeichens verwendet.</span><span class="sxs-lookup"><span data-stu-id="b26ea-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=fullName> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="b26ea-104">Der Wert eines `Char`-Objekts ist ein numerischer 16-Bit-Wert (ordinal).</span><span class="sxs-lookup"><span data-stu-id="b26ea-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="b26ea-105">Unicode-Zeichen werden zur Repräsentation der meisten geschriebenen Sprachen auf der ganzen Welt verwendet.</span><span class="sxs-lookup"><span data-stu-id="b26ea-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="b26ea-106">Typ</span><span class="sxs-lookup"><span data-stu-id="b26ea-106">Type</span></span>|<span data-ttu-id="b26ea-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="b26ea-107">Range</span></span>|<span data-ttu-id="b26ea-108">Größe</span><span class="sxs-lookup"><span data-stu-id="b26ea-108">Size</span></span>|<span data-ttu-id="b26ea-109">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="b26ea-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="b26ea-110">U+0000 in U+FFFF</span><span class="sxs-lookup"><span data-stu-id="b26ea-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="b26ea-111">Ein Unicode-Zeichen (16 Bit)</span><span class="sxs-lookup"><span data-stu-id="b26ea-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="b26ea-112">Literale</span><span class="sxs-lookup"><span data-stu-id="b26ea-112">Literals</span></span>  
 <span data-ttu-id="b26ea-113">Konstanten des Typ `char` können als Zeichenliterale, als Escapesequenz für Hexadezimalzahlen oder als Unicode-Repräsentation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b26ea-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="b26ea-114">Sie können auch die ganzzahligen Zeichencodes umwandeln.</span><span class="sxs-lookup"><span data-stu-id="b26ea-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="b26ea-115">Im folgenden Beispiel werden vier `char`-Variablen mit dem gleichen Zeichen `X` initialisiert:</span><span class="sxs-lookup"><span data-stu-id="b26ea-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 <span data-ttu-id="b26ea-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b26ea-116">[!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="b26ea-117">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b26ea-117">Conversions</span></span>  
 <span data-ttu-id="b26ea-118">Ein `char` kann implizit in ein [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b26ea-118">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="b26ea-119">Es gibt allerdings keine impliziten Konvertierungen anderen Typen in Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="b26ea-119">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="b26ea-120">Der Typ <xref:System.Char?displayProperty=fullName> stellt einige statistische Methoden für das Arbeiten mit `char`-Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="b26ea-120">The <xref:System.Char?displayProperty=fullName> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b26ea-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b26ea-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b26ea-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b26ea-122">See Also</span></span>  
 <span data-ttu-id="b26ea-123"><xref:System.Char></span><span class="sxs-lookup"><span data-stu-id="b26ea-123"><xref:System.Char></span></span>   
 <span data-ttu-id="b26ea-124">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b26ea-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b26ea-126">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b26ea-127">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-127">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="b26ea-128">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-128">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="b26ea-129">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-129">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="b26ea-130">[Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-130">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="b26ea-131">[Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="b26ea-131">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="b26ea-132">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b26ea-132">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

