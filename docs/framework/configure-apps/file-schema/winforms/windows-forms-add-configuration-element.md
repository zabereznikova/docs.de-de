---
title: "Windows Forms hinzufügen Konfigurationselement"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 828a28769e164535d4dde989ef8cce91caf9cb48
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2017
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms hinzufügen Konfigurationselement

Die `<add>` -Element fügt einen vordefinierten Schlüssel, der angibt, ob Ihre Windows Forms-Anwendung Funktionen hinzugefügt, um Windows Forms-apps in der .NET Framework-4.7 oder höher unterstützt.

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
| `key`     | Erforderliches Attribut. Ein vordefinierter Schlüsselname, der eine bestimmte anpassbare Windows Forms-Funktion entspricht. |
| `value`   | Erforderliches Attribut. Der zuzuweisende Wert `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key`Attributnamen und zugehörigen Werte

| `key`-Name | Werte | Beschreibung |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true" &#124;" "false"" | Gibt an, ob es sich bei gebundenen Steuerelementen in einem Durchgang skaliert werden. "true", um einzelne deaktivieren übergeben Skalierung. andernfalls "false". Finden Sie im Abschnitt "Single übergeben Skalierung" in der ["Hinweise"](#Remarks) für Weitere Informationen. |
| "DpiAwareness" | "PerMonitorV2" &#124;" "false"" | Gibt an, ob eine Anwendung DPI-fähig ist. Legen Sie den Schlüssel auf "PerMonitorV2" zur Unterstützung der Dpi-Ausführung; Legen Sie sie andernfalls auf "False". DPI-Ausführung ist eine opt-in-Funktion. um Windows Forms Unterstützung für hohe DPI nutzen zu können, sollten Sie dessen Wert auf "PerMonitorV2" festlegen. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. |
| "CheckedListBox.DisableHighDpiImprovements" | "true" &#124;" "false"" | Gibt an, ob die <xref:System.Windows.Forms.CheckedListBox> Steuerelement nutzt die Skalierung und das Layout Verbesserungen, die in der .NET Framework-4.7 eingeführt. "true" Caling und Layout Verbesserungen Betaphase; andernfalls "False". |
| "DataGridView.DisableHighDpiImprovements" | "true" &#124;" "false"" | Gibt an, ob die <xref:System.Windows.Forms.DataGridView> steuern, Skalierung und das Layout Verbesserungen, die in der .NET Framework-4.7 eingeführt. "true" DPI-Ausführung Betaphase; "false" andernfalls. |
| "DisableDpiChangedMessageHandling" | "true" &#124;" "false"" | "true" zum Empfangen von Nachrichten, die im Zusammenhang mit der DPI-Skalierung Änderungen abwählen; "false" andernfalls. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true" &#124;" "false"" | Gibt an, ob eine Windows Forms-Anwendung aufgrund von Änderungen der DPI-Skalierung automatisch angepasst wird. "true" zum Aktivieren der automatischen Größenänderung; andernfalls "false". |
| "Form.DisableSinglePassControlScaling" | "true" &#124;" "false"" | Gibt an, ob die <xref:System.Windows.Forms.Form> in einem Durchgang skaliert wird. So deaktivieren Sie "Wahr" einzelnen Durchläufen Skalierung; andernfalls "false". Finden Sie im Abschnitt "Single übergeben Skalierung" in der ["Hinweise"](#Remarks) für Weitere Informationen. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true" &#124;" "false"" | Gibt an, ob die <xref:System.Windows.Forms.MonthCalendar> in einem Durchgang Steuerelement skaliert wird. So deaktivieren Sie "Wahr" einzelnen Durchläufen Skalierung; andernfalls "false". Finden Sie im Abschnitt "Single übergeben Skalierung" in der ["Hinweise"](#Remarks) für Weitere Informationen. |
| "Toolstrip.DisableHighDpiImprovements" | "true" &#124;" "false"" | Gibt an, ob die <xref:System.Windows.Forms.ToolStrip> Steuerelement nutzt die Skalierung und das Layout Verbesserungen, die in der .NET Framework-4.7 eingeführt. "true" DPI-Ausführung Betaphase; "false" andernfalls. |

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Konfiguriert die Unterstützung für die neuen Funktionen von Windows Forms-Anwendung. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" />"Hinweise"

Ab .NET Framework 4.7 ermöglicht das `<System.Windows.Forms.ApplicationConfigurationSection>`-Element die Konfiguration von Windows Forms-Anwendungen für die Nutzung von Funktionen, die in neueren Versionen von .NET Framework hinzugefügt werden. 

Die `<System.Windows.Forms.ApplicationConfigurationSection>` Element können Sie eine oder mehrere untergeordnete hinzuzufügende `<add>` Elemente, von denen jede eine bestimmte Konfigurationseinstellung definiert.  

Einen Überblick über die Unterstützung von Windows Forms hohen dpi-WERTEN finden Sie unter [hoher DPI-Unterstützung in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Windows Forms-apps, die unter Windows-Versionen ab Windows 10-Ersteller-Edition und die auf Versionen von .NET Framework ausgeführt werden beginnend mit der .NET Framework-4.7 können konfiguriert werden, um hohe DPI-Verbesserungen eingeführt, die in .NET Framework nutzen 4.7. Dazu gehören:

- Unterstützung für dynamische DPI-Szenarien, in denen der Benutzer eine Faktor für die DPI-Wert oder der Dezimalstellen ändert, nachdem Windows Forms-Anwendung gestartet wurde.

- Verbesserungen bei der die Skalierung und das Layout einer Reihe von Windows Forms-Steuerelemente, z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement und dem <xref:System.Windows.Forms.CheckedListBox> Steuerelement. 

Hohe DPI-Ausführung ist eine opt-in-Funktion. Standardmäßig wird der Wert der `DpiAwareness` ist `false`. Wahlweise können Sie in Windows Forms Unterstützung für DPI-Ausführung durch Festlegen des Werts dieses Schlüssels auf `PerMonitorV2` in der Anwendungskonfigurationsdatei. Wenn DPI-Ausführung aktiviert ist, werden auch alle einzelnen DPI-Features aktiviert. Dazu gehören:

- DPI-Wert geändert, Nachrichten, die von kontrolliert werden die `DisableDpiChangedMessageHandling` Schlüssel.

- Dynamische DPI-Unterstützung, die mithilfe der `EnableWindowsFormsHighDpiAutoResizing` Schlüssel.

- Einzelnen Durchläufen Steuerelement zu skalieren, wird durch gesteuert der `Form.DisableSinglePassControlScaling` für einzelne <xref:System.Windows.Forms.Form> Steuerelemente, die von der `AnchorLayout.DisableSinglePassControlScaling` Schlüssel für die gebundenen Steuerelementen und durch die `MonthCalendar.DisableSinglePassControlScaling` Schlüssel für die <xref:System.Windows.Forms.MonthCalendar> Steuerelement 

- Hohe DPI-Skalierung und Layout Verbesserungen, die von gesteuert wird der `CheckListBox.DisableHighDpiImprovements` Schlüssel für die <xref:System.Windows.Forms.CheckedListBox> steuern, indem die `DataGridView.DisableHighDpiImprovements` Schlüssel für die <xref:System.Windows.Forms.DataGridView> -Steuerelement, und die `Toolstrip.DisableHighDpiImprovements` Schlüssel für die <xref:System.Windows.Forms.ToolStrip> Steuerelement.  

Die einzelnen teilnehmen Standardeinstellung gebotenen festlegen `DpiAwareness` zu `PerMonitorV2` ist im allgemeinen ausreichend, für neue Windows Forms-Anwendungen. Allerdings können Sie dann einzelne hoher DPI-Verbesserungen abzuwählen durch Hinzufügen der entsprechenden Schlüssels in der Anwendungskonfigurationsdatei. Um alle neuen DPI Featuers mit Ausnahme der dynamischen DPI-Unterstützung nutzen zu können, würden Sie z. B. Folgendes in der Anwendungskonfigurationsdatei hinzufügen:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
In der Regel abwählen Sie eine bestimmte Funktion, da Sie ausgewählt haben, dass er programmgesteuert zu verarbeiten.

Weitere Informationen zum Nutzen der hohen DPI-Unterstützung in Windows Forms-Anwendungen, finden Sie unter [hoher DPI-Unterstützung in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

Beginnend mit der .NET Framework-4.7, löst Windows Forms-Steuerelemente eine Anzahl von Ereignissen im Zusammenhang mit der Änderungen in DPI-Skalierung. Dazu gehören die <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, und <xref:System.Windows.Forms.Form.DpiChanged> Ereignisse. Der Wert, der die `DisableDpiChangedMessageHandling` Schlüssel bestimmt, ob diese Ereignisse in einer Windows Forms-Anwendung ausgelöst werden. 

### <a name="single-pass-scaling"></a>Single-Pass-Skalierung

Einzelne "oder" mit mehreren Pass Skalierung wirkt sich auf die wahrgenommene Reaktionsfähigkeit der Benutzeroberfläche und die visuelle Darstellung von Benutzeroberflächenelementen wie sie skaliert werden. Beginnend mit der .NET Framework-4.7, verwendet Windows Forms Durchgang zu skalieren. In früheren Versionen von .NET Framework wurde Skalierung über mehrere Durchläufe ausgeführt verursacht einige Steuerelemente skaliert werden mehr als notwendig war. Skalierung der einzelnen Durchläufen sollte nur deaktiviert werden, wenn Ihre app auf dem alten Verhalten abhängig ist.  

## <a name="see-also"></a>Siehe auch
 
[Abschnitt "Windows Forms-Konfiguration"](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[High DPI Support in Windows Forms (Unterstützung für hohe DPI-Werte in Windows Forms)](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
