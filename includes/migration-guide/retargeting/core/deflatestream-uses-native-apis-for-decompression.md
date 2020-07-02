---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614487"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream verwendet native APIs für die Dekomprimierung

#### <a name="details"></a>Details

Ab .NET Framework 4.7.2 hat sich die Implementierung der Dekomprimierung in der `T:System.IO.Compression.DeflateStream`-Klasse so geändert, dass standardmäßig native Windows-APIs verwendet werden. In der Regel führt dies zu einer beträchtlichen Leistungssteigerung. Alle .NET-Anwendungen für .NET Framework Version 4.7.2 oder höher verwenden die native Implementierung. Diese Änderung kann zu einigen Unterschieden im Verhalten führen, beispielsweise:

- Die Ausnahmemeldungen können sich unterscheiden. Der Typ der ausgelösten Ausnahme bleibt jedoch gleich.
- Einige besondere Situationen (z.B. nicht ausreichender Speicher zum Abschließen eines Vorgangs) werden möglicherweise anders behandelt.
- Es gibt bekannte Unterschiede für die Analyse von GZip-Headern (Hinweis: nur `GZipStream` für die Dekomprimierung ist davon betroffen):
- Ausnahmen beim Analysieren ungültiger Header werden möglicherweise zu anderen Zeiten ausgelöst.
- Die native Implementierung führt dazu, dass Werte für einige reservierte Flags im GZip-Header (d.h. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) gemäß der Spezifikation festgelegt werden. Dies kann dazu führen, dass in Fällen möglicherweise eine Ausnahme ausgelöst wird, in denen zuvor ungültige Werte ignoriert wurden.

#### <a name="suggestion"></a>Vorschlag

Wenn sich die Dekomprimierung mit nativen APIs negativ auf das Verhalten Ihrer App ausgewirkt hat, können Sie diese Funktion durch Hinzufügen des `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression`-Schalters zum Abschnitt `runtime` der Datei „app.config“ und Festlegen des Werts auf `true` deaktivieren:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
