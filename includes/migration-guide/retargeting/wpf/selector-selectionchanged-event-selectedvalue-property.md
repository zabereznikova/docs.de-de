---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614600"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>Selector-Klasse – SelectionChanged-Ereignis und SelectedValue-Eigenschaft

#### <a name="details"></a>Details

Ab .NET Framework 4.7.1 aktualisiert ein <xref:System.Windows.Controls.Primitives.Selector>-Objekt immer den Wert der zugehörigen <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft, bevor das Ereignis <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> ausgelöst wird, wenn die Auswahl geändert wird. Dadurch wird die „SelectedValue“-Eigenschaft mit den anderen Auswahleigenschaften (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> und <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>) in Einklang gebracht, die vor dem Auslösen des Ereignisses aktualisiert werden.<p/>In .NET Framework 4.7 und früheren Versionen wurde „SelectValue“ in den meisten Fällen vor der Auslösung des Ereignisses aktualisiert. Wenn die Änderung der Auswahl durch Ändern der <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft ausgelöst wurde, fand die Aktualisierung jedoch nach dem Auslösen des Ereignisses statt.

#### <a name="suggestion"></a>Vorschlag

Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei Folgendes hinzufügen:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
