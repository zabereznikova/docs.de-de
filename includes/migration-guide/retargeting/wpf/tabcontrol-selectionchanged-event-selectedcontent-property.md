---
ms.openlocfilehash: dfdb62e8dd6db67d4fd12aba93928f4615e3f284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614608"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>SelectionChanged-Ereignis und SelectedContent-Eigenschaft von „TabControl“

#### <a name="details"></a>Details

Ab .NET Framework 4.7.1 aktualisiert <xref:System.Windows.Controls.TabControl> den Wert der <xref:System.Windows.Controls.TabControl.SelectedContent>-Eigenschaft, bevor das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>-Ereignis ausgelöst wird, wenn die Auswahl geändert wird. In .NET Framework 4.7 und früher wurde das Update für „SelectedContent“ nach dem Ereignis durchgeführt.

#### <a name="suggestion"></a>Vorschlag

Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei Folgendes hinzufügen:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
