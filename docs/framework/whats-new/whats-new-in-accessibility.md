---
title: Neuerungen der Barrierefreiheit in .NET Framework
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Neuerungen der Barrierefreiheit in .NET Framework

Die Anwendungen von .NET Framework sollen eine bessere Barrierefreiheit für Ihre Benutzer bieten. Durch Barrierefreiheitsfunktionen wird es einer Anwendung ermöglicht, den Benutzern von Hilfstechnologien ein angemessenes Erlebnis zu bieten. Ab .NET Framework 4.7.1 enthält .NET Framework zahlreiche Verbesserungen der Barrierefreiheit, die es den Entwicklern ermöglichen, barrierefreie Anwendungen zu erstellen. 

Die neuen Barrierefreiheitsfunktionen werden standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen. Zusätzlich können Anwendungen, die eine frühere Version von .NET Framework anzielen, aber unter .NET Framework 4.7.1 oder höher ausgeführt werden, veraltete Verhaltensweisen für die Barrierefreiheit deaktivieren (und dadurch die Verbesserungen der Barrierefreiheit in .NET Framework 4.7.1 aktivieren), indem folgendes Element zum [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt wird. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Auf ähnliche Weise können Anwendungen, die Versionen von .NET Framework ab 4.7.1 anzielen, die Barrierefreiheitsfunktionen deaktivieren, indem folgendes Element zum [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt wird. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Neuerungen der Barrierefreiheit in .NET Framework 4.7.1

.NET Framework 4.7.1 enthält neue Barrierefreiheitsfunktionen für folgende Bereiche:

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows Forms](#windows-forms-accessibility-improvements)

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

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType> Das Element sendet keine Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType> Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType> Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.   

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

    Das visuelle Fokuselement für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt. Das visuelle Tastaturelement für die <xref:System.Windows.Controls.ComboBox>-, <xref:System.Windows.Controls.ListBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente wird ebenfalls angezeigt. Zum Beispiel:

    Vorher: 
    
    ![Das Expander-Steuerelement mit Fokus vor der Verbesserung der Barrierefreiheit](media/expander-before.png)

    Nachher: 

    ![Das Expander-Steuerelement mit Fokus nach der Verbesserung der Barrierefreiheit](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente
 
    Der Text in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen ist nun leichter zu erkennen, wenn das Design mit hohem Kontrast ausgewählt ist. Zum Beispiel:

    Vorher: 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus vor der Verbesserung der Barrierefreiheit](media/radio-button-before.png)
    
    Nachher: 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus nach der Verbesserung der Barrierefreiheit](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox>-Steuerelement
 
    Ab .NET Framework 4.7.1 hat der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Steuerelements die gleiche Farbe wie der deaktivierte Text. Zum Beispiel:
    
    Vorher: 

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements vor der Verbesserung der Barrierefreiheit](media/combo-disabled-before.png)

    Nachher:   

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements nach der Verbesserung der Barrierefreiheit](media/combo-disabled-after.png)

    Darüber hinaus verwenden deaktivierte Schaltflächen und Schaltflächen mit Fokus das richtige Farbdesign.

    Vorher:

    ![Farbdesign der Schaltflächen vor der Verbesserung der Barrierefreiheit](media/button-themes-before.png) 
    
    Nachher: 

    ![Farbdesign der Schaltflächen nach der Verbesserung der Barrierefreiheit](media/button-themes-after.png) 

    In .NET Framework 4.7 und früher führte das Festlegen des Formats eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf `Toolbar.ComboBoxStyleKey` dazu, dass der Dropdownpfeil nicht angezeigt wurde. Dieses Problem wurde in .NET Framework 4.7.1 behoben. Zum Beispiel:

    Vorher: 

    ![„Toolbar.ComboBoxStyleKey“ vor der Verbesserung der Barrierefreiheit](media/comboboxstylekey-before.png) 
    
    Nachher: 

    ![„Toolbar.ComboBoxStyleKey“ nach der Verbesserung der Barrierefreiheit](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid>-Steuerelement

    Ab .NET Framework 4.7.1 verwendet der Pfeil für die Sortieranzeige in den <xref:System.Windows.Controls.DataGrid>-Steuerelementen das richtige Farbdesign. Zum Beispiel:

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

## <a name="windows-forms-accessibility-improvements"></a>Verbesserung der Barrierefreiheit von Windows Forms

In .NET Framework 4.7.1 enthält Windows Forms (WinForms) Verbesserungen der Barrierefreiheit für folgende Bereiche:

**Verbesserte Anzeige im Modus mit hohem Kontrast**

Ab .NET Framework 4.7.1 bieten viele WinForms-Steuerelemente ein verbessertes Rendering für die Modi mit hohem Kontrast, die im Betriebssystem verfügbar sind. In Windows 10 wurden die Werte für einige Systemfarbe im Design mit hohem Kontrast geändert, und Windows Forms basiert auf dem Win32-Framework von Windows 10. Führen Sie für die besten Ergebnisse die aktuelle Version von Windows aus, und aktivieren Sie die neuesten Änderungen am Betriebssystem, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus der supportedOS-Zeile für Windows 10 entfernen, sodass diese folgendermaßen aussieht:

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Folgende Änderungen wurden am Design mit hohem Kontrast vorgenommen:

- Die Kontrollkästchen der <xref:System.Windows.Forms.MenuStrip>-Elemente können einfacher angezeigt werden.

- Wenn diese aktiviert werden, können deaktivierte <xref:System.Windows.Forms.MenuStrip>-Elemente einfacher angezeigt werden.

- Der Text in einem ausgewählten <xref:System.Windows.Forms.Button>-Kontrollkästchen bildet einen Kontrast zur Auswahlfarbe.

- Deaktivierter Text ist einfacher zu lesen. Zum Beispiel:

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
 
## <a name="see-also"></a>Siehe auch
[What's new in the .NET Framework (Neuerungen in .NET Framework)](whats-new.md)   
 