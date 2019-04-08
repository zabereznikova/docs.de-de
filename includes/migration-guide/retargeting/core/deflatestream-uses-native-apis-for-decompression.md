---
ms.openlocfilehash: ed0dde302e30ae0cf3c7a8d0985f2314d91cab66
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760836"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a>DeflateStream verwendet native APIs für die Dekomprimierung

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.2 hat sich die Implementierung der Dekomprimierung in der <code>T:System.IO.Compression.DeflateStream</code>-Klasse so geändert, dass standardmäßig native Windows-APIs verwendet werden. In der Regel führt dies zu einer beträchtlichen Leistungssteigerung. Alle .NET-Anwendungen für .NET Framework Version 4.7.2 oder höher verwenden die native Implementierung. Diese Änderung kann zu einigen Unterschieden im Verhalten führen, beispielsweise:<ul><li>Die Ausnahmemeldungen können sich unterscheiden. Der Typ der ausgelösten Ausnahme bleibt jedoch gleich.</li><li>Einige besondere Situationen (z.B. nicht ausreichender Speicher zum Abschließen eines Vorgangs) werden möglicherweise anders behandelt.</li><li>Es gibt bekannte Unterschiede für die Analyse von GZip-Headern (Hinweis: nur <code>GZipStream</code> für die Dekomprimierung ist davon betroffen):</li><li>Ausnahmen beim Analysieren ungültiger Header werden möglicherweise zu anderen Zeiten ausgelöst.</li><li>Die native Implementierung führt dazu, dass Werte für einige reservierte Flags im GZip-Header (d.h. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) gemäß der Spezifikation festgelegt werden. Dies kann dazu führen, dass in Fällen möglicherweise eine Ausnahme ausgelöst wird, in denen zuvor ungültige Werte ignoriert wurden.</li></ul>|
|Vorschlag|Wenn sich die Dekomprimierung mit nativen APIs negativ auf das Verhalten Ihrer App ausgewirkt hat, können Sie diese Funktion durch Hinzufügen des <code>Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression</code>-Schalters zum Abschnitt <code>runtime</code> der Datei „app.config“ und Festlegen des Werts auf <code>true</code> deaktivieren:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot; ?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType></li><li><xref:System.IO.Compression.GZipStream?displayProperty=nameWithType></li></ul>|

