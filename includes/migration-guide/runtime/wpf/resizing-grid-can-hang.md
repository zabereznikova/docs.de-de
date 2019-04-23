---
ms.openlocfilehash: 63101fb127c84de21d165994bba85a2753e97344
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236592"
---
### <a name="resizing-a-grid-can-hang"></a>Die Änderung der Größe eines Rasters kann zu einem Absturz führen

|   |   |
|---|---|
|Details|Beim Anpassen des Layouts eines <code>T:System.Windows.Controls.Grid</code>-Rasters kann in den folgenden Situationen eine Endlosschleife entstehen:<ul><li>Die Zeilendefinitionen enthalten zwei *-Zeilen, die jeweils einen MinHeight- und einen MaxHeight-Wert angeben.</li><li>Der Inhalt der *-Zeilen übersteigt den MaxHeight-Wert nicht</li><li>Die verfügbare Höhe des Rasters liegt unterhalb des ersten MinHeight-Werts (dies gilt auch für sämtliche anderen festgelegten oder automatisch generierten Zeilen)</li><li>Die App ist auf .NET Framework 4.7 ausgelegt oder aktiviert den Zuweisungsalgorithmus der Version 4.7 durch Einstellung von <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></li></ul>Außerdem würde eine Endlosschleife entstehen, wenn es mehr als zwei Zeilen oder Spalten gäbe. Dieses Problem wurde in .NET Framework 4.7.1 behoben.|
|Vorschlag|Upgrade auf .NET Framework 4.7.1  Wenn Sie hingegen den .NET 4.7-Zuweisungsalgorithmus nicht benötigen, können Sie auch die folgenden Konfigurationseinstellungen verwenden:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|
