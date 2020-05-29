---
ms.openlocfilehash: 1e4c0ac1f0f9011f4b8fc136ec2e383d38567355
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83435406"
---
### <a name="resizing-a-grid-can-hang"></a>Die Änderung der Größe eines Rasters kann zu einem Absturz führen

|   |   |
|---|---|
|Details|Beim Anpassen des Layouts eines <code>T:System.Windows.Controls.Grid</code>-Rasters kann in den folgenden Situationen eine Endlosschleife entstehen:<ul><li>Die Zeilendefinitionen enthalten zwei \*-Zeilen, die jeweils einen MinHeight- und einen MaxHeight-Wert angeben.</li><li>Der Inhalt der \*-Zeilen übersteigt den MaxHeight-Wert nicht</li><li>Die verfügbare Höhe des Rasters liegt unterhalb des ersten MinHeight-Werts (dies gilt auch für sämtliche anderen festgelegten oder automatisch generierten Zeilen)</li><li>Die App ist auf .NET Framework 4.7 ausgelegt oder aktiviert den Zuweisungsalgorithmus der Version 4.7, indem sie die Einstellung <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code> festlegt.</li></ul>Eine Endlosschleife würde auch entstehen, wenn es mehr als zwei Zeilen oder Spalten gäbe. Dieses Problem wurde in .NET Framework 4.7.1 behoben.|
|Vorschlag|Upgrade auf .NET Framework 4.7.1  Wenn Sie hingegen den .NET 4.7-Zuweisungsalgorithmus nicht benötigen, können Sie auch die folgenden Konfigurationseinstellungen verwenden:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|
