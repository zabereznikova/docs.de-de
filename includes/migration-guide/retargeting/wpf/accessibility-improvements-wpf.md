---
ms.openlocfilehash: 895d09e4ec39bd4a92ed1f4910da80474334d99b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497598"
---
### <a name="accessibility-improvements-in-wpf"></a>Verbesserungen der Barrierefreiheit in WPF

#### <a name="details"></a>Details

**Verbesserungen beim hohen Kontrast**

- Der Fokus für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Der Text, der in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen angezeigt wird, wenn diese ausgewählt sind, ist nun einfacher erkennbar als in den vorherigen Versionen von .NET Framework.
- Der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Elements hat nun die gleiche Farbe wie der deaktivierte Text. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Deaktivierte Schaltflächen und Schaltflächen mit Fokus verwenden nun das richtige Farbdesign. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Die Dropdownschaltfläche ist nun sichtbar, wenn der Stil eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType> festgelegt ist. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Der Pfeil für die Sortieranzeige in einem <xref:System.Windows.Controls.DataGrid>-Steuerelement verwendet nun die Farben des Designs. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Das Standardformat für Links ändert sich nun in das richtige Farbdesign, wenn mit der Maus darauf gezeigt wird. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Es wird nun angezeigt, wenn der Tastaturfokus sich auf Optionsfeldern befindet. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Die Spalte für Kontrollkästchen des <xref:System.Windows.Controls.DataGrid>-Steuerelements verwendet nun die erwarteten Farben für das Feedback des Tastaturfokus. In früheren Versionen des .NET Framework war dies nicht der Fall.
- Die visuellen Elemente des Tastaturfokus werden nun für <xref:System.Windows.Controls.ComboBox>- und <xref:System.Windows.Controls.ListBox>-Steuerelemente angezeigt. In früheren Versionen des .NET Framework war dies nicht der Fall.

**Verbesserungen der Interaktion mit der Sprachausgabe**

- <xref:System.Windows.Controls.Expander>-Steuerelemente werden von der Sprachausgabe nun richtig als Gruppen (erweitern/reduzieren) ausgegeben.
- <xref:System.Windows.Controls.DataGridCell>-Steuerelemente werden von der Sprachausgabe nun richtig als Datenrasterzellen (lokalisiert) ausgegeben.
- Die Sprachausgabe gibt nun den Namen eines bearbeitbaren <xref:System.Windows.Controls.ComboBox>-Elements aus.
- <xref:System.Windows.Controls.PasswordBox>-Steuerelemente werden von der Sprachausgabe nicht mehr als „Es befindet sich kein Element in der Ansicht“ ausgegeben.

**LiveRegion-Unterstützung**

Sprachausgaben wie das Feature „Sprachausgabe“ helfen Benutzern, die Benutzeroberfläche einer Anwendung zu verstehen. In der Regel wird dazu das Benutzeroberflächenelement beschrieben, das gerade im Fokus ist. Wenn ein Element der Benutzeroberfläche sich jedoch an einer beliebigen Stelle des Bildschirms ändert und nicht fokussiert wird, wird der Benutzer möglicherweise nicht informiert und verpasst wichtige Informationen. LiveRegions wurden dafür entwickelt, dieses Problem zu lösen. Entwickler können diese verwenden, um der Sprachausgabe oder einem anderen [Benutzeroberflächen-Automatisierungsclient](~/docs/framework/ui-automation/ui-automation-overview.md) mitzuteilen, dass eine wichtige Änderung an einem Element der Benutzeroberfläche vorgenommen wurde. Die Sprachausgabe kann dann entscheiden, wie und wann der Benutzer über diese Änderung informiert wird. Die LiveSetting-Eigenschaft sorgt ebenfalls dafür, dass die Sprachausgabe den Benutzer über Änderungen an der Benutzeroberfläche informiert.

#### <a name="suggestion"></a>Vorschlag

**Aktivieren bzw. Deaktivieren dieser Änderungen**

Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.1 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:

- Richten Sie die Anwendung auf .NET Framework-Version 4.7.1 aus. Dies ist die empfohlene Vorgehensweise. Diese Änderungen für mehr Barrierefreiheit werden automatisch für WPF-Anwendungen aktiviert, die für .NET Framework 4.7.1 oder höher entwickelt wurden.
- Veraltete Verhaltensweisen der Barrierefreiheit werden deaktiviert, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) im Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
    </startup>
    <runtime>
      <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
    </runtime>
  </configuration>
  ```

Bei Anwendungen, deren Zielplattform .NET Framework 4.7.1 oder höher ist und für die das Legacyverhalten für die Barrierefreiheit beibehalten sollen, können Sie das Legacyfeature für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.
Einen Überblick über die Benutzeroberflächenautomatisierung finden Sie unter [Übersicht über die Benutzeroberflächenautomatisierung](~/docs/framework/ui-automation/ui-automation-overview.md).

| Name    | Wert       |
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
