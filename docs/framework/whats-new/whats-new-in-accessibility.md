---
title: Neuerungen der Barrierefreiheit in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: 4243599f44749e7b38ebe78ca88b8ec2a9390650
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249720"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Neuerungen der Barrierefreiheit in .NET Framework

Die Anwendungen von .NET Framework sollen eine bessere Barrierefreiheit für Ihre Benutzer bieten. Durch Barrierefreiheitsfunktionen wird es einer Anwendung ermöglicht, den Benutzern von Hilfstechnologien ein angemessenes Erlebnis zu bieten. Ab .NET Framework 4.7.1 enthält .NET Framework zahlreiche Verbesserungen der Barrierefreiheit, die es den Entwicklern ermöglichen, barrierefreie Anwendungen zu erstellen.

## <a name="accessibility-switches"></a>Barrierefreiheitsparameter

Wenn Ihre App auf .NET Framework 4.7 oder niedriger ausgerichtet ist, aber auf .NET Framework 4.7.1 oder höher ausgeführt wird, können Sie sie für Barrierefreiheitsfeatures konfigurieren. Sie können auch Ihre App für Legacy-Features konfigurieren (und Barrierefreiheitsfeatures außen vor lassen), wenn diese auf .NET Framework 4.7.1 oder höher ausgerichtet ist. Jede .NET Framework-Version, die Barrierefreiheitsfeatures umfasst, verfügt über einen versionsspezifischen Barrierefreiheitsparameter, den Sie dem [`<runtime>`](../configure-apps/file-schema/runtime/index.md)-Abschnitt des [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Elements in der Konfigurationsdatei der Anwendung hinzufügen. Die folgenden Parameter werden unterstützt:

|Version|Schalter|
|---|---|
|.NET Framework 4.7.1|„Switch.UseLegacyAccessibilityFeatures“|
|.NET Framework 4.7.2|„Switch.UseLegacyAccessibilityFeatures.2“|
|.NET Framework 4.8|"Switch.UseLegacyAccessibilityFeatures.3"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Profitieren von Barrierefreiheitserweiterungen

Die neuen Barrierefreiheitsfunktionen werden standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen. Zusätzlich können Anwendungen, die eine frühere Version von .NET Framework anzielen, aber unter .NET Framework 4.7.1 oder höher ausgeführt werden, veraltete Verhaltensweisen für die Barrierefreiheit deaktivieren (und dadurch die Verbesserungen der Barrierefreiheit nutzen), indem Sie dem [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](../configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung einen Parameter hinzufügen und deren Wert auf `false` festlegen. Das folgende Beispiel zeigt, wie Sie die in .NET Framework 4.7.1 eingeführten Barrierefreiheitsverbesserungen aktivieren:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Wenn Sie die Barrierefreiheitsoptionen in einer höheren Version von .NET Framework aktivieren, müssen Sie ebenfalls die Features früherer Versionen aktivieren. Sie benötigen das folgende [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element, um Ihre App so zu konfigurieren, dass Sie die Verbesserungen der Barrierefreiheit sowohl in .NET Framework 4.7.1 als auch in Version 4.7.2 nutzen können:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

Sie benötigen das folgende [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element, um Ihre App so zu konfigurieren, dass Sie die Verbesserungen der Barrierefreiheit in NET Framework 4.7.1, 4.7.2 und 4.8 nutzen können:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Wiederherstellen von Legacyverhalten

Anwendungen, die Versionen von .NET Framework ab 4.7.1 anzielen, können die Barrierefreiheitsfeatures deaktivieren, indem folgendes Element zum [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](../configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und deren Wert auf `true` festgelegt wird. Beispielsweise deaktiviert die folgende Konfiguration die Barrierefreiheitsfeatures, die in .NET Framework 4.7.2 eingeführt wurden:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a>Neuerungen der Barrierefreiheit in .NET Framework 4.8

.NET Framework 4.8 enthält neue Barrierefreiheitsfunktionen für die folgenden Bereiche:

- [Windows Forms](#winforms48)

- [Windows Presentation Foundation (WPF)](#wpf48)

- [Workflow-Designer von Windows Workflow Foundation (WF)](#wf48)

<a name="winforms48" />

### <a name="windows-forms"></a>Windows Forms

In .NET Framework 4.8 bieten Windows Forms jetzt Unterstützung für LiveRegions und Benachrichtigungsereignisse für viele häufig verwendete Steuerelemente. Es bietet auch Unterstützung für QuickInfos, wenn ein Benutzer mit der Tastatur zu einem Steuerelement navigiert.

**Unterstützung für UIA-LiveRegions in den Bezeichnungen und StatusStrips**

UIA LiveRegions ermöglichen es Anwendungsentwicklern, Sprachausgaben über eine Textänderung in einem Steuerelement zu informieren, das sich außerhalb des Bereichs befindet, in dem der Benutzer arbeitet. Dies ist z.B. für ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement nützlich, das einen Verbindungsstatus anzeigt. Wenn die Verbindung unterbrochen wird und sich der Status ändert, kann der Entwickler die Sprachausgabe benachrichtigen.

Ab .NET Framework 4.8 implementiert Windows Forms UIA-LiveRegions für sowohl <xref:System.Windows.Forms.Label>- als auch <xref:System.Windows.Forms.StatusStrip>-Steuerelemente. Der folgende Code verwendet die LiveRegion beispielsweise in einem <xref:System.Windows.Forms.Label>-Steuerelement mit dem Namen `label1`:

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

Die Sprachausgabe kündigt „Bereit“ an, unabhängig davon, wo der Benutzer mit der Anwendung gerade interagiert.

Sie können Ihr <xref:System.Windows.Forms.UserControl> ebenfalls als LiveRegion implementieren:

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

**UIA-Benachrichtigungsereignisse**

Das UIA-Benachrichtigungsereignis, das mit dem Windows 10 Fall Creators Update eingeführt wurde, ermöglicht es Ihrer App, ein UIA-Ereignis auszulösen, was dazu führt, dass die Sprachausgabe einfach eine Ankündigung basierend auf dem Text macht, den Sie mit dem Ereignis bereitstellen. Dafür muss in der Benutzeroberfläche kein entsprechendes Steuerelement vorhanden sein. In einigen Szenarien ist dies eine einfache Möglichkeit, um die Barrierefreiheit Ihrer App erheblich zu verbessern. Auch kann damit über den Fortschritt eines Prozesses zu informiert werden, der viel Zeit in Anspruch nehmen kann. Weitere Informationen über UIA-Benachrichtigungsereignisse finden Sie in [Can your desktop app leverage the new UI Notification event?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need) (Kann Ihre Desktop-App das neue UI-Benachrichtigungsereignis nutzen?).

Im folgenden Beispiel wird ein [Benachrichtigungsereignis](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A) ausgelöst:

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

**QuickInfos für den Tastaturzugriff**

In Anwendungen, die auf .NET Framework 4.7.2 und frühere Versionen abzielen, kann ein Steuerelement [tooltip](xref:System.Windows.Forms.ToolTip) nur durch Bewegen eines Mauszeigers in das Steuerelement angezeigt werden. Ab .NET Framework 4.8 kann ein Tastaturbenutzer die QuickInfo eines Steuerelements aufrufen, indem er das Steuerelement mit einer Tabulatortaste oder Pfeiltasten mit oder ohne Zusatztasten fokussiert. Für diese Verbesserungen der Barrierefreiheit ist ein zusätzlicher [AppContext-Schalter](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) erforderlich:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

Die folgende Abbildung zeigt die QuickInfo, wenn der Benutzer eine Schaltfläche mit der Tastatur ausgewählt hat.

![Screenshot der QuickInfo, wenn Benutzer mit der Tastatur zur Schaltfläche navigiert.](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

Ab .NET Framework 4.8 enthält WPF eine Reihe von Verbesserungen der Barrierefreiheit.

**Die Sprachausgabe kündigt keine Elemente mit der Sichtbarkeit „Collapsed“ oder „Hidden“ mehr an**

Elemente mit der Sichtbarkeit „Collapsed“ oder „Hidden“ werden von der Sprachausgabe nicht mehr angekündigt. Benutzeroberflächen, die Elemente mit einer Sichtbarkeit <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> oder <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> enthalten, können durch die Sprachausgabe falsch interpretiert werden, wenn sie dem Benutzer angekündigt werden. Ab .NET Framework 4.8 enthält WPF keine komprimierten oder ausgeblendeten Elemente mehr in der Steuerelementansicht der UIAutomation-Struktur, sodass die Sprachausgabe diese Elemente nicht mehr ankündigen kann.

**SelectionTextBrush-Eigenschaft für die Verwendung mit einer nicht Adorner-basierten Textauswahl**

In .NET Framework 4.7.2.2 hat WPF die Möglichkeit hinzugefügt, eine <xref:System.Windows.Controls.TextBox>- und <xref:System.Windows.Controls.PasswordBox>-Textauswahl zu zeichnen, ohne die Adornerebene zu verwenden. Die Vordergrundfarbe des markierten Texts in diesem Szenario wurde von <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType> vorgegeben.

.NET Framework 4.8 fügt eine neue Eigenschaft, `SelectionTextBrush`, hinzu, die es Entwicklern ermöglicht, den spezifischen Pinsel für den ausgewählten Text auszuwählen, wenn sie eine nicht Adorner-basierte Textauswahl verwenden. Diese Eigenschaft funktioniert nur bei <xref:System.Windows.Controls.Primitives.TextBoxBase>-basierten Steuerelementen und dem <xref:System.Windows.Controls.PasswordBox>-Steuerelement in WPF-Anwendungen, bei denen die nicht auf Adorner basierende Textauswahl aktiviert ist. Sie funktioniert nicht für das <xref:System.Windows.Controls.RichTextBox>-Steuerelement. Wenn die nicht auf Adorner basierende Textauswahl nicht aktiviert ist, wird diese Eigenschaft ignoriert.

Um diese Eigenschaft zu verwenden, fügen Sie sie einfach zu Ihrem XAML-Code hinzu, und verwenden Sie den entsprechenden Pinsel oder die passende Bindung. Die sich daraus ergebende Textauswahl sieht folgendermaßen aus:

![Screenshot der ausgeführten App mit den ausgewählten Wörtern „Hello World“.](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

Sie können die Verwendung der Eigenschaften `SelectionBrush` und `SelectionTextBrush` kombinieren, um jede beliebige Hintergrund- und Vordergrundfarbkombination zu generieren, die Sie für zweckmäßig halten.

**Unterstützung für die UIAutomation ControllerFor-Eigenschaft**

Die `ControllerFor`-Eigenschaft von UIAutomation gibt ein Array von Automatisierungselementen zurück, die von dem Automatisierungselement geändert werden, das diese Eigenschaft unterstützt. Diese Eigenschaft wird häufig bei der Vorschlagsuche verwendet. `ControllerFor` wird verwendet, wenn ein Automatisierungselement ein oder mehrere Segmente der Benutzeroberfläche der Anwendung oder des Desktops beeinflusst. Andernfalls ist es schwierig, die Auswirkungen des Steuerelementvorgangs den Elementen der Benutzeroberfläche zuzuordnen. Dieses Feature fügt die Möglichkeit hinzu, dass Steuerelemente einen Wert für die `ControllerFor`-Eigenschaft bereitstellen.

.NET Framework 4.8 fügt eine neue virtuelle Methode hinzu: <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>. Auf einen Wert für die `ControllerFor` Eigenschaft einfach diese Methode überschreiben und Zurückgeben einer `List<AutomationPeer>` für die Steuerelemente, die von diesem bearbeiteten <xref:System.Windows.Automation.Peers.AutomationPeer>:

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

**QuickInfos für den Tastaturzugriff**

In .NET Framework 4.7.2 und früheren Versionen werden QuickInfos nur angezeigt, wenn der Benutzer den Mauszeiger über ein Steuerelement bewegt. In .NET Framework 4.8 werden QuickInfos auch beim Fokussieren mit der Tastatur sowie über eine Tastenkombination angezeigt.

Um dieses Feature zu aktivieren, muss eine Anwendung .NET Framework 4.8 als Ziel verwenden oder sich mit den `Switch.UseLegacyAccessibilityFeatures.3`- und `Switch.UseLegacyToolTipDisplay`-[AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Optionen anmelden. Nachfolgend finden Sie die Konfigurationsdatei für eine Beispielanwendung:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

Nach der Aktivierung zeigen alle Steuerelemente, die eine QuickInfo enthalten, diese an, sobald die Tastatur auf das Steuerelement fokussiert. Die QuickInfo kann im Laufe der Zeit oder bei einer Änderung des Tastaturfokus deaktiviert werden. Benutzer können die QuickInfo auch manuell verwerfen, indem sie eine neue Tastenkombination verwenden, STRG + UMSCHALT + F10. Wenn die QuickInfo verworfen wurde, kann sie mithilfe der gleichen Tastenkombination wieder angezeigt werden.

> [!NOTE]
> [Menüband-QuickInfos](xref:System.Windows.Controls.Ribbon.RibbonToolTip) auf <xref:System.Windows.Controls.Ribbon.Ribbon>-Steuerelementen werden nicht beim Tastaturfokus angezeigt, sondern nur über die Tastenkombination.

**Unterstützung für SizeOfSet- und PositionInSet-UIAutomation-Eigenschaften hinzugefügt**

Windows 10 hat zwei neue UIAutomation-Eigenschaften eingeführt, `SizeOfSet` und `PositionInSet`, die von Anwendungen verwendet werden, um die Anzahl der Elemente in einem Satz zu beschreiben. UIAutomation-Clientanwendungen wie die Sprachausgabe können dann eine Anwendung hinsichtlich dieser Eigenschaften abfragen und eine genaue Darstellung der Benutzeroberfläche der Anwendung ankündigen.

Ab .NET Framework 4.8 stellt WPF diese beiden Eigenschaften für UIAutomation in WPF-Anwendungen bereit. Dafür stehen zwei Methoden zur Verfügung:

- Verwenden von Abhängigkeitseigenschaften

  WPF fügt zwei neue Abhängigkeitseigenschaften, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> und <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>, hinzu. Ein Entwickler kann diese Werte mit XAML festlegen:

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- Überschreiben von virtuellen AutomationPeer-Methoden

  Die AutomationPeer-Klasse wurde mit den virtuellen Methoden <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> erweitert. Ein Entwickler kann diese Werte für `SizeOfSet` und `PositionInSet` durch Überschreiben dieser Methode bereitstellen, wie im folgenden Beispiel gezeigt:

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

Darüber hinaus stellen Elemente in <xref:System.Windows.Controls.ItemsControl>-Instanzen automatisch einen Wert für diese Eigenschaften ohne zusätzliche Maßnahmen des Entwicklers bereit. Wenn ein <xref:System.Windows.Controls.ItemsControl> gruppiert ist, wird die Sammlung von Gruppen als Satz dargestellt, und jede Gruppe wird als separater Satz gezählt. Dabei gibt jedes Element innerhalb dieser Gruppe seine Position innerhalb dieser Gruppe sowie die Größe der Gruppe an. Automatische Werte werden durch Virtualisierung nicht beeinflusst. Selbst wenn ein Element nicht realisiert wird, wird es dennoch auf die Gesamtgröße des Satzes angerechnet und beeinflusst die Position im Satz seiner gleichgeordneten Elemente.

Automatische Werte werden nur bereitgestellt, wenn die Anwendung auf .NET Framework 4.8 abzielt. Für Anwendungen, die auf eine frühere Version von .NET-Frameworks abzielen, können Sie die `Switch.UseLegacyAccessibilityFeatures.3`-[AppContext-Option](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) einrichten, wie in der folgenden App.config-Datei gezeigt:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48" />

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Workflow-Designer von Windows Workflow Foundation (WF)

Der Workflow-Designer umfasst in .NET Framework 4.8 folgende Änderungen:

- Benutzer, die die Sprachausgabe verwenden, werden Verbesserungen bei FlowSwitch-case-Bezeichnungen feststellen.

- Benutzer, die die Sprachausgabe verwenden, werden Verbesserungen bei Schaltflächenbeschreibungen feststellen.

- Benutzer, die Designs mit hohem Kontrast verwenden, werden Verbesserungen in der Sichtbarkeit des Workflow-Designers und dessen Steuerelementen feststellen. Dazu zählen verbesserte Kontrastverhältnisse zwischen Elementen und leichter erkennbare Auswahlfelder für Fokuselemente.

Wenn Ihre Anwendung auf .NET Framework 4.7.2 oder eine frühere Version abzielt, können Sie diese Änderungen übernehmen, indem Sie die `Switch.UseLegacyAccessibilityFeatures.3`-[AppContext-Option](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in Ihrer Anwendungskonfigurationsdatei auf `false` festlegen. Weitere Informationen finden Sie im Abschnitt [Profitieren von Barrierefreiheitsverbesserungen](#taking-advantage-of-accessibility-enhancements) in diesem Artikel.

## <a name="whats-new-in-accessibility-in-net-framework-472"></a>Neuerungen der Barrierefreiheit in .NET Framework 4.7.2

.NET Framework 4.7.2 enthält neue Barrierefreiheitsfunktionen für die folgenden Bereiche:

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

## <a name="whats-new-in-accessibility-in-net-framework-471"></a>Neuerungen der Barrierefreiheit in .NET Framework 4.7.1

.NET Framework 4.7.1 enthält neue Barrierefreiheitsfunktionen für die folgenden Bereiche:

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

  ![Screenshot des Expander-Steuerelements mit Fokus und ohne visuelles Fokuselement.](./media/whats-new-in-accessibility/expander-control-before.png)

  Nachher:

  ![Screenshot des Expander-Steuerelements, bei dem der Fokus eine gepunktete Linie um den Text des Steuerelements zeigt.](./media/whats-new-in-accessibility/expander-control-after.png)

- <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente

  Der Text in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen ist nun leichter zu erkennen, wenn das Design mit hohem Kontrast ausgewählt ist. Zum Beispiel:

  Vorher:

  ![Screenshot der Optionsschaltflächen und der Kontrollkästchen mit schlechter Lesbarkeit des Texts bei Designs mit hohem Kontrast.](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  Nachher:

  ![Screenshot der Optionsschaltflächen und der Kontrollkästchen mit besserer Lesbarkeit des Texts bei Designs mit hohem Kontrast.](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox>-Steuerelement

  Ab .NET Framework 4.7.1 hat der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Steuerelements die gleiche Farbe wie der deaktivierte Text. Zum Beispiel:

  Vorher:

  ![Screenshot einer deaktivierten ComboBox, bei der Rahmen und Steuerelementtext unterschiedliche Farben aufweisen.](./media/whats-new-in-accessibility/combo-disabled-before.png)

  Nachher:

  ![Screenshot einer deaktivierten ComboBox, bei der Rahmen und Steuerelementtext dieselbe Farbe aufweisen.](./media/whats-new-in-accessibility/combo-disabled-after.png)

  Darüber hinaus verwenden deaktivierte Schaltflächen und Schaltflächen mit Fokus das richtige Farbdesign.

  Vorher:

  ![Screenshot einer schwarzen Schaltfläche mit grauem Text „Focus Me“.](./media/whats-new-in-accessibility/button-theme-colors-before.png)

  Nachher:

  ![Screenshot einer blauen Schaltfläche mit schwarzem Text „Focus Me“.](./media/whats-new-in-accessibility/button-theme-colors-after.png)

  In .NET Framework 4.7 und früher führte das Festlegen des Formats eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf `Toolbar.ComboBoxStyleKey` dazu, dass der Dropdownpfeil nicht angezeigt wurde. Dieses Problem wurde in .NET Framework 4.7.1 behoben. Zum Beispiel:

  Vorher:

  ![Screenshot eines ComboBox-Steuerelements mit nicht sichtbarem Dropdownpfeil.](./media/whats-new-in-accessibility/combo-box-style-key-before.png)

  Nachher:

  ![Screenshot eines ComboBox-Steuerelements mit sichtbarem Dropdownpfeil.](./media/whats-new-in-accessibility/combo-box-style-key-after.png)

- <xref:System.Windows.Controls.DataGrid>-Steuerelement

  Ab .NET Framework 4.7.1 verwendet der Pfeil für die Sortieranzeige in den <xref:System.Windows.Controls.DataGrid>-Steuerelementen das richtige Farbdesign. Zum Beispiel:

  Vorher:

  ![Screenshot des Pfeils für die Sortieranzeige vor der Verbesserung.](./media/whats-new-in-accessibility/sort-indicator-before.png)

  Nachher:

  ![Screenshot des Pfeils für die Sortieranzeige nach der Verbesserung.](./media/whats-new-in-accessibility/sort-indicator-after.png)

  Darüber hinaus wurde in .NET Framework 4.7 und früher das Standarddesign für Links geändert, wodurch Links beim Bewegen der Maus über diese im Modus mit hohem Kontrast in der falschen Farbe angezeigt wurden. Dieses Problem wurde in .NET Framework 4.7.1 behoben. Auf ähnliche Weise verwenden die Spalten des Kontrollkästchens <xref:System.Windows.Controls.DataGrid> ab .NET Framework 4.7.1 die erwarteten Farben für das Feedback des Tastaturfokus.

  Vorher:

  ![Screenshot eines Links mit dem Text „Click Me!“ in Rot.](./media/whats-new-in-accessibility/default-link-style-before.png)

  Nachher:

  ![Screenshot eines Links mit dem Text „Click Me!“ in Gelb.](./media/whats-new-in-accessibility/default-link-style-after.png)

Weitere Informationen zu Verbesserungen der WPF-Barrierefreiheit in .NET Framework 4.7.1 finden Sie unter [Verbesserung der Barrierefreiheit in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a>Verbesserung der Barrierefreiheit von Windows Forms

In .NET Framework 4.7.1 enthält Windows Forms (WinForms) Verbesserungen der Barrierefreiheit für folgende Bereiche:

**Verbesserte Anzeige im Modus mit hohem Kontrast**

Ab .NET Framework 4.7.1 bieten viele WinForms-Steuerelemente ein verbessertes Rendering für die Modi mit hohem Kontrast, die im Betriebssystem verfügbar sind. In Windows 10 wurden die Werte für einige Systemfarbe im Design mit hohem Kontrast geändert, und Windows Forms basiert auf dem Win32-Framework von Windows 10. Führen Sie für die besten Ergebnisse die aktuelle Version von Windows aus, und aktivieren Sie die neuesten Änderungen am Betriebssystem, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus der SupportedOS-Zeile für Windows 10 entfernen, sodass diese folgendermaßen aussieht:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

Folgende Änderungen wurden am Design mit hohem Kontrast vorgenommen:

- Die Kontrollkästchen der <xref:System.Windows.Forms.MenuStrip>-Elemente können einfacher angezeigt werden.

- Wenn diese aktiviert werden, können deaktivierte <xref:System.Windows.Forms.MenuStrip>-Elemente einfacher angezeigt werden.

- Der Text in einem ausgewählten <xref:System.Windows.Forms.Button>-Kontrollkästchen bildet einen Kontrast zur Auswahlfarbe.

- Deaktivierter Text ist einfacher zu lesen. Zum Beispiel:

  Vorher:

  ![Screenshot einer APP, die verschiedene im Modus für hohe Kontraste ausgeführte Steuerelemente verwendet, vor den Verbesserungen für die Barrierefreiheit.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png)

  Nachher:

  ![Screenshot einer APP, die verschiedene im Modus für hohe Kontraste ausgeführte Steuerelemente verwendet, nach den Verbesserungen für die Barrierefreiheit.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png)

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

Ab .NET Framework 4.7.1 und Visual Studio 2017 Version 15.3 arbeiten ASP.NET-Websteuerelemente effizienter mit den Funktionen für die Barrierefreiheit in Visual Studio zusammen. Dazu gehören folgende Änderungen:

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

- [What's new in the .NET Framework (Neuerungen in .NET Framework)](index.md)
