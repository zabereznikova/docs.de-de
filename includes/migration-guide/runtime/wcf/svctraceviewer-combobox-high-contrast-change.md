---
ms.openlocfilehash: 6a6c0af9cc0f3e5d1bbc3a4462a9ff7eaa748a5f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497068"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Änderungen bei ComboBox in svcTraceViewer

#### <a name="details"></a>Details

Bei bestimmten Designs mit hohem Kontrast wurden ComboBox-Steuerelemente im Tool [Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) nicht in der richtigen Farbe angezeigt. Dieses Problem wurde in .NET Framework 4.7.2 behoben. Aufgrund der für .NET Framework SDK geltenden Abwärtskompatibilitätsanforderungen war die Korrektur für Kunden nicht standardmäßig sichtbar. In .NET 4.8 zeigt sich diese Änderung nun, da der Datei „svcTraceViewer.exe.config“ die folgenden [AppContext-Konfigurationsswitches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) hinzugefügt wurden:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a>Vorschlag

<ul><li>Deaktivieren der Änderung Wenn Sie die Änderung im Verhalten bei hohem Kontrast nicht möchten, können Sie diese deaktivieren, indem Sie den folgenden Abschnitt in der Konfigurationsdatei „svcTraceViewer.exe.config“ entfernen:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.8|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
