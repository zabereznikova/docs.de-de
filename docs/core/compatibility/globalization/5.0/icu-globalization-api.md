---
title: 'Breaking Change: Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows'
description: Hier erfahren Sie mehr über den Globalisierungs-Breaking-Change in .NET 5.0, bei dem anstelle von NLS ICU-Bibliotheken für Globalisierungsfunktionen verwendet werden.
ms.date: 05/19/2020
ms.openlocfilehash: efc20e21969ea4a83c9122e40b262e1dc38e6770
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759559"
---
# <a name="globalization-apis-use-icu-libraries-on-windows"></a>Globalisierungs-APIs verwenden ICU-Bibliotheken unter Windows

.NET 5.0 und höhere Versionen verwenden bei der Ausführung unter dem Windows 10-Update vom Mai 2019 oder später [ICU](http://site.icu-project.org/home)-Bibliotheken (International Components for Unicode, internationale Komponenten für Unicode) für die Globalisierungsfunktionalität.

## <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 1.0-3.1 und .NET Framework 4 und höher verwenden .NET-Bibliotheken [NLS](/windows/win32/intl/national-language-support)-APIs (National Language Support) für Globalisierungsfunktionalität unter Windows. Beispielsweise wurden NLS-Funktionen verwendet, um Zeichenfolgen zu vergleichen, Informationen zur Kultur abzurufen und Groß-/Kleinschreibung von Zeichenfolgen gemäß der entsprechenden Kultur umzusetzen.

Ab .NET 5.0 verwenden .NET-Bibliotheken standardmäßig Globalisierungs-APIs von [ICU](http://site.icu-project.org/home), wenn eine Anwendung unter Windows 10 mit Update vom Mai 2019 oder höher ausgeführt wird.

> [!NOTE]
> Das Windows 10-Update von Mai 2019 und spätere Versionen werden mit der nativen ICU-Bibliothek ausgeliefert. Wenn die .NET-Runtime ICU nicht laden kann, verwendet sie stattdessen NLS.

## <a name="behavioral-differences"></a>Verhaltensunterschiede

Möglicherweise bemerken Sie Änderungen in Ihrer Anwendung, auch wenn Sie sich nicht bewusst sind, dass Sie Globalisierungsfunktionen nutzen. In diesem Abschnitt finden einige der Verhaltensänderungen, die Sie möglicherweise beobachten, aber es gibt noch weitere.

### <a name="stringindexof"></a>String.IndexOf

Betrachten Sie den folgenden Code, der <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> aufruft, um den Index des Zeilenvorschubzeichens in einer Zeichenfolge zu finden.

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- In früheren Versionen von .NET unter Windows gibt der Ausschnitt `6` aus.
- Ab .NET 5.0 unter Windows 19H1 und höheren Versionen gibt der Ausschnitt `-1` aus.

Um diesen Code durch eine ordinale Suche anstelle einer kulturabhängigen Suche zu korrigieren, rufen Sie die Überladung <xref:System.String.IndexOf(System.String,System.StringComparison)> auf, an die Sie <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> als Argument übergeben.

Sie können Codeanalyseregeln entsprechend [CA1307: Angeben von StringComparison für mehr Klarheit](../../../../fundamentals/code-analysis/quality-rules/ca1307.md) und [CA1309: Verwenden eines ordinalen StringComparison](../../../../fundamentals/code-analysis/quality-rules/ca1309.md) ausführen, um diese Aufrufstellen in Ihrem Code zu finden.

Weitere Informationen finden Sie unter [Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5](../../../../standard/base-types/string-comparison-net-5-plus.md).

### <a name="currency-symbol"></a>Währungssymbol

Betrachten Sie den folgenden Code, der eine Zeichenfolge mit `C` als Spezifizierer des Währungsformats formatiert. Die Kultur des aktuellen Threads ist auf eine Kultur festgelegt, die nur die Sprache und nicht das Land umfasst.

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- In früheren Versionen von .NET unter Windows ist der Wert des Texts `"100,00 €"`.
- Ab .NET 5.0 unter Windows 19H1 und späteren Versionen ist der Wert des Texts `"100,00 ¤"`, der das internationale Währungssymbol anstelle von Euro verwendet. In ICU ist eine Währung eine Eigenschaft eines Landes oder einer Region und nicht einer Sprache.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde eingeführt, um das Globalisierungsverhalten von .NET in allen unterstützten Betriebssystemen zu vereinheitlichen. Darüber hinaus können Anwendungen ihre eigenen Globalisierungsbibliotheken bündeln, anstatt von den in das Betriebssystem integrierten Bibliotheken abhängig zu sein.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

## <a name="recommended-action"></a>Empfohlene Aktion

Auf der Seite des Entwicklers ist keine Aktion erforderlich. Wenn Sie jedoch weiterhin NLS-Globalisierungs-APIs verwenden möchten, können Sie einen [Runtimeschalter festlegen](../../../run-time-config/globalization.md#nls), um zu diesem Verhalten zurückzukehren. Weitere Informationen zu den verfügbaren Schaltern finden Sie im Artikel [.NET-Globalisierung und ICU](../../../../standard/globalization-localization/globalization-icu.md).

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- Die meisten Typen im <xref:System.Globalization?displayProperty=fullName>-Namespace
- <xref:System.Array.Sort%2A?displayProperty=fullName> (beim Sortieren eines Zeichenfolgenarrays)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (wenn die Listenelemente Zeichenfolgen sind)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (wenn die Gruppe Zeichenfolgen enthält)

<!--

### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

### Category

- Core .NET libraries
- Globalization

-->
