---
title: 'Breaking Change: StringInfo und TextElementEnumerator jetzt mit UAX29 kompatibel'
description: Hier erfahren Sie mehr über den Globalisierungs-Breaking-Change in .NET 5.0, bei dem StringInfo und TextElementEnumerator die Graphemcluster gemäß der aktuellen Version des Unicode-Standards verarbeiten.
ms.date: 04/07/2020
ms.openlocfilehash: cd5ae5a3eb9f2dd9c02bc179a40d454d24101199
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759214"
---
# <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="7c664-103">StringInfo und TextElementEnumerator jetzt mit UAX29 kompatibel</span><span class="sxs-lookup"><span data-stu-id="7c664-103">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="7c664-104">Vor dieser Änderung haben <xref:System.Globalization.StringInfo?displayProperty=fullName> und <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> nicht alle Graphemhaufen ordnungsgemäß verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="7c664-104">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="7c664-105">Einige Grapheme wurden nicht als Ganzes beibehalten, sondern in ihre Bestandteile aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="7c664-105">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="7c664-106">Nun verarbeiten <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> Graphemhaufen der aktuellen Version des Unicode-Standards entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7c664-106">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="7c664-107">Außerdem folgt die <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>-Methode, die die Zeichen in einer Zeichenfolge in Visual Basic umkehrt, nun auch dem Unicode-Standard für Graphemhaufen.</span><span class="sxs-lookup"><span data-stu-id="7c664-107">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

## <a name="change-description"></a><span data-ttu-id="7c664-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="7c664-108">Change description</span></span>

<span data-ttu-id="7c664-109">Bei einem [Graphem](https://www.unicode.org/glossary/#grapheme) oder [erweiterten Graphemhaufen](https://www.unicode.org/glossary/#extended_grapheme_cluster) handelt es sich um ein vom Benutzer als Einzelzeichen wahrgenommenes Zeichen, das aus mehreren Unicode-Codepunkten bestehen kann.</span><span class="sxs-lookup"><span data-stu-id="7c664-109">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="7c664-110">Die Zeichenfolge, die das Thai-Zeichen „kam“ (:::no-loc text="กำ":::) enthält, besteht beispielsweise aus den folgenden beiden Zeichen:</span><span class="sxs-lookup"><span data-stu-id="7c664-110">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="7c664-111">:::no-loc text="ก"::: (= '\u0e01') THAI-ZEICHEN KO KAI</span><span class="sxs-lookup"><span data-stu-id="7c664-111">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="7c664-112">:::no-loc text=" ำ"::: (= '\u0e33') THAI-Zeichen SARA AM</span><span class="sxs-lookup"><span data-stu-id="7c664-112">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="7c664-113">Wenn diese dem Benutzer angezeigt werden, kombiniert das Betriebssystem die beiden Zeichen und formt das angezeigte Einzelzeichen (oder Graphem) „kam“ oder :::no-loc text="กำ":::.</span><span class="sxs-lookup"><span data-stu-id="7c664-113">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="7c664-114">Auch Emojis können aus mehreren Zeichen bestehen, die auf ähnliche Weise kombiniert werden, bevor sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7c664-114">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="7c664-115">In der .NET-Dokumentation wird manchmal der Begriff „Textelement“ verwendet, wenn Grapheme gemeint sind.</span><span class="sxs-lookup"><span data-stu-id="7c664-115">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="7c664-116">Die Klassen <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> untersuchen Zeichenfolgen und geben Informationen zu den darin enthaltenen Graphemen zurück.</span><span class="sxs-lookup"><span data-stu-id="7c664-116">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="7c664-117">In .NET Framework (alle Versionen) und .NET Core 3.x und früher verwenden diese beiden Klassen eine benutzerdefinierte Logik, die einige kombinierte Klassen verarbeitet, aber nicht vollständig mit dem [Unicode-Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries) konform ist.</span><span class="sxs-lookup"><span data-stu-id="7c664-117">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="7c664-118">Beispielsweise teilen die Klassen <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> fälschlicherweise das Thai-Einzelzeichen „kam“ wieder in seine Bestandteile auf, anstatt diese zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="7c664-118">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="7c664-119">Diese Klassen teilen auch fälschlicherweise das Emoji-Zeichen „🤷🏽 ♀️“ in vier Bestandteile auf (achselzuckende Person, Hautfarbenmodifizierer, Geschlechtsmodifizierer, unsichtbarer Combiner), anstatt es als einen einzelnen Graphemhaufen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7c664-119">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="7c664-120">Ab .NET 5 implementieren die Klassen <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> den Unicode-Standard, der im [Unicode® Standard Annex \#29 (Revision 35, Abschnitt 3)](https://www.unicode.org/reports/tr29/tr29-35.html) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7c664-120">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="7c664-121">Insbesondere werden nun [erweiterte Graphemhaufen](https://www.unicode.org/glossary/#extended_grapheme_cluster) für alle kombinierenden Klassen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c664-121">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="7c664-122">Sehen Sie sich folgenden C#-Code an:</span><span class="sxs-lookup"><span data-stu-id="7c664-122">Consider the following C# code:</span></span>

```csharp
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

<span data-ttu-id="7c664-123">In .NET Framework und .NET Core 3.x und früheren Versionen werden die Grapheme aufgeteilt, und die Konsolenausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7c664-123">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

<span data-ttu-id="7c664-124">In .NET 5 und höheren Versionen werden die Grapheme zusammengehalten, und die Konsolenausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7c664-124">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="7c664-125">Außerdem folgt die <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>-Methode, die die Zeichen in einer Zeichenfolge in Visual Basic umkehrt, ab .NET 5 auch dem Unicode-Standard für Graphemhaufen.</span><span class="sxs-lookup"><span data-stu-id="7c664-125">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="7c664-126">Diese Änderungen sind Teil umfangreicher Verbesserungen von Unicode und UTF-8 in .NET, die auch eine Enumerations-API für erweiterte Graphemhaufen umfassen, um die Enumerations-APIs für Unicode-Skalarwerte zu ergänzen, die mit dem <xref:System.Text.Rune?displayProperty=fullName>-Typ in .NET Core 3.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="7c664-126">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7c664-127">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7c664-127">Version introduced</span></span>

<span data-ttu-id="7c664-128">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7c664-128">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7c664-129">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="7c664-129">Recommended action</span></span>

<span data-ttu-id="7c664-130">Sie müssen keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="7c664-130">You don't need to take any action.</span></span> <span data-ttu-id="7c664-131">Ihre Apps verhalten sich in vielen Globalisierungsszenarios automatisch standardkonformer.</span><span class="sxs-lookup"><span data-stu-id="7c664-131">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7c664-132">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7c664-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

### Category

Globalization

-->
