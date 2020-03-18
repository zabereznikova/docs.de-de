---
ms.openlocfilehash: 0b087fca59d60a086a9ea8b2bb19c09f646c3dfd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858967"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Verbesserte Barrierefreiheit für einige .NET SDK-Tools

|   |   |
|---|---|
|Details|Im .NET Framework SDK 4.7.1 wurden die Tools „SvcConfigEditor.exe“ und „SvcTraceViewer.exe“ verbessert, indem verschiedene Probleme mit der Barrierefreiheit behoben wurden. Bei den meisten handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden. Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden. Diese Problembehebungen ändern vorherige Verhalten wie z.B. die Tastaturfokusreihenfolge. Sie können der Datei „app.config“ Folgendes hinzufügen, um alle Problembehebungen für die Barrierefreiheit in diesen Tools nutzen zu können:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Edge|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
