---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den Schaltflächen-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Button
- UI Automation, Button control type
- Button control type
ms.assetid: 057c983a-da83-4c50-86c7-26fe381076a6
ms.openlocfilehash: d9eef575efb5309fe3df20e2f0ab3e0347105e55
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441211"
---
# <a name="ui-automation-support-for-the-button-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den Schaltflächen-Steuerelementtyp
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „Button“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte, Steuerelementmuster und [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse ein.  
  
 Eine Schaltfläche ist ein Objekt, das ein Benutzer dazu verwendet, eine Aktion auszuführen, z. B. die Schaltflächen **OK** und **Abbrechen** in einem Dialogfeld. Das Schaltflächen-Steuerelement ist hinsichtlich des Verfügbarmachens ein einfaches Steuerelement, weil es einem einzelnen Befehl zugeordnet ist, den der Benutzer ausführen möchte.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „Button“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Schaltflächen-Steuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Schaltflächen-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen über die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|Schaltfläche<br /><br /> -Image (0 oder mehr)<br />-Text (0 oder mehr)|Schaltfläche|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften aufgelistet, deren Wert oder Definition für die Steuerelemente besonders relevant ist, die den Button-Steuerelementtyp implementieren (wie z. B. Schaltflächen-Steuerelemente). Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>|Siehe Hinweise.|Das Schaltflächen-Steuerelement muss in der Regel eine Tastenkombination unterstützen, damit ein Endbenutzer die Aktion, der das Steuerelement entspricht, schnell über die Tastatur ausführen kann.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie einen Punkt, auf den geklickt werden kann, außer Kraft und stellen ihn anschließend bereit.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Schaltfläche|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Siehe Hinweise.|Der Hilfetext kann angeben, welches Ergebnis durch Aktivieren der Schaltfläche erreicht wird. Hierbei handelt es sich in der Regel um dieselben Informationen, wie sie über eine QuickInfo angezeigt werden.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Schaltflächen-Steuerelement muss immer ein Inhaltselement sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Schaltflächen-Steuerelement muss immer ein Steuerelement sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Schaltflächen-Steuerelemente werden durch ihren Inhalt selbstbeschriftet.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Schaltfläche“|Lokalisierte Zeichenfolge für den Steuerelementtyp „Button“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Der Name des Schaltflächen-Steuerelements ist der Text, mit dem es beschriftet wird. Wird ein Bild verwendet, um eine Schaltfläche zu beschriften, muss für die Name-Eigenschaft der Schaltfläche ein Alternativtext angegeben werden.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster aufgelistet, die von Schaltflächen-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster|Unterstützungswert|Hinweise|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Siehe Hinweise.|Alle Schaltflächen müssen das Invoke-Steuerelementmuster oder das Toggle-Steuerelementmuster unterstützen. Invoke wird unterstützt, wenn die Schaltfläche auf Anforderung des Benutzers einen Befehl ausführt. Dieser Befehl ist einem einzelnen Vorgang zugeordnet, etwa Ausschneiden, Kopieren, Einfügen oder Löschen.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Siehe Hinweise.|Alle Schaltflächen müssen das Invoke-Steuerelementmuster oder das Toggle-Steuerelementmuster unterstützen. Toggle wird unterstützt, wenn die Schaltfläche eine Reihe von maximal drei Zuständen durchlaufen kann. In der Regel ist dies als Ein-/Ausschalter für bestimmte Features zu sehen.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Siehe Hinweise.|Wird eine Schaltfläche als untergeordnete Schaltfläche einer unterteilten Schaltfläche gehostet, kann die untergeordnete Schaltfläche anstelle des Invoke- oder Toggle-Musters das ExpandCollapse-Muster unterstützen. Das ExpandCollapse-Muster kann zum Öffnen oder Schließen eines Menüs oder einer anderen Unterstruktur verwendet werden, die dem Schaltflächenelement zugeordnet ist.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 In der folgenden Tabelle sind die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse aufgeführt, die von allen Schaltflächen-Steuerelementen unterstützt werden müssen. Weitere Informationen zu [UI Automation Events Overview](ui-automation-events-overview.md)-Ereignissen finden Sie unter  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützungswert|Hinweise|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Variabel|Wenn das Steuerelement das Invoke-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Wenn das Steuerelement das Toggle-Steuerelementmuster unterstützt, muss es dieses Ereignis unterstützen.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.Button>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
