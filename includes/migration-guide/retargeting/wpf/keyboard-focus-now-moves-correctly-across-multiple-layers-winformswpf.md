---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614601"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>Der Tastaturfokus bewegt sich jetzt ordnungsgemäß über mehrere Ebenen von WinForms-/WPF-Hosting

#### <a name="details"></a>Details

Nehmen Sie als Beispiel eine WPF-Anwendung, die ein WinForms-Steuerelement hostet, das wiederum WPF-Steuerelemente hostet. Benutzer können die WinForms-Ebene möglicherweise nicht mit der TABULATORTASTE verlassen, wenn das erste oder letzte Steuerelement in diese Ebene `System.Windows.Forms.Integration.ElementHost` von WPF ist. Diese Änderung behebt dieses Problem, und Benutzer können die WinForms-Ebene jetzt mit der TABULATORTASTE verlassen. Automatisierte Anwendungen, die erfordern, dass der Fokus die WinForms-Ebene nie verlässt, funktionieren möglicherweise nicht mehr wie erwartet.

#### <a name="suggestion"></a>Vorschlag

Ein Entwickler, der diese Änderung für eine niedrigere Frameworkversion als .NET 4.7.2 nutzen möchte, kann die folgende Gruppe von AppContext-Flags auf FALSE festlegen, damit die Änderung aktiviert wird.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

WPF-Anwendungen müssen alle frühen Barrierefreiheitsverbesserungen aktivieren, um die späteren Verbesserungen abrufen zu können. Das heißt, die `Switch.UseLegacyAccessibilityFeatures`- und `Switch.UseLegacyAccessibilityFeatures.2`-Schalter müssen festgelegt werden. Ein-Entwickler, der die vorherige Funktionalität für .NET 4.7.2 oder höher benötigt, kann das folgende AppContext-Flag auf TRUE festlegen, damit die Änderung deaktiviert wird.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
