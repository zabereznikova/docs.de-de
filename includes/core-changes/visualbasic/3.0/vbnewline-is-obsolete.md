---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116357"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>„Microsoft.VisualBasic.Constants.vbNewLine“ ist veraltet

Die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> ist ab .NET Core 3.0 Preview 8 als [\[Veraltet\]](xref:System.ObsoleteAttribute) gekennzeichnet.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

Ab .NET Core 3.0 Preview 8 wird das Attribut [Veraltet](xref:System.ObsoleteAttribute) auf die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> angewendet. Die Verwendung der Konstante führt zu einer Compilerwarnung. In NET Framework Core und in früheren Releases von .NET Core war sie nicht als veraltet gekennzeichnet.

Diese Änderung wurde vorgenommen, um Visual Basic als Sprache für die Entwicklung auf mehreren Plattformen zu unterstützen. Die Konstante <xref:Microsoft.VisualBasic.Constants.vbNewLine> entspricht `\r\n`, der Zeichenfolge für neue Zeile bei Windows. Bei Unix-basierten Systemen ist `\n` das Zeichen für eine neue Zeile.

#### <a name="recommended-action"></a>Empfohlene Aktion

Die [ObsoleteAttribute](xref:System.ObsoleteAttribute)-Meldung für <xref:Microsoft.VisualBasic.Constants.vbNewLine> enthält folgende Empfehlung:

Für einen Wagenrücklauf oder Zeilenvorschub verwenden Sie <xref:Microsoft.VisualBasic.Constants.vbCrLf>. For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>. (Verwenden Sie für einen Wagenrücklauf und Zeilenvorschub „vbCrLf“. Verwenden Sie auf der aktuellen Plattform für einen Zeilenumbruch „Environment.NewLine“.).

#### <a name="category"></a>Kategorie

Visual Basic

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
