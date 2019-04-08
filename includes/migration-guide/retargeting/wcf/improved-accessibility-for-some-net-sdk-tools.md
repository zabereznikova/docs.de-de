---
ms.openlocfilehash: 79005f19ac31ba32e7e468ef61eb867a052eff40
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760277"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Verbesserte Barrierefreiheit für einige .NET SDK-Tools

|   |   |
|---|---|
|Details|Im .NET Framework SDK 4.7.1 wurden die Tools „SvcConfigEditor.exe“ und „SvcTraceViewer.exe“ verbessert, indem verschiedene Probleme mit der Barrierefreiheit behoben wurden. Bei den meisten handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden. Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden. Diese Problembehebungen ändern vorherige Verhalten wie z.B. die Tastaturfokusreihenfolge. Sie können der Datei „app.config“ Folgendes hinzufügen, um alle Problembehebungen für die Barrierefreiheit in diesen Tools nutzen zu können:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7.1|
|Typ|Neuzuweisung|

