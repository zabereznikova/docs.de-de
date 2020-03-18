---
ms.openlocfilehash: e6c93a1bc31c041f36fca3704bca32012a2b42ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859011"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>Selector-Klasse – SelectionChanged-Ereignis und SelectedValue-Eigenschaft

|   |   |
|---|---|
|Details|Ab .NET Framework 4.7.1 aktualisiert ein <xref:System.Windows.Controls.Primitives.Selector>-Objekt immer den Wert der zugehörigen <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft, bevor das Ereignis <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> ausgelöst wird, wenn die Auswahl geändert wird. Dadurch wird die „SelectedValue“-Eigenschaft mit den anderen Auswahleigenschaften (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> und <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>) in Einklang gebracht, die vor dem Auslösen des Ereignisses aktualisiert werden.<p/>In .NET Framework 4.7 und früheren Versionen wurde „SelectValue“ in den meisten Fällen vor der Auslösung des Ereignisses aktualisiert. Wenn die Änderung der Auswahl durch Ändern der <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft ausgelöst wurde, fand die Aktualisierung jedoch nach dem Auslösen des Ereignisses statt.|
|Vorschlag|Für Apps mit der Zielplattform .NET Framework 4.7.1 oder höher kann diese Änderung deaktiviert und das Legacyverhalten verwendet werden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei Folgendes hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Apps mit der Zielplattform .NET Framework 4.7 oder früheren Versionen, die unter .NET Framework 4.7.1 oder höher ausgeführt werden, kann das neue Verhalten aktiviert werden, indem Sie dem Abschnitt <code>&lt;runtime&gt;</code> der Anwendungskonfigurationsdatei die folgende Zeile hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.7.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
