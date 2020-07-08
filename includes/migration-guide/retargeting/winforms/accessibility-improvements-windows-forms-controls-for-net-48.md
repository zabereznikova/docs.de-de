---
ms.openlocfilehash: e528a41748d9353c96d443f68e15e7a98ee7f4ae
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616257"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-48"></a>Verbesserung der Barrierefreiheit von Windows Forms-Steuerelementen für .NET 4.8

#### <a name="details"></a>Details

Die Arbeitsweise des Windows Forms-Frameworks mit Technologien für die Barrierefreiheit wird weiter verbessert, um Kunden von Windows Forms besser zu unterstützen. Folgende Änderungen wurden u.a. vorgenommen:

- Änderungen zum Verbessern der Anzeige während des Modus mit hohem Kontrast
- Änderungen an der Interaktion mit der Sprachausgabe.
- Änderungen an der Hierarchie der Barrierefreiheit (Verbesserung der Navigation durch die Benutzeroberflächenautomatisierungsstruktur)

#### <a name="suggestion"></a>Vorschlag

**Aktivieren oder Deaktivieren dieser Änderungen:** Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden. Die Anwendung kann diese Änderungen aktivieren, wenn Sie Folgendes durchführen:

- Kompilieren Sie diese nochmals, um .NET Framework 4.8 zu verwenden. Diese Änderungen der Barrierefreiheit werden standardmäßig für Windows Forms-Anwendungen aktiviert, die .NET Framework 4.8 oder höher verwenden.
- Die Anwendung verwendet .NET Framework 4.7.2 oder eine frühere Version und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
  </runtime>
</configuration>
```

Beachten Sie Folgendes: Um die Barrierefreiheitsfunktionen zu aktivieren, die in .NET Framework 4.8 hinzugefügt wurden, müssen Sie auch die Barrierefreiheitsfunktion von .NET Framework 4.7.1 und 4.7.2 aktivieren. Bei Anwendungen, die .NET Framework 4.8 verwenden und die veralteten Verhaltensweisen für die Barrierefreiheit beibehalten sollen, können Sie die Verwendung des veralteten Features für die Barrierefreiheit aktivieren, indem Sie den AppContext-Switch auf `true` festlegen. Wenn Sie die Unterstützung zum Aufrufen der QuickInfo für Tastenkombinationen aktivieren möchten, müssen Sie dem „AppContextSwitchOverrides“-Wert die Zeile `Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false` hinzufügen:

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false" />
```

Zum Aktivieren dieser Funktion müssen Sie die bereits erwähnten Barrierefreiheitsfunktionen von .NET Framework 4.7.1 bis 4.8 aktivieren. Wenn eine der Barrierefreiheitsfunktionen nicht aktiviert wurde, die Funktion für die Anzeige von QuickInfos jedoch aktiviert wurde, wird beim ersten Zugriff auf diese Funktion ein Laufzeit-<xref:System.NotSupportedException> ausgelöst. Die Ausnahmemeldung gibt an, dass für QuickInfos für Tastenkombinationen die Barrierefreiheitsverbesserungen der Stufe 3 aktiviert werden müssen.

**Verwendung von durch das Betriebssystem definierten Farben in Designs mit hohem Kontrast**

- Verbesserte Designs mit hohem Kontrast

**Verbesserte Unterstützung für die Sprachausgabe**

- Die Sprachausgabe kündigt nun bei der Ankündigung eines barrierefreien Namens von <xref:System.Windows.Forms.DataGridViewCell> die Sortierreihenfolge von <xref:System.Windows.Forms.DataGridViewColumn> an.

**Verbesserte Unterstützung der CheckedListBox-Barrierefreiheit**

- Verbesserte Unterstützung für die Sprachausgabe beim <xref:System.Windows.Forms.CheckedListBox>-Steuerelement Beim Navigieren zum <xref:System.Windows.Forms.CheckedListBox>-Steuerelement mit der Tastatur konzentriert sich die Sprachausgabe auf das <xref:System.Windows.Forms.CheckedListBox>-Element und kündigt es an.
- Bei einem leeren CheckedListBox-Steuerelement wird nun ein Fokusrechteck für ein virtuelles erstes Element angezeigt, wenn der Fokus auf dem Steuerelement liegt.

**Verbesserte Unterstützung der ComboBox-Barrierefreiheit**

- Die Unterstützung für die Benutzeroberflächenautomatisierung wurde für das <xref:System.Windows.Forms.ComboBox>-Steuerelement mit der Möglichkeit aktiviert, Benachrichtigungen der Benutzeroberflächenautomatisierung und andere Funktionen der Benutzeroberflächenautomatisierung zu verwenden.
**Verbesserte Unterstützung der DataGridView-Barrierefreiheit**

- Die Unterstützung für die Benutzeroberflächenautomatisierung wurde für das <xref:System.Windows.Forms.DataGridView>-Steuerelement mit der Möglichkeit aktiviert, Benachrichtigungen der Benutzeroberflächenautomatisierung und andere Funktionen der Benutzeroberflächenautomatisierung zu verwenden.
- Das Element der Benutzeroberflächenautomatisierung, das <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl> oder <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl> entspricht, ist nun ein untergeordnetes Element der entsprechenden Bearbeitungszelle.

**Verbesserte Unterstützung der LinkLabel-Barrierefreiheit**

- Verbesserte Barrierefreiheit für das <xref:System.Windows.Forms.LinkLabel>-Steuerelement: Die Sprachausgabe kündigt den deaktivierten Zustand für den Link an, wenn das entsprechende <xref:System.Windows.Forms.LinkLabel>-Steuerelement deaktiviert ist.

**Verbesserte Unterstützung der ProgressBar-Barrierefreiheit**

- Die Unterstützung für die Benutzeroberflächenautomatisierung wurde für das <xref:System.Windows.Forms.ProgressBar>-Steuerelement mit der Möglichkeit aktiviert, Benachrichtigungen der Benutzeroberflächenautomatisierung und andere Funktionen der Benutzeroberflächenautomatisierung zu verwenden. Entwickler können nun Benachrichtigungen zur Benutzeroberflächenautomatisierung verwenden, die von der Sprachausgabe zur Angabe des Status angekündigt werden können.
Eine Übersicht über Ereignisse der Benutzeroberflächenautomatisierung, einschließlich Benachrichtigungsereignisse der Benutzeroberflächenautomatisierung, finden Sie unter [Übersicht über Ereignisse zur Benutzeroberflächenautomatisierung](https://docs.microsoft.com/windows/desktop/WinAuto/uiauto-eventsoverview).

**Verbesserte Unterstützung der PropertyGrid-Barrierefreiheit**

- Die Unterstützung für die Benutzeroberflächenautomatisierung wurde für das <xref:System.Windows.Forms.PropertyGrid>-Steuerelement mit der Möglichkeit aktiviert, Benachrichtigungen der Benutzeroberflächenautomatisierung und andere Funktionen der Benutzeroberflächenautomatisierung zu verwenden.
- Das Element der Benutzeroberflächenautomatisierung, das der derzeit bearbeiteten Eigenschaft entspricht, ist nun ein untergeordnetes Element des entsprechenden Benutzeroberflächenautomatisierungselements des Eigenschaftselements.
- Das Element der Benutzeroberflächenautomatisierung des Eigenschaftselements ist nun ein untergeordnetes Element des entsprechenden Kategorieelements, wenn das übergeordnete <xref:System.Windows.Forms.PropertyGrid>-Steuerelement auf die Kategorieansicht festgelegt ist.

**Verbesserte ToolStrip-Unterstützung**

- Die Unterstützung für die Benutzeroberflächenautomatisierung wurde für das <xref:System.Windows.Forms.ToolStrip>-Steuerelement mit der Möglichkeit aktiviert, Benachrichtigungen der Benutzeroberflächenautomatisierung und andere Funktionen der Benutzeroberflächenautomatisierung zu verwenden.
- Verbesserte Navigation durch <xref:System.Windows.Forms.ToolStrip>-Elemente.
- Im Elementmodus verschwindet der Sprachausgabefokus nicht und wechselt nicht zu ausgeblendeten Elementen.

**Verbesserte visuelle Hinweise**

- Ein leeres <xref:System.Windows.Forms.CheckedListBox>-Steuerelement zeigt nun einen Fokusindikator an, wenn es den Fokus erhält.
Hinweis: Die Unterstützung für die Benutzeroberflächenautomatisierung für Steuerelemente wird zur Laufzeit aktiviert, wird jedoch zur Entwurfszeit nicht verwendet. Einen Überblick über die Benutzeroberflächenautomatisierung finden Sie unter [Benutzeroberflächenautomatisierung: Übersicht](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).

**Aufrufen von QuickInfos für Steuerelemente über die Tastatur**

- QuickInfos für Steuerelemente können nun durch Fokussieren des Steuerelements über die Tastatur aufgerufen werden. Diese Funktion muss für die Anwendung explizit aktiviert werden. (Informationen hierzu finden Sie unter **&quot;Aktivieren bzw. Deaktivieren dieser Änderungen&quot;** .)

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.8         |
| Typ    | Neuzuweisung |
