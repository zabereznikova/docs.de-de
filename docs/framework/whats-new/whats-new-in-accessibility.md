---
title: Neuerungen der Barrierefreiheit in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bdb1bf5d7e32c2e05eb779eed16c311cbd3eae7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212507"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Neuerungen der Barrierefreiheit in .NET Framework

Die Anwendungen von .NET Framework sollen eine bessere Barrierefreiheit für Ihre Benutzer bieten. Durch Barrierefreiheitsfunktionen wird es einer Anwendung ermöglicht, den Benutzern von Hilfstechnologien ein angemessenes Erlebnis zu bieten. Ab .NET Framework 4.7.1 enthält .NET Framework zahlreiche Verbesserungen der Barrierefreiheit, die es den Entwicklern ermöglichen, barrierefreie Anwendungen zu erstellen.

## <a name="accessibility-switches"></a>Barrierefreiheitsparameter

Wenn Ihre App auf .NET Framework 4.7 oder niedriger ausgerichtet ist, aber auf .NET Framework 4.7.1 oder höher ausgeführt wird, können Sie sie für Barrierefreiheitsfeatures konfigurieren. Sie können auch Ihre App für Legacy-Features konfigurieren (und Barrierefreiheitsfeatures außen vor lassen), wenn diese auf .NET Framework 4.7.1 oder höher ausgerichtet ist. Jede .NET Framework-Version, die Barrierefreiheitsfeatures umfasst, verfügt über einen versionsspezifischen Barrierefreiheitsparameter, den Sie dem [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt des [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Elements in der Konfigurationsdatei der Anwendung hinzufügen. Die folgenden Parameter werden unterstützt:

|Version|Schalter|
|---|---|
|.NET Framework 4.7.1|„Switch.UseLegacyAccessibilityFeatures“|
|.NET Framework 4.7.2|„Switch.UseLegacyAccessibilityFeatures.2“|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Profitieren von Barrierefreiheitserweiterungen

Die neuen Barrierefreiheitsfunktionen werden standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen. Zusätzlich können Anwendungen, die eine frühere Version von .NET Framework anzielen, aber unter .NET Framework 4.7.1 oder höher ausgeführt werden, veraltete Verhaltensweisen für die Barrierefreiheit deaktivieren (und dadurch die Verbesserungen der Barrierefreiheit nutzen), indem Sie dem [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung einen Parameter hinzufügen und deren Wert auf `false` festlegen. Das folgende Beispiel zeigt, wie Sie die in .NET Framework 4.7.1 eingeführten Barrierefreiheitserweiterungen aktivieren:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Wenn Sie die Barrierefreiheitsoptionen in einer höheren Version von .NET Framework aktivieren, müssen Sie ebenfalls die Features früherer Versionen aktivieren. Sie benötigen das folgende [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element, um Ihre App so zu konfigurieren, dass Sie die Verbesserungen der Barrierefreiheit sowohl in .NET Framework 4.7.1 als auch in Version 4.7.2 nutzen können:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Wiederherstellen von Legacyverhalten

Anwendungen, die Versionen von .NET Framework ab 4.7.1 anzielen, können die Barrierefreiheitsfeatures deaktivieren, indem folgendes Element zum [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und deren Wert auf `true` festgelegt wird. Beispielsweise deaktiviert die folgende Konfiguration die Barrierefreiheitsfeatures, die in .NET Framework 4.7.2 eingeführt wurden:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a>Neuerungen der Barrierefreiheit in .NET Framework 4.7.2

.NET Framework 4.7.2 enthält neue Barrierefreiheitsfeatures für die folgenden Bereiche:

- [Windows Forms](#winforms472)

- [Windows Presentation Foundation (WPF)](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a>Windows Forms

**Vom Betriebssystem definierte Farben in Designs mit hohem Kontrast**

Ab .NET Framework 4.7.2 verwendet Windows Forms vom Betriebssystem definierte Farben in Designs mit hohem Kontrast. Dies hat Auswirkungen auf die folgenden Steuerelemente:

- Den Dropdownpfeil des <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelements

- Die Steuerelemente <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> und <xref:System.Windows.Forms.CheckBox>, wenn <xref:System.Windows.Forms.ButtonBase.FlatStyle> auf <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> oder <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> festgelegt ist. Zuvor gab es keinen Kontrast zwischen ausgewähltem Text und Hintergrundfarbe, wodurch der Text schwer lesbar war.

- Steuerelemente, die in einem <xref:System.Windows.Forms.GroupBox>-Objekt enthalten sind, dessen <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft auf `false` festgelegt ist

- Die <xref:System.Windows.Forms.ToolStripButton>-, <xref:System.Windows.Forms.ToolStripComboBox>- und <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelemente weisen ein höheres Helligkeitskontrastverhältnis im Modus „Hoher Kontrast“ auf.

- Die <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor>-Eigenschaft von <xref:System.Windows.Forms.DataGridViewLinkCell>.

**Verbesserungen der Sprachausgabe**

Ab .NET Framework 4.7.2 treten die folgenden Verbesserungen der Unterstützung der Sprachausgabe in Kraft:

- Sie kündigt jetzt den Wert der <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType>-Eigenschaft an, wenn sie den Text eines <xref:System.Windows.Forms.ToolStripMenuItem> ankündigt.

- Sie gibt jetzt an, wenn die <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft von <xref:System.Windows.Forms.ToolStripMenuItem> auf `false` festgelegt ist.

- Sie stellt jetzt Feedback zum Zustand eines Kontrollkästchens bereit, wenn die <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt ist.

- Die Fokusreihenfolge des Scanmodus der Sprachausgabe ist mit der visuellen Reihenfolge der Steuerelemente für das ClickOnce-Downloaddialogfenster konsistent.

**DataGridView-Verbesserungen**

Ab .NET Framework 4.7.2 wurden mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement die folgenden Barrierefreiheitsverbesserungen eingeführt:

- Zeilen können jetzt mithilfe der Tastatur sortiert werden. Ein Benutzer kann die F3-TASTE verwenden, um anhand der aktuellen Spalte zu sortieren.

- Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> festgelegt ist, ändert sich die Farbe der Spaltenüberschrift, um die aktuelle Spalte anzugeben, wenn der Benutzer mit der TABULATORTASTE die Zellen in der aktuellen Zeile durchläuft.

- Die <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType>-Elements gibt jetzt das richtige übergeordnete Steuerelement zurück.

**Verbesserte visuelle Hinweise**

- Die <xref:System.Windows.Forms.RadioButton>- und <xref:System.Windows.Forms.CheckBox>-Steuerelemente mit einer leeren <xref:System.Windows.Forms.ButtonBase.Text>-Eigenschaft zeigen einen Fokusindikator an, wenn sie den Fokus erhalten.

**Verbesserte Unterstützung für das Eigenschaftenraster**

- Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben jetzt nur dann `true` für die <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element aktiviert ist.

- Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben nur dann `false` für die <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element vom Benutzer geändert werden kann.

**Verbesserte Tastaturnavigation**

- Das <xref:System.Windows.Forms.ToolStripButton>-Steuerelement lässt den Fokus zu, wenn das Element in einem <xref:System.Windows.Forms.ToolStripPanel>-Element enthalten ist, für das die <xref:System.Windows.Forms.ToolStripPanel.TabStop>-Eigenschaft auf `true` festgelegt ist.

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Änderungen an den Steuerelementen CheckBox und RadioButton**

In .NET Framework 4.7.1 und früheren Versionen weisen die WPF-Steuerelemente <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> und <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> inkonsistente und im klassischen Design sowie im Design mit hohem Kontrast falsche visuelle Fokuselemente auf.  Diese Probleme treten in Fällen auf, in denen für die Steuerelemente keine Inhalte festgelegt sind.  Dadurch kann der Übergang zwischen Designs verwirrend wirken und das visuelle Fokuselement schwer zu erkennen sein.

In .NET Framework, 4.7.2 sind diese visuellen Elemente jetzt designübergreifend konsistenter und im klassischen Design sowie im Design mit hohem Kontrast leichter zu erkennen.

**WinForms-Steuerelemente, die in einer WPF-Anwendungen gehostet werden**

In .NET Framework 4.7.1 und früheren Versionen konnten Benutzer für das in einer WPF-Anwendung gehostete Steuerelement nicht die TAB-TASTE verwenden, um die WinForms-Ebene zu verlassen, wenn es sich bei dem ersten Steuerelement auf dieser Ebene um das WPF-Steuerelement <xref:System.Windows.Forms.Integration.ElementHost> handelte. In .NET Framework 4.7.2 können Benutzer jetzt die WinForms-Ebene über die TAB-TASTE verlassen.

Es kann jedoch sein, dass automatisierte Anwendungen, für die der Fokus dauerhaft auf der WinForms-Ebene liegen muss, nicht mehr einwandfrei funktionieren.

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Neuerungen der Barrierefreiheit in .NET Framework 4.7.1

.NET Framework 4.7.1 enthält neue Barrierefreiheitsfunktionen für folgende Bereiche:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Forms](#winforms471)

- [ASP.NET-Websteuerelemente](#aspnet471)

- [.NET SDK-Tools](#tools471)

- [Workflow-Designer von Windows Workflow Foundation (WF)](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Verbesserungen der Sprachausgabe**

Wenn die Verbesserungen der Barrierefreiheit aktiviert sind, enthält .NET Framework 4.7.1 folgende Verbesserungen, die sich auf die Sprachausgabe auswirken:

- In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.Expander>-Steuerelemente von der Sprachausgabe als Schaltflächen ausgegeben. Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als erweiterbare bzw. reduzierbare Gruppen ausgegeben.

- In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.DataGridCell>-Steuerelemente von der Sprachausgabe als „benutzerdefiniert“ ausgegeben. Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als (lokalisierte) Datenrasterzellen ausgegeben.

- Ab .NET Framework 4.7.1 gibt die Sprachausgabe den Namen einer bearbeitbaren <xref:System.Windows.Controls.ComboBox>-Klasse aus.

- In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.PasswordBox>-Steuerelemente als „Es befindet sich kein Element in der Ansicht.“ ausgegeben oder wiesen andere fehlerhafte Verhaltensweisen auf. Dieses Problem wurde in .NET Framework 4.7.1 behoben.

**Unterstützung von dynamischen Bereichen für die UIAutomation**

Die Sprachausgabe unterstützt die Benutzer beim Lesen der Inhalte der Benutzeroberfläche einer Anwendung. Dies geschieht üblicherweise durch eine Sprachausgabe des Texts der Inhalte der Benutzeroberfläche, die den Fokus besitzen. Wenn ein Element der Benutzeroberfläche sich jedoch verändert oder den Fokus nicht besitzt, wird der Benutzer möglicherweise nicht benachrichtigt, wodurch ihm wichtige Informationen entgehen können. Durch dynamische Bereiche soll dieses Problem behoben werden. Entwickler können diese verwenden, um der Sprachausgabe oder einem anderen UIAutomation-Client mitzuteilen, dass eine wichtige Änderung an einem Element der Benutzeroberfläche vorgenommen wurde. Die Sprachausgabe kann dann entscheiden, wie und wann der Benutzer über diese Änderung informiert wird.

Folgende APIs wurden zu WPF hinzugefügt, um dynamische Bereiche zu unterstützen:

- Die <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>-Felder, die die **LiveSetting**-Eigenschaft und das **LiveRegionChanged**-Ereignis identifizieren. Diese können mithilfe von XAML festgelegt werden.

- Die angefügte Eigenschaft **AutomationProperties.LiveSetting**, die der Sprachausgabe die Wichtigkeit der Änderung der Benutzeroberfläche für den Benutzer mitteilt.

- Die <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>-Eigenschaft, die die angefügte Eigenschaft **AutomationProperties.LiveSetting** identifiziert.

- Die <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>-Methode, die überschrieben werden kann, um einen **LiveSetting**-Wert bereitzustellen.

- Die <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>-Methoden, die einen **LiveSetting**-Wert abrufen und festlegen.

- Die <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>-Enumeration, die die folgenden möglichen **LiveSetting**-Werte definiert:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. Das Element sendet keine Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.

   - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.

Sie können einen dynamischen Bereich erstellen, indem Sie die Eigenschaft **AutomationProperties.LiveSetting** wie im folgenden Beispiel dargestellt auf das relevante Element festlegen:

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Wenn die Daten im dynamischen Bereich geändert werden und diese Änderung der Sprachausgabe mitgeteilt werden soll, müssen Sie wie im folgenden Beispiel dargestellt explizit ein Ereignis auslösen.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Hoher Kontrast**

Ab .NET Framework 4.7.1 wurden Verbesserungen am Design „Hoher Kontrast“ für verschiedene WPF-Steuerelemente vorgenommen. Diese sind nun sichtbar, wenn das <xref:System.Windows.SystemParameters.HighContrast%2A>-Design festgelegt ist. Dazu gehören:

- <xref:System.Windows.Controls.Expander>-Steuerelement

    Das visuelle Fokuselement für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt. Das visuelle Tastaturelement für die <xref:System.Windows.Controls.ComboBox>-, <xref:System.Windows.Controls.ListBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente wird ebenfalls angezeigt. Beispiel:

    Vorher: 

    ![Das Expander-Steuerelement mit Fokus vor der Verbesserung der Barrierefreiheit](media/expander-before.png)

    Nachher: 

    ![Das Expander-Steuerelement mit Fokus nach der Verbesserung der Barrierefreiheit](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente

    Der Text in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen ist nun leichter zu erkennen, wenn das Design mit hohem Kontrast ausgewählt ist. Beispiel:

    Vorher: 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus vor der Verbesserung der Barrierefreiheit](media/radio-button-before.png)

    Nachher: 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus nach der Verbesserung der Barrierefreiheit](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox>-Steuerelement

    Ab .NET Framework 4.7.1 hat der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Steuerelements die gleiche Farbe wie der deaktivierte Text. Beispiel:

    Vorher: 

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements vor der Verbesserung der Barrierefreiheit](media/combo-disabled-before.png)

    Nachher:   

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements nach der Verbesserung der Barrierefreiheit](media/combo-disabled-after.png)

    Darüber hinaus verwenden deaktivierte Schaltflächen und Schaltflächen mit Fokus das richtige Farbdesign.

    Vorher:

    ![Farbdesign der Schaltflächen vor der Verbesserung der Barrierefreiheit](media/button-themes-before.png) 

    Nachher: 

    ![Farbdesign der Schaltflächen nach der Verbesserung der Barrierefreiheit](media/button-themes-after.png) 

    In .NET Framework 4.7 und früher führte das Festlegen des Formats eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf `Toolbar.ComboBoxStyleKey` dazu, dass der Dropdownpfeil nicht angezeigt wurde. Dieses Problem wurde in .NET Framework 4.7.1 behoben. Beispiel:

    Vorher: 

    ![„Toolbar.ComboBoxStyleKey“ vor der Verbesserung der Barrierefreiheit](media/comboboxstylekey-before.png) 

    Nachher: 

    ![„Toolbar.ComboBoxStyleKey“ nach der Verbesserung der Barrierefreiheit](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid>-Steuerelement

    Ab .NET Framework 4.7.1 verwendet der Pfeil für die Sortieranzeige in den <xref:System.Windows.Controls.DataGrid>-Steuerelementen das richtige Farbdesign. Beispiel:

    Vorher: 

    ![Pfeil für die Sortieranzeige vor der Verbesserung der Barrierefreiheit](media/sort-indicator-before.png) 

    Nachher:   

    ![Pfeil für die Sortieranzeige nach der Verbesserung der Barrierefreiheit](media/sort-indicator-after.png) 

    Darüber hinaus wurde in .NET Framework 4.7 und früher das Standarddesign für Links geändert, wodurch Links beim Bewegen der Maus über diese im Modus mit hohem Kontrast in der falschen Farbe angezeigt wurden. Dieses Problem wurde in .NET Framework 4.7.1 behoben. Auf ähnliche Weise verwenden die Spalten des Kontrollkästchens <xref:System.Windows.Controls.DataGrid> ab .NET Framework 4.7.1 die erwarteten Farben für das Feedback des Tastaturfokus.

    Vorher: 

    ![DataGrid-Standarddesign für Links vor der Verbesserung der Barrierefreiheit](media/default-link-style-before.png) 

    Nachher:    

    ![DataGrid-Standarddesign für Links nach der Verbesserung der Barrierefreiheit](media/default-link-style-after.png) 

Weitere Informationen zu Verbesserungen der WPF-Barrierefreiheit in .NET Framework 4.7.1 finden Sie unter [Verbesserung der Barrierefreiheit in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a>Verbesserung der Barrierefreiheit von Windows Forms

In .NET Framework 4.7.1 enthält Windows Forms (WinForms) Verbesserungen der Barrierefreiheit für folgende Bereiche:

**Verbesserte Anzeige im Modus mit hohem Kontrast**

Ab .NET Framework 4.7.1 bieten viele WinForms-Steuerelemente ein verbessertes Rendering für die Modi mit hohem Kontrast, die im Betriebssystem verfügbar sind. In Windows 10 wurden die Werte für einige Systemfarbe im Design mit hohem Kontrast geändert, und Windows Forms basiert auf dem Win32-Framework von Windows 10. Führen Sie für die besten Ergebnisse die aktuelle Version von Windows aus, und aktivieren Sie die neuesten Änderungen am Betriebssystem, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus der SupportedOS-Zeile für Windows 10 entfernen, sodass diese folgendermaßen aussieht:

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

Folgende Änderungen wurden am Design mit hohem Kontrast vorgenommen:

- Die Kontrollkästchen der <xref:System.Windows.Forms.MenuStrip>-Elemente können einfacher angezeigt werden.

- Wenn diese aktiviert werden, können deaktivierte <xref:System.Windows.Forms.MenuStrip>-Elemente einfacher angezeigt werden.

- Der Text in einem ausgewählten <xref:System.Windows.Forms.Button>-Kontrollkästchen bildet einen Kontrast zur Auswahlfarbe.

- Deaktivierter Text ist einfacher zu lesen. Beispiel:

    Vorher:

    ![Deaktivierter Text vor der Verbesserung der Barrierefreiheit](media/wf-disabled-before.png) 

    Nachher:

    ![Deaktivierter Text nach der Verbesserung der Barrierefreiheit](media/wf-disabled-after.png) 

- Verbesserungen am Design mit hohem Kontrast im Dialogfeld der Threadausnahme.

**Verbesserte Unterstützung für die Sprachausgabe**

Windows Forms in .NET Framework 4.7.1 enthält folgende Verbesserungen für die Barrierefreiheit der Sprachausgabe:

- Auf das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann über die Sprachausgabe sowie über andere Tools zur Automatisierung der Benutzeroberfläche zugegriffen werden.

- Das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement teilt der Sprachausgabe mit, wenn der Aktivierungszustand eines Elements geändert wurde, sodass der Benutzer darüber benachrichtigt wird, dass der Wert eines Listenelements verändert wurde.

- Das <xref:System.Windows.Forms.DataGridViewCell>-Steuerelement teilt der Sprachausgabe den richtigen schreibgeschützten Status mit.

- Die Sprachausgabe kann nun deaktivierten <xref:System.Windows.Forms.ToolStripMenuItem>-Text ausgeben, während deaktivierte Menüelemente zuvor übersprungen wurden.

**Verbesserte Unterstützung für die Barrierefreiheitsmuster der UIAutomation**

Ab .NET Framework 4.7.1 können die Entwickler von Tools für Barrierefreiheitstechnologien allgemeine API-Barrierefreiheitsmuster und -eigenschaften für mehrere WinForms-Steuerelemente verwenden. Folgende Verbesserungen der Barrierefreiheit wurden vorgenommen:

- Die <xref:System.Windows.Forms.ComboBox>- und <xref:System.Windows.Forms.ToolStripSplitButton>-Steuerelemente unterstützen nun das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Das <xref:System.Windows.Forms.DataGridViewCheckBoxCell>-Steuerelement unterstützt nun das [Umschaltmuster](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).

- Das <xref:System.Windows.Forms.ToolStripItem>-Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft und das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Die <xref:System.Windows.Forms.NumericUpDown>- und <xref:System.Windows.Forms.DomainUpDown>-Steuerelemente unterstützen die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft.

**Verbesserter Eigenschaftenbrowser**

Ab .NET Framework 4.7.1 enthält Windows Forms Folgendes:

- Eine verbesserte Tastaturnavigation durch die verschiedenen Fenster der Dropdownauswahl
- Eine Verringerung unnötiger Tabstopps
- Eine verbesserte Berichterstellung der Steuerelementtypen
- Ein verbessertes Verhalten der Sprachausgabe

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a>ASP.NET-Websteuerelemente

Ab .NET Framework 4.7.1 und Visual Studio 2017 15.3 arbeiten .ASP.NET-Websteuerelemente effizienter mit den Funktionen für die Barrierefreiheit in Visual Studio zusammen. Dazu gehören folgende Änderungen:

- Änderungen, durch die fehlende Barrierefreiheitsmuster für Steuerelemente der Benutzeroberfläche implementiert werden. Zu diesen Steuerelementen zählen z.B. das Dialogfeld **Feld hinzufügen** im **Detailansicht-Assistenten** oder das Dialogfeld **ListView konfigurieren** im **ListView**-Assistenten.

- Änderungen zur Verbesserung der Anzeige im Modus für hohe Kontraste, z.B. beim **DataPager-Feld-Editor**.

- Änderungen zur Verbesserung der Benutzerfreundlichkeit bei der Tastaturnavigation für Steuerelemente, z.B. beim Dialogfeld **Felder** im Assistenten für das **Bearbeiten von Pagerfeldern** des DataPager-Steuerelements, beim Dialogfeld **ObjectContext konfigurieren** oder beim Dialogfeld **Datenauswahl konfigurieren** des Assistenten zum **Konfigurieren der Datenquelle**.

<a name="tools471"></a>

### <a name="net-sdk-tools"></a>.NET SDK-Tools

Das [Configuration Editor-Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) und das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) wurden verbessert, indem verschiedene Barrierefreiheitsprobleme verbessert wurden. In den meisten Fälle handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden. Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden.

Durch diese Verbesserungen ändert sich vorheriges Verhalten wie die Reihenfolge des Tastaturfokus.

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Workflow-Designer von Windows Workflow Foundation (WF)

Die Barrierefreiheitsänderungen im Workflow-Designer umfassen Folgendes:

- Die Aktivierreihenfolge wurde bei manchen Steuerelementen in „Von links nach rechts“ und in „Von oben nach unten“ geändert:

  - Das Fenster „Korrelation initialisieren“ für das Festlegen von Korrelationsdaten für die <xref:System.ServiceModel.Activities.InitializeCorrelation>-Aktivität

  - Das Fenster „Inhaltsdefinition“ für die Aktivitäten <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>

- Weitere Funktionen sind über die Tastatur verfügbar:

  - Beim Bearbeiten der Eigenschaften einer Aktivität können die Eigenschaftengruppen über die Tastatur reduziert werden, wenn diese zum ersten Mal fokussiert werden.

  - Auf Warnsymbole kann über die Tastatur zugegriffen werden.

  - Auf die Schaltfläche **Weitere Eigenschaften** im Fenster **Eigenschaften** kann über die Tastatur zugegriffen werden.

  - Tastaturbenutzer können auf die Headerelemente in den Bereichen **Argumente** und **Variablen** des Workflow-Designers zugreifen.

- Verbesserte Sichtbarkeit von Elementen mit Fokus, z.B. in folgenden Fällen:

  - Hinzufügen von Zeilen zu Datenrastern, die vom Workflow-Designer und von Aktivitäts-Designern verwendet werden

  - Wechseln von Feldern mit der TAB-TASTE in den Aktivitäten <xref:System.ServiceModel.Activities.ReceiveReply> und <xref:System.ServiceModel.Activities.SendReply>

  - Festlegen von Standardwerten für Variablen oder Argumente

- Sprachausgaben können Folgendes nun richtig erkennen:

  - Breakpoints, die im Workflow-Designer festgelegt wurden

  - Die Aktivitäten <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> und <xref:System.ServiceModel.Activities.CorrelationScope>
  - Die Inhalte der <xref:System.ServiceModel.Activities.Receive>-Aktivität

  - Den Zieltyp für die <xref:System.Activities.Statements.InvokeMethod>-Aktivität

  - Das Kombinationsfeld „Ausnahme“ und den Abschnitt „Finally“ in der <xref:System.Activities.Statements.TryCatch>-Aktivität

  - Das Kombinationsfeld „Nachrichtentyp“, den Splitter im Fenster „Korrelationsinitialisierer hinzufügen“, das Fenster „Inhaltsdefinition“ und das Definitionsfenster „CorrelatesOn“ in den Messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>)

  - Übertragungen von Zustandsautomaten und Übertragungsziele

  - Anmerkungen und Connectors von <xref:System.Activities.Statements.FlowDecision>-Aktivitäten

  - Die per Rechtsklick aufrufbaren Kontextmenüs von Aktivitäten

  - Die Editors für Eigenschaftswerte, die Schaltfläche, „Suche löschen“, die Sortierschaltflächen „Nach Kategorie“ und „Alphabetisch“ sowie das Dialogfeld „Ausdrucks-Editor“ im Eigenschaftenraster

  - Den Zoomprozentwert im Workflow-Designer

  - Das Trennzeichen in den Aktivitäten <xref:System.Activities.Statements.Parallel> und <xref:System.Activities.Statements.Pick>

  - Die <xref:System.Activities.Statements.InvokeDelegate>-Aktivität

  - Das Fenster „Typen auswählen“ für Wörterbuchaktivitäten (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` usw.)

  - Das Fenster „.NET-Typ suchen und auswählen“

  - Breadcrumbs im Workflow-Designer

- Benutzer, die Designs mit hohem Kontrast verwenden, werden viele Verbesserungen in der Sichtbarkeit des Workflow-Designers und dessen Steuerelementen feststellen. Dazu zählen verbesserte Kontrastverhältnisse zwischen Elementen und leichter erkennbare Auswahlfelder für Fokuselemente.

## <a name="see-also"></a>Siehe auch

- [What's new in the .NET Framework (Neuerungen in .NET Framework)](whats-new.md)
