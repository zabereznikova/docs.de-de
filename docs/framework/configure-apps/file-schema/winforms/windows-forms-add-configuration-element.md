---
title: Windows Forms hinzufügen Konfigurationselement
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 107de172e523758474bafb3b86a2960b926a010a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371371"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms hinzufügen Konfigurationselement

Die `<add>` -Element fügt einen vordefinierten Schlüssel, der angibt, ob Ihre Windows-Formular-app mit Features in Windows Forms-apps, die in .NET Framework 4.7 oder höher unterstützt.

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
| `key`     | Erforderliches Attribut. Ein vordefinierter Schlüsselname, der eine bestimmte Funktion von Windows Forms anpassbare entspricht. |
| `value`   | Erforderliches Attribut. Der zuzuweisende Wert `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` Attributnamen und zugehörigen Werte

| `key` Name | Werte | Beschreibung |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true"&#124;"false" | Gibt an, ob der verankerten Steuerelemente in einem einzelnen Durchlauf skaliert werden. "true", um einzelne deaktivieren übergeben Skalierung; andernfalls "false". Finden Sie im Abschnitt "Einzelne pass Skalierung" in der ["Hinweise"](#Remarks) für Weitere Informationen. |
| "DpiAwareness" | "PerMonitorV2"&#124;"false" | Gibt an, ob eine Anwendung DPI kompatibel ist. Legen Sie den Schlüssel auf "PerMonitorV2" zur Unterstützung der Dpi-Unterstützung; Legen Sie sie andernfalls auf "False". DPI-Unterstützung ist ein optionales Feature. um Windows Forms-Unterstützung für hohe DPI-Werte nutzen zu können, sollten Sie seinen Wert in "PerMonitorV2" festlegen. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. |
| "CheckedListBox.DisableHighDpiImprovements" | "true"&#124;"false" | Gibt an, ob die <xref:System.Windows.Forms.CheckedListBox> Control nutzt die Vorteile der skalieren und layouthinweise Verbesserungen in .NET Framework 4.7 eingeführt wurden. "true" zum Deaktivieren der Verbesserungen bei der Caling und Layout; andernfalls "False". |
| "DataGridView.DisableHighDpiImprovements" | "true"&#124;"false" | Gibt an, ob die <xref:System.Windows.Forms.DataGridView> steuern, skalieren und layouthinweise Verbesserungen in .NET Framework 4.7 eingeführt wurden. "true" zum Deaktivieren der DPI-Unterstützung; "false" andernfalls. |
| "DisableDpiChangedMessageHandling" | "true"&#124;"false" | "true" zum Empfang von Nachrichten, die im Zusammenhang mit der DPI-Skalierung Änderungen; "false" andernfalls. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true"&#124;"false" | Gibt an, ob es sich bei eine Windows Forms-Anwendung aufgrund von Änderungen der DPI-Skalierung automatisch angepasst wird. "true" aktiviert automatische Größenänderung. andernfalls "false". |
| "Form.DisableSinglePassControlScaling" | "true"&#124;"false" | Gibt an, ob die <xref:System.Windows.Forms.Form> in einem einzelnen Durchlauf skaliert wird. So deaktivieren Sie "true" Single-Pass Skalierung; andernfalls "false". Finden Sie im Abschnitt "Einzelne pass Skalierung" in der ["Hinweise"](#Remarks) für Weitere Informationen. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true"&#124;"false" | Gibt an, ob die <xref:System.Windows.Forms.MonthCalendar> Steuerelement in einem einzelnen Durchlauf skaliert wird. So deaktivieren Sie "true" Single-Pass Skalierung; andernfalls "false". Finden Sie im Abschnitt "Einzelne pass Skalierung" in der ["Hinweise"](#Remarks) für Weitere Informationen. |
| "Toolstrip.DisableHighDpiImprovements" | "true"&#124;"false" | Gibt an, ob die <xref:System.Windows.Forms.ToolStrip> Control nutzt die Vorteile der skalieren und layouthinweise Verbesserungen in .NET Framework 4.7 eingeführt wurden. "true" zum Deaktivieren der DPI-Unterstützung; "false" andernfalls. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Konfiguriert die Unterstützung für neue Features von Windows Forms-Anwendung. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> "Hinweise"

Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden.

Die `<System.Windows.Forms.ApplicationConfigurationSection>` -Element können Sie einen oder mehrere untergeordnete hinzufügen `<add>` Elemente, von denen jede eine bestimmte Konfigurationseinstellung definiert.

Eine Übersicht über Windows Forms-High-DPI-Unterstützung, finden Sie unter [hohe DPI-Unterstützung in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Windows Forms-apps, die unter Windows-Versionen ab Windows 10 Creators-Edition und die Zielversion von .NET Framework ab .NET Framework 4.7 ausgeführt werden können so konfiguriert werden, um hohe DPI-Verbesserungen eingeführt, die in .NET Framework nutzen 4.7. Dazu gehören:

- Unterstützung für dynamische DPI-Szenarien, in denen der Benutzer den Faktor für die DPI-Einstellung oder Skalierung geändert wird, nachdem eine Windows Forms-Anwendung gestartet wurde.

- Verbesserungen bei der die Skalierung und das Layout einer Reihe von Windows Forms-Steuerelemente, z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement und die <xref:System.Windows.Forms.CheckedListBox> Steuerelement.

Hohe DPI-Unterstützung ist ein optionales Feature. Standardmäßig wird der Wert des `DpiAwareness` ist `false`. Sie können festlegen, Windows Forms-Unterstützung für die DPI-Unterstützung durch Festlegen des Werts dieses Schlüssels auf `PerMonitorV2` in der Konfigurationsdatei der Anwendung. Wenn DPI-Unterstützung aktiviert ist, werden auch alle einzelnen DPI-Features aktiviert. Dazu gehören:

- DPI-Wert geändert, Nachrichten, die von kontrolliert werden die `DisableDpiChangedMessageHandling` Schlüssel.

- Dynamische DPI-Unterstützung, dazu die `EnableWindowsFormsHighDpiAutoResizing` Schlüssel.

- Einzelne durchlaufende Steuerelement zu skalieren, die über gesteuert der `Form.DisableSinglePassControlScaling` für einzelne <xref:System.Windows.Forms.Form> gesteuert wird, indem die `AnchorLayout.DisableSinglePassControlScaling` Schlüssel für die verankerten Steuerelemente und durch die `MonthCalendar.DisableSinglePassControlScaling` Schlüssel für die <xref:System.Windows.Forms.MonthCalendar> Steuerelement

- Hohe DPI-Wert skalieren und layouthinweise Verbesserungen, die von gesteuert wird die `CheckListBox.DisableHighDpiImprovements` Schlüssel für die <xref:System.Windows.Forms.CheckedListBox> zu steuern, indem die `DataGridView.DisableHighDpiImprovements` Schlüssel für die <xref:System.Windows.Forms.DataGridView> -Steuerelement, und durch die `Toolstrip.DisableHighDpiImprovements` Schlüssel für die <xref:System.Windows.Forms.ToolStrip> Steuerelement.

Die einzelnen teilnehmen Standardeinstellung durch Festlegen von bereitgestellten `DpiAwareness` zu `PerMonitorV2` ist für neue Windows Forms-Anwendungen in der Regel ausreichend. Jedoch können Sie dann einzelne hohe DPI-Verbesserungen ablehnen, indem der Anwendungskonfigurationsdatei den entsprechenden Schlüssel hinzugefügt. Um alle neuen DPI-Features mit Ausnahme der Unterstützung für dynamische DPI-Werte nutzen zu können, würden Sie z. B. Folgendes in Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
In der Regel, deaktivieren Sie eine bestimmte Funktion, da Sie ausgewählt haben, um programmgesteuert zu verarbeiten.

Weitere Informationen zu profitieren, hohe DPI-Unterstützung in Windows Forms-Anwendungen, finden Sie unter [hohe DPI-Unterstützung in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

Ab .NET Framework 4.7, lösen Windows Forms-Steuerelemente eine Anzahl von Ereignissen im Zusammenhang mit Änderungen an der DPI-Skalierung. Dazu gehören die <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, und <xref:System.Windows.Forms.Form.DpiChanged> Ereignisse. Der Wert des der `DisableDpiChangedMessageHandling` Schlüssel bestimmt, ob diese Ereignisse in Windows Forms-Anwendungen ausgelöst werden.

### <a name="single-pass-scaling"></a>Single-Pass-Skalierung

Skalieren von einzelnen oder mehreren Pass beeinflusst die wahrgenommene Reaktionsfähigkeit der Benutzeroberfläche und die visuelle Darstellung der Elemente der Benutzeroberfläche, wie sie skaliert werden. Ab .NET Framework 4.7, verwendet Windows Forms die einzelnen Durchlauf zu skalieren. In früheren Versionen von .NET Framework Skalierung über mehrere Durchläufe, erfolgt die verursacht einige Steuerelemente skaliert werden, mehr als notwendig war. Skalierung der einzelnen Durchläufen sollte nur deaktiviert werden, wenn Ihre app das alte Verhalten abhängig ist.

## <a name="see-also"></a>Siehe auch

- [Windows Forms Configuration Section (Konfigurationsabschnitt für Windows Forms)](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)
- [High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
