---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615716"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap konvertiert Symbole mit PNG-Frames erfolgreich in Bitmap-Objekte

#### <a name="details"></a>Details

Beginnend mit den Apps für .NET Framework 4.6 konvertiert die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode Symbole mit PNG-Bildern erfolgreich in „Bitmap“-Objekte.<p/>In Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgelegt sind, löst die <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>-Methode eine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus, wenn das „Icon“-Objekt PNG-Bilder aufweist.<p/>Diese Änderung betrifft Apps, die für .NET Framework 4.6 neu kompiliert werden und eine spezielle Behandlung für die <xref:System.ArgumentOutOfRangeException> implementieren, die ausgelöst wird, wenn ein „Icon“-Objekt PNG-Bilder aufweist. Bei der Ausführung unter .NET Framework 4.6 wird die Konvertierung erfolgreich durchgeführt und eine <xref:System.ArgumentOutOfRangeException> wird nicht mehr ausgelöst. Daher wird der Ausnahmehandler nicht mehr aufgerufen.

#### <a name="suggestion"></a>Vorschlag

Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten beibehalten, indem Sie das folgende Element zum `<runtime>`-Abschnitt Ihrer app.config-Datei hinzufügen:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

Wenn die Datei „app.config“ bereits das `AppContextSwitchOverrides`-Element enthält, muss der neue Wert wie folgt mit dem Attribut zusammengeführt werden:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
