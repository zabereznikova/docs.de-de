---
ms.openlocfilehash: 06f4186e8f233f5c769dfc5e05d2de5eacd9b053
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621990"
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
