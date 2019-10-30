---
title: Konfigurations Element Windows Forms hinzufügen
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
ms.openlocfilehash: 26b806f84c3e1bc44e0437a8f8806316b14897b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109660"
---
# <a name="windows-forms-add-configuration-element"></a>Konfigurations Element Windows Forms hinzufügen

Das `<add>` Element fügt einen vordefinierten Schlüssel hinzu, der angibt, ob Ihre Windows Forms-App Features unterstützt, die Windows Forms apps in der .NET Framework 4,7 oder höher hinzugefügt werden.

## <a name="syntax"></a>Syntax

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

| Attribut | Beschreibung |
| --------- | ----------- |
| `key`     | Erforderliches Attribut. Ein vordefinierter Schlüssel Name, der einer bestimmten Windows Forms anpassbaren Funktion entspricht. |
| `value`   | Erforderliches Attribut. Der Wert, der `key`zugewiesen werden soll. |

### <a name="key-attribute-names-and-associated-values"></a>`key` von Attributnamen und zugeordneten Werten

| `key`-Name | Werte | Beschreibung |
| ---------- | ------ | ----------- |
| "Anchorlayout. disablesinglepasscontrolscaling" | "true"&#124;"false" | Gibt an, ob verankerte Steuerelemente in einem einzelnen Durchlauf skaliert werden. "true", um die Skalierung einzelner Pass zu deaktivieren; andernfalls false. Weitere Informationen finden Sie im Abschnitt "Einzel Durchlauf-Skalierung" [in den Hinweisen](#remarks) . |
| "Dpiawareness" | "PerMonitorV2"&#124;"false" | Gibt an, ob eine Anwendung dpi-fähig ist. Legen Sie den Schlüssel auf "PerMonitorV2" fest, um dpi-Informationen zu unterstützen. andernfalls legen Sie diese Einstellung auf "false" fest. DPI-Informationen sind eine Opt-in-Funktion. Legen Sie den Wert auf "PerMonitorV2" fest, um Windows Forms "hohe dpi-Unterstützung zu nutzen. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". |
| "CheckedListBox. disablehighdpiverbesserungen" | "true"&#124;"false" | Gibt an, ob das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement die in der .NET Framework 4,7 eingeführten Skalierungs-und Layoutverbesserungen nutzt. "true", um die Skalierungs-und Layoutverbesserungen zu abonnieren; andernfalls "false". |
| "DataGridView. disablehighdpiverbesserungen" | "true"&#124;"false" | Gibt an, ob die Skalierungs-und Layoutverbesserungen des <xref:System.Windows.Forms.DataGridView>-Steuer Elements im .NET Framework 4,7 eingeführt wurden "true", um das dpi-Bewusstsein zu abonnieren. andernfalls "false". |
| "Disabledpichangedmessagehandling" | "true"&#124;"false" | "true", um den Empfang von Nachrichten im Zusammenhang mit dpi-Skalierungs Änderungen zu beenden; andernfalls "false". Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". |
| "Enablewindowsformshighdpiautoresialisierung" | "true"&#124;"false" | Gibt an, ob die Größe einer Windows Forms Anwendung aufgrund von dpi-Skalierungs Änderungen automatisch geändert wird. "true", um die automatische Größe der Größe zu aktivieren; andernfalls false. |
| "Form. disablesinglepasscontrolscaling" | "true"&#124;"false" | Gibt an, ob die <xref:System.Windows.Forms.Form> in einem einzelnen Durchlauf skaliert wird. "true", um die Skalierung mit einem Durchlauf zu deaktivieren; andernfalls false. Weitere Informationen finden Sie im Abschnitt "Einzel Durchlauf-Skalierung" [in den Hinweisen](#remarks) . |
| "MonthCalendar. disablesinglepasscontrolscaling" | "true"&#124;"false" | Gibt an, ob das <xref:System.Windows.Forms.MonthCalendar> Steuerelement in einem einzelnen Durchlauf skaliert wird. "true", um die Skalierung mit einem Durchlauf zu deaktivieren; andernfalls false. Weitere Informationen finden Sie im Abschnitt "Einzel Durchlauf-Skalierung" [in den Hinweisen](#remarks) . |
| "ToolStrip. disablehighdpiverbesserungen" | "true"&#124;"false" | Gibt an, ob das <xref:System.Windows.Forms.ToolStrip>-Steuerelement die in der .NET Framework 4,7 eingeführten Skalierungs-und Layoutverbesserungen nutzt. "true", um das dpi-Bewusstsein zu abonnieren. andernfalls "false". |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](index.md) | Konfiguriert die Unterstützung für neue Windows Forms Anwendungs Features. |

## <a name="remarks"></a>Hinweise

Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.

Das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element ermöglicht es Ihnen, ein oder mehrere untergeordnete `<add>` Elemente hinzuzufügen, von denen jede eine bestimmte Konfigurationseinstellung definiert.

Eine Übersicht über Windows Forms hohe dpi-Unterstützung finden Sie unter [Unterstützung für hohe dpi-Unterstützung in Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>Dpiawareness

Windows Forms apps, die unter Windows-Versionen gestartet werden, beginnend mit Windows 10 Creators Edition und Ziel Versionen des .NET Framework, beginnend mit dem .NET Framework 4,7, können so konfiguriert werden, dass Sie die Vorteile von hohen dpi-Verbesserungen in der .NET Framework 4,7. Dazu gehören:

- Unterstützung für dynamische dpi-Szenarien, in denen der Benutzer den dpi-oder Skalierungsfaktor ändert, nachdem eine Windows Forms Anwendung gestartet wurde.

- Verbesserungen an der Skalierung und dem Layout mehrerer Windows Forms Steuerelemente, wie z. b. das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement und das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement.

Ein hohes dpi-Bewusstsein ist eine Opt-in-Funktion. Standardmäßig ist der Wert von `DpiAwareness` `false`. Sie können Windows Forms "Unterstützung für die dpi-Bekanntheit wählen, indem Sie den Wert dieses Schlüssels auf `PerMonitorV2` in der Anwendungs Konfigurationsdatei festlegen. Wenn die dpi-Informationen aktiviert sind, sind alle einzelnen dpi-Funktionen ebenfalls aktiviert. Dazu gehören:

- Geänderte dpi-Nachrichten, die vom `DisableDpiChangedMessageHandling` Schlüssel gesteuert werden.

- Dynamische dpi-Unterstützung, die vom `EnableWindowsFormsHighDpiAutoResizing`-Schlüssel gesteuert wird.

- Skalierung von Einzelpass-Steuerelementen, die von der `Form.DisableSinglePassControlScaling` für einzelne <xref:System.Windows.Forms.Form> Steuerelemente, durch den `AnchorLayout.DisableSinglePassControlScaling` Schlüssel für verankerte Steuerelemente und durch den `MonthCalendar.DisableSinglePassControlScaling` Schlüssel für das <xref:System.Windows.Forms.MonthCalendar> Steuerelement gesteuert wird.

- Hohe dpi-Skalierungs-und Layoutverbesserungen, die durch den `CheckListBox.DisableHighDpiImprovements`-Schlüssel für das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement gesteuert werden, durch den `DataGridView.DisableHighDpiImprovements` Schlüssel für das <xref:System.Windows.Forms.DataGridView> Steuerelement und durch den `Toolstrip.DisableHighDpiImprovements` Schlüssel für das <xref:System.Windows.Forms.ToolStrip> Steuerelement.

Die einmalige Standardeinstellung, die durch Festlegen von `DpiAwareness` auf `PerMonitorV2` bereitgestellt wird, ist im Allgemeinen für neue Windows Forms Anwendungen ausreichend. Sie können jedoch die einzelnen hohen dpi-Verbesserungen ablehnen, indem Sie den entsprechenden Schlüssel zur Anwendungs Konfigurationsdatei hinzufügen. Wenn Sie z. b. alle neuen dpi-Features außer dynamischer dpi-Unterstützung nutzen möchten, fügen Sie der Anwendungs Konfigurationsdatei Folgendes hinzu:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

In der Regel entscheiden Sie sich für eine bestimmte Funktion, da Sie Sie zur programmgesteuerten Verarbeitung ausgewählt haben.

Weitere Informationen zur Nutzung der hohen dpi-Unterstützung in Windows Forms-Anwendungen finden Sie unter [hohe dpi-Unterstützung in Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>Disabledpichangedmessagehandling

Beginnend mit dem .NET Framework 4,7 werden Windows Forms Steuerelemente eine Reihe von Ereignissen im Zusammenhang mit Änderungen in der DPI-Skalierung aufkommen. Hierzu gehören die Ereignisse <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>und <xref:System.Windows.Forms.Form.DpiChanged>. Der Wert des `DisableDpiChangedMessageHandling` Schlüssels bestimmt, ob diese Ereignisse in einer Windows Forms Anwendung ausgelöst werden.

### <a name="single-pass-scaling"></a>Skalierung mit einem Durchlauf

Die Skalierung mit einem oder mehreren Durchlauf wirkt sich auf die wahrgenommene Reaktionsfähigkeit der Benutzeroberfläche und die visuelle Darstellung von Elementen der Benutzeroberfläche aus, wenn Sie skaliert werden. Beginnend mit dem .NET Framework 4,7 verwendet Windows Forms die Skalierung mit einem einzelnen Durchlauf. In früheren Versionen der .NET Framework wurde die Skalierung über mehrere Durchgänge durchgeführt, was dazu führte, dass einige Steuerelemente mehr als notwendig skaliert wurden. Die Einzel Durchlauf Skalierung sollte nur deaktiviert werden, wenn Ihre APP vom alten Verhalten abhängig ist.

## <a name="see-also"></a>Siehe auch

- [Windows Forms Configuration Section (Konfigurationsabschnitt für Windows Forms)](index.md)
- [High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)](../../../winforms/high-dpi-support-in-windows-forms.md)
