---
title: Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5
description: Erfahren Sie mehr über Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5 unter Windows.
ms.date: 12/07/2020
ms.openlocfilehash: a53c36b31785fb43c0aa5f5040042abb6d40031a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851750"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a>Verhaltensänderungen beim Vergleichen von Zeichenfolgen ab .NET 5

In NET 5.0 wird eine Änderung des Runtimeverhaltens eingeführt, aufgrund derer Globalisierungs-APIs auf allen unterstützten Plattformen [jetzt standardmäßig ICU verwenden](../../core/compatibility/globalization/5.0/icu-globalization-api.md). Dies ist eine Abkehr von früheren Versionen von .NET Core und .NET Framework, die bei Ausführung unter Windows die NLS-Funktionalität (National Language Support) des Betriebssystems nutzen. Weitere Informationen zu diesen Änderungen, einschließlich Kompatibilitätsschalter, mit denen die Verhaltensänderung rückgängig gemacht werden kann, finden Sie unter [.NET-Globalisierung und ICU](../globalization-localization/globalization-icu.md).

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde eingeführt, um das Globalisierungsverhalten von .NET in allen unterstützten Betriebssystemen zu vereinheitlichen. Darüber hinaus können Anwendungen ihre eigenen Globalisierungsbibliotheken bündeln, anstatt von den in das Betriebssystem integrierten Bibliotheken abhängig zu sein. Weitere Informationen finden Sie in der [ Breaking Change-Benachrichtigung](../../core/compatibility/globalization/5.0/icu-globalization-api.md).

## <a name="behavioral-differences"></a>Verhaltensunterschiede

Wenn Sie Funktionen wie `string.IndexOf(string)` verwenden, ohne die Überladung aufzurufen, die das Argument <xref:System.StringComparison> verwendet, könnten Sie beabsichtigen, eine *ordinale Suche* durchzuführen. Doch stattdessen greifen Sie unbeabsichtigt auf eine Abhängigkeit von kulturspezifischem Verhalten zurück. Da NLS und ICU unterschiedliche Logik in ihren linguistischen Vergleichsfunktionen implementieren, können die Ergebnisse von Methoden wie `string.IndexOf(string)` unerwartete Werte zurückgeben.

Dies kann sich sogar dort manifestieren, wo Sie nicht unbedingt erwarten, dass Globalisierungsfunktionen aktiv sind. Beispielsweise kann der folgende Code abhängig von der aktuellen Runtime eine andere Antwort liefern.

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a>Schutz vor unerwartetem Verhalten

Dieser Abschnitt enthält zwei Optionen für den Umgang mit unerwarteten Verhaltensänderungen in .NET 5.0.

### <a name="enable-code-analyzers"></a>Aktivieren von Codeanalysetools

[Codeanalysetools](../../fundamentals/code-analysis/overview.md) können möglicherweise fehlerhafte Aufrufstellen erkennen. Es wird empfohlen, die Analysetools von .NET Compiler Platform (Roslyn) in Ihrem Projekt zu aktivieren, um unerwünschtem Verhalten vorzubeugen. Mithilfe dieser Analysetools kann Code gekennzeichnet werden, der versehentlich eine linguistische Vergleichsfunktion verwendet, obwohl wahrscheinlich eine ordinale Vergleichsfunktion beabsichtigt war. Die folgenden Regeln sind bei der Kennzeichnung dieser Probleme nützlich:

- [CA1307: "StringComparison" zur Verdeutlichung angeben](../../fundamentals/code-analysis/quality-rules/ca1307.md)
- [CA1309: Ordinal-StringComparison verwenden.](../../fundamentals/code-analysis/quality-rules/ca1309.md)
- [CA1310: "StringComparison" für Richtigkeit angeben](../../fundamentals/code-analysis/quality-rules/ca1310.md)

Diese spezifischen Regeln sind standardmäßig nicht aktiviert. Legen Sie die folgenden Eigenschaften in Ihrer Projektdatei fest, um diese zu aktivieren und Verstöße wie Buildfehler anzuzeigen:

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
  <WarningsAsErrors>$(WarningsAsErrors);CA1307;CA1309;CA1310</WarningsAsErrors>
</PropertyGroup>
```

Der folgende Ausschnitt ist ein Codebeispiel, das die relevanten Warnungen oder Fehlermeldungen des Codeanalysetools erzeugt.

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1310 for string; CA1307 matches on char ','
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

Wenn Sie eine sortierte Zeichenfolgensammlung instanziieren oder eine vorhandene auf Zeichenfolgen basierende Sammlung sortieren, geben Sie in ähnlicher Weise eine explizite Vergleichsfunktion an.

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

### <a name="revert-back-to-nls-behaviors"></a>Zurücksetzen auf NLS-Verhaltensweisen

Um .NET 5-Anwendungen bei Ausführung unter Windows auf ältere NLS-Verhaltensweisen zurückzusetzen, folgen Sie den Anweisungen unter [.NET-Globalisierung und ICU](../globalization-localization/globalization-icu.md). Dieser anwendungsweite Kompatibilitätsschalter muss auf Anwendungsebene festgelegt werden. Einzelne Bibliotheken können dieses Verhalten nicht aktivieren oder deaktivieren.

> [!TIP]
> Es wird dringend empfohlen, die Codeanalyseregeln [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) und [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) zu aktivieren, um die Codepflege zu verbessern und eventuell vorhandene latente Fehler aufzudecken. Weitere Informationen finden Sie unter [Aktivieren von Codeanalysetools](#enable-code-analyzers).

## <a name="affected-apis"></a>Betroffene APIs

Die meisten .NET-Anwendungen werden aufgrund der Änderungen in .NET 5.0 nicht auf unerwartete Verhaltensweisen stoßen. Aufgrund der Anzahl der betroffenen APIs und ihrer Bedeutung für das gesamte .NET-Ökosystem sollten Sie sich jedoch bewusst sein, dass .NET 5.0 das Potenzial hat, unerwünschte Verhaltensweisen einzuführen oder latente Fehler offenzulegen, die bereits in Ihrer Anwendung vorhanden sind.

Zu den betroffenen APIs gehören u. a.:

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <xref:System.Globalization.TextInfo?displayProperty=fullName> (die meisten Member)
- <xref:System.Globalization.CompareInfo?displayProperty=fullName> (die meisten Member)
- <xref:System.Array.Sort%2A?displayProperty=fullName> (beim Sortieren von Zeichenfolgenarrays)
- <xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (wenn die Listenelemente Zeichenfolgen sind)
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)
- <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (wenn die Schlüssel Zeichenfolgen sind)
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (wenn die Gruppe Zeichenfolgen enthält)

> [!NOTE]
> Dies ist keine vollständige Liste der betroffenen APIs.

Alle der oben genannten APIs verwenden standardmäßig *linguistische* Zeichenfolgensuchen und -vergleiche unter Verwendung der [aktuellen Kultur](xref:System.Threading.Thread.CurrentCulture) des Threads. Die Unterschiede zwischen  *linguistischen* und *ordinalen* Suchen und Vergleichen werden im Abschnitt [Vergleich ordinaler und linguistischer Suchen und Vergleiche](#ordinal-vs-linguistic-search-and-comparison) vorgestellt.

Da ICU linguistische Zeichenfolgevergleiche anders als NLS implementiert, können Windows-basierte Anwendungen, bei denen ein Upgrade von einer früheren Version von .NET Core oder .NET Framework auf .NET 5.0 erfolgt und die eine der betroffenen APIs aufrufen, feststellen, dass die APIs beginnen, ein anderes Verhalten zu zeigen.

### <a name="exceptions"></a>Ausnahmen

* Wenn eine API einen expliziten Parameter des Typs `StringComparison` oder `CultureInfo` akzeptiert, setzt dieser Parameter das Standardverhalten der API außer Kraft.
* `System.String`-Member, bei denen der erste Parameter den Typ `char` hat (z. B. <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>), verwenden die ordinale Suche, es sei denn, der Aufrufer übergibt ein explizites `StringComparison`-Argument, das `CurrentCulture[IgnoreCase]` oder `InvariantCulture[IgnoreCase]` angibt.

Eine detailliertere Analyse des Standardverhaltens der einzelnen <xref:System.String>-APIs finden Sie im Abschnitt [Standardsuch- und -Vergleichstypen](#default-search-and-comparison-types).

## <a name="ordinal-vs-linguistic-search-and-comparison"></a>Vergleich ordinaler und linguistischer Suchen und Vergleiche

Bei *ordinalen* Suchen und Vergleichen (die auch als *nicht linguistisch* bezeichnet werden) wird eine Zeichenfolge in ihre einzelnen `char`-Elemente zerlegt und eine zeichenweise Suche bzw. ein zeichenweiser Vergleich durchgeführt. Beispielsweise werden die Zeichenfolgen `"dog"` und `"dog"` von der Vergleichsfunktion `Ordinal` als *gleich* bewertet, da die beiden Zeichenfolgen aus exakt der gleichen Folge von Zeichen bestehen. Allerdings werden `"dog"` und `"Dog"` von der Vergleichsfunktion `Ordinal` als *ungleich* bewertet, da sie nicht aus der exakt gleichen Folge von Zeichen bestehen. Das heißt, dass der Codepunkt von `'D'` in Großschreibung `U+0044` vor dem Codepunkt von `'d'` in Kleinschreibung `U+0064` vorkommt, was bedeutet dass `"dog"` vor `"Dog"` sortiert wird.

Die Vergleichsfunktion `OrdinalIgnoreCase` arbeitet weiterhin zeichenweise, berücksichtigt aber beim Durchführen des Vorgangs keine Unterschiede zwischen Groß- und Kleinschreibung. Bei der Vergleichsfunktion `OrdinalIgnoreCase` werden die Zeichenpaare `'d'` und `'D'` als *gleich* bewertet. Gleiches gilt für die Zeichenpaare `'á'` und `'Á'`. Aber das Zeichen ohne Akzent `'a'` wird als *ungleich* dem Zeichen mit Akzent `'á'` bewertet.

Einige Beispiele hierfür finden Sie in der folgenden Tabelle:

| Zeichenfolge 1 | Zeichenfolge 2 | Vergleich mit `Ordinal` | Vergleich mit `OrdinalIgnoreCase` |
|---|---|---|---|
| `"dog"` | `"dog"` | equal | equal |
| `"dog"` | `"Dog"` | Ungleich | equal |
| `"resume"` | `"Resume"` | Ungleich | equal |
| `"resume"` | `"résumé"` | Ungleich | Ungleich |

Unicode erlaubt auch Zeichenfolgen mit mehreren verschiedenen InMemory-Darstellungen. Zum Beispiel kann ein e mit Accent aigu (é) auf zwei mögliche Arten dargestellt werden:

* Als einzelnes Literalzeichen `'é'` (auch als `'\u00E9'` geschrieben).
* Als Literalzeichen ohne Akzent `'e'`, gefolgt von einer Kombination von Akzentmodifiziererzeichen `'\u0301'`.

Dies bedeutet, dass die folgenden _vier_ Zeichenfolgen bei der Anzeige alle in `"résumé"` resultieren, auch wenn ihre Bestandteile unterschiedlich sind. Die Zeichenfolgen verwenden eine Kombination aus Literalzeichen (`'é'`) oder Literalzeichen ohne Akzent (`'e'`) sowie den kombinierenden Akzentmodifizierer (`'\u0301'`).

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

Bei einer ordinalen Vergleichsfunktion wird keine dieser Zeichenfolgen als gleich zueinander bewertet. Das liegt daran, dass sie alle unterschiedliche zugrunde liegende Zeichenfolgen enthalten, auch wenn sie beim Rendern auf dem Bildschirm alle identisch aussehen.

Bei der Ausführung des Vorgangs `string.IndexOf(..., StringComparison.Ordinal)` sucht die Runtime nach einer exakten Teilzeichenfolgenübereinstimmung. Die Ergebnisse sind wie folgt.

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

Ordinale Such- und Vergleichsroutinen werden grundsätzlich nicht durch die Einstellung der Kultur des aktuellen Threads beeinflusst.

*Linguistische* Such- und Vergleichsroutinen zerlegen eine Zeichenfolge in *Sortierungselemente* und wenden Suchen oder Vergleiche auf diese Elemente an. Es gibt nicht notwendigerweise eine 1:1-Zuordnung zwischen den Zeichen einer Zeichenfolge und den zugehörigen Sortierungselementen. Beispielsweise kann eine Zeichenfolge der Länge 2 nur aus einem einzigen Sortierungselement bestehen. Wenn zwei Zeichenfolgen linguistisch sinnvoll verglichen werden, prüft die Vergleichsfunktion, ob die Sortierungselemente der beiden Zeichenfolgen die gleiche semantische Bedeutung haben, auch wenn die Literalzeichen der Zeichenfolge unterschiedlich sind.

Betrachten Sie nochmals die Zeichenfolge `"résumé"` und ihre vier Darstellungen. In der folgenden Tabelle ist jede Darstellung in ihre Sortierungselemente unterteilt.

| Zeichenfolge | Als Sortierungselemente |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

Ein Sortierungselement entspricht im Großen und Ganzen dem, was Leser als ein einzelnes oder eine Gruppe von Zeichen ansehen würden. Es ist konzeptionell einem [Graphemhaufen](character-encoding-introduction.md#grapheme-clusters) ähnlich, umfasst aber einen etwas größeren Schirm.

Bei einer linguistischen Vergleichsfunktion sind exakte Übereinstimmungen nicht notwendig. Stattdessen werden Sortierungselemente auf Grundlage ihrer semantischen Bedeutung verglichen. Beispielsweise bewertet eine linguistische Vergleichsfunktion die Teilzeichenketten `"\u00E9"` und `"e\u0301"` als gleich, da beide semantisch „ein kleingeschriebenes e mit einem Akut“ bedeuten. Dies ermöglicht es der `IndexOf`-Methode, die Teilzeichenfolge `"e\u0301"` innerhalb einer größeren Zeichenfolge zu finden, die die semantisch äquivalente Teilzeichenfolge `"\u00E9"` enthält (siehe das folgende Codebeispiel).

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

Dies hat zur Folge, dass zwei Zeichenfolgen unterschiedlicher Länge bei einem linguistischen Vergleich als gleich bewertet werden können. Aufrufer sollten darauf achten, keine von Groß-/Kleinschreibung geprägte Logik zu verwenden, die die Zeichenfolgenlänge in solchen Szenarien behandelt.

*Kulturabhängige* Such- und Vergleichsroutinen sind eine spezielle Form linguistischer Such- und Vergleichsroutinen. Bei einer kulturabhängigen Vergleichsfunktion wird das Konzept eines Sortierungselements um Informationen erweitert, die für die jeweilige Kultur spezifisch sind.

Wenn z. B. [ im ungarischen Alphabet](https://en.wikipedia.org/wiki/Hungarian_alphabet) die beiden Zeichen \<dz\> hintereinander stehen, werden sie als eigener Buchstabe betrachtet, der sich sowohl von \<d\> als auch von \<z\> unterscheidet. Das bedeutet, dass wenn \<dz\> in einer Zeichenfolge vorkommt, eine kulturabhängige ungarische Vergleichsfunktion diese als einzelnes Sortierungselement behandelt.

| Zeichenfolge | Als Sortierungselemente | Hinweise |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | (bei einer standardmäßigen linguistischen Vergleichsfunktion) |
| `"endz"` | `"e" + "n" + "dz"` | (bei einer von der ungarischen Kultur abhängigen Vergleichsfunktion) |

Bei Verwendung einer von der ungarischen Kultur abhängigen Vergleichsfunktion bedeutet dies, dass die Zeichenfolge `"endz"` *nicht* mit der Teilzeichenfolge `"z"` endet, da <\dz\> und <\z\> als Sortierungselemente mit unterschiedlicher semantischer Bedeutung anzusehen sind.

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - Verhalten: Sprach- und kulturabhängige Vergleichsfunktionen können von Zeit zu Zeit Verhaltensanpassungen erfahren. Sowohl ICU als auch die ältere Windows-Funktion NLS werden aktualisiert, um dem Wandel der Sprachen in der Welt Rechnung zu tragen. Weitere Informationen finden Sie im Blogbeitrag [Locale (Culture) Data Churn](/archive/blogs/shawnste/locale-culture-data-churn). Das Verhalten der *ordinalen* Vergleichsfunktion ändert sich nicht, da sie exakte bitweise Such- und Vergleichsvorgänge durchführt. Das Verhalten der Vergleichsfunktion *OrdinalIgnoreCase* kann sich jedoch ändern, wenn Unicode immer mehr Zeichensätze umfasst und Lücken in vorhandenen Daten zu Groß- und Kleinschreibung schließt.
> - Verwendung: Die Vergleichsfunktionen `StringComparison.InvariantCulture` und `StringComparison.InvariantCultureIgnoreCase` sind linguistische Vergleichsfunktionen, die nicht kulturabhängig sind. Das heißt, dass diese Vergleichsfunktionen Konzepte wie den Akzentbuchstaben é mit mehreren möglichen zugrunde liegenden Darstellungen verstehen und dass alle diese Darstellungen gleich behandelt werden sollten. Nicht kulturabhängige linguistische Vergleichsfunktionen sehen jedoch im Unterschied zu \<d\> oder \<z\> keine besondere Behandlung von \<dz\> vor, wie oben gezeigt. Sie enthalten auch keine Behandlung für Sonderfälle wie das deutsche Eszett (ß).

.NET bietet auch den *invarianten Globalisierungsmodus*. Dieser wählbare Modus deaktiviert Codepfade, die sich mit linguistischen Such- und Vergleichsroutinen befassen. In diesem Modus wird bei allen Vorgängen das Verhalten von *Ordinal* oder *OrdinalIgnoreCase* verwendet, und zwar unabhängig davon, welches `CultureInfo`- oder `StringComparison`-Argument der Aufrufer angibt. Weitere Informationen finden Sie unter [Runtimekonfigurationsoptionen für die Globalisierung](../../core/run-time-config/globalization.md) und [Invarianter Modus für .NET Core-Globalisierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET](best-practices-strings.md).

## <a name="security-implications"></a>Folgen für die Sicherheit

Wenn Ihre Anwendung eine betroffene API zum Filtern verwendet, empfehlen wir, die Codeanalyseregeln CA1307 und CA1309 zu aktivieren, um Stellen ausfindig zu machen, an denen statt einer gewöhnlichen Suche versehentlich eine linguistische Suche verwendet worden sein könnte. Codemuster wie die folgenden können anfällig für Sicherheitslücken sein.

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

Da die `string.IndexOf(string)`-Methode standardmäßig eine linguistische Suche verwendet, ist es möglich, dass eine Zeichenfolge das Literal `'<'` oder Zeichen `'&'` enthält und dass die `string.IndexOf(string)`-Routine `-1` zurückgibt, was darauf hinweist, dass die gesuchte Teilzeichenfolge nicht gefunden wurde. Die Codeanalyseregeln CA1307 und CA1309 kennzeichnen solche Aufrufstellen und warnen den Entwickler, dass ein potenzielles Problem vorliegt.

## <a name="default-search-and-comparison-types"></a>Typen von Standardsuchen und -vergleichen

Die folgende Tabelle enthält die standardmäßigen Such- und Vergleichstypen für verschiedene Zeichenfolgen und zeichenfolgenähnliche APIs. Wenn der Aufrufer einen expliziten `CultureInfo`- oder `StringComparison`-Parameter angibt, wird dieser Parameter gegenüber jeder Standardeinstellung bevorzugt.

| API | Standardverhalten | Hinweise |
|---|---|---|
| `string.Compare` | CurrentCulture | |
| `string.CompareTo` | CurrentCulture | |
| `string.Contains` | Ordinal | |
| `string.EndsWith` | Ordinal | (wenn der erste Parameter ein `char` ist) |
| `string.EndsWith` | CurrentCulture | (wenn der erste Parameter ein `string` ist) |
| `string.Equals` | Ordinal | |
| `string.GetHashCode` | Ordinal | |
| `string.IndexOf` | Ordinal | (wenn der erste Parameter ein `char` ist) |
| `string.IndexOf` | CurrentCulture | (wenn der erste Parameter ein `string` ist) |
| `string.IndexOfAny` | Ordinal | |
| `string.LastIndexOf` | Ordinal | (wenn der erste Parameter ein `char` ist) |
| `string.LastIndexOf` | CurrentCulture | (wenn der erste Parameter ein `string` ist) |
| `string.LastIndexOfAny` | Ordinal | |
| `string.Replace` | Ordinal | |
| `string.Split` | Ordinal | |
| `string.StartsWith` | Ordinal | (wenn der erste Parameter ein `char` ist) |
| `string.StartsWith` | CurrentCulture | (wenn der erste Parameter ein `string` ist) |
| `string.ToLower` | CurrentCulture | |
| `string.ToLowerInvariant` | InvariantCulture | |
| `string.ToUpper` | CurrentCulture | |
| `string.ToUpperInvariant` | InvariantCulture | |
| `string.Trim` | Ordinal | |
| `string.TrimEnd` | Ordinal | |
| `string.TrimStart` | Ordinal | |
| `string == string` | Ordinal | |
| `string != string` | Ordinal | |

Anders als `string`-APIs führen alle `MemoryExtensions`-APIs standardmäßig *ordinale* Suchen und Vergleiche durch, bei folgenden Ausnahmen.

| API | Standardverhalten | Hinweise |
|---|---|---|
| `MemoryExtensions.ToLower` | CurrentCulture | (bei Übergeben von NULL für ein `CultureInfo`-Argument) |
| `MemoryExtensions.ToLowerInvariant` | InvariantCulture | |
| `MemoryExtensions.ToUpper` | CurrentCulture | (bei Übergeben von NULL für ein `CultureInfo`-Argument) |
| `MemoryExtensions.ToUpperInvariant` | InvariantCulture | |

Eine Folge davon ist, dass bei der Konvertierung von Code von der Nutzung von `string` in die Nutzung von `ReadOnlySpan<char>` unbeabsichtigt Verhaltensänderungen herbeigeführt werden können. Es folgt ein Beispiel dafür.

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

Um dem zu begegnen, wird empfohlen, einen expliziten `StringComparison`-Parameter an diese APIs zu übergeben. Die Codeanalyseregeln CA1307 und CA1309 können dabei helfen.

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a>Weitere Informationen

- [Breaking Changes bei der Globalisierung](../../core/compatibility/globalization.md)
- [Bewährte Methoden zum Vergleichen von Zeichenfolgen in .NET](best-practices-strings.md)
- [Vergleichen von Zeichenfolgen in C#](../../csharp/how-to/compare-strings.md)
- [.NET-Globalisierung und ICU](../globalization-localization/globalization-icu.md)
- [Vergleich von ordinalen und kulturabhängigen Zeichenfolgenvorgängen](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [Übersicht über die Analyse von .NET-Quellcode](../../fundamentals/code-analysis/overview.md)
