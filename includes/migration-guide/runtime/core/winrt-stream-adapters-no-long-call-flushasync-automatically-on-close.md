---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804078"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>WinRT-Streamadapter rufen nicht mehr automatisch FlushAsync auf, wenn sie geschlossen werden

|   |   |
|---|---|
|Details|In Windows Store-Apps rufen Windows Runtime-Streamadapter nicht mehr über die Dispose-Methode die FlushAsync-Methode auf.|
|Vorschlag|Diese Änderung sollte transparent sein. Entwickler können das vorherige Verhalten wiederherstellen, indem sie Code wie den folgenden schreiben:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|Bereich|Transparent|
|Version|4.5.1|
|Typ|Laufzeit|
