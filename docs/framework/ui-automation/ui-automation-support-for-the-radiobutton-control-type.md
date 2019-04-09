---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den RadioButton-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Radio Button
- UI Automation, Radio Button control type
- RadioButton control type
ms.assetid: 87170464-7857-41f1-bcf7-bb41be31cb53
ms.openlocfilehash: b437e19b10b534ce1c1dfae8ef0cca083cac2d61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149567"
---
# <a name="ui-automation-support-for-the-radiobutton-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den RadioButton-Steuerelementtyp
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „RadioButton“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Ein Optionsfeld besteht aus einer runden Schaltfläche und anwendungsdefiniertem Text (eine Bezeichnung), einem Symbol oder eine Bitmap, die eine Option anzeigt, die der Benutzer durch Aktivieren der Schaltfläche auswählen kann. Eine Anwendung verwendet in der Regel Optionsfelder in einem Gruppenfeld, um es dem Benutzer zu gestatten, aus einer Gruppe von verwandten, aber sich gegenseitig ausschließenden Optionen auszuwählen. Die Anwendung kann z. B. eine Gruppe von Optionsfeldern darstellen, unter denen der Benutzer eine Formateinstellung für Text auswählen kann, der im Clientbereich markiert ist. Der Benutzer kann ein linksbündiges, rechtsbündiges oder zentriertes Format auswählen, indem er das entsprechende Optionsfeld aktiviert. In der Regel kann der Benutzer jeweils nur eine Option zur Zeit aus einer Gruppe von Optionsfeldern auswählen.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „RadioButton“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Listensteuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für RadioButton-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|RadioButton|RadioButton|  
  
 Es sind keine untergeordneten Elemente in der Steuerelementansicht oder der Inhaltsansicht enthalten.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für den RadioButton-Steuerelementtyp besonders relevant sind. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Der Name des Optionsfeldsteuerelements ist der Text, der neben der Schaltfläche angezeigt wird, die den Auswahlzustand beibehält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Der durch Klicken aktivierbare Punkt des Optionsfeldsteuerelements MUSS ein Punkt sein, der die Auswahl für das Optionsfeld festlegt, wenn mit dem Mauszeiger auf ihn geklickt wird.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Optionsfelder sind selbstbeschriftende Steuerelemente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|RadioButton|Dieser Wert gilt für alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Frameworks.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Optionsfeld“|Lokalisierte Zeichenfolge für den Steuerelementtyp „RadioButton“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Optionsfeldsteuerelement ist in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur immer enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Optionsfeldsteuerelement ist in der Strukturansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur immer enthalten.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster aufgelistet, die von RadioButton-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster/Steuerelementmustereigenschaft|Unterstützung/Wert|Hinweise|  
|-----------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Ja|Alle Optionsfeldsteuerelemente müssen das SelectionItem-Muster unterstützen, um ihre Aktivierung zu ermöglichen.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider.SelectionContainer%2A>|Siehe Hinweise.|Die `SelectionContainerProperty` muss immer abgeschlossen werden, damit ein Benutzeroberflächenautomatisierungs-Client ermitteln kann, welche anderen Optionsfelder sich in einem bestimmten Kontext aufeinander beziehen.  Für die [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Version des Optionsfelds wird diese Eigenschaft nicht unterstützt, da es nicht möglich ist, diese Informationen vom Legacyframework abzurufen.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Nie|Das Optionsfeld kann seinen Zustand nicht durchlaufen, nachdem es festgelegt wurde.  Dieses Muster darf von einem Optionsfeld nie unterstützt werden.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen RadioButton-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event|Unterstützung|Hinweise|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Nie|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> Durch geänderte Eigenschaften ausgelöste Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keiner|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.RadioButton>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
