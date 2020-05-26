---
ms.openlocfilehash: 298cb441bf9fe7daddb30c85f9d7366dc972628c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721791"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a>Ersetzen von falsch formatierten UTF-8-Bytesequenzen von Unicode-Vorgaben abhängig

Wenn die Klasse <xref:System.Text.UTF8Encoding> während einer Byte-zu-Zeichen-Transcodierung auf eine falsch formatierte UTF-8-Bytesequenz trifft, ersetzt sie diese in der Ausgabezeichenfolge durch ein „�“-Zeichen (U+FFFD, ERSETZUNGSZEICHEN). .NET Core 3.0 unterscheidet sich von früheren Versionen von .NET Core und .NET Framework durch die Einhaltung der bewährten Unicode-Methoden für die Durchführung dieser Ersetzung während des Transcodierungsvorgangs.

Dies ist Teil einer größeren Maßnahme zur Verbesserung der UTF-8-Verarbeitung in .NET, auch bei den neuen Typen <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> und <xref:System.Text.Rune?displayProperty=nameWithType>. Der Typ <xref:System.Text.UTF8Encoding> wurde mit einem verbesserten Verfahren für die Fehlerbehandlung versehen, sodass die Ausgabe konsistent mit den neu eingeführten Typen generiert wird.

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Core 3.0 führt die <xref:System.Text.UTF8Encoding>-Klasse bei der Transcodierung von Bytes in Zeichen Zeichenersetzung basierend auf bewährten Unicode-Methoden aus. Der verwendete Ersetzungsmechanismus wird durch [The Unicode Standard, Version 12.0, Abschnitt 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) unter der Überschrift _U+FFFD Substitution of Maximum Subparts_ beschrieben.

Dieses Verhalten gilt _nur_, wenn die Eingabebytesequenz falsch formatierte UTF-8-Daten enthält. Außerdem gilt: Wenn die <xref:System.Text.UTF8Encoding>-Instanz mit `throwOnInvalidBytes: true` erstellt wurde, löst die `UTF8Encoding`-Instanz bei ungültiger Eingabe weiterhin eine Ausnahme aus, anstatt eine Ersetzung mit U+FFFD auszuführen. Weitere Informationen über den Konstruktor `UTF8Encoding` finden Sie unter <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.

In der folgenden Tabelle wird die Auswirkung dieser Änderung mit einer ungültigen 3-Byte-Eingabe veranschaulicht:

| Falsch formatierte 3-Byte-Eingabe | Ausgabe vor .NET Core 3.0          | Ausgabe ab .NET Core 3.0        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | `[ FFFD FFFD ]` (2-Zeichen-Ausgabe) | `[ FFFD FFFD FFFD ]` (3-Zeichen-Ausgabe) |

Die 3-Zeichen-Ausgabe ist die bevorzugte Ausgabe gemäß _Tabelle 3–9_ der oben genannten PDF-Datei zum Unicode-Standard.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Auf der Seite des Entwicklers ist keine Aktion erforderlich.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
