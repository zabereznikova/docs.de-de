---
ms.openlocfilehash: 47d3829748deef2c7c3610816b8941bf88da7ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614592"
---
### <a name="accessibility-improvements-in-wpf"></a>Verbesserungen der Barrierefreiheit in WPF

#### <a name="details"></a>Details

**Verbesserungen beim hohen Kontrast**
<ul><li>Der Fokus für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Der Text, der in den Steuerelementen <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.RadioButton> angezeigt wird, wenn diese ausgewählt sind, ist nun einfacher erkennbar als in den vorherigen Versionen von .NET Framework.
- Der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Elements hat nun die gleiche Farbe wie der deaktivierte Text. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Deaktivierte Schaltflächen und Schaltflächen mit Fokus verwenden nun das richtige Farbdesign. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Die Dropdownschaltfläche ist nun sichtbar, wenn das Format eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType> festgelegt ist. In früheren Versionen vom .NET Framework war dies nicht der Fall.
- Der Pfeil für die Sortieranzeige in einem <xref:System.Windows.Controls.DataGrid>-Steuerelement verwendet nun die Farben des Designs. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Das Standardformat für Links ändert sich nun in das richtige Farbdesign, wenn mit der Maus darauf gezeigt wird. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Es wird nun angezeigt, wenn der Tastaturfokus sich auf Optionsfeldern befindet. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Die Spalte für Kontrollkästchen des <xref:System.Windows.Controls.DataGrid>-Steuerelements verwendet nun die erwarteten Farben für das Feedback des Tastaturfokus. In früheren Versionen von .NET Framework war dies nicht der Fall.
- Die visuellen Elemente des Tastaturfokus werden nun für <xref:System.Windows.Controls.ComboBox>- und <xref:System.Windows.Controls.ListBox>-Steuerelemente angezeigt. In früheren Versionen von .NET Framework war dies nicht der Fall.</p>
**Verbesserungen der Interaktion mit der Sprachausgabe**
<ul><li><xref:System.Windows.Controls.Expander>-Steuerelemente werden von der Sprachausgabe nun richtig als Gruppen (erweitern/reduzieren) ausgegeben.
- <xref:System.Windows.Controls.DataGridCell>-Steuerelemente werden von der Sprachausgabe nun richtig als Datenrasterzellen (lokalisiert) ausgegeben.
- Die Sprachausgabe gibt nun den Namen eines bearbeitbaren <xref:System.Windows.Controls.ComboBox>-Elements aus.
- <xref:System.Windows.Controls.PasswordBox>-Steuerelemente werden von der Sprachausgabe nicht mehr als &quot;Es befindet sich kein Element in der Ansicht.&quot; ausgegeben.</p>
**LiveRegion-Unterstützung** Sprachausgaben wie die Microsoft-Sprachausgabe unterstützen die Benutzer dabei, die Inhalte der Benutzeroberfläche einer Anwendung zu erkennen. Üblicherweise wird dies durch eine Beschreibung des Teils der Benutzeroberfläche erreicht, auf dem zum jeweiligen Zeitpunkt der Fokus liegt, da es sich dabei wahrscheinlich um das Element handelt, das für den Benutzer gerade am wichtigsten ist. Wenn ein Element der Benutzeroberfläche sich jedoch an einer beliebigen Stelle des Bildschirms ändert und nicht fokussiert wird, wird der Benutzer möglicherweise nicht informiert und verpasst wichtige Informationen. LiveRegions wurden dafür entwickelt, dieses Problem zu lösen. Entwickler können diese verwenden, um der Sprachausgabe oder einem anderen [Benutzeroberflächen-Automatisierungsclient](~/docs/framework/ui-automation/ui-automation-overview.md) mitzuteilen, dass eine wichtige Änderung an einem Element der Benutzeroberfläche vorgenommen wurde. Die Sprachausgabe kann dann entscheiden, wie und wann der Benutzer über diese Änderung informiert wird. Die LiveSetting-Eigenschaft sorgt ebenfalls dafür, dass die Sprachausgabe den Benutzer über Änderungen an der Benutzeroberfläche informiert.

#### <a name="suggestion"></a>Vorschlag

**Aktivieren oder Deaktivieren dieser Änderungen**: Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.1 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:

- Festlegen von .NET Framework 4.7.1 als Ziel. Dies ist die empfohlene Vorgehensweise. Diese Änderungen der Barrierefreiheit werden standardmäßig für WPF-Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen.
- Veraltete Verhaltensweisen der Barrierefreiheit werden deaktiviert, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) im Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Bei Anwendungen, die .NET Framework 4.7.1 oder höher als Zielplattform verwenden und die Legacy-Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Features für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.
Einen Überblick über die Benutzeroberflächenautomatisierung finden Sie unter [Benutzeroberflächenautomatisierung: Übersicht](~/docs/framework/ui-automation/ui-automation-overview.md).

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
