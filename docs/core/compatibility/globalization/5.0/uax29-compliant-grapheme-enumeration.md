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
# <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a>StringInfo und TextElementEnumerator jetzt mit UAX29 kompatibel

Vor dieser Änderung haben <xref:System.Globalization.StringInfo?displayProperty=fullName> und <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> nicht alle Graphemhaufen ordnungsgemäß verarbeitet. Einige Grapheme wurden nicht als Ganzes beibehalten, sondern in ihre Bestandteile aufgeteilt. Nun verarbeiten <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> Graphemhaufen der aktuellen Version des Unicode-Standards entsprechend.

Außerdem folgt die <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>-Methode, die die Zeichen in einer Zeichenfolge in Visual Basic umkehrt, nun auch dem Unicode-Standard für Graphemhaufen.

## <a name="change-description"></a>Änderungsbeschreibung

Bei einem [Graphem](https://www.unicode.org/glossary/#grapheme) oder [erweiterten Graphemhaufen](https://www.unicode.org/glossary/#extended_grapheme_cluster) handelt es sich um ein vom Benutzer als Einzelzeichen wahrgenommenes Zeichen, das aus mehreren Unicode-Codepunkten bestehen kann. Die Zeichenfolge, die das Thai-Zeichen „kam“ (:::no-loc text="กำ":::) enthält, besteht beispielsweise aus den folgenden beiden Zeichen:

- :::no-loc text="ก"::: (= '\u0e01') THAI-ZEICHEN KO KAI
- :::no-loc text=" ำ"::: (= '\u0e33') THAI-Zeichen SARA AM

Wenn diese dem Benutzer angezeigt werden, kombiniert das Betriebssystem die beiden Zeichen und formt das angezeigte Einzelzeichen (oder Graphem) „kam“ oder :::no-loc text="กำ":::. Auch Emojis können aus mehreren Zeichen bestehen, die auf ähnliche Weise kombiniert werden, bevor sie angezeigt werden.

> [!TIP]
> In der .NET-Dokumentation wird manchmal der Begriff „Textelement“ verwendet, wenn Grapheme gemeint sind.

Die Klassen <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> untersuchen Zeichenfolgen und geben Informationen zu den darin enthaltenen Graphemen zurück. In .NET Framework (alle Versionen) und .NET Core 3.x und früher verwenden diese beiden Klassen eine benutzerdefinierte Logik, die einige kombinierte Klassen verarbeitet, aber nicht vollständig mit dem [Unicode-Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries) konform ist. Beispielsweise teilen die Klassen <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> fälschlicherweise das Thai-Einzelzeichen „kam“ wieder in seine Bestandteile auf, anstatt diese zu kombinieren. Diese Klassen teilen auch fälschlicherweise das Emoji-Zeichen „🤷🏽 ♀️“ in vier Bestandteile auf (achselzuckende Person, Hautfarbenmodifizierer, Geschlechtsmodifizierer, unsichtbarer Combiner), anstatt es als einen einzelnen Graphemhaufen zu speichern.

Ab .NET 5 implementieren die Klassen <xref:System.Globalization.StringInfo> und <xref:System.Globalization.TextElementEnumerator> den Unicode-Standard, der im [Unicode® Standard Annex \#29 (Revision 35, Abschnitt 3)](https://www.unicode.org/reports/tr29/tr29-35.html) definiert ist. Insbesondere werden nun [erweiterte Graphemhaufen](https://www.unicode.org/glossary/#extended_grapheme_cluster) für alle kombinierenden Klassen zurückgegeben.

Sehen Sie sich folgenden C#-Code an:

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

In .NET Framework und .NET Core 3.x und früheren Versionen werden die Grapheme aufgeteilt, und die Konsolenausgabe sieht wie folgt aus:

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

In .NET 5 und höheren Versionen werden die Grapheme zusammengehalten, und die Konsolenausgabe sieht wie folgt aus:

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

Außerdem folgt die <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>-Methode, die die Zeichen in einer Zeichenfolge in Visual Basic umkehrt, ab .NET 5 auch dem Unicode-Standard für Graphemhaufen.

Diese Änderungen sind Teil umfangreicher Verbesserungen von Unicode und UTF-8 in .NET, die auch eine Enumerations-API für erweiterte Graphemhaufen umfassen, um die Enumerations-APIs für Unicode-Skalarwerte zu ergänzen, die mit dem <xref:System.Text.Rune?displayProperty=fullName>-Typ in .NET Core 3.0 eingeführt wurden.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

## <a name="recommended-action"></a>Empfohlene Aktion

Sie müssen keine Maßnahmen ergreifen. Ihre Apps verhalten sich in vielen Globalisierungsszenarios automatisch standardkonformer.

## <a name="affected-apis"></a>Betroffene APIs

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
