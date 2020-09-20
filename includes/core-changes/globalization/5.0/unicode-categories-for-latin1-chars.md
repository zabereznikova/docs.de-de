---
ms.openlocfilehash: 48d2f1b5fa2eced30d3c9fb65804268904f11ab8
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065062"
---
### <a name="unicode-category-changed-for-some-latin-1-characters"></a>Geänderte Unicode-Kategorie für einige Zeichen in Lateinisch-1

<xref:System.Char>-Methoden geben nun die richtige Unicode-Kategorie für Zeichen im Bereich Lateinisch-1 zurück. Die Kategorie entspricht der des Unicode-Standards.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET verwendeten <xref:System.Char>-Methoden eine feste Liste mit Unicode-Kategorien für Zeichen im Bereich Lateinisch-1. Im Unicode-Standard wurden jedoch seit der Implementierung dieser APIs die Kategorien für einige dieser Zeichen geändert, was zu Abweichungen führte. Außerdem gab es Unterschiede zwischen <xref:System.Char> und <xref:System.Globalization.CharUnicodeInfo>-APIs, die dem Unicode-Standard folgen. Ab .NET 5.0 verwenden <xref:System.Char>-Methoden für alle Zeichen die dem Unicode-Standard entsprechende Unicode-Kategorie und geben auch diese zurück.

In der folgenden Tabelle sind die Zeichen aufgeführt, deren Unicode-Kategorie sich in .NET 5.0 geändert hat:

| Zeichen    | Unicode-Kategorie<br>in früheren .NET-Versionen | Unicode-Kategorie<br>in .NET 5.0 und höher |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| § (\u00a7)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| ª (\u00aa)   | `LowercaseLetter`                             | `OtherLetter`                                      |
| SHY (\u00ad) | `DashPunctuation`                             | `Format`                                           |
| ¶ (\u00b6)   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| º (\u00ba)   | `LowercaseLetter`                             | `OtherLetter`                                      |

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0 RC1

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie über Code verfügen, der die Unicode-Zeichenkategorie mithilfe der Klasse <xref:System.Char> abruft und davon ausgeht, dass die Kategorie sich nie ändert, müssen Sie diesen möglicherweise aktualisieren.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde vorgenommen, damit die vom Typ <xref:System.Char> zurückgegebenen Kategorien sowohl dem Unicode-Standard als auch dem Typ <xref:System.Globalization.CharUnicodeInfo> entsprechen.

#### <a name="category"></a>Kategorie

- Core .NET-Bibliotheken
- Globalisierung

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

Darüber hinaus sind von dieser Änderung alle Klassen betroffen, die beim Abrufen der Unicode-Zeichenkategorie von <xref:System.Char> abhängen, z. B. <xref:System.Text.RegularExpressions.Regex>.

<!--

#### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

-->
