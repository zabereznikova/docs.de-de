---
title: Implementieren des Value-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
ms.openlocfilehash: eb77f26bbe3546a3f90804c3648f8547fb6abad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180092"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a>Implementieren des Value-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IValueProvider>, einschließlich Informationen zu Ereignissen und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.ValuePattern> -Steuerelementmuster wird verwendet, um Steuerelemente zu unterstützen, die einen systeminternen Wert haben, der keinen Bereich umfasst und als Zeichenfolge dargestellt werden kann. Diese Zeichenfolge kann je nach Steuerelement und dessen Einstellungen bearbeitet werden. Beispiele für Steuerelemente, die dieses Muster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Value-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Steuerelemente wie <xref:System.Windows.Automation.ControlType.ListItem> und <xref:System.Windows.Automation.ControlType.TreeItem> müssen, unabhängig vom aktuellen Bearbeitungsmodus des Steuerelements, <xref:System.Windows.Automation.ValuePattern> unterstützen, wenn der Wert irgendeines der Elemente bearbeitet werden kann. Das übergeordnete Steuerelement muss außerdem <xref:System.Windows.Automation.ValuePattern> unterstützen, wenn die untergeordneten Elemente bearbeitbar sind.  
  
 ![Bearbeitbares Listenelement](./media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")  
Beispiel eines bearbeitbaren Listenelements  
  
- Einzeilige Bearbeitungssteuerelemente unterstützen programmgesteuerten Zugriff auf ihren Inhalt, indem <xref:System.Windows.Automation.Provider.IValueProvider>für sie implementiert wird. Für mehrzeilige Bearbeitungssteuerelemente wird <xref:System.Windows.Automation.Provider.IValueProvider>jedoch nicht implementiert. Stattdessen wird Zugriff auf ihre Inhalte geboten, indem <xref:System.Windows.Automation.Provider.ITextProvider>für sie implementiert wird.  
  
- Um den Textinhalt eines mehrzeiligen Bearbeitungssteuerelements abzurufen, muss <xref:System.Windows.Automation.Provider.ITextProvider>für das Steuerelement implementiert sein. <xref:System.Windows.Automation.Provider.ITextProvider> bietet aber nicht die Möglichkeit, den Wert eines Steuerelements festzulegen.  
  
- Mit<xref:System.Windows.Automation.Provider.IValueProvider> ist es nicht möglich, Formatierungsinformationen oder Teilzeichenfolgen abzurufen. Implementieren Sie <xref:System.Windows.Automation.Provider.ITextProvider> in diesen Fällen.  
  
- <xref:System.Windows.Automation.Provider.IValueProvider>muss durch Steuerelemente wie das **Auswahlsteuerelement "Farbauswahl"** von Microsoft Word (siehe unten) implementiert werden, das die Zeichenfolgenzuordnung zwischen einem Farbwert (z. B. "gelb") und einer entsprechenden internen RGB-Struktur unterstützt.  
  
 ![Farbauswahl mit ausgewählter Farbe Gelb.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Beispiel für eine Zuordnung zwischen Farbmustern und Zeichenfolgen  
  
- Für ein Steuerelement sollte dessen <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> auf `true` und dessen <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> auf `false` festgelegt sein, bevor ein Aufruf von <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>zugelassen wird.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-ivalueprovider"></a>Erforderliche Member für IValueProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IValueProvider>erforderlich.  
  
|Erforderliche Member|Memberart|Notizen|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|Eigenschaft|Keine|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|Methode|Keine|  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> - Wenn gebietsschemaspezifische Informationen in einem falschen Format, z. B. einem falsch formatierten Datum, an ein Steuerelement übergeben werden.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> - Wenn ein neuer Wert nicht von einer Zeichenfolge in ein Format konvertiert werden kann, das das Steuerelement erkennt.|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> - Wenn versucht wird, ein Steuerelement zu manipulieren, das nicht aktiviert ist.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [ValuePattern Insert Textbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
