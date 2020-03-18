---
ms.openlocfilehash: 3463b6c45952aab0023e40921739e84eb51ca001
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859149"
---
### <a name="wpf-pointer-based-touch-stack"></a>Zeigerbasierte Touch-Stapel in WPF

|   |   |
|---|---|
|Details|Diese Änderung ermöglicht das Aktivieren eines optionalen WM_POINTER-basierten WPF-Touch-/Stift-Stapels.  Entwickler, die diesen Stapel nicht explizit aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen. Folgende Probleme sind mit dem optionalen WM_POINTER-basierten Touch-/Stift-Stapel bekannt:<ul><li>Keine Unterstützung für Freihand in Echtzeit.</li><li>Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, jedoch werden sie im Benutzeroberflächenthread verarbeitet, was zu schlechter Leistung führen kann.</li><li>Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.</li><li>Die Bearbeitung verhält sich möglicherweise anders.</li><li>Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben.</li><li>Dies betrifft keine Stifteingaben.</li><li>Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.</li><li>Dadurch kann es möglicherweise zu einem Hängen der Anwendung kommen, bis die Mauseingabe erkannt wird.</li><li>Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.</li></ul>|
|Vorschlag|Entwickler, die diesen Stapel aktivieren möchten, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Entfernen oder Festlegen des Werts auf FALSE deaktiviert diesen optionalen Stapel. Beachten Sie, dass dieser Stapel nur unter Windows 10 Creators Update und höher verfügbar ist.|
|`Scope`|Edge|
|Version|4.7|
|Geben Sie Folgendes ein:|Neuzuweisung|
