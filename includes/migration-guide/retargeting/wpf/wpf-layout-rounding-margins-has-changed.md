---
ms.openlocfilehash: 73096e5f61e5257e062df9743cae0f5464892357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804553"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>Die WPF-Layoutglättung von Rändern wurde geändert

|   |   |
|---|---|
|Details|Die Art und Weise, wie Ränder und die Grenzen und der Hintergrund darin geglättet werden, hat sich geändert. Auswirkungen durch diese Änderung:<ul><li>Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.</li><li>Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.</li><li>Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.</li></ul>Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.|
|Vorschlag|Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“ hinzugefügt wird:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>Apps, die auf .NET Framework 4.6 ausgelegt sind, aber WPF-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt <code>&lt;runtime&gt;</code> der Datei „app.config“ hinzugefügt wird:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.6|
|Geben Sie Folgendes ein:|Neuzuweisung|
