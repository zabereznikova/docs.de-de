---
ms.openlocfilehash: 86cdb845c436f424bbcc70e0736568031143b204
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522692"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>„Microsoft.VisualBasic.Constants.vbNewLine“ ist veraltet

Die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> ist ab .NET Core 3.0 Preview 8 als [Veraltet](xref:System.ObsoleteAttribute) gekennzeichnet.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Core 3.0 Preview 8 wird das Attribut [Veraltet](xref:System.ObsoleteAttribute) auf die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> angewendet. Die Verwendung der Konstante führt zu einer Compilerwarnung. In früheren Releases von .NET Core und .NET Framework war sie nicht als veraltet gekennzeichnet.

Diese Änderung wurde vorgenommen, um Visual Basic als Sprache für die Entwicklung auf mehreren Plattformen zu unterstützen. Die Konstante `vbNewLine` entspricht `\r\n`, der Zeichenfolge für neue Zeile bei Windows. Bei Unix-basierten Systemen ist `\n` das Zeichen für eine neue Zeile.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Die [ObsoleteAttribute](xref:System.ObsoleteAttribute)-Meldung für `vbNewLine` enthält folgende Empfehlung:

> For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>. (Verwenden Sie für einen Wagenrücklauf und Zeilenvorschub „vbCrLf“. Verwenden Sie auf der aktuellen Plattform für einen Zeilenumbruch „Environment.NewLine“.).

#### <a name="category"></a>Kategorie

Visual Basic

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
