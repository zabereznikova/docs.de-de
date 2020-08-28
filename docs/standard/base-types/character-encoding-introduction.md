---
title: Einführung in die char-Codierung in .NET
description: Hier erfahren Sie mehr über die char-Codierung und -Decodierung in .NET.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: a5d838176bf4437a295ebe6c2cea8b1fe0eeeb61
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656292"
---
# <a name="character-encoding-in-net"></a><span data-ttu-id="0e651-103">Zeichencodierung in .NET</span><span class="sxs-lookup"><span data-stu-id="0e651-103">Character encoding in .NET</span></span>

<span data-ttu-id="0e651-104">Dieser Artikel bietet eine Einführung in die von .NET verwendeten char-Codierungssysteme.</span><span class="sxs-lookup"><span data-stu-id="0e651-104">This article provides an introduction to character encoding systems that are used by .NET.</span></span> <span data-ttu-id="0e651-105">Es wird erläutert, wie die Typen <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune> und <xref:System.Globalization.StringInfo> mit Unicode, UTF-16 und UTF-8 funktionieren.</span><span class="sxs-lookup"><span data-stu-id="0e651-105">The article explains how the <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune>, and <xref:System.Globalization.StringInfo> types work with Unicode, UTF-16, and UTF-8.</span></span>

<span data-ttu-id="0e651-106">Der Begriff *char* wird hier im allgemeinen Sinn für ein Zeichen verwendet, das *vom Leser als einzelnes Anzeigeelement wahrgenommen wird*.</span><span class="sxs-lookup"><span data-stu-id="0e651-106">The term *character* is used here in the general sense of *what a reader perceives as a single display element*.</span></span> <span data-ttu-id="0e651-107">Gängige Beispiele sind der Buchstabe „a“, das Symbol „@“ und das Emoji 🐂.</span><span class="sxs-lookup"><span data-stu-id="0e651-107">Common examples are the letter "a", the symbol "@", and the emoji "🐂".</span></span> <span data-ttu-id="0e651-108">Mitunter setzt sich ein als ein Zeichen wahrgenommenes char tatsächlich aus mehreren unabhängigen Anzeigeelementen zusammen. Dies wird im Abschnitt zu [Graphemhaufen](#grapheme-clusters) erläutert.</span><span class="sxs-lookup"><span data-stu-id="0e651-108">Sometimes what looks like one character is actually composed of multiple independent display elements, as the section on [grapheme clusters](#grapheme-clusters) explains.</span></span>

## <a name="the-no-locstring-and-no-locchar-types"></a><span data-ttu-id="0e651-109">Die string- und char-Typen.</span><span class="sxs-lookup"><span data-stu-id="0e651-109">The string and char types</span></span>

<span data-ttu-id="0e651-110">Eine Instanz der [string](xref:System.String)-Klasse stellt Text dar.</span><span class="sxs-lookup"><span data-stu-id="0e651-110">An instance of the [string](xref:System.String) class represents some text.</span></span> <span data-ttu-id="0e651-111">Ein `string` ist logisch gesehen eine Abfolge von 16-Bit-Werten, von denen jeder eine Instanz der [char](xref:System.Char)-Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="0e651-111">A `string` is logically a sequence of 16-bit values, each of which is an instance of the [char](xref:System.Char) struct.</span></span> <span data-ttu-id="0e651-112">Die [string.Length](xref:System.String.Length)-Eigenschaft gibt die Anzahl von `char`-Instanzen in der `string`-Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="0e651-112">The [string.Length](xref:System.String.Length) property returns the number of `char` instances in the `string` instance.</span></span>

<span data-ttu-id="0e651-113">Die folgende Beispielfunktion gibt die Werte aller `char`-Instanzen in einem `string` in Hexadezimalnotation zurück:</span><span class="sxs-lookup"><span data-stu-id="0e651-113">The following sample function prints out the values in hexadecimal notation of all the `char` instances in a `string`:</span></span>

<span data-ttu-id="0e651-114">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::</span><span class="sxs-lookup"><span data-stu-id="0e651-114">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::</span></span>

<span data-ttu-id="0e651-115">Wenn Sie an diese Funktion die string „Hello“ übergeben, erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0e651-115">Pass the string "Hello" to this function, and you get the following output:</span></span>

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

<span data-ttu-id="0e651-116">Jedes char wird durch einen einzelnen `char`-Wert repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="0e651-116">Each character is represented by a single `char` value.</span></span> <span data-ttu-id="0e651-117">Dieses Muster gilt für die meisten Sprachen der Welt.</span><span class="sxs-lookup"><span data-stu-id="0e651-117">That pattern holds true for most of the world's languages.</span></span> <span data-ttu-id="0e651-118">Beispielsweise sehen Sie nachfolgend die Ausgabe für zwei chinesische char, die ausgesprochen wie *nǐ hǎo* klingen und *Hallo* bedeuten:</span><span class="sxs-lookup"><span data-stu-id="0e651-118">For example, here's the output for two Chinese characters that sound like *nǐ hǎo* and mean *Hello*:</span></span>

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

<span data-ttu-id="0e651-119">Für einige Sprachen und für einige Symbole und Emojis werden jedoch zwei `char`-Instanzen benötigt, um ein einzelnes char darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e651-119">However, for some languages and for some symbols and emoji, it takes two `char` instances to represent a single character.</span></span> <span data-ttu-id="0e651-120">Vergleichen Sie beispielsweise die char und `char`-Instanzen in dem Wort, das in der Osage-Sprache *Osage* bedeutet:</span><span class="sxs-lookup"><span data-stu-id="0e651-120">For example, compare the characters and `char` instances in the word that means *Osage* in the Osage language:</span></span>

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

<span data-ttu-id="0e651-121">Im vorherigen Beispiel wird jedes char mit Ausnahme des Leerzeichens durch zwei `char`-Instanzen repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="0e651-121">In the preceding example, each character except the space is represented by two `char` instances.</span></span>

<span data-ttu-id="0e651-122">Ein einzelnes Unicode-Emoji wird ebenfalls durch zwei `char`s dargestellt, wie im folgenden Beispiel eines Emojis für einen Ochsen:</span><span class="sxs-lookup"><span data-stu-id="0e651-122">A single Unicode emoji is also represented by two `char`s, as seen in the following example showing an ox emoji:</span></span>

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

<span data-ttu-id="0e651-123">Diese Beispiele zeigen, dass der Wert von `string.Length`, der die Anzahl von `char`-Instanzen angibt, nicht notwendigerweise der Anzahl angezeigter char entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="0e651-123">These examples show that the value of `string.Length`, which indicates the number of `char` instances, doesn't necessarily indicate the number of displayed characters.</span></span> <span data-ttu-id="0e651-124">Eine einzelne `char`-Instanz repräsentiert für sich genommen nicht zwingend ein char.</span><span class="sxs-lookup"><span data-stu-id="0e651-124">A single `char` instance by itself doesn't necessarily represent a character.</span></span>

<span data-ttu-id="0e651-125">Die `char`-Paare, die einem einzelnen char zugeordnet sind, werden als *Ersatzzeichenpaare* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e651-125">The `char` pairs that map to a single character are called *surrogate pairs*.</span></span> <span data-ttu-id="0e651-126">Um deren Funktionsweise zu verstehen, müssen wir die Unicode- und die UTF-16-Codierung verstehen.</span><span class="sxs-lookup"><span data-stu-id="0e651-126">To understand how they work, you need to understand Unicode and UTF-16 encoding.</span></span>

## <a name="unicode-code-points"></a><span data-ttu-id="0e651-127">Unicode-Codepunkte</span><span class="sxs-lookup"><span data-stu-id="0e651-127">Unicode code points</span></span>

<span data-ttu-id="0e651-128">Unicode ist ein internationaler Codierungsstandard, der in zahlreichen Plattformen und mit verschiedenen Sprachen und Skripts eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="0e651-128">Unicode is an international encoding standard for use on various platforms and with various languages and scripts.</span></span>

<span data-ttu-id="0e651-129">Der Unicode-Standard definiert über 1,1 Millionen [Codepunkte](https://www.unicode.org/glossary/#code_point).</span><span class="sxs-lookup"><span data-stu-id="0e651-129">The Unicode Standard defines over 1.1 million [code points](https://www.unicode.org/glossary/#code_point).</span></span> <span data-ttu-id="0e651-130">Ein Codepunkt ist ein ganzzahliger Wert, der zwischen 0 und `U+10FFFF` liegen kann (in Dezimalschreibweise: 1.114.111).</span><span class="sxs-lookup"><span data-stu-id="0e651-130">A code point is an integer value that can range from 0 to `U+10FFFF` (decimal 1,114,111).</span></span> <span data-ttu-id="0e651-131">Einige Codepunkte sind Buchstaben, Symbolen oder Emojis zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0e651-131">Some code points are assigned to letters, symbols, or emoji.</span></span> <span data-ttu-id="0e651-132">Andere sind Aktionen zugeordnet, die steuern, wie Textelemente oder char angezeigt werden – beispielsweise ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="0e651-132">Others are assigned to actions that control how text or characters are displayed, such as advance to a new line.</span></span> <span data-ttu-id="0e651-133">Viele Codepunkte sind noch nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0e651-133">Many code points are not yet assigned.</span></span>

<span data-ttu-id="0e651-134">Nachfolgend werden einige Beispiele für Codepunktzuweisungen aufgelistet, mit Links zu Unicode-charts, in denen sie angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="0e651-134">Here are some examples of code point assignments, with links to Unicode charts in which they appear:</span></span>

|<span data-ttu-id="0e651-135">Decimal</span><span class="sxs-lookup"><span data-stu-id="0e651-135">Decimal</span></span>|<span data-ttu-id="0e651-136">Hex</span><span class="sxs-lookup"><span data-stu-id="0e651-136">Hex</span></span>       |<span data-ttu-id="0e651-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e651-137">Example</span></span>|<span data-ttu-id="0e651-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e651-138">Description</span></span>|
|------:|----------|-------|-----------|
|<span data-ttu-id="0e651-139">10</span><span class="sxs-lookup"><span data-stu-id="0e651-139">10</span></span>     | `U+000A` |<span data-ttu-id="0e651-140">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="0e651-140">N/A</span></span>| <span data-ttu-id="0e651-141">[ZEILENVORSCHUB](https://www.unicode.org/charts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="0e651-141">[LINE FEED](https://www.unicode.org/charts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="0e651-142">65</span><span class="sxs-lookup"><span data-stu-id="0e651-142">65</span></span>     | `U+0061` | <span data-ttu-id="0e651-143">a</span><span class="sxs-lookup"><span data-stu-id="0e651-143">a</span></span> | <span data-ttu-id="0e651-144">[LATEINISCHER KLEINBUCHSTABE A](https://www.unicode.org/charts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="0e651-144">[LATIN SMALL LETTER A](https://www.unicode.org/charts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="0e651-145">562</span><span class="sxs-lookup"><span data-stu-id="0e651-145">562</span></span>    | `U+0232` | <span data-ttu-id="0e651-146">Ȳ</span><span class="sxs-lookup"><span data-stu-id="0e651-146">Ȳ</span></span> | <span data-ttu-id="0e651-147">[LATEINISCHER GROSSBUCHSTABE MIT MAKRON](https://www.unicode.org/charts/PDF/U0180.pdf)</span><span class="sxs-lookup"><span data-stu-id="0e651-147">[LATIN CAPITAL LETTER Y WITH MACRON](https://www.unicode.org/charts/PDF/U0180.pdf)</span></span> |
|<span data-ttu-id="0e651-148">68.675</span><span class="sxs-lookup"><span data-stu-id="0e651-148">68,675</span></span> | `U+10C43`| <span data-ttu-id="0e651-149">𐱃</span><span class="sxs-lookup"><span data-stu-id="0e651-149">𐱃</span></span> | <span data-ttu-id="0e651-150">[ALTTÜRKISCHES ORCHON-SCHRIFTZEICHEN AT](https://www.unicode.org/charts/PDF/U10C00.pdf)</span><span class="sxs-lookup"><span data-stu-id="0e651-150">[OLD TURKIC LETTER ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf)</span></span> |
|<span data-ttu-id="0e651-151">127.801</span><span class="sxs-lookup"><span data-stu-id="0e651-151">127,801</span></span>| `U+1F339`| <span data-ttu-id="0e651-152">🌹</span><span class="sxs-lookup"><span data-stu-id="0e651-152">🌹</span></span> | <span data-ttu-id="0e651-153">[Rosen-Emoji](https://www.unicode.org/charts/PDF/U1F300.pdf)</span><span class="sxs-lookup"><span data-stu-id="0e651-153">[ROSE emoji](https://www.unicode.org/charts/PDF/U1F300.pdf)</span></span> |

<span data-ttu-id="0e651-154">Auf Codepunkte wird hauptsächlich durch Verwendung der Syntax `U+xxxx` verwiesen, wobei es sich bei `xxxx` um den ganzzahligen Wert in Hexadezimalcodierung handelt.</span><span class="sxs-lookup"><span data-stu-id="0e651-154">Code points are customarily referred to by using the syntax `U+xxxx`, where `xxxx` is the hex-encoded integer value.</span></span>

<span data-ttu-id="0e651-155">Der vollständige Bereich der Codepunkte enthält zwei Unterbereiche:</span><span class="sxs-lookup"><span data-stu-id="0e651-155">Within the full range of code points there are two subranges:</span></span>

* <span data-ttu-id="0e651-156">Die **Basic Multilingual Plane (BMP)** im Bereich `U+0000..U+FFFF`.</span><span class="sxs-lookup"><span data-stu-id="0e651-156">The **Basic Multilingual Plane (BMP)** in the range `U+0000..U+FFFF`.</span></span> <span data-ttu-id="0e651-157">Dieser 16-Bit-Bereich umfasst 65.536 Codepunkte und reicht zur Abdeckung der meisten Schriftsysteme der Welt aus.</span><span class="sxs-lookup"><span data-stu-id="0e651-157">This 16-bit range provides 65,536 code points, enough to cover the majority of the world's writing systems.</span></span>
* <span data-ttu-id="0e651-158">**Ergänzende Codepunkte** im Bereich `U+10000..U+10FFFF`.</span><span class="sxs-lookup"><span data-stu-id="0e651-158">**Supplementary code points** in the range `U+10000..U+10FFFF`.</span></span> <span data-ttu-id="0e651-159">Dieser 21-Bit-Bereich umfasst mehr als eine Million zusätzlicher Codepunkte, die für weniger bekannte Sprachen und zu anderen Zwecken genutzt werden können, wie beispielsweise Emojis.</span><span class="sxs-lookup"><span data-stu-id="0e651-159">This 21-bit range provides more than a million additional code points that can be used for less well-known languages and other purposes such as emojis.</span></span>

<span data-ttu-id="0e651-160">Das folgende Diagramm veranschaulicht die Beziehung zwischen der BMP und den ergänzenden Codepunkten.</span><span class="sxs-lookup"><span data-stu-id="0e651-160">The following diagram illustrates the relationship between the BMP and the supplementary code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP und ergänzende Codepunkte":::

## <a name="utf-16-code-units"></a><span data-ttu-id="0e651-162">UTF-16-Codeeinheiten</span><span class="sxs-lookup"><span data-stu-id="0e651-162">UTF-16 code units</span></span>

<span data-ttu-id="0e651-163">16-Bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) ist ein char-Codierungssystem, das *16-Bit-Codeeinheiten* zur Darstellung von Unicode-Codepunkten verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e651-163">16-bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) is a character encoding system that uses 16-bit *code units* to represent Unicode code points.</span></span> <span data-ttu-id="0e651-164">.NET verwendet UTF-16 zum Codieren von Text in einem `string`.</span><span class="sxs-lookup"><span data-stu-id="0e651-164">.NET uses UTF-16 to encode the text in a `string`.</span></span> <span data-ttu-id="0e651-165">Eine `char`-Instanz repräsentiert eine 16-Bit-Codeeinheit.</span><span class="sxs-lookup"><span data-stu-id="0e651-165">A `char` instance represents a 16-bit code unit.</span></span>

<span data-ttu-id="0e651-166">Eine einzelne 16-Bit-Codeeinheit kann jeden Codepunkt im 16-Bit-Bereich der Basic Multilingual Plane (BMP) repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="0e651-166">A single 16-bit code unit can represent any code point in the 16-bit range of the Basic Multilingual Plane.</span></span> <span data-ttu-id="0e651-167">Aber für einen Codepunkt im ergänzenden Bereich werden zwei `char`-Instanzen benötigt.</span><span class="sxs-lookup"><span data-stu-id="0e651-167">But for a code point in the supplementary range, two `char` instances are needed.</span></span>

## <a name="surrogate-pairs"></a><span data-ttu-id="0e651-168">Ersatzzeichenpaare</span><span class="sxs-lookup"><span data-stu-id="0e651-168">Surrogate pairs</span></span>

<span data-ttu-id="0e651-169">Die Übersetzung von zwei 16-Bit-Werten in einen einzelnen 21-Bit-Wert wird durch einen speziellen Bereich ermöglicht, der die sogenannten *Ersatzcodepunkte* von `U+D800` bis `U+DFFF` einschließlich (in Dezimalschreibweise: 55.296 bis 57.343) umfasst.</span><span class="sxs-lookup"><span data-stu-id="0e651-169">The translation of two 16-bit values to a single 21-bit value is facilitated by a special range called the *surrogate code points*, from `U+D800` to `U+DFFF` (decimal 55,296 to 57,343), inclusive.</span></span>

<span data-ttu-id="0e651-170">Das folgende Diagramm veranschaulicht die Beziehung zwischen der BMP und den Ersatzcodepunkten.</span><span class="sxs-lookup"><span data-stu-id="0e651-170">The following diagram illustrates the relationship between the BMP and the surrogate code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="BMP und Ersatzcodepunkte":::

<span data-ttu-id="0e651-172">Wenn auf einen *hohen* Ersatzcodepunkt (`U+D800..U+DBFF`) unmittelbar ein *niedriger* Ersatzcodepunkt (`U+DC00..U+DFFF`) folgt, wird das Paar anhand der folgenden Formel als ergänzender Codepunkt interpretiert:</span><span class="sxs-lookup"><span data-stu-id="0e651-172">When a *high surrogate* code point (`U+D800..U+DBFF`) is immediately followed by a *low surrogate* code point (`U+DC00..U+DFFF`), the pair is interpreted as a supplementary code point by using the following formula:</span></span>

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

<span data-ttu-id="0e651-173">Nachstehend sehen Sie die gleiche Formel unter Verwendung der Dezimalschreibweise:</span><span class="sxs-lookup"><span data-stu-id="0e651-173">Here's the same formula using decimal notation:</span></span>

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

<span data-ttu-id="0e651-174">Ein *hoher* Ersatzcodepunkt weist keinen höheren Zahlenwert auf als ein *niedriger* Ersatzcodepunkt.</span><span class="sxs-lookup"><span data-stu-id="0e651-174">A *high* surrogate code point doesn't have a higher number value than a *low* surrogate code point.</span></span> <span data-ttu-id="0e651-175">Der hohe Ersatzcodepunkt wird so bezeichnet, weil er zum Berechnen der hohen 11 Bits des vollständigen 21-Bit-Codepunktbereichs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e651-175">The high surrogate code point is called "high" because it's used to calculate the higher-order 11 bits of the full 21-bit code point range.</span></span> <span data-ttu-id="0e651-176">Der niedrige Ersatzcodepunkt wird zum Berechnen der unteren 10 Bits verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e651-176">The low surrogate code point is used to calculate the lower-order 10 bits.</span></span>

<span data-ttu-id="0e651-177">Beispielsweise wird der tatsächliche Codepunkt, der dem Ersatzzeichenpaar `0xD83C` und `0xDF39` entspricht, folgendermaßen berechnet:</span><span class="sxs-lookup"><span data-stu-id="0e651-177">For example, the actual code point that corresponds to the surrogate pair `0xD83C` and `0xDF39`  is computed as follows:</span></span>

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

<span data-ttu-id="0e651-178">Hier dieselbe Berechnung in Dezimalschreibweise:</span><span class="sxs-lookup"><span data-stu-id="0e651-178">Here's the same calculation using decimal notation:</span></span>

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

<span data-ttu-id="0e651-179">Das vorstehende Beispiel zeigt, dass es sich bei `"\ud83c\udf39"` um die UTF-16-Codierung des zuvor erwähnten Codepunkts `U+1F339 ROSE ('🌹')` handelt.</span><span class="sxs-lookup"><span data-stu-id="0e651-179">The preceding example demonstrates that `"\ud83c\udf39"` is the UTF-16 encoding of the `U+1F339 ROSE ('🌹')` code point mentioned earlier.</span></span>

## <a name="unicode-scalar-values"></a><span data-ttu-id="0e651-180">Unicode-Skalarwerte</span><span class="sxs-lookup"><span data-stu-id="0e651-180">Unicode scalar values</span></span>

<span data-ttu-id="0e651-181">Der Begriff [Unicode-Skalarwert](https://www.unicode.org/glossary/#unicode_scalar_value) bezieht sich auf alle Codepunkte mit Ausnahme der Ersatzcodepunkte.</span><span class="sxs-lookup"><span data-stu-id="0e651-181">The term [Unicode scalar value](https://www.unicode.org/glossary/#unicode_scalar_value) refers to all code points other than the surrogate code points.</span></span> <span data-ttu-id="0e651-182">Anders ausgedrückt: Ein Skalarwert ist ein beliebiger Codepunkt, der einem char zugewiesen ist oder in Zukunft einem char zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e651-182">In other words, a scalar value is any code point that is assigned a character or can be assigned a character in the future.</span></span> <span data-ttu-id="0e651-183">„Zeichen“ bezieht sich hierbei auf ein beliebiges Element, das einem Codepunkt zugewiesen werden kann, darunter z. B. Aktionen zum Steuern der Anzeige von Text oder char.</span><span class="sxs-lookup"><span data-stu-id="0e651-183">"Character" here refers to anything that can be assigned to a code point, which includes such things as actions that control how text or characters are displayed.</span></span>

<span data-ttu-id="0e651-184">Das nachstehende Diagramm veranschaulicht die Skalarwert-Codepunkte.</span><span class="sxs-lookup"><span data-stu-id="0e651-184">The following diagram illustrates the scalar value code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Skalarwerte":::

### <a name="the-no-locrune-type-as-a-scalar-value"></a><span data-ttu-id="0e651-186">Der Rune-Typ als Skalarwert</span><span class="sxs-lookup"><span data-stu-id="0e651-186">The Rune type as a scalar value</span></span>

<span data-ttu-id="0e651-187">Ab .NET Core 3.0 repräsentiert der <xref:System.Text.Rune?displayProperty=fullName>-Typ einen Unicode-Skalarwert.</span><span class="sxs-lookup"><span data-stu-id="0e651-187">Beginning with .NET Core 3.0, the <xref:System.Text.Rune?displayProperty=fullName> type represents a Unicode scalar value.</span></span> <span data-ttu-id="0e651-188">**`Rune` ist in .NET Core 2. oder .NET Framework 4.x nicht verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="0e651-188">**`Rune` is not available in .NET Core 2.x or .NET Framework 4.x.**</span></span>

<span data-ttu-id="0e651-189">Der `Rune`-Konstruktor überprüft, ob die Ergebnisinstanz ein gültiger Unicode-Skalarwert ist, anderenfalls wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0e651-189">The `Rune` constructors validate that the resulting instance is a valid Unicode scalar value, otherwise they throw an exception.</span></span> <span data-ttu-id="0e651-190">Das folgende Codebeispiel zeigt eine erfolgreiche Instanziierung von `Rune`-Instanzen, weil es sich bei der Eingabe um gültige Skalarwerte handelt:</span><span class="sxs-lookup"><span data-stu-id="0e651-190">The following example shows code that successfully instantiates `Rune` instances because the input represents valid scalar values:</span></span>

<span data-ttu-id="0e651-191">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::</span><span class="sxs-lookup"><span data-stu-id="0e651-191">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::</span></span>

<span data-ttu-id="0e651-192">Das folgende Beispiel führt zu einer Ausnahme, weil der Codepunkt sich im Ersatzbereich befindet und nicht Teil eines Ersatzzeichenpaars ist:</span><span class="sxs-lookup"><span data-stu-id="0e651-192">The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span></span>

<span data-ttu-id="0e651-193">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::</span><span class="sxs-lookup"><span data-stu-id="0e651-193">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::</span></span>

<span data-ttu-id="0e651-194">Das nachstehende Beispiel führt zu einer Ausnahme, weil der Codepunkt nicht im ergänzenden Bereich liegt:</span><span class="sxs-lookup"><span data-stu-id="0e651-194">The following example throws an exception because the code point is beyond the supplementary range:</span></span>

<span data-ttu-id="0e651-195">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::</span><span class="sxs-lookup"><span data-stu-id="0e651-195">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::</span></span>

### <a name="no-locrune-usage-example-changing-letter-case"></a><span data-ttu-id="0e651-196">Beispiel für die Verwendung von Rune: Änderung der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="0e651-196">Rune usage example: changing letter case</span></span>

<span data-ttu-id="0e651-197">Eine API, die einen `char`-Wert verwendet und annimmt, dass sie mit einem Codepunkt arbeitet, bei dem es sich um einen Skalarwert handelt, funktioniert nicht ordnungsgemäß, wenn der `char`-Wert aus einem Ersatzzeichenpaar stammt.</span><span class="sxs-lookup"><span data-stu-id="0e651-197">An API that takes a `char` and assumes it is working with a code point that is a scalar value doesn't work correctly if the `char` is from a surrogate pair.</span></span> <span data-ttu-id="0e651-198">Betrachten Sie beispielsweise die folgende Methode, die <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> für jeden char in einem string aufruft:</span><span class="sxs-lookup"><span data-stu-id="0e651-198">For example, consider the following method that calls <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> on each char in a string:</span></span>

<span data-ttu-id="0e651-199">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::</span><span class="sxs-lookup"><span data-stu-id="0e651-199">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="0e651-200">Wenn die Eingabezeichenfolge (`input` string) den Deseret-Buchstaben `er` in Kleinschreibung (`𐑉`) enthält, wird mit diesem Code keine Konvertierung in einen Großbuchstaben (`𐐡`) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e651-200">If the `input` string contains the lowercase Deseret letter `er` (`𐑉`), this code won't convert it to uppercase (`𐐡`).</span></span> <span data-ttu-id="0e651-201">Der Code ruft `char.ToUpperInvariant` separat für jeden Ersatzcodepunkt auf, `U+D801` und `U+DC49`.</span><span class="sxs-lookup"><span data-stu-id="0e651-201">The code calls `char.ToUpperInvariant` separately on each surrogate code point, `U+D801` and `U+DC49`.</span></span> <span data-ttu-id="0e651-202">Aber `U+D801` selbst weist nicht genügend Informationen für die Identifizierung als Kleinbuchstabe auf und wird daher von `char.ToUpperInvariant` nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0e651-202">But `U+D801` doesn't have enough information by itself to identify it as a lowercase letter, so `char.ToUpperInvariant` leaves it alone.</span></span> <span data-ttu-id="0e651-203">`U+DC49` wird in gleicher Weise behandelt.</span><span class="sxs-lookup"><span data-stu-id="0e651-203">And it handles `U+DC49` the same way.</span></span> <span data-ttu-id="0e651-204">Als Ergebnis wird der Kleinbuchstabe „𐑉“ in der Eingabezeichenfolge (`input` string) nicht in den Großbuchstaben „𐐡“ konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="0e651-204">The result is that lowercase '𐑉' in the `input` string doesn't get converted to uppercase '𐐡'.</span></span>

<span data-ttu-id="0e651-205">Hier sind zwei Optionen für die korrekte Konvertierung von string in Großbuchstaben:</span><span class="sxs-lookup"><span data-stu-id="0e651-205">Here are two options for correctly converting a string to uppercase:</span></span>

* <span data-ttu-id="0e651-206">Rufen Sie <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> für den Eingabe-string auf, statt `char` für `char` zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0e651-206">Call <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> on the input string rather than iterating `char`-by-`char`.</span></span> <span data-ttu-id="0e651-207">Die `string.ToUpperInvariant`-Methode hat Zugriff auf beide Teile des Ersatzzeichenpaars, deshalb können alle Unicode-Codepunkte ordnungsgemäß verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-207">The `string.ToUpperInvariant` method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span></span>
* <span data-ttu-id="0e651-208">Durchlaufen Sie die Unicode-Skalarwerte nicht als `char`-Instanzen, sondern als `Rune`-Instanzen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e651-208">Iterate through the Unicode scalar values as `Rune` instances instead of `char` instances, as shown in the following example.</span></span> <span data-ttu-id="0e651-209">Eine `Rune`-Instanz ist ein gültiger Unicode-Skalarwert, deshalb kann sie an APIs übergeben werden, die einen Skalarwert für die Verarbeitung erwarten.</span><span class="sxs-lookup"><span data-stu-id="0e651-209">Since a `Rune` instance is a valid Unicode scalar value, it can be passed to APIs that expect to operate on a scalar value.</span></span> <span data-ttu-id="0e651-210">Beispielsweise liefert der Aufruf von <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> wie im folgenden Beispiel richtige Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="0e651-210">For example, calling <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> as shown in the following example gives correct results:</span></span>

  <span data-ttu-id="0e651-211">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::</span><span class="sxs-lookup"><span data-stu-id="0e651-211">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::</span></span>

### <a name="other-no-locrune-apis"></a><span data-ttu-id="0e651-212">Andere Rune-APIs</span><span class="sxs-lookup"><span data-stu-id="0e651-212">Other Rune APIs</span></span>

<span data-ttu-id="0e651-213">Der `Rune`-Typ macht Entsprechungen vieler der `char`-APIs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0e651-213">The `Rune` type exposes analogs of many of the `char` APIs.</span></span> <span data-ttu-id="0e651-214">Beispielsweise spiegeln die folgenden Methoden statische APIs für den `char`-Typ:</span><span class="sxs-lookup"><span data-stu-id="0e651-214">For example, the following methods mirror static APIs on the `char` type:</span></span>

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

<span data-ttu-id="0e651-215">Um den Rohskalarwert aus einer `Rune`-Instanz abzurufen, verwenden Sie die <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0e651-215">To get the raw scalar value from a `Rune` instance, use the <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="0e651-216">Um eine `Rune`-Instanz wieder ein eine `char`-Sequenz zu konvertieren, verwenden Sie <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> oder die <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="0e651-216">To convert a `Rune` instance back to a sequence of `char`s, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> or the <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="0e651-217">Da jeder Unicode-Skalarwert durch einen einzelnen `char` oder durch ein Ersatzzeichenpaar dargestellt wird, kann jede `Rune`-Instanz durch höchstens 2 `char`-Instanzen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-217">Since any Unicode scalar value is representable by a single `char` or by a surrogate pair, any `Rune` instance can be represented by at most 2 `char` instances.</span></span> <span data-ttu-id="0e651-218">Verwenden Sie <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType>, um anzuzeigen, wie viele `char`-Instanzen zur Darstellung einer `Rune`-Instanz benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-218">Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> to see how many `char` instances are required to represent a `Rune` instance.</span></span>

<span data-ttu-id="0e651-219">Weitere Informationen zum .NET-Typ `Rune` finden Sie in der [`Rune`API-Referenz](xref:System.Text.Rune).</span><span class="sxs-lookup"><span data-stu-id="0e651-219">For more information about the .NET `Rune` type, see the [`Rune` API reference](xref:System.Text.Rune).</span></span>

## <a name="grapheme-clusters"></a><span data-ttu-id="0e651-220">Graphemhaufen</span><span class="sxs-lookup"><span data-stu-id="0e651-220">Grapheme clusters</span></span>

<span data-ttu-id="0e651-221">Was wie ein einziges char aussieht, kann tatsächlich eine Kombination mehrerer Codepunkte sein, deshalb wird zur Beschreibung anstelle des Begriffs „char“ häufig der Begriff [Graphemhaufen](https://www.unicode.org/glossary/#grapheme_cluster) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e651-221">What looks like one character might result from a combination of multiple code points, so a more descriptive term that is often used in place of "character" is [grapheme cluster](https://www.unicode.org/glossary/#grapheme_cluster).</span></span> <span data-ttu-id="0e651-222">Der äquivalente Begriff in .NET lautet [Textelement](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span><span class="sxs-lookup"><span data-stu-id="0e651-222">The equivalent term in .NET is [text element](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span></span>

<span data-ttu-id="0e651-223">Betrachten Sie die `string`-Instanzen „a“, „á“, „á“ und „`👩🏽‍🚒`“.</span><span class="sxs-lookup"><span data-stu-id="0e651-223">Consider the `string` instances "a", "á", "á", and "`👩🏽‍🚒`".</span></span> <span data-ttu-id="0e651-224">Wenn Ihr Betriebssystem diese gemäß Spezifikation im Unicode-Standard verarbeitet, wird jede dieser `string`-Instanzen als ein einzelnes Textelement bzw. als Graphemhaufen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e651-224">If your operating system handles them as specified by the Unicode standard, each of these `string` instances appears as a single text element or grapheme cluster.</span></span> <span data-ttu-id="0e651-225">Aber die letzten beiden werden durch mehr als einen Skalarwert-Codepunkt repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="0e651-225">But the last two are represented by more than one scalar value code point.</span></span>

* <span data-ttu-id="0e651-226">Die string-Instanz „a“ wird durch einen Skalarwert repräsentiert und enthält eine `char`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e651-226">The string "a" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+0061 LATIN SMALL LETTER A`

* <span data-ttu-id="0e651-227">Die string-Instanz „á“ wird durch einen Skalarwert repräsentiert und enthält eine `char`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e651-227">The string "á" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* <span data-ttu-id="0e651-228">Die string-Instanz „á“ sieht aus wie „á“, wird jedoch durch zwei Skalarwerte repräsentiert und enthält zwei `char`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="0e651-228">The string "á" looks the same as "á" but is represented by two scalar values and contains two `char` instances.</span></span>

  * `U+0061 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* <span data-ttu-id="0e651-229">Die string-Instanz `👩🏽‍🚒` schließlich wird durch vier Skalarwerte repräsentiert und enthält sieben `char`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="0e651-229">Finally, the string "`👩🏽‍🚒`" is represented by four scalar values and contains seven `char` instances.</span></span>

  * <span data-ttu-id="0e651-230">`U+1F469 WOMAN` (ergänzender Bereich, erfordert ein Ersatzzeichenpaar)</span><span class="sxs-lookup"><span data-stu-id="0e651-230">`U+1F469 WOMAN` (supplementary range, requires a surrogate pair)</span></span>
  * <span data-ttu-id="0e651-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (ergänzender Bereich, erfordert ein Ersatzzeichenpaar)</span><span class="sxs-lookup"><span data-stu-id="0e651-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (supplementary range, requires a surrogate pair)</span></span>
  * `U+200D ZERO WIDTH JOINER`
  * <span data-ttu-id="0e651-232">`U+1F692 FIRE ENGINE` (ergänzender Bereich, erfordert ein Ersatzzeichenpaar)</span><span class="sxs-lookup"><span data-stu-id="0e651-232">`U+1F692 FIRE ENGINE` (supplementary range, requires a surrogate pair)</span></span>

<span data-ttu-id="0e651-233">In einigen der vorhergehenden Beispiele – beispielsweise dem kombinierten Akzentmodifizierer oder dem Modifizierer für den Hautton – wird der Codepunkt nicht als eigenständiges Element auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e651-233">In some of the preceding examples - such as the combining accent modifier or the skin tone modifier - the code point does not display as a standalone element on the screen.</span></span> <span data-ttu-id="0e651-234">Stattdessen dient er zum Ändern des Aussehens eines vorangegangenen Textelements.</span><span class="sxs-lookup"><span data-stu-id="0e651-234">Rather, it serves to modify the appearance of a text element that came before it.</span></span> <span data-ttu-id="0e651-235">Diese Beispiele zeigen, dass möglicherweise mehrere Skalarwerte erforderlich sind, um ein einzelnes char oder einen Graphemhaufen zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0e651-235">These examples show that it might take multiple scalar values to make up what we think of as a single "character," or "grapheme cluster."</span></span>

<span data-ttu-id="0e651-236">Um die Graphemhaufen für einen `string` aufzulisten, verwenden Sie die <xref:System.Globalization.StringInfo>-Klasse wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e651-236">To enumerate the grapheme clusters of a `string`, use the <xref:System.Globalization.StringInfo> class as shown in the following example.</span></span> <span data-ttu-id="0e651-237">Wenn Sie mit Swift vertraut sind: Der .NET-Typ `StringInfo` ähnelt vom Konzept her dem [`character`-Typ in Swift](https://developer.apple.com/documentation/swift/character).</span><span class="sxs-lookup"><span data-stu-id="0e651-237">If you're familiar with Swift, the .NET `StringInfo` type is conceptually similar to [Swift's `character` type](https://developer.apple.com/documentation/swift/character).</span></span>

### <a name="example-count-no-locchar-no-locrune-and-text-element-instances"></a><span data-ttu-id="0e651-238">Beispiel: Zählen von char-, Rune- und Textelementinstanzen</span><span class="sxs-lookup"><span data-stu-id="0e651-238">Example: count char, Rune, and text element instances</span></span>

<span data-ttu-id="0e651-239">In den .NET-APIs wird ein Graphemhaufen als *Textelement* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0e651-239">In .NET APIs, a grapheme cluster is called a *text element*.</span></span> <span data-ttu-id="0e651-240">Die folgenden Methoden veranschaulichen die Unterschiede zwischen `char`-, `Rune`- und Textelementinstanzen in einem `string`:</span><span class="sxs-lookup"><span data-stu-id="0e651-240">The following method demonstrates the differences between `char`, `Rune`, and text element instances in a `string`:</span></span>

<span data-ttu-id="0e651-241">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::</span><span class="sxs-lookup"><span data-stu-id="0e651-241">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::</span></span>

<span data-ttu-id="0e651-242">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::</span><span class="sxs-lookup"><span data-stu-id="0e651-242">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::</span></span>

<span data-ttu-id="0e651-243">Wenn Sie diesen Code in .NET Framework oder .NET Code 3.1 oder früher ausführen, wird die Textelementanzahl für das Emoji als `4` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e651-243">If you run this code in .NET Framework or .NET Core 3.1 or earlier, the text element count for the emoji shows `4`.</span></span> <span data-ttu-id="0e651-244">Dies liegt an einem Fehler in der `StringInfo`-Klasse, der in .NET 5 behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="0e651-244">That is due to a bug in the `StringInfo` class that is fixed in .NET 5.</span></span>

### <a name="example-splitting-no-locstring-instances"></a><span data-ttu-id="0e651-245">Beispiel: Aufteilen von string-Instanzen</span><span class="sxs-lookup"><span data-stu-id="0e651-245">Example: splitting string instances</span></span>

<span data-ttu-id="0e651-246">Vermeiden Sie beim Aufteilen von `string`-Instanzen das Teilen von Ersatzzeichenpaaren und Graphemhaufen.</span><span class="sxs-lookup"><span data-stu-id="0e651-246">When splitting `string` instances, avoid splitting surrogate pairs and grapheme clusters.</span></span> <span data-ttu-id="0e651-247">Sehen Sie sich das folgende fehlerhafte Codebeispiel an, bei dem nach jeweils 10 char in einer string ein Zeilenumbruch eingefügt werden soll:</span><span class="sxs-lookup"><span data-stu-id="0e651-247">Consider the following example of incorrect code, which intends to insert line breaks every 10 characters in a string:</span></span>

<span data-ttu-id="0e651-248">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::</span><span class="sxs-lookup"><span data-stu-id="0e651-248">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="0e651-249">Dieser Code zählt `char`-Instanzen auf, deshalb wird ein Ersatzzeichenpaar, dass sich über eine 10-`char`-Grenze erstreckt, aufgeteilt und dazwischen ein Zeilenumbruch eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0e651-249">Because this code enumerates `char` instances, a surrogate pair that happens to straddle a 10-`char` boundary will be split and a newline injected between them.</span></span> <span data-ttu-id="0e651-250">Diese Einfügung führt zu einer Datenbeschädigung, weil Ersatzcodepunkte nur als Paar eine Bedeutung tragen.</span><span class="sxs-lookup"><span data-stu-id="0e651-250">This insertion introduces data corruption, because surrogate code points are meaningful only as pairs.</span></span>

<span data-ttu-id="0e651-251">Die Möglichkeit einer Datenbeschädigung ist nicht ausgeschlossen, wenn Sie anstelle von `char`-Instanzen `Rune`-Instanzen (Skalarwerte) aufzählen.</span><span class="sxs-lookup"><span data-stu-id="0e651-251">The potential for data corruption isn't eliminated if you enumerate `Rune` instances (scalar values) instead of `char` instances.</span></span> <span data-ttu-id="0e651-252">Ein Satz aus `Rune`-Instanzen kann einen Graphemhaufen bilden, der sich über eine 10-`char`-Grenze erstreckt.</span><span class="sxs-lookup"><span data-stu-id="0e651-252">A set of `Rune` instances might make up a grapheme cluster that straddles a 10-`char` boundary.</span></span> <span data-ttu-id="0e651-253">Wenn der Graphemhaufen geteilt wird, kann er nicht ordnungsgemäß interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-253">If the grapheme cluster set is split up, it can't be interpreted correctly.</span></span>

<span data-ttu-id="0e651-254">Ein besserer Ansatz besteht darin, den string durch Zählen der Graphemhaufen oder Textelemente zu teilen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0e651-254">A better approach is to break the string by counting grapheme clusters, or text elements, as in the following example:</span></span>

<span data-ttu-id="0e651-255">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::</span><span class="sxs-lookup"><span data-stu-id="0e651-255">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::</span></span>

<span data-ttu-id="0e651-256">Wie bereits erwähnt, kann die `StringInfo`-Klasse in .NET-Implementierungen (im Gegensatz zu .NET 5) einige Graphemhaufen jedoch falsch verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0e651-256">As noted earlier, however, in implementations of .NET other than .NET 5, the `StringInfo` class might handle some grapheme clusters incorrectly.</span></span>

## <a name="utf-8-and-utf-32"></a><span data-ttu-id="0e651-257">UTF-8 und UTF-32</span><span class="sxs-lookup"><span data-stu-id="0e651-257">UTF-8 and UTF-32</span></span>

<span data-ttu-id="0e651-258">Die vorangegangenen Abschnitte konzentrierten sich auf UTF-16, weil .NET UTF-16 zur Codierung von `string`-Instanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e651-258">The preceding sections focused on UTF-16 because that's what .NET uses to encode `string` instances.</span></span> <span data-ttu-id="0e651-259">Für Unicode sind einige weitere Codierungssysteme vorhanden – [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) und [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span><span class="sxs-lookup"><span data-stu-id="0e651-259">There are other encoding systems for Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) and [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span></span> <span data-ttu-id="0e651-260">Diese Codierungen verwenden 8-Bit-Codeeinheiten bzw. 32-Bit-Codeeinheiten.</span><span class="sxs-lookup"><span data-stu-id="0e651-260">These encodings use 8-bit code units and 32-bit code units, respectively.</span></span>

<span data-ttu-id="0e651-261">Wie UTF-16 werden in UTF-8 mehrere Codeeinheiten benötigt, um einige Unicode-Skalarwerte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e651-261">Like UTF-16, UTF-8 requires multiple code units to represent some Unicode scalar values.</span></span> <span data-ttu-id="0e651-262">UTF-32 kann jeden beliebigen Skalarwert in einer einzelnen 32-Bit-Codeeinheit darstellen.</span><span class="sxs-lookup"><span data-stu-id="0e651-262">UTF-32 can represent any scalar value in a single 32-bit code unit.</span></span>

<span data-ttu-id="0e651-263">Hier sind einige Beispiele, die zeigen, wie derselbe Unicode-Codepunkt in jedem dieser drei Unicode-Codierungssysteme dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="0e651-263">Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span></span>

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

<span data-ttu-id="0e651-264">Wie bereits erwähnt, ist eine einzelne UTF-16-Codeeinheit aus einem [Einzelzeichenpaar](#surrogate-pairs) für sich genommen bedeutungslos.</span><span class="sxs-lookup"><span data-stu-id="0e651-264">As noted earlier, a single UTF-16 code unit from a [surrogate pair](#surrogate-pairs) is meaningless by itself.</span></span> <span data-ttu-id="0e651-265">Ebenso ist eine einzelne UTF-8-Codeeinheit für sich genommen bedeutungslos, wenn sie in einer Sequenz von zwei, drei oder vier Einheiten zur Berechnung eines Skalarwerts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e651-265">In the same way, a single UTF-8 code unit is meaningless by itself if it's in a sequence of two, three, or four used to calculate a scalar value.</span></span>

### <a name="endianness"></a><span data-ttu-id="0e651-266">Endianness</span><span class="sxs-lookup"><span data-stu-id="0e651-266">Endianness</span></span>

<span data-ttu-id="0e651-267">In .NET werden die UTF-16-Codeeinheiten für einen string in zusammenhängenden Speicherbereichen als Sequenz aus 16-Bit-Ganzzahlen (`char`-Instanzen) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0e651-267">In .NET, the UTF-16 code units of a string are stored in contiguous memory as a sequence of 16-bit integers (`char` instances).</span></span> <span data-ttu-id="0e651-268">Die Bits der einzelnen Codeeinheiten werden gemäß [Endianwert](https://en.wikipedia.org/wiki/Endianness) der aktuellen Architektur angeordnet.</span><span class="sxs-lookup"><span data-stu-id="0e651-268">The bits of individual code units are laid out according to the [endianness](https://en.wikipedia.org/wiki/Endianness) of the current architecture.</span></span>

<span data-ttu-id="0e651-269">In einer Little-Endian-Architektur wird der aus UTF-16-Codeeinheiten `[ D801 DCCC ]` bestehende string im Arbeitsspeicher in Form der Bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]` angeordnet.</span><span class="sxs-lookup"><span data-stu-id="0e651-269">On a little-endian architecture, the string consisting of the UTF-16 code points `[ D801 DCCC ]` would be laid out in memory as the bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span></span> <span data-ttu-id="0e651-270">In einer Big-Endian-Architektur würde derselbe string im Arbeitsspeicher in Form der Bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]` angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-270">On a big-endian architecture that same string would be laid out in memory as the bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span></span>

<span data-ttu-id="0e651-271">Computersysteme, die miteinander kommunizieren, müssen sich auf die Darstellung von Daten einigen, die übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-271">Computer systems that communicate with each other must agree on the representation of data crossing the wire.</span></span> <span data-ttu-id="0e651-272">Die meisten Netzwerkprotokolle verwenden UTF-8 als Standard für die Textübertragung – unter anderem, um Probleme zu vermeiden, die durch die Kommunikation eines Big-Endian-Computers mit einem Little-Endian-Computer entstehen könnten.</span><span class="sxs-lookup"><span data-stu-id="0e651-272">Most network protocols use UTF-8 as a standard when transmitting text, partly to avoid issues that might result from a big-endian machine communicating with a little-endian machine.</span></span> <span data-ttu-id="0e651-273">Der aus den UTF-8-Codepunkten `[ F0 90 93 8C ]` bestehende string wird immer in Form der Bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` dargestellt, unabhängig vom Endianwert.</span><span class="sxs-lookup"><span data-stu-id="0e651-273">The string consisting of the UTF-8 code points `[ F0 90 93 8C ]` will always be represented as the bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` regardless of endianness.</span></span>

<span data-ttu-id="0e651-274">Um UTF-8 für die Übertragung von Text zu verwenden, nutzen .NET-Anwendungen häufig Code wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0e651-274">To use UTF-8 for transmitting text, .NET applications often use code like the following example:</span></span>

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

<span data-ttu-id="0e651-275">Im vorstehenden Beispiel decodiert die Methode [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) den UTF-16-`string` zurück in eine Reihe von Unicode-Skalarwerten. Anschließend werden diese Skalarwerte wieder in UTF-8 codiert, und die Ergebnissequenz wird in einem `byte`-Array platziert.</span><span class="sxs-lookup"><span data-stu-id="0e651-275">In the preceding example, the method [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodes the UTF-16 `string` back into a series of Unicode scalar values, then it re-encodes those scalar values into UTF-8 and places the resulting sequence into a `byte` array.</span></span> <span data-ttu-id="0e651-276">Die Methode [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) führt die umgekehrte Transformation durch, sie konvertiert einen UTF-8-`byte`-Array in einen UTF-16-`string`.</span><span class="sxs-lookup"><span data-stu-id="0e651-276">The method [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) performs the opposite transformation, converting a UTF-8 `byte` array to a UTF-16 `string`.</span></span>

> [!WARNING]
> <span data-ttu-id="0e651-277">Weil UTF-8 im Internet so weit verbreitet ist, kann es verlockend sein, Rohbytes aus der Verbindung zu lesen und die Daten so zu behandeln, als handele es sich um UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0e651-277">Since UTF-8 is commonplace on the internet, it may be tempting to read raw bytes from the wire and to treat the data as if it were UTF-8.</span></span> <span data-ttu-id="0e651-278">Sie müssen jedoch sicherstellen, dass die Daten tatsächlich wohlgeformt sind.</span><span class="sxs-lookup"><span data-stu-id="0e651-278">However, you should validate that it is indeed well-formed.</span></span> <span data-ttu-id="0e651-279">Ein schädlicher Client überträgt möglicherweise nicht wohlgeformte UTF-8-Daten an Ihren Dienst.</span><span class="sxs-lookup"><span data-stu-id="0e651-279">A malicious client might submit ill-formed UTF-8 to your service.</span></span> <span data-ttu-id="0e651-280">Wenn Sie mit diesen Daten arbeiten, als seien es wohlgeformte Daten, kann dies zu Fehlern oder Sicherheitslücken in Ihrer Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="0e651-280">If you operate on that data as if it were well-formed, it could cause errors or security holes in your application.</span></span> <span data-ttu-id="0e651-281">Um UTF-8-Daten zu validieren, können Sie eine Methode wie `Encoding.UTF8.GetString` verwenden, die während der Konvertierung der eingehenden Daten in einen `string` eine Überprüfung durchführt.</span><span class="sxs-lookup"><span data-stu-id="0e651-281">To validate UTF-8 data, you can use a method like `Encoding.UTF8.GetString`, which will perform validation while converting the incoming data to a `string`.</span></span>

### <a name="well-formed-encoding"></a><span data-ttu-id="0e651-282">Wohlgeformte Codierung</span><span class="sxs-lookup"><span data-stu-id="0e651-282">Well-formed encoding</span></span>

<span data-ttu-id="0e651-283">Eine wohlgeformte Unicode-Codierung ist ein string aus Codeeinheiten, die eindeutig decodiert und ohne Fehler in eine Sequenz von Unicode-Skalarwerten konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="0e651-283">A well-formed Unicode encoding is a string of code units that can be decoded unambiguously and without error into a sequence of Unicode scalar values.</span></span> <span data-ttu-id="0e651-284">Wohlgeformte Daten können ohne Einschränkung zwischen UTF-8, UTF-16 und UTF-32 hin- und her transcodiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-284">Well-formed data can be transcoded freely back and forth between UTF-8, UTF-16, and UTF-32.</span></span>

<span data-ttu-id="0e651-285">Die Frage, ob eine Codierungssequenz wohlgeformt ist oder nicht, hat nichts mit dem Endianwert einer Computerarchitektur zu tun.</span><span class="sxs-lookup"><span data-stu-id="0e651-285">The question of whether an encoding sequence is well-formed or not is unrelated to the endianness of a machine's architecture.</span></span> <span data-ttu-id="0e651-286">Eine nicht wohlgeformte UTF-8-Sequenz ist sowohl für einen Big-Endian- als auch für einen Little-Endian-Computer nicht wohlgeformt.</span><span class="sxs-lookup"><span data-stu-id="0e651-286">An ill-formed UTF-8 sequence is ill-formed in the same way on both big-endian and little-endian machines.</span></span>

<span data-ttu-id="0e651-287">Hier sehen Sie einige Beispiele für nicht wohlgeformte Codierungen:</span><span class="sxs-lookup"><span data-stu-id="0e651-287">Here are some examples of ill-formed encodings:</span></span>

* <span data-ttu-id="0e651-288">In UTF-8 ist die Sequenz `[ 6C C2 61 ]` nicht wohlgeformt, weil auf `C2` nicht `61` folgen darf.</span><span class="sxs-lookup"><span data-stu-id="0e651-288">In UTF-8, the sequence `[ 6C C2 61 ]` is ill-formed because `C2` cannot be followed by `61`.</span></span>

* <span data-ttu-id="0e651-289">In UTF-16 ist die Sequenz `[ DC00 DD00 ]` nicht wohlgeformt (oder in C# der string `"\udc00\udd00"`), weil auf das niedrige Ersatzzeichen `DC00` nicht ein weiteres niedriges Ersatzzeichen `DD00` folgen kann.</span><span class="sxs-lookup"><span data-stu-id="0e651-289">In UTF-16, the sequence `[ DC00 DD00 ]` (or, in C#, the string `"\udc00\udd00"`) is ill-formed because the low surrogate `DC00` cannot be followed by another low surrogate `DD00`.</span></span>

* <span data-ttu-id="0e651-290">In UTF-32 ist die Sequenz `[ 0011ABCD ]` nicht wohlgeformt, weil `0011ABCD` außerhalb des Bereichs für Unicode-Skalarwerte liegt.</span><span class="sxs-lookup"><span data-stu-id="0e651-290">In UTF-32, the sequence `[ 0011ABCD ]` is ill-formed because `0011ABCD` is outside the range of Unicode scalar values.</span></span>

<span data-ttu-id="0e651-291">In .NET enthalten `string`-Instanzen fast immer wohlgeformte UTF-16-Daten, aber dies ist nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="0e651-291">In .NET, `string` instances almost always contain well-formed UTF-16 data, but that isn't guaranteed.</span></span> <span data-ttu-id="0e651-292">Die folgenden Beispiele zeigen gültigen C#-Code, der nicht wohlgeformte UTF-16-Daten in `string`-Instanzen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="0e651-292">The following examples show valid C# code that creates ill-formed UTF-16 data in `string` instances.</span></span>

* <span data-ttu-id="0e651-293">Ein nicht wohlgeformtes Literal:</span><span class="sxs-lookup"><span data-stu-id="0e651-293">An ill-formed literal:</span></span>

  ```csharp
  const string s = "\ud800";
  ```

* <span data-ttu-id="0e651-294">Eine Teil-string, die ein Ersatzzeichenpaar aufteilt:</span><span class="sxs-lookup"><span data-stu-id="0e651-294">A substring that splits up a surrogate pair:</span></span>

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

<span data-ttu-id="0e651-295">APIs wie [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) geben keine nicht wohlgeformten `string`-Instanzen zurück.</span><span class="sxs-lookup"><span data-stu-id="0e651-295">APIs like [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) never return ill-formed `string` instances.</span></span> <span data-ttu-id="0e651-296">Die Methoden `Encoding.GetString` und `Encoding.GetBytes` erkennen falsch formatierte Sequenzen in der Eingabe und führen beim Generieren der Ausgabe char-Ersetzungen durch.</span><span class="sxs-lookup"><span data-stu-id="0e651-296">`Encoding.GetString` and `Encoding.GetBytes` methods detect ill-formed sequences in the input and perform character substitution when generating the output.</span></span> <span data-ttu-id="0e651-297">Wenn [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) beispielsweise ein Nicht-ASCII-Byte (außerhalb des Bereichs U+0000..U+007F) in der Eingabe erkennt, wird ein ? in die zurückgegebene `string`-Instanz eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0e651-297">For example, if [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) sees a non-ASCII byte in the input (outside the range U+0000..U+007F), it inserts a '?' into the returned `string` instance.</span></span> <span data-ttu-id="0e651-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) ersetzt nicht wohlgeformte UTF-8-Sequenzen in der zurückgegebenen `string`-Instanz durch `U+FFFD REPLACEMENT CHARACTER ('�')`.</span><span class="sxs-lookup"><span data-stu-id="0e651-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) replaces ill-formed UTF-8 sequences with `U+FFFD REPLACEMENT CHARACTER ('�')` in the returned `string` instance.</span></span> <span data-ttu-id="0e651-299">Weitere Informationen finden Sie unter [Unicode-Standard](https://www.unicode.org/versions/latest/) in den Abschnitten 5.22 und 3.9.</span><span class="sxs-lookup"><span data-stu-id="0e651-299">For more information, see [the Unicode Standard](https://www.unicode.org/versions/latest/), Sections 5.22 and 3.9.</span></span>

<span data-ttu-id="0e651-300">Die integrierten `Encoding`-Klassen können auch so konfiguriert werden, dass sie anstelle einer char-Ersetzung eine Ausnahme auslösen, wenn falsch formatierte Sequenzen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="0e651-300">The built-in `Encoding` classes can also be configured to throw an exception rather than perform character substitution when ill-formed sequences are seen.</span></span> <span data-ttu-id="0e651-301">Dieser Ansatz findet häufig in Anwendungen mit hohen Sicherheitsanforderungen Anwendung, bei denen eine char-Ersetzung möglicherweise nicht akzeptabel ist.</span><span class="sxs-lookup"><span data-stu-id="0e651-301">This approach is often used in security-sensitive applications where character substitution might not be acceptable.</span></span>

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

<span data-ttu-id="0e651-302">Informationen zur Verwendung der integrierten `Encoding`-Klassen finden Sie unter [Verwenden von char-Codierungsklassen in .NET](character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="0e651-302">For information about how to use the built-in `Encoding` classes, see [How to use character encoding classes in .NET](character-encoding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e651-303">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e651-303">See also</span></span>

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [<span data-ttu-id="0e651-304">Globalisierung und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="0e651-304">Globalization and Localization</span></span>](../globalization-localization/index.md)
