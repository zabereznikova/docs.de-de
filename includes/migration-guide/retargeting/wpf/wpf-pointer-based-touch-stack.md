---
ms.openlocfilehash: a620028a4e286799a6762c57145264ac0e2dbaf9
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859149"
---
### <a name="wpf-pointer-based-touch-stack"></a>Zeigerbasierte Touch-Stapel in WPF

|   |   |
|---|---|
|Details|Diese Änderung ermöglicht das Aktivieren eines optionalen WM_POINTER-basierten WPF-Touch-/Stift-Stapels.  Entwickler, die diesen Stapel nicht explizit aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen. Folgende Probleme sind mit dem optionalen WM_POINTER-basierten Touch-/Stift-Stapel bekannt:<ul><li>Keine Unterstützung für Freihand in Echtzeit.</li><li>Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, jedoch werden sie im Benutzeroberflächenthread verarbeitet, was zu schlechter Leistung führen kann.</li><li>Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.</li><li>Die Bearbeitung verhält sich möglicherweise anders.</li><li>Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben.</li><li>Dies betrifft keine Stifteingaben.</li><li>Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.</li><li>Dadurch kann es möglicherweise zu einem Hängen der Anwendung kommen, bis die Mauseingabe erkannt wird.</li><li>Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.</li></ul>|
|Vorschlag|Entwickler, die diesen Stapel aktivieren möchten, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Entfernen oder Festlegen des Werts auf FALSE deaktiviert diesen optionalen Stapel. Beachten Sie, dass dieser Stapel nur unter Windows 10 Creators Update und höher verfügbar ist.|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Neuzuweisung|

