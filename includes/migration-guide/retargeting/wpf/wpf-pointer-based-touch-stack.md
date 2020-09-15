---
ms.openlocfilehash: eb89cbc72d8b09fd1aa5bc775a6c539eb208fa70
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614576"
---
### <a name="wpf-pointer-based-touch-stack"></a>Zeigerbasierte Touch-Stapel in WPF

#### <a name="details"></a>Details

Diese Änderung ermöglicht das Aktivieren eines optionalen WM_POINTER-basierten WPF-Touch-/Stift-Stapels.  Entwickler, die diesen Stapel nicht explizit aktivieren, sollten keine Änderung im WPF-Touch/Stift-Verhalten feststellen. Folgende Probleme sind mit dem optionalen WM_POINTER-basierten Touch-/Stift-Stapel bekannt:

- Keine Unterstützung für Freihand in Echtzeit.
- Zwar funktionieren Freihand- und Stift-Plug-Ins nach wie vor, jedoch werden sie im Benutzeroberflächenthread verarbeitet, was zu schlechter Leistung führen kann.
- Verhaltensänderungen aufgrund der Verlagerung von Touch/Stift-Ereignissen zu Mausereignissen.
- Die Bearbeitung verhält sich möglicherweise anders.
- Drag/Drop zeigt keine angemessene Rückmeldung bei Toucheingaben.
- Dies betrifft keine Stifteingaben.
- Drag/Drop kann für Touch/Stift-Ereignisse nicht mehr ausgelöst werden.
- Dadurch kann es möglicherweise zu einem Hängen der Anwendung kommen, bis die Mauseingabe erkannt wird.
- Stattdessen sollten Entwickler Drag & Drop über Mausereignisse einleiten.

#### <a name="suggestion"></a>Vorschlag

Entwickler, die diesen Stapel aktivieren möchten, können der Datei „app.config“ ihrer Anwendung Folgendes hinzufügen:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Input.Stylus.EnablePointerSupport=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Entfernen oder Festlegen des Werts auf FALSE deaktiviert diesen optionalen Stapel. Beachten Sie, dass dieser Stapel nur unter Windows 10 Creators Update und höher verfügbar ist.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7         |
| Typ    | Neuzuweisung |
