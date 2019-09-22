---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117104"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>„Microsoft.VisualBasic.Constants.vbNewLine“ ist veraltet

Die <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>-Konstante ist im .NET Framework mit [ObsoleteAttribute](xref:System.ObsoleteAttribute) versehen und damit als veraltet gekennzeichnet. Das Attribut fehlte jedoch bislang in der .NET Core 3.0-Bibliothek.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 3.0 Preview 8

#### <a name="details"></a>Details

Ab Preview 8 von .NET Core 3.0 wird das Attribut [ObsoleteAttribute](xref:System.ObsoleteAttribute) auf die <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>-Konstante angewendet, um eine Angleichung an `vbNewLine` im .NET Framework zu erzielen. Die Verwendung der `vbNewLine`-Konstante führt zu einer Compilerwarnung. 

In früheren Versionen von .NET Core löste `vbNewLine` keine Compilerwarnung aus.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Die [ObsoleteAttribute](xref:System.ObsoleteAttribute)-Meldung für `vbNewLine` enthält folgende Empfehlung:

> For a carriage return and line feed, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). For the current platform's newline, use <xref:System.Environment.NewLine?displayProperty=nameWithType>. (Verwenden Sie für einen Wagenrücklauf und Zeilenvorschub „vbCrLf“. Verwenden Sie auf der aktuellen Plattform für einen Zeilenumbruch „Environment.NewLine“.).

#### <a name="category"></a>Category (Kategorie)

Visual Basic

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-- >

