---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496291"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>WinRT-Streamadapter rufen nicht mehr automatisch FlushAsync auf, wenn sie geschlossen werden

#### <a name="details"></a>Details

In Windows Store-Apps rufen Windows Runtime-Streamadapter nicht mehr über die Dispose-Methode die FlushAsync-Methode auf.

#### <a name="suggestion"></a>Vorschlag

Diese Änderung sollte transparent sein. Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Transparent|
|Version|4.5.1|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
