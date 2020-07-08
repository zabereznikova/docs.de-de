---
ms.openlocfilehash: c8e1c91f4fee8aa896b6617c815fe2a4b6d22f2a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614571"
---
### <a name="accessibility-improvements-in-windows-forms-controls"></a>Verbesserung der Barrierefreiheit von Windows Forms-Steuerelementen

#### <a name="details"></a>Details

Die Arbeitsweise von Windows Forms mit Technologien für die Barrierefreiheit wird verbessert, um die Kunden von Windows Forms besser zu unterstützen. Dazu gehören die folgenden Änderungen ab .NET Framework 4.7.1:

- Änderungen zum Verbessern der Anzeige während des Modus mit hohem Kontrast
- Änderungen zum Verbessern der Benutzerfreundlichkeit des Eigenschaftenbrowsers Folgende Verbesserungen wurden am Eigenschaftenbrowser vorgenommen:
- Eine verbesserte Tastaturnavigation durch die verschiedenen Fenster der Dropdownauswahl
- Unnötige Tabstopps wurden reduziert.
- Eine verbesserte Berichterstellung der Steuerelementtypen
- Ein verbessertes Verhalten der Sprachausgabe
- Änderungen an der Implementierung fehlender Barrierefreiheitsmuster für die Benutzeroberfläche in Steuerelementen

#### <a name="suggestion"></a>Vorschlag

**Aktivieren oder Deaktivieren dieser Änderungen**: Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.1 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:

- Kompilieren Sie diese erneut, um .NET Framework 4.7.1 anzuzielen. Diese Änderungen der Barrierefreiheit werden standardmäßig für WPF-Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen.
- Veraltete Verhaltensweisen der Barrierefreiheit werden deaktiviert, indem wie im folgenden Beispiel dargestellt folgendes [AppContext-Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) zum `<runtime>`-Abschnitt der app.config-Datei hinzugefügt und auf `false` festgelegt wird.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
  </runtime>
</configuration>
```

Bei Anwendungen, die .NET Framework 4.7.1 oder höher als Zielplattform verwenden und die Legacy-Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Features für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.<p/>Einen Überblick über die Benutzeroberflächenautomatisierung finden Sie unter [Benutzeroberflächenautomatisierung: Übersicht](~/docs/framework/ui-automation/ui-automation-overview.md).<p/>**Hinzugefügte Unterstützung für Benutzeroberflächen-Automatisierungsmuster und -Eigenschaften**<br/>Barrierefreiheitsclients können neue WinForms-Barrierefreiheitsfunktionen nutzen, indem allgemeine, öffentlich beschriebene Aufrufmuster verwendet werden. Diese Muster sind nicht für WinForms spezifisch. Clients für die Barrierefreiheit können beispielsweise die QueryInterface-Methode der IAccessible-Schnittstelle (MAAS) aufrufen, um eine IServiceProvider-Schnittstelle abzurufen. Wenn diese Schnittstelle verfügbar ist, können Clients die QueryService-Methode verwenden, um eine IAccessibleEx-Schnittstelle anzufordern. Weitere Informationen finden Sie unter [Using IAccessibleEx from a Client (Verwenden von IAccessibleEx über einen Client)](https://docs.microsoft.com/windows/desktop/WinAuto/using-iaccessibleex-from-a-client). Ab .NET Framework 4.7.1 sind IServiceProvider und [IAccessibleEx](https://docs.microsoft.com/windows/desktop/WinAuto/iaccessibleex) gegebenenfalls für WinForms-Objekte für die Barrierefreiheit verfügbar.<p/>.NET Framework 4.7.1 fügt Unterstützung für folgende Muster und Eigenschaften für die Automatisierung der Benutzeroberfläche hinzu:

- Die Steuerelemente <xref:System.Windows.Forms.ToolStripSplitButton> und <xref:System.Windows.Forms.ComboBox> unterstützen das Muster [Erweitern/Reduzieren](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Das <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelement weist einen [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)-Eigenschaftswert von <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType> auf.
- Das <xref:System.Windows.Forms.ToolStripItem>-Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.NameProperty>-Eigenschaft und das [Muster für das Erweitern/Reduzieren](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Das <xref:System.Windows.Forms.ToolStripDropDownItem>-Steuerelement unterstützt das <xref:System.Windows.Forms.AccessibleEvents>-Element, das StateChange und NameChange angibt, wenn das Dropdownmenü erweitert oder reduziert ist.
- Das <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelement weist einen [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)-Eigenschaftswert von <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType> auf.
- Das <xref:System.Windows.Forms.DataGridViewCheckBoxCell>-Steuerelement unterstützt das <xref:System.Windows.Automation.TogglePattern>.
- Die <xref:System.Windows.Forms.NumericUpDown>- und <xref:System.Windows.Forms.DomainUpDown>-Steuerelemente unterstützen die <xref:System.Windows.Automation.AutomationElement.NameProperty>-Eigenschaft und weisen einen [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md) von <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType> auf.</p>
**Verbesserungen am PropertyGrid-Steuerelement:** Mit .NET Framework 4.7.1 werden folgende Verbesserungen zum PropertyBrowser-Steuerelement hinzugefügt:

- Die Schaltfläche **Details** im Dialogfeld „Fehler“, das angezeigt wird, wenn der Benutzer einen falschen Wert in das <xref:System.Windows.Forms.PropertyGrid>-Steuerelement eingibt, unterstützt das Muster [Erweitern/Reduzieren](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), Benachrichtigungen für Status- und Namensänderungen und eine [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)-Eigenschaft mit einem Wert von <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.
- Auf den Bereich „Meldung“, der angezeigt wird, wenn die Schaltfläche **Details** des Dialogfelds „Fehler“ erweitert ist, kann nun über die Tastatur zugegriffen werden. Außerdem kann die Microsoft-Sprachausgabe den Inhalt der Fehlermeldung ausgeben.
- Das <xref:System.Windows.Forms.AccessibleRole>-Element der Zeilen im <xref:System.Windows.Forms.PropertyGrid>-Steuerelement wurde von &quot;Zeile&quot; in &quot;Zelle&quot; geändert. Die Zelle wird dem UIA-ControlType-Element &quot;DataItem&quot; zugeordnet, wodurch entsprechende Tastenkombinationen und Microsoft-Sprachausgaben unterstützt werden.
- Die Zeilen des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements, die Headerelemente darstellen, wenn die <xref:System.Windows.Forms.PropertyGrid.PropertySort>-Eigenschaft des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements auf <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> festgelegt ist, weisen einen [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)-Eigenschaftswert von <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType> auf.
- Die Zeilen des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements, die Headerelemente darstellen, wenn die <xref:System.Windows.Forms.PropertyGrid.PropertySort>-Eigenschaft des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements auf <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> festgelegt ist, unterstützen das Muster [Erweitern/Reduzieren](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
- Verbesserte Tastaturnavigation zwischen dem Raster und der darüber liegenden Symbolleiste. Durch das Drücken von &quot;UMSCHALTTASTE+TAB&quot; wird nun die erste Schaltfläche der Symbolleiste anstelle der gesamten Symbolleiste ausgewählt.
- Bei den <xref:System.Windows.Forms.PropertyGrid>-Steuerelementen, die im Modus mit hohem Kontrast angezeigt werden, wird nun ein Fokusrechteck um die Schaltfläche des Steuerelements angezeigt, die dem aktuellen Wert der <xref:System.Windows.Forms.PropertyGrid.PropertySort>-Eigenschaft entspricht.
- Bei <xref:System.Windows.Forms.PropertyGrid>-Steuerelementen, die im Modus mit hohem Kontrast angezeigt werden, und bei denen eine <xref:System.Windows.Forms.PropertyGrid.PropertySort>-Eigenschaft auf <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> festgelegt ist, wird nun der Hintergrund von Kategorieheadern in kontrastreicher Farbe angezeigt.
- Bei <xref:System.Windows.Forms.PropertyGrid>-Steuerelementen wird besser zwischen den Elementen der Symbolleiste mit Fokus und denen, die den aktuellen Wert der <xref:System.Windows.Forms.PropertyGrid.PropertySort>-Eigenschaft angeben, unterschieden. Dieser Fehlerbehebung besteht aus einer Änderung für Szenarios mit und ohne hohen Kontrast.
- ToolBar-Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements, die den aktuellen Wert der <xref:System.Windows.Forms.PropertyGrid.PropertySort>-Eigenschaft angeben, unterstützen das <xref:System.Windows.Automation.TogglePattern>.
- Verbesserte Unterstützung der Unterscheidung der ausgewählten Ausrichtung in der Ausrichtungsauswahl durch die Microsoft-Sprachausgabe.
- Wenn ein leeres <xref:System.Windows.Forms.PropertyGrid>-Steuerelement in einem Formular angezeigt wird, wird dieses nun fokussiert. Dies war zuvor nicht der Fall.

**Verwendung von durch das Betriebssystem definierten Farben in Designs mit hohem Kontrast**

- Die <xref:System.Windows.Forms.Button>- und <xref:System.Windows.Forms.CheckBox>-Steuerelementen, deren <xref:System.Windows.Forms.ButtonBase.FlatStyle>-Eigenschaft auf <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType> (Standardformat) festgelegt ist, verwenden nun die vom Betriebssystem definierten Farben im Design mit hohem Kontrast, wenn dieses ausgewählt ist. Zuvor gab es keinen Kontrast zwischen Text und Hintergrundfarbe, wodurch der Text schwer lesbar war.
- Die <xref:System.Windows.Forms.Button>-, <xref:System.Windows.Forms.CheckBox>-, <xref:System.Windows.Forms.RadioButton>-, <xref:System.Windows.Forms.Label>-, <xref:System.Windows.Forms.LinkLabel>- und <xref:System.Windows.Forms.GroupBox>-Steuerelemente, deren <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft auf **FALSE** festgelegt ist, verwendeten schattierte Farben zum Rendern von Text in Designs mit hohem Kontrast. Dies führt zu geringem Kontrast vor dem Hintergrund. Diese Steuerelemente verwenden nun die vom Betriebssystem definierte Farbe für &quot;deaktivierten Text&quot;. Diese Fehlerbehebung gilt für Steuerelemente, bei denen die `FlatStyle`-Eigenschaft auf einen anderen Wert als <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType> festgelegt ist. Die zuletzt aufgeführten Steuerelemente werden vom Betriebssystem gerendert.
- <xref:System.Windows.Forms.DataGridView> rendert nun ein sichtbares Rechteck um den Inhalt der Zelle, die derzeit fokussiert wird. Zuvor wurde dieses in bestimmten Designs mit hohem Kontrast nicht angezeigt.
- <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelemente, deren <xref:System.Windows.Forms.ToolStripMenuItem.Enabled>-Eigenschaft auf **FALSE** festgelegt ist, verwenden nun die vom Betriebssystem definierte Farbe für &quot;deaktivierten Text&quot;.
- <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelemente, deren <xref:System.Windows.Forms.ToolStripMenuItem.Checked>-Eigenschaft auf **TRUE** festgelegt ist, rendern nun das zugehörige Häkchen in einer kontrastreichen Systemfarbe.  Zuvor war die Farbe des Häkchens nicht kontrastreich genug, weshalb es in Designs mit hohem Kontrast nicht sichtbar war.
HINWEIS: In Windows 10 wurden die Werte für einige Systemfarben mit hohem Kontrast geändert. Das Windows Forms-Framework basiert auf dem Win32-Framework. Die besten Ergebnisse erhalten Sie, wenn Sie die aktuelle Version von Windows ausführen und die neuesten Änderungen am Betriebssystem aktivieren, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus folgendem Code entfernen:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Verbesserte Tastaturnavigation**

- Wenn für ein <xref:System.Windows.Forms.ComboBox>-Steuerelement seine <xref:System.Windows.Forms.ComboBox.DropDownStyle>-Eigenschaft auf <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType> festgelegt ist und es das erste Steuerelement in der Aktivierreihenfolge des Formulars ist, zeigt dieses nun ein Fokusrechteck an, wenn das übergeordnete Formular mithilfe der Tastatur geöffnet wird. Vor dieser Änderung lag der Tastaturfokus auf diesem Steuerelement, es wurde jedoch kein Fokusindikator gerendert.

**Verbesserte Unterstützung für die Sprachausgabe**

- Dem <xref:System.Windows.Forms.MonthCalendar>-Steuerelement wurde die Unterstützung für Hilfstechnologien hinzugefügt, damit diese auf das Steuerelement zugreifen können. Dazu zählt auch die Funktion der Microsoft-Sprachausgabe, den Wert des Steuerelements auszugeben. Dies war zuvor nicht möglich.

- Das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement benachrichtigt die Sprachausgabe nun, wenn eine <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType>-Eigenschaft geändert wurde. Zuvor erhielt die Sprachausgabe keine Benachrichtigung. Deshalb wurden Benutzer nicht darüber informiert, dass die <xref:System.Windows.Forms.CheckBox.CheckState>-Eigenschaft aktualisiert wurde.
- Die Art, wie das <xref:System.Windows.Forms.LinkLabel>-Steuerelement die Microsoft-Sprachausgabe über den Text des Steuerelements benachrichtigt, wurde geändert. Zuvor hat die Microsoft-Sprachausgabe diesen Text zweimal und die Symbole &quot;&amp;&quot; als Text ausgegeben, obwohl diese für den Benutzer nicht sichtbar sind. Der doppelten Text sowie die unnötigen &quot;&amp;&quot;-Symbole wurden aus den Ausgaben der Microsoft-Sprachausgabe entfernt.
- Die <xref:System.Windows.Forms.DataGridViewCell>-Steuerelementtypen melden den schreibgeschützten Status nun ordnungsgemäß an die Microsoft-Sprachausgabe und andere Hilfstechnologien.
- Die Sprachausgabe kann jetzt das Systemmenü untergeordneter Fenster in [Multiple-Document Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)-Anwendungen lesen.
- Die Microsoft-Sprachausgabe kann nun <xref:System.Windows.Forms.ToolStripMenuItem>-Steuerelemente ausgeben, bei der die <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType>-Eigenschaft auf **FALSE** festgelegt ist. Zuvor konnte die Sprachausgabe den Fokus nicht auf deaktivierte Menüelemente verschieben, um deren Inhalt auszugeben.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.8         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType>
- [MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)
