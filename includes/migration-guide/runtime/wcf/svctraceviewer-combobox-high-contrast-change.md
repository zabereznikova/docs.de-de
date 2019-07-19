---
ms.openlocfilehash: 5a45d616001be5a2a2bdf2c654c10526125d7d86
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802688"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Änderungen bei ComboBox in svcTraceViewer

|   |   |
|---|---|
|Details|Bei bestimmten Designs mit hohem Kontrast wurden ComboBox-Steuerelemente im Tool [Microsoft Service Trace Viewer](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) nicht in der richtigen Farbe angezeigt. Dieses Problem wurde in .NET Framework 4.7.2 behoben. Aufgrund der für .NET Framework SDK geltenden Abwärtskompatibilitätsanforderungen war die Korrektur für Kunden nicht standardmäßig sichtbar. In .NET 4.8 zeigt sich diese Änderung nun, da der Datei „svcTraceViewer.exe.config“ die folgenden [AppContext-Konfigurationsswitches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) hinzugefügt wurden:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Vorschlag|<ul><li>Deaktivieren der Änderung Wenn Sie die Änderung im Verhalten bei hohem Kontrast nicht möchten, können Sie diese deaktivieren, indem Sie den folgenden Abschnitt in der Konfigurationsdatei „svcTraceViewer.exe.config“ entfernen:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.8|
|Typ|Laufzeit|

