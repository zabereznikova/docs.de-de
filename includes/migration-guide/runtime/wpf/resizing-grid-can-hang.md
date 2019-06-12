---
ms.openlocfilehash: 5df5afec17d400ed14fe9b4c03c2f754895f0dd7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378767"
---
### <a name="resizing-a-grid-can-cause-an-application-to-become-unresponsive"></a>Das Ändern der Rastergröße kann dazu führen, dass eine Anwendung nicht mehr reagiert.

|   |   |
|---|---|
|Details|Beim Anpassen des Layouts eines <code>T:System.Windows.Controls.Grid</code>-Rasters kann in den folgenden Situationen eine Endlosschleife entstehen:<ul><li>Die Zeilendefinitionen enthalten zwei *-Zeilen, die jeweils einen MinHeight- und einen MaxHeight-Wert angeben.</li><li>Der Inhalt der *-Zeilen übersteigt den MaxHeight-Wert nicht</li><li>Die verfügbare Höhe des Rasters liegt unterhalb des ersten MinHeight-Werts (dies gilt auch für sämtliche anderen festgelegten oder automatisch generierten Zeilen)</li><li>Die App ist auf .NET Framework 4.7 ausgelegt oder aktiviert den Zuweisungsalgorithmus der Version 4.7, indem sie die Einstellung <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code> festlegt.</li></ul>Außerdem würde eine Endlosschleife entstehen, wenn es mehr als zwei Zeilen oder Spalten gäbe. Dieses Problem wurde in .NET Framework 4.7.1 behoben.|
|Vorschlag|Upgrade auf .NET Framework 4.7.1  Wenn Sie hingegen den .NET 4.7-Zuweisungsalgorithmus nicht benötigen, können Sie auch die folgenden Konfigurationseinstellungen verwenden:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|
