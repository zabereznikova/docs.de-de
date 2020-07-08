---
ms.openlocfilehash: cc3c2c2be179842f87be8892d057a6c4138086cb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614565"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a>Verbesserung der Barrierefreiheit von Windows Forms-Steuerelementen für .NET 4.7.2

#### <a name="details"></a>Details

Die Arbeitsweise des Windows Forms-Frameworks mit Technologien für die Barrierefreiheit wird verbessert, um Kunden von Windows Forms besser zu unterstützen. Folgende Änderungen wurden u.a. vorgenommen:

- Änderungen zum Verbessern der Anzeige während des Modus mit hohem Kontrast
- Änderungen zum Verbessern der Tastaturnavigation in den DataGridView- und MenuStrip-Steuerelementen.
- Änderungen an der Interaktion mit der Sprachausgabe.

#### <a name="suggestion"></a>Vorschlag

**Aktivieren oder Deaktivieren dieser Änderungen**: Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.7.2 oder höher ausgeführt werden. Die Anwendung kann von diesen Änderungen profitieren, wenn Sie Folgendes durchführen:

- Kompilieren Sie diese erneut, um .NET Framework 4.7.2 als Ziel zu verwenden. Diese Änderungen der Barrierefreiheit werden standardmäßig für Windows Forms-Anwendungen aktiviert, die .NET Framework 4.7.2 oder höher als Ziel verwenden.
- Die Anwendung verwendet .NET Framework 4.7.1 oder eine frühere Version als Ziel und deaktiviert veraltete Verhaltensweisen der Barrierefreiheit, indem wie im folgenden Beispiel dargestellt folgender [AppContext-Schalter](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt und auf `false` festgelegt wird.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
  </runtime>
</configuration>
```

Beachten Sie Folgendes: Um die Barrierefreiheitsfunktionen zu aktivieren, die in .NET Framework 4.7.2 hinzugefügt wurden, müssen Sie auch die Barrierefreiheitsfunktion von .NET Framework 4.7.1 aktivieren. Bei Anwendungen, die .NET Framework 4.7.2 oder höher als Zielplattform verwenden und das Legacyverhalten für die Barrierefreiheit beibehalten sollen, können Sie die Verwendung des Legacyfeatures für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.

**Verwendung von durch das Betriebssystem definierten Farben in Designs mit hohem Kontrast**

- Der Dropdownpfeil von <xref:System.Windows.Forms.ToolStripDropDownButton> verwendet jetzt vom Betriebssystem definierte Farben im Design mit hohem Kontrast.
- <xref:System.Windows.Forms.Button>-, <xref:System.Windows.Forms.RadioButton>- und <xref:System.Windows.Forms.CheckBox>-Steuerelemente, bei denen <xref:System.Windows.Forms.ButtonBase.FlatStyle> auf <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> oder <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> festgelegt ist, verwenden nun die vom Betriebssystem definierten Farben im Design mit hohem Kontrast, wenn dieses ausgewählt ist. Zuvor gab es keinen Kontrast zwischen Text und Hintergrundfarbe, wodurch der Text schwer lesbar war.
- In einem <xref:System.Windows.Forms.GroupBox>-Element enthaltene Steuerelemente, deren<xref:System.Windows.Forms.Control.Enabled>-Eigenschaft auf `false` festgelegt ist, verwenden nun die vom Betriebssystem definierten Farben im Design mit hohem Kontrast.
- Die <xref:System.Windows.Forms.ToolStripButton>-, <xref:System.Windows.Forms.ToolStripComboBox>- und <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelemente weisen ein höheres Helligkeitskontrastverhältnis im Modus „Hoher Kontrast“ auf.
- <xref:System.Windows.Forms.DataGridViewLinkCell> verwendet standardmäßig die vom Betriebssystem definierten Farben im Modus „Hoher Kontrast“ für die <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType>-Eigenschaft.
HINWEIS: In Windows 10 wurden die Werte für einige Systemfarben mit hohem Kontrast geändert. Das Windows Forms-Framework basiert auf dem Win32-Framework. Die besten Ergebnisse erhalten Sie, wenn Sie die aktuelle Version von Windows ausführen und die neuesten Änderungen am Betriebssystem aktivieren, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus folgendem Code entfernen:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Verbesserte Unterstützung für die Sprachausgabe**

- Die Sprachausgabe kündigt jetzt den Wert der <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType>-Eigenschaft an, wenn Sie den Text eines <xref:System.Windows.Forms.ToolStripMenuItem> ankündigt.
- Die Sprachausgabe gibt jetzt an, wenn die <xref:System.Windows.Forms.Control.Enabled>-Eigenschaftensatz eines <xref:System.Windows.Forms.ToolStripMenuItem> auf `false` festgelegt ist.
- Die Sprachausgabe stellt jetzt Feedback zum Zustand eines Kontrollkästchens bereit, wenn die <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt ist.
- Die Fokusreihenfolge des Scanmodus der Sprachausgabe ist jetzt mit der visuellen Reihenfolge der Steuerelemente für das ClickOnce-Downloaddialogfenster konsistent.

**Verbesserte Unterstützung der DataGridView-Barrierefreiheit**

- Zeilen in einer <xref:System.Windows.Forms.DataGridView> können jetzt mithilfe der Tastatur sortiert werden. Ein Benutzer kann jetzt die F3-TASTE verwenden, um anhand der aktuellen Spalte zu sortieren.
- Wenn der <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> festgelegt ist, ändert sich die Farbe der Spaltenüberschrift, um die aktuelle Spalte anzugeben, wenn der Benutzer mit der TABULATORTASTE die Zellen in der aktuellen Zeile durchläuft.
- Die <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType>-Eigenschaft gibt jetzt das richtige übergeordnete Steuerelement zurück.

**Verbesserte visuelle Hinweise**

- Die <xref:System.Windows.Forms.RadioButton>- und <xref:System.Windows.Forms.CheckBox>-Steuerelemente mit einer leeren <xref:System.Windows.Forms.ButtonBase.Text>-Eigenschaft zeigen nun einen Fokusindikator an, wenn sie den Fokus erhalten.

**Verbesserte Unterstützung für das Eigenschaftenraster**

- Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben jetzt nur dann `true` für die <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element aktiviert ist.
- Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben jetzt nur dann `false` für die <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element vom Benutzer geändert werden kann.
Einen Überblick über die Benutzeroberflächenautomatisierung finden Sie unter [Benutzeroberflächenautomatisierung: Übersicht](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</p>**Verbesserte Tastaturnavigation**

- <xref:System.Windows.Forms.ToolStripButton> lässt nun den Fokus zu, wenn das Element in einem <xref:System.Windows.Forms.ToolStripPanel> enthalten ist, für das die <xref:System.Windows.Forms.ToolStripPanel.TabStop>-Eigenschaft auf `true` festgelegt ist.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Hauptversion       |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |
