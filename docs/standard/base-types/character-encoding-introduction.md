---
title: Einführung in die Zeichencodierung in .NET
description: Erfahren Sie mehr über die Zeichencodierung und -decodierung in .NET.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: 1b6ec6a7275408d4a8061c0de92cdf6e82dd533a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288042"
---
# <a name="character-encoding-in-net"></a>Zeichencodierung in .NET

Dieser Artikel bietet eine Einführung in die von .NET verwendeten Zeichencodierungssysteme. Es wird erläutert, wie die Typen <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune> und <xref:System.Globalization.StringInfo> mit Unicode, UTF-16 und UTF-8 funktionieren.

Der Begriff *Zeichen* wird hier im allgemeinen Sinn für ein Zeichen verwendet, das *vom Leser als einzelnes Anzeigeelement wahrgenommen wird*. Gängige Beispiele sind der Buchstabe „a“, das Symbol „@“ und das Emoji 🐂. Mitunter setzt sich ein als ein Zeichen wahrgenommenes Zeichen tatsächlich aus mehreren unabhängigen Anzeigeelementen zusammen, dies wird im Abschnitt zu [Graphemhaufen](#grapheme-clusters) erläutert.

## <a name="the-string-and-char-types"></a>Die string- und char-Typen.

Eine Instanz der [string](xref:System.String)-Klasse stellt Text dar. Ein `string` ist logisch gesehen eine Abfolge von 16-Bit-Werten, von denen jeder eine Instanz der [char](xref:System.Char)-Struktur ist. Die [string.Length](xref:System.String.Length)-Eigenschaft gibt die Anzahl von `char`-Instanzen in der `string`-Instanz zurück.

Die folgende Beispielfunktion gibt die Werte aller `char`-Instanzen in einem `string` in Hexadezimalnotation zurück:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::

Wenn Sie an diese Funktion die string „Hello“ übergeben, erhalten Sie die folgende Ausgabe:

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

Jedes Zeichen wird durch einen einzelnen `char`-Wert repräsentiert. Dieses Muster gilt für die meisten Sprachen der Welt. Beispielsweise sehen Sie nachfolgend die Ausgabe für zwei chinesische Zeichen, die ausgesprochen wie *nǐ hǎo* klingen und *Hallo* bedeuten:

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

Für einige Sprachen und für einige Symbole und Emojis werden jedoch zwei `char`-Instanzen benötigt, um ein einzelnes Zeichen darzustellen. Vergleichen Sie beispielsweise die Zeichen und `char`-Instanzen in dem Wort, das in der Osage-Sprache *Osage* bedeutet:

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

Im vorherigen Beispiel wird jedes Zeichen mit Ausnahme des Leerzeichens durch zwei `char`-Instanzen repräsentiert.

Ein einzelnes Unicode-Emoji wird ebenfalls durch zwei `char`s dargestellt, wie im folgenden Beispiel eines Emojis für einen Ochsen:

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

Diese Beispiele zeigen, dass der Wert von `string.Length`, der die Anzahl von `char`-Instanzen angibt, nicht notwendigerweise der Anzahl angezeigter Zeichen entsprechen muss. Eine einzelne `char`-Instanz repräsentiert für sich genommen nicht zwingend ein Zeichen.

Die `char`-Paare, die einem einzelnen Zeichen zugeordnet sind, werden als *Ersatzzeichenpaare* bezeichnet. Um deren Funktionsweise zu verstehen, müssen wir die Unicode- und die UTF-16-Codierung verstehen.

## <a name="unicode-code-points"></a>Unicode-Codepunkte

Unicode ist ein internationaler Codierungsstandard, der in zahlreichen Plattformen und mit verschiedenen Sprachen und Skripts eingesetzt wird.

Der Unicode-Standard definiert über 1,1 Millionen [Codepunkte](https://www.unicode.org/glossary/#code_point). Ein Codepunkt ist ein ganzzahliger Wert, der zwischen 0 und `U+10FFFF` liegen kann (in Dezimalschreibweise: 1.114.111). Einige Codepunkte sind Buchstaben, Symbolen oder Emojis zugewiesen. Andere sind Aktionen zugeordnet, die steuern, wie Textelemente oder Zeichen angezeigt werden – beispielsweise ein Zeilenvorschub. Viele Codepunkte sind noch nicht zugewiesen.

Nachfolgend werden einige Beispiele für Codepunktzuweisungen aufgelistet, mit Links zu Unicode-Diagrammen, in denen sie angezeigt werden:

|Decimal|Hex       |Beispiel|Beschreibung|
|------:|----------|-------|-----------|
|10     | `U+000A` |Nicht zutreffend| [ZEILENVORSCHUB](https://www.unicode.org/charts/PDF/U0000.pdf) |
|65     | `U+0061` | eine | [LATEINISCHER KLEINBUCHSTABE A](https://www.unicode.org/charts/PDF/U0000.pdf) |
|562    | `U+0232` | Ȳ | [LATEINISCHER GROSSBUCHSTABE MIT MAKRON](https://www.unicode.org/charts/PDF/U0180.pdf) |
|68.675 | `U+10C43`| 𐱃 | [ALTTÜRKISCHES ORCHON-SCHRIFTZEICHEN AT](https://www.unicode.org/charts/PDF/U10C00.pdf) |
|127.801| `U+1F339`| 🌹 | [Rosen-Emoji](https://www.unicode.org/charts/PDF/U1F300.pdf) |

Auf Codepunkte wird hauptsächlich durch Verwendung der Syntax `U+xxxx` verwiesen, wobei es sich bei `xxxx` um den ganzzahligen Wert in Hexadezimalcodierung handelt.

Der vollständige Bereich der Codepunkte enthält zwei Unterbereiche:

* Die **Basic Multilingual Plane (BMP)** im Bereich `U+0000..U+FFFF`. Dieser 16-Bit-Bereich umfasst 65.536 Codepunkte und reicht zur Abdeckung der meisten Schriftsysteme der Welt aus.
* **Ergänzende Codepunkte** im Bereich `U+10000..U+10FFFF`. Dieser 21-Bit-Bereich umfasst mehr als eine Million zusätzlicher Codepunkte, die für weniger bekannte Sprachen und zu anderen Zwecken genutzt werden können, wie beispielsweise Emojis.

Das folgende Diagramm veranschaulicht die Beziehung zwischen der BMP und den ergänzenden Codepunkten.

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP und ergänzende Codepunkte":::

## <a name="utf-16-code-units"></a>UTF-16-Codeeinheiten

16-Bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) ist ein Zeichencodierungssystem, das 16-Bit-*Codeeinheiten* zur Darstellung von Unicode-Codepunkten verwendet. .NET verwendet UTF-16 zum Codieren von Text in einem `string`. Eine `char`-Instanz repräsentiert eine 16-Bit-Codeeinheit.

Eine einzelne 16-Bit-Codeeinheit kann jeden Codepunkt im 16-Bit-Bereich der Basic Multilingual Plane (BMP) repräsentieren. Aber für einen Codepunkt im ergänzenden Bereich werden zwei `char`-Instanzen benötigt.

## <a name="surrogate-pairs"></a>Ersatzzeichenpaare

Die Übersetzung von zwei 16-Bit-Werten in einen einzelnen 21-Bit-Wert wird durch einen speziellen Bereich ermöglicht, der die sogenannten *Ersatzcodepunkte* von `U+D800` bis `U+DFFF` einschließlich (in Dezimalschreibweise: 55.296 bis 57.343) umfasst.

Das folgende Diagramm veranschaulicht die Beziehung zwischen der BMP und den Ersatzcodepunkten.

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="BMP und Ersatzcodepunkte":::

Wenn auf einen *hohen* Ersatzcodepunkt (`U+D800..U+DBFF`) unmittelbar ein *niedriger* Ersatzcodepunkt (`U+DC00..U+DFFF`) folgt, wird das Paar anhand der folgenden Formel als ergänzender Codepunkt interpretiert:

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

Nachstehend sehen Sie die gleiche Formel unter Verwendung der Dezimalschreibweise:

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

Ein *hoher* Ersatzcodepunkt weist keinen höheren Zahlenwert auf als ein *niedriger* Ersatzcodepunkt. Der hohe Ersatzcodepunkt wird so bezeichnet, weil er zum Berechnen der hohen 11 Bits des vollständigen 21-Bit-Codepunktbereichs verwendet wird. Der niedrige Ersatzcodepunkt wird zum Berechnen der unteren 10 Bits verwendet.

Beispielsweise wird der tatsächliche Codepunkt, der dem Ersatzzeichenpaar `0xD83C` und `0xDF39` entspricht, folgendermaßen berechnet:

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

Hier dieselbe Berechnung in Dezimalschreibweise:

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

Das vorstehende Beispiel zeigt, dass es sich bei `"\ud83c\udf39"` um die UTF-16-Codierung des zuvor erwähnten Codepunkts `U+1F339 ROSE ('🌹')` handelt.

## <a name="unicode-scalar-values"></a>Unicode-Skalarwerte

Der Begriff [Unicode-Skalarwert](https://www.unicode.org/glossary/#unicode_scalar_value) bezieht sich auf alle Codepunkte mit Ausnahme der Ersatzcodepunkte. Anders ausgedrückt: Ein Skalarwert ist ein beliebiger Codepunkt, der einem Zeichen zugewiesen ist oder in Zukunft einem Zeichen zugewiesen werden kann. „Zeichen“ bezieht sich hierbei auf ein beliebiges Element, das einem Codepunkt zugewiesen werden kann, darunter z. B. Aktionen zum Steuern der Anzeige von Text oder Zeichen.

Das nachstehende Diagramm veranschaulicht die Skalarwert-Codepunkte.

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="Skalarwerte":::

### <a name="the-rune-type-as-a-scalar-value"></a>Der Rune-Typ als Skalarwert

Ab .NET Core 3.0 repräsentiert der <xref:System.Text.Rune?displayProperty=fullName>-Typ einen Unicode-Skalarwert. **`Rune` ist in .NET Core 2. oder .NET Framework 4.x nicht verfügbar.**

Der `Rune`-Konstruktor überprüft, ob die Ergebnisinstanz ein gültiger Unicode-Skalarwert ist, anderenfalls wird eine Ausnahme ausgelöst. Das folgende Codebeispiel zeigt eine erfolgreiche Instanziierung von `Rune`-Instanzen, weil es sich bei der Eingabe um gültige Skalarwerte handelt:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::

Das folgende Beispiel führt zu einer Ausnahme, weil der Codepunkt sich im Ersatzbereich befindet und nicht Teil eines Ersatzzeichenpaars ist:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::

Das nachstehende Beispiel führt zu einer Ausnahme, weil der Codepunkt nicht im ergänzenden Bereich liegt:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::

### <a name="rune-usage-example-changing-letter-case"></a>Beispiel für die Verwendung von Rune: Änderung der Groß-/Kleinschreibung

Eine API, die einen `char`-Wert verwendet und annimmt, dass sie mit einem Codepunkt arbeitet, bei dem es sich um einen Skalarwert handelt, funktioniert nicht ordnungsgemäß, wenn der `char`-Wert aus einem Ersatzzeichenpaar stammt. Betrachten Sie beispielsweise die folgende Methode, die <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> für jeden char in einem string aufruft:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::

Wenn die Eingabezeichenfolge (`input` string) den Deseret-Buchstaben `er` in Kleinschreibung (`𐑉`) enthält, wird mit diesem Code keine Konvertierung in einen Großbuchstaben (`𐐡`) durchgeführt. Der Code ruft `char.ToUpperInvariant` separat für jeden Ersatzcodepunkt auf, `U+D801` und `U+DC49`. Aber `U+D801` selbst weist nicht genügend Informationen für die Identifizierung als Kleinbuchstabe auf und wird daher von `char.ToUpperInvariant` nicht verarbeitet. `U+DC49` wird in gleicher Weise behandelt. Als Ergebnis wird der Kleinbuchstabe „𐑉“ in der Eingabezeichenfolge (`input` string) nicht in den Großbuchstaben „𐐡“ konvertiert wird.

Hier sind zwei Optionen für die korrekte Konvertierung von string in Großbuchstaben:

* Rufen Sie <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> für den Eingabe-string auf, statt `char` für `char` zu durchlaufen. Die `string.ToUpperInvariant`-Methode hat Zugriff auf beide Teile des Ersatzzeichenpaars, deshalb können alle Unicode-Codepunkte ordnungsgemäß verarbeitet werden.
* Durchlaufen Sie die Unicode-Skalarwerte nicht als `char`-Instanzen, sondern als `Rune`-Instanzen, wie im folgenden Beispiel gezeigt. Eine `Rune`-Instanz ist ein gültiger Unicode-Skalarwert, deshalb kann sie an APIs übergeben werden, die einen Skalarwert für die Verarbeitung erwarten. Beispielsweise liefert der Aufruf von <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> wie im folgenden Beispiel richtige Ergebnisse:

  :::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::

### <a name="other-rune-apis"></a>Andere Rune-APIs

Der `Rune`-Typ macht Entsprechungen vieler der `char`-APIs verfügbar. Beispielsweise spiegeln die folgenden Methoden statische APIs für den `char`-Typ:

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

Um den Rohskalarwert aus einer `Rune`-Instanz abzurufen, verwenden Sie die <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType>-Eigenschaft.

Um eine `Rune`-Instanz wieder ein eine `char`-Sequenz zu konvertieren, verwenden Sie <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> oder die <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType>-Methode.

Da jeder Unicode-Skalarwert durch einen einzelnen `char` oder durch ein Ersatzzeichenpaar dargestellt wird, kann jede `Rune`-Instanz durch höchstens 2 `char`-Instanzen dargestellt werden. Verwenden Sie <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType>, um anzuzeigen, wie viele `char`-Instanzen zur Darstellung einer `Rune`-Instanz benötigt werden.

Weitere Informationen zum .NET-Typ `Rune` finden Sie in der [`Rune`API-Referenz](xref:System.Text.Rune).

## <a name="grapheme-clusters"></a>Graphemhaufen

Was wie ein einziges Zeichen aussieht, kann tatsächlich eine Kombination mehrerer Codepunkte sein, deshalb wird zur Beschreibung anstelle des Begriffs „Zeichen“ häufig der Begriff [Graphemhaufen](https://www.unicode.org/glossary/#grapheme_cluster) verwendet. Der äquivalente Begriff in .NET lautet [Textelement](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).

Betrachten Sie die `string`-Instanzen „a“, „á“, „á“ und `👩🏽‍🚒`. Wenn Ihr Betriebssystem diese gemäß Spezifikation im Unicode-Standard verarbeitet, wird jede dieser `string`-Instanzen als ein einzelnes Textelement bzw. als Graphemhaufen angezeigt. Aber die letzten beiden werden durch mehr als einen Skalarwert-Codepunkt repräsentiert.

* Die string-Instanz „a“ wird durch einen Skalarwert repräsentiert und enthält eine `char`-Instanz.

  * `U+0061 LATIN SMALL LETTER A`

* Die string-Instanz „á“ wird durch einen Skalarwert repräsentiert und enthält eine `char`-Instanz.

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* Die string-Instanz „á“ sieht aus wie „á“, wird jedoch durch zwei Skalarwerte repräsentiert und enthält zwei `char`-Instanzen.

  * `U+0065 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* Die string-Instanz `👩🏽‍🚒` schließlich wird durch vier Skalarwerte repräsentiert und enthält sieben `char`-Instanzen.

  * `U+1F469 WOMAN` (ergänzender Bereich, erfordert ein Ersatzzeichenpaar)
  * `U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (ergänzender Bereich, erfordert ein Ersatzzeichenpaar)
  * `U+200D ZERO WIDTH JOINER`
  * `U+1F692 FIRE ENGINE` (ergänzender Bereich, erfordert ein Ersatzzeichenpaar)

In einigen der vorhergehenden Beispiele – beispielsweise dem kombinierten Akzentmodifizierer oder dem Modifizierer für den Hautton – wird der Codepunkt nicht als eigenständiges Element auf dem Bildschirm angezeigt. Stattdessen dient er zum Ändern des Aussehens eines vorangegangenen Textelements. Diese Beispiele zeigen, dass möglicherweise mehrere Skalarwerte erforderlich sind, um ein einzelnes „Zeichen“ oder einen „Graphemhaufen“ zu erzeugen.

Um die Graphemhaufen für einen `string` aufzulisten, verwenden Sie die <xref:System.Globalization.StringInfo>-Klasse wie im folgenden Beispiel gezeigt. Wenn Sie mit Swift vertraut sind: Der .NET-Typ `StringInfo` ähnelt vom Konzept her dem [`character`-Typ in Swift](https://developer.apple.com/documentation/swift/character).

### <a name="example-count-char-rune-and-text-element-instances"></a>Beispiel: Zählen von char-, Rune- und Textelementinstanzen

In den .NET-APIs wird ein Graphemhaufen als *Textelement* bezeichnet. Die folgenden Methoden veranschaulichen die Unterschiede zwischen `char`-, `Rune`- und Textelementinstanzen in einem `string`:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::

Wenn Sie diesen Code in .NET Framework oder .NET Code 3.1 oder früher ausführen, wird die Textelementanzahl für das Emoji als `4` angezeigt. Dies liegt an einem Fehler in der `StringInfo`-Klasse, der in .NET 5 behoben wurde.

### <a name="example-splitting-string-instances"></a>Beispiel: Aufteilen von string-Instanzen

Vermeiden Sie beim Aufteilen von `string`-Instanzen das Teilen von Ersatzzeichenpaaren und Graphemhaufen. Sehen Sie sich das folgende fehlerhafte Codebeispiel an, bei dem nach jeweils 10 Zeichen in einem string ein Zeilenumbruch eingefügt werden soll:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::

Dieser Code zählt `char`-Instanzen auf, deshalb wird ein Ersatzzeichenpaar, dass sich über eine 10-`char`-Grenze erstreckt, aufgeteilt und dazwischen ein Zeilenumbruch eingefügt. Diese Einfügung führt zu einer Datenbeschädigung, weil Ersatzcodepunkte nur als Paar eine Bedeutung tragen.

Die Möglichkeit einer Datenbeschädigung ist nicht ausgeschlossen, wenn Sie anstelle von `char`-Instanzen `Rune`-Instanzen (Skalarwerte) aufzählen. Ein Satz aus `Rune`-Instanzen kann einen Graphemhaufen bilden, der sich über eine 10-`char`-Grenze erstreckt. Wenn der Graphemhaufen geteilt wird, kann er nicht ordnungsgemäß interpretiert werden.

Ein besserer Ansatz besteht darin, den string durch Zählen der Graphemhaufen oder Textelemente zu teilen, wie im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::

Wie bereits erwähnt, kann die `StringInfo`-Klasse in .NET-Implementierungen (im Gegensatz zu .NET 5) einige Graphemhaufen jedoch falsch verarbeiten.

## <a name="utf-8-and-utf-32"></a>UTF-8 und UTF-32

Die vorangegangenen Abschnitte konzentrierten sich auf UTF-16, weil .NET UTF-16 zur Codierung von `string`-Instanzen verwendet. Für Unicode sind einige weitere Codierungssysteme vorhanden – [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) und [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32). Diese Codierungen verwenden 8-Bit-Codeeinheiten bzw. 32-Bit-Codeeinheiten.

Wie UTF-16 werden in UTF-8 mehrere Codeeinheiten benötigt, um einige Unicode-Skalarwerte darzustellen. UTF-32 kann jeden beliebigen Skalarwert in einer einzelnen 32-Bit-Codeeinheit darstellen.

Hier sind einige Beispiele, die zeigen, wie derselbe Unicode-Codepunkt in jedem dieser drei Unicode-Codierungssysteme dargestellt wird:

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

Wie bereits erwähnt, ist eine einzelne UTF-16-Codeeinheit aus einem [Einzelzeichenpaar](#surrogate-pairs) für sich genommen bedeutungslos. Ebenso ist eine einzelne UTF-8-Codeeinheit für sich genommen bedeutungslos, wenn sie in einer Sequenz von zwei, drei oder vier Einheiten zur Berechnung eines Skalarwerts verwendet wird.

### <a name="endianness"></a>Endianness

In .NET werden die UTF-16-Codeeinheiten für einen string in zusammenhängenden Speicherbereichen als Sequenz aus 16-Bit-Ganzzahlen (`char`-Instanzen) gespeichert. Die Bits der einzelnen Codeeinheiten werden gemäß [Endianwert](https://en.wikipedia.org/wiki/Endianness) der aktuellen Architektur angeordnet.

In einer Little-Endian-Architektur wird der aus UTF-16-Codeeinheiten `[ D801 DCCC ]` bestehende string im Arbeitsspeicher in Form der Bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]` angeordnet. In einer Big-Endian-Architektur würde derselbe string im Arbeitsspeicher in Form der Bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]` angeordnet werden.

Computersysteme, die miteinander kommunizieren, müssen sich auf die Darstellung von Daten einigen, die übertragen werden. Die meisten Netzwerkprotokolle verwenden UTF-8 als Standard für die Textübertragung – unter anderem, um Probleme zu vermeiden, die durch die Kommunikation eines Big-Endian-Computers mit einem Little-Endian-Computer entstehen könnten. Der aus den UTF-8-Codepunkten `[ F0 90 93 8C ]` bestehende string wird immer in Form der Bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` dargestellt, unabhängig vom Endianwert.

Um UTF-8 für die Übertragung von Text zu verwenden, nutzen .NET-Anwendungen häufig Code wie im folgenden Beispiel:

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

Im vorstehenden Beispiel decodiert die Methode [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) den UTF-16-`string` zurück in eine Reihe von Unicode-Skalarwerten. Anschließend werden diese Skalarwerte wieder in UTF-8 codiert, und die Ergebnissequenz wird in einem `byte`-Array platziert. Die Methode [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) führt die umgekehrte Transformation durch, sie konvertiert einen UTF-8-`byte`-Array in einen UTF-16-`string`.

> [!WARNING]
> Weil UTF-8 im Internet so weit verbreitet ist, kann es verlockend sein, Rohbytes aus der Verbindung zu lesen und die Daten so zu behandeln, als handele es sich um UTF-8. Sie müssen jedoch sicherstellen, dass die Daten tatsächlich wohlgeformt sind. Ein schädlicher Client überträgt möglicherweise nicht wohlgeformte UTF-8-Daten an Ihren Dienst. Wenn Sie mit diesen Daten arbeiten, als seien es wohlgeformte Daten, kann dies zu Fehlern oder Sicherheitslücken in Ihrer Anwendung führen. Um UTF-8-Daten zu validieren, können Sie eine Methode wie `Encoding.UTF8.GetString` verwenden, die während der Konvertierung der eingehenden Daten in einen `string` eine Überprüfung durchführt.

### <a name="well-formed-encoding"></a>Wohlgeformte Codierung

Eine wohlgeformte Unicode-Codierung ist ein string aus Codeeinheiten, die eindeutig decodiert und ohne Fehler in eine Sequenz von Unicode-Skalarwerten konvertiert werden können. Wohlgeformte Daten können ohne Einschränkung zwischen UTF-8, UTF-16 und UTF-32 hin- und her transcodiert werden.

Die Frage, ob eine Codierungssequenz wohlgeformt ist oder nicht, hat nichts mit dem Endianwert einer Computerarchitektur zu tun. Eine nicht wohlgeformte UTF-8-Sequenz ist sowohl für einen Big-Endian- als auch für einen Little-Endian-Computer nicht wohlgeformt.

Hier sehen Sie einige Beispiele für nicht wohlgeformte Codierungen:

* In UTF-8 ist die Sequenz `[ 6C C2 61 ]` nicht wohlgeformt, weil auf `C2` nicht `61` folgen darf.

* In UTF-16 ist die Sequenz `[ DC00 DD00 ]` nicht wohlgeformt (oder in C# der string `"\udc00\udd00"`), weil auf das niedrige Ersatzzeichen `DC00` nicht ein weiteres niedriges Ersatzzeichen `DD00` folgen kann.

* In UTF-32 ist die Sequenz `[ 0011ABCD ]` nicht wohlgeformt, weil `0011ABCD` außerhalb des Bereichs für Unicode-Skalarwerte liegt.

In .NET enthalten `string`-Instanzen fast immer wohlgeformte UTF-16-Daten, aber dies ist nicht garantiert. Die folgenden Beispiele zeigen gültigen C#-Code, der nicht wohlgeformte UTF-16-Daten in `string`-Instanzen erzeugt.

* Ein nicht wohlgeformtes Literal:

  ```csharp
  const string s = "\ud800";
  ```

* Eine Teilzeichenfolge, die ein Ersatzzeichenpaar aufteilt:

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

APIs wie [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) geben keine nicht wohlgeformten `string`-Instanzen zurück. Die Methoden `Encoding.GetString` und `Encoding.GetBytes` erkennen nicht wohlgeformte Sequenzen in der Eingabe und führen beim Generieren der Ausgabe Zeichenersetzungen durch. Wenn [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) beispielsweise ein Nicht-ASCII-Byte (außerhalb des Bereichs U+0000..U+007F) in der Eingabe erkennt, wird ein ? in die zurückgegebene `string`-Instanz eingefügt. [`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) ersetzt nicht wohlgeformte UTF-8-Sequenzen in der zurückgegebenen `string`-Instanz durch `U+FFFD REPLACEMENT CHARACTER ('�')`. Weitere Informationen finden Sie unter [Unicode-Standard](https://www.unicode.org/versions/latest/) in den Abschnitten 5.22 und 3.9.

Die integrierten `Encoding`-Klassen können auch so konfiguriert werden, dass sie anstelle einer Zeichenersetzung eine Ausnahme auslösen, wenn falsch formatierte Sequenzen erkannt werden. Dieser Ansatz findet häufig in Anwendungen mit hohen Sicherheitsanforderungen Anwendung, bei denen eine Zeichenersetzung möglicherweise nicht akzeptabel ist.

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

Informationen zur Verwendung der integrierten `Encoding`-Klassen finden Sie unter [Verwenden von Zeichencodierungsklassen in .NET](character-encoding.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [Globalisierung und Lokalisierung](../globalization-localization/index.md)
