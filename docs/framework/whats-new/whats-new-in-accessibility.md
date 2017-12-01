---
title: Was ist neu in Barrierefreiheit in .NET Framework
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Was ist neu in Barrierefreiheit in .NET Framework

.NET Framework zielt darauf ab, zu Anwendungen Weitere Accessibile für Ihre Benutzer. Barrierefreiheitsfunktionen ermöglichen eine Anwendung in eine entsprechende Erfahrung für Benutzer der Hilfstechnologie bereitstellen. Ab .NET Framework 4.7.1 enthält .NET Framework eine große Anzahl von Eingabehilfen-Verbesserungen, die Entwicklern das Erstellen von Anwendungen mit Barrierefreiheit zu ermöglichen. 

Die neuen Funktionen für Barrierefreiheit sind standardmäßig für Anwendungen, die das .NET 4.7.1 Framework enabled "oder" weiter unten. Darüber hinaus Anwendungen, die auf eine frühere Version von .NET Framework, jedoch auf .NET Framework 4.7.1 ausgeführt werden oder später entscheiden können, ältere Eingabehilfen-Verhalten (und somit entscheiden Sie sich für die Barrierefreiheit Verbesserungen in .NET Framework 4.7.1) durch Hinzufügen des folgenden Switches, die [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) Abschnitt der Konfigurationsdatei der Anwendung. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Auf ähnliche Weise können Anwendungen, die gezielt Versionen von .NET Framework 4.7.1 ab Barrierefreiheitsfunktionen deaktivieren, indem Sie die folgenden Schalter zum Hinzufügen der [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) Abschnitt der Konfigurationsdatei der Anwendung. 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>Neuigkeiten in .NET Framework 4.7.1 Eingabehilfe

.NET Framework 4.7.1 enthält neue Features für Eingabehilfen in den folgenden Bereichen:

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows Forms](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Bildschirm Reader Verbesserungen**

Wenn Barrierefreiheit Verbesserungen aktiviert sind, enthält .NET Framework 4.7.1 die folgenden Verbesserungen, die Bildschirmsprachausgaben beeinflussen:

- In .NET Framework 4.7 und früheren Versionen <xref:System.Windows.Controls.Expander> Steuerelemente von Bildschirmsprachausgaben als Schaltflächen angekündigt wurden. Ab .NET Framework 4.7.1, werden sie ordnungsgemäß als erweiterbaren/reduzierbaren Gruppen angekündigt.

- In .NET Framework 4.7 und früheren Versionen <xref:System.Windows.Controls.DataGridCell> Steuerelemente von Bildschirmsprachausgaben angekündigt wurden, als "Benutzerdefiniert". Ab .NET Framework 4.7.1, werden sie jetzt ordnungsgemäß als Raster Datenzelle (lokalisiert) angekündigt.
 
- Ab .NET Framework 4.7.1, ankündigen Sprachausgaben den Namen einer bearbeitbaren <xref:System.Windows.Controls.ComboBox>.

- In .NET Framework 4.7 und früheren Versionen <xref:System.Windows.Controls.PasswordBox> Steuerelemente wurden als "kein Element in der Ansicht" angekündigt wird, oder hatte fehlerhafte Verhalten. Dieses Problem ist behoben, beginnend mit .NET Framework 4.7.1.     

**UIAutomation LiveRegion-Unterstützung**

Sprachausgabe, z. B. Sprachausgabe Hilfe Personen lesen den Inhalt der Benutzeroberfläche einer Anwendung in der Regel von-Sprach-Ausgabe von UI-Inhalten, die Fokus besitzt. Jedoch, wenn ein Element der Benutzeroberfläche ändert und verfügt nicht über den Fokus, und der Benutzer möglicherweise nicht benachrichtigt werden wichtige Informationen verstößt. Live-Regionen Ziel der Lösung dieses Problems. Entwickler können sie um zu informieren, die Bildschirmsprachausgaben oder einem anderen UIAutomation-Client, den auf ein Element der Benutzeroberfläche eine wichtige Änderung vorgenommen wurde. Die Sprachausgabe kann dann entscheiden, wie und wann auf die Benutzer über diese Änderung zu informieren. 

Um live Regionen zu unterstützen, wurden die folgenden APIs in WPF hinzugefügt:

- Die <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> und <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> Felder, die Identifizieren der **LiveSetting** Eigenschaft und die **LiveRegionChanged** Ereignis. Sie können mit XAML festgelegt werden.

- Die **AutomationProperties.LiveSetting** angefügten Eigenschaft, die die Bildschirmsprachausgaben die Wichtigkeit der UI-Änderung an den Benutzer darüber informiert.

- Die <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> -Eigenschaft, die identifiziert die **AutomationProperties.LiveSetting** -Eigenschaft.
 
- Die <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> -Methode, die überschrieben werden kann, ermöglichen eine **LiveSetting** Wert.

- Die <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> und <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> -Methoden, die abrufen und Festlegen einer **LiveSetting** Wert.
 
- Die <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> -Enumeration, die die folgenden möglichen definiert **LiveSetting** Werte:

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. Das Element ist keine Benachrichtigungen gesendet werden, wenn der Inhalt des aktiven Bereichs geändert wurde.   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.   

Sie können eine LiveRegion erstellen, durch Festlegen der **AutomationProperties.LiveSetting** -Eigenschaft des Elements von Interesse sind, wie im folgenden Beispiel gezeigt:   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Wenn die Daten in den aktiven Bereich ändern und Sie eine Bildschirmsprachausgabe informieren müssen, lösen Sie explizit ein Ereignis, wie im folgenden Beispiel gezeigt.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**Hoher Kontrast**

Beginnend mit .NET Framework 4.7.1, Verbesserungen bei hohem Kontrast verschiedene WPF-Steuerelemente wurden. Sie sind jetzt sichtbar, wenn die <xref:System.Windows.SystemParameters.HighContrast%2A> Design "festgelegt ist. Dazu gehören:

- <xref:System.Windows.Controls.Expander>-Steuerelement

    Der Schwerpunkt für visual der <xref:System.Windows.Controls.Expander> -Steuerelement ist nun sichtbar. Die Tastatur visuellen Elemente für <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, und <xref:System.Windows.Controls.RadioButton> Steuerelemente werden ebenfalls angezeigt. Zum Beispiel:

    Vorher: 
    
    ![Expandersteuerelement mit Fokus vor Eingabehilfen-Verbesserungen](media/expander-before.png)

    Nachher: 

    ![Expandersteuerelement mit Fokus nach Eingabehilfen-Verbesserungen](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>und <xref:System.Windows.Controls.RadioButton> Steuerelemente
 
    Der Text in der <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.RadioButton> Steuerelemente ist jetzt leichter zu erkennen, wenn Sie in Designs mit hohem Kontrast auswählen. Zum Beispiel:

    Vorher: 

    ![Hoher Kontrast Optionsfeld den Fokus hat, vor dem Zugriff auf Verbesserungen](media/radio-button-before.png)
    
    Nachher: 

    ![Hoher Kontrast Optionsfeld mit dem Fokus nach Eingabehilfen-Verbesserungen](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox>-Steuerelement
 
    Ab .NET Framework 4.7.1, den Rahmen einen deaktivierten <xref:System.Windows.Controls.ComboBox> -Steuerelement ist die gleiche Farbe wie deaktiviertem Text. Zum Beispiel:
    
    Vorher: 

     ![ComboBox deaktiviert, Rahmen und Text vor dem Eingabehilfen-Verbesserungen](media/combo-disabled-before.png)

    Nachher:   

     ![Rahmen und Text deaktiviert nach Eingabehilfen Verbesserungen ComboBox](media/combo-disabled-after.png)

    Darüber hinaus verwenden deaktivierte und konzentriert sich Schaltflächen die richtige Farbdesign.

    Vorher:

    ![Schaltfläche Designfarben vor Eingabehilfen-Verbesserungen](media/button-themes-before.png) 
    
    Nachher: 

    ![Schaltfläche Designfarben nach Eingabehilfen-Verbesserungen](media/button-themes-after.png) 

    Schließlich in der .NET Framework 4.7 und frühere Versionen, die Einstellung einer <xref:System.Windows.Controls.ComboBox> Steuerelementformats zu `Toolbar.ComboBoxStyleKey` verursacht den Dropdown Pfeil unsichtbar. Dieses Problem ist behoben, beginnend mit .NET Framework 4.7.1. Zum Beispiel:

    Vorher: 

    ![Toolbar.ComboBoxStyleKey vor Eingabehilfen-Verbesserungen](media/comboboxstylekey-before.png) 
    
    Nachher: 

    ![Toolbar.ComboBoxStyleKey nach Eingabehilfen-Verbesserungen](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid>-Steuerelement

    Ab .NET Framework 4.7.1, die Sortierreihenfolge Indikator Pfeil in <xref:System.Windows.Controls.DataGrid> steuert nun verwendet Designfarben korrigieren. Zum Beispiel:

    Vorher: 

    ![Sortieren von Indikator Pfeile neben den Eingabehilfen-Verbesserungen](media/sort-indicator-before.png) 
    
    Nachher:   
 
    ![Sortieren von Indikator Pfeil nach Eingabehilfen-Verbesserungen](media/sort-indicator-after.png) 
    
    Darüber hinaus geändert in .NET Framework 4.7 und früheren Versionen müssen der Standardstil für den Link auf eine falsche Farbe auf Maus über im Modus für hohen Kontrast. Dies ist die beginnen mit .NET Framework 4.7.1 aufgelöst. Auf ähnliche Weise <xref:System.Windows.Controls.DataGrid> Kontrollkästchen Spalten die erwarteten Farben für Tastatur Fokus Feedback beginnend mit .NET Framework 4.7.1 verwendet.

    Vorher: 

    ![Link DataGrid-Standardformat vor Eingabehilfen-Verbesserungen](media/default-link-style-before.png) 
 
    Nachher:    
  
    ![Link DataGrid-Standardformat nach Eingabehilfen-Verbesserungen](media/default-link-style-after.png)  

Weitere Informationen zu den Eingabehilfen-Verbesserungen für WPF in .NET Framework 4.7.1 finden Sie unter [Eingabehilfen-Verbesserungen in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

## <a name="windows-forms-accessibility-improvements"></a>Verbesserungen für Windows Forms-Eingabehilfen

In .NET Framework, 4.7.1 umfasst Windows Forms (WinForms) Zugriff auf Änderungen in den folgenden Bereichen.

**Verbesserte Anzeige im Modus für hohe Kontraste**

Ab .NET Framework 4.7.1, bieten verschiedene WinForms-Steuerelemente verbesserte Renderingerweiterungen in den Modi für hoher Kontrast im Betriebssystem verfügbar. Windows 10 die Werte für einige hoher Kontrast Systemfarben geändert wurde, und Windows Forms basiert auf Windows 10-Win32-Framework. Optimale Ergebnisse zu erzielen führen Sie die neueste Version von Windows, und entscheiden Sie sich mit den aktuellen OS-Änderungen, indem Sie das Hinzufügen einer Datei "app.manifest" in einer testanwendung und Windows 10-Kommentar OS Zeile unterstützt, damit es im folgenden wird erläutert:

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
Einige Beispiele für hohen Kontrast Änderungen:

- Häkchen im <xref:System.Windows.Forms.MenuStrip> Elemente sind einfacher zu anzeigen.

- Bei Auswahl dieser Option deaktiviert <xref:System.Windows.Forms.MenuStrip> Elemente sind einfacher zu anzeigen.

- Text in einem ausgewählten <xref:System.Windows.Forms.Button> Gegensatz die Auswahlfarbe steuern.

- Deaktivierter Text ist einfacher zu lesen. Zum Beispiel:

    Vorher:

    ![Deaktiviertem Text vor dem Eingabehilfen-Verbesserungen](media/wf-disabled-before.png) 

    Nachher:

    ![Deaktivierte Text nach Eingabehilfen-Verbesserungen](media/wf-disabled-after.png) 

- Hoher Kontrast Verbesserungen im Thread-Dialogfeld "Ausnahme".

**Verbesserte Unterstützung für die Sprachausgabe**

Windows Forms in .NET Framework 4.7.1 umfasst die folgenden Eingabehilfen-Verbesserungen für die Sprachausgabe:

- Die <xref:System.Windows.Forms.MonthCalendar> Steuerelement möglich, die von der Sprachausgabe sowie von anderen Automatisierungstools UI.

- Die <xref:System.Windows.Forms.CheckedListBox> Steuerelement Sprachausgabe benachrichtigt, wenn der Aktivierungszustand eines Elements geändert wurde, damit der Benutzer informiert wird, dass sie den Wert eines Listenelement geändert haben.
 
- Die <xref:System.Windows.Forms.DataGridViewCell> Steuerelement des korrekten Status der nur-Lese Sprachausgabe meldet.
 
- Sprachausgabe kann nun deaktiviert lesen <xref:System.Windows.Forms.ToolStripMenuItem> Text, wohingegen zuvor es deaktiviert Menüelemente überspringen möchten.

**Verbesserte Unterstützung für UIAutomation Eingabehilfen-Muster**

Ab .NET Framework 4.7.1, können Entwickler von Eingabehilfen-Technologie häufige Muster von API-Zugriff und die Eigenschaften für mehrere WinForms-Steuerelemente nutzen. Diese Eingabehilfen Verbesserungen umfassen:

- Die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ToolStripSplitButton> unterstützen jetzt die [erweitern/reduzieren-Muster](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).
 
- Die <xref:System.Windows.Forms.DataGridViewCheckBoxCell> unterstützt jetzt die [Toggle-Muster](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).
 
- Die <xref:System.Windows.Forms.ToolStripItem> -Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.Name> Eigenschaft und die [erweitern/reduzieren-Muster](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- Die <xref:System.Windows.Forms.NumericUpDown> und <xref:System.Windows.Forms.DomainUpDown> Steuerelemente unterstützen die <xref:System.Windows.Automation.automationElement.Name> Eigenschaft.

**Verbesserte Eigenschaft Browserfunktionen**

Ab .NET Framework 4.7.1, umfasst Windows Forms:

- Eine bessere Tastaturnavigation durch die verschiedenen Dropdownfeld-Fenster.
- Eine Verringerung unnötiger Tabstopps.
- Melden besser von Steuerelementtypen.
- Verbesserte Sprachausgabe Verhalten.
 
## <a name="see-also"></a>Siehe auch
[Was ist neu in .NET Framework](whats-new.md)   
 