---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620273"
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
