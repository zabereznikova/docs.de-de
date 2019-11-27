---
title: Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- UI Automation, events
- clients, UI Automation
- events, UI Automation
- providers, UI Automation
- UI Automation, clients
ms.assetid: 69eebd8b-39ed-40e7-93cc-4457c4caf746
ms.openlocfilehash: 5f9362814eb671a6d7a111cadb96be6d06f5cb3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441495"
---
# <a name="ui-automation-events-overview"></a>Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Die[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Ereignisbenachrichtigung ist ein wesentliches Feature für Hilfstechnologien wie Sprachausgabe und Bildschirmlupe. Diese Benutzeroberflächenautomatisierungs-Clients überwachen Ereignisse, die von den Benutzeroberflächenautomatisierungs-Anbietern ausgelöst werden, wenn etwas auf der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] passiert, und verwenden diese Informationen dann, um Endbenutzer zu benachrichtigen.  
  
 Die Effizienz wird dadurch erhöht, dass Anbieteranwendungen Ereignisse selektiv (abhängig davon, ob Clients für diese Ereignisse abonniert sind) oder gar nicht auslösen dürfen (wenn kein Client auf Ereignisse wartet).  
  
<a name="Types_of_Events"></a>   
## <a name="types-of-events"></a>Ereignistypen  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse werden in die folgenden Kategorien eingeteilt:  
  
|Ereignis|Beschreibung|  
|-----------|-----------------|  
|Eigenschaftenänderung|Wird ausgelöst, wenn sich eine Eigenschaft eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elements oder -Steuerelementmusters ändert. Wenn ein Client beispielsweise das Kontrollkästchen-Steuerelement einer Anwendung überwachen muss, kann er sich mithilfe der <xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> -Eigenschaft registrieren, um auf ein Eigenschaftenänderungsereignis zu warten. Wenn das Kontrollkästchen-Steuerelement aktiviert oder deaktiviert wird, löst der Anbieter das Ereignis aus, und der Client kann entsprechend reagieren.|  
|Elementaktion|Wird ausgelöst, wenn eine Änderung in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] durch einen Endbenutzer oder eine programmgesteuerte Aktivität erfolgt, beispielsweise, wenn auf eine Schaltfläche geklickt oder diese durch <xref:System.Windows.Automation.InvokePattern>aktiviert wird.|  
|Strukturänderung|Wird ausgelöst, wenn sich die Struktur der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur ändert. Die Struktur ändert sich, wenn neue [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente auf dem Desktop eingeblendet, ausgeblendet oder entfernt werden.|  
|Globale Desktopänderung|Wird ausgelöst, wenn Aktionen auftreten, die für den Client von allgemeinem Interesse sind, z. B., wenn der Fokus von einem Element zum anderen wechselt oder ein Fenster geschlossen wird.|  
  
 Einige Ereignisse bedeuten nicht zwangsläufig, dass sich der Zustand der Benutzeroberfläche geändert hat. Wenn der Benutzer zum Beispiel mit der Tabulatortaste zu einem Texteingabefeld wechselt und dann auf eine Schaltfläche klickt, um das Feld zu aktualisieren, wird ein `TextChangedEvent` ausgelöst, auch wenn der Benutzer den Text nicht geändert hat. Bei der Verarbeitung eines Ereignisses muss eine Clientanwendung möglicherweise erst überprüfen, ob sich tatsächlich etwas geändert hat, bevor eine Aktion ausgeführt wird.  
  
 Die folgenden Ereignisse können auch dann ausgelöst werden, wenn sich der Zustand der Benutzeroberfläche nicht geändert hat.  
  
- `AutomationPropertyChangedEvent` (abhängig von der Eigenschaft, die sich geändert hat)  
  
- `ElementSelectedEvent`  
  
- `InvalidatedEvent`  
  
- `TextChangedEvent`  
  
<a name="UI_Automation_Event_Identifiers"></a>   
## <a name="ui-automation-event-identifiers"></a>Bezeichner für Benutzeroberlächen-Automatisierungsereignisse  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Ereignisse werden mit <xref:System.Windows.Automation.AutomationEvent> -Objekten gekennzeichnet. Die <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> -Eigenschaft enthält einen Wert, der die Ereignisart eindeutig bezeichnet.  
  
 Die möglichen Werte für <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> sind in der folgenden Tabelle zusammen mit dem für die Ereignisargumente verwendeten Typ aufgeführt. Beachten Sie, dass es sich bei den von Clients und Anbietern verwendeten Bezeichnern um Felder mit identischen Namen aus verschiedenen Klassen handelt.  
  
|Clientkennung|Anbieterbezeichner|Typ der Ereignisargumente|  
|-----------------------|-------------------------|--------------------------|  
|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|  
|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionPattern.InvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.InvokePattern.InvokedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.LayoutInvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPattern.TextChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPattern.TextSelectionChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipClosedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.AutomationElementIdentifiers.ToolTipOpenedEvent?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.AutomationPropertyChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationPropertyChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.StructureChangedEventArgs>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent?displayProperty=nameWithType>|<xref:System.Windows.Automation.WindowClosedEventArgs>|  
  
<a name="UI_Automation_Event_Arguments"></a>   
## <a name="ui-automation-event-arguments"></a>Argumente für Benutzeroberlächen-Automatisierungsereignisse  
 Die folgenden Klassen kapseln Ereignisargumente.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Automation.AsyncContentLoadedEventArgs>|Enthält Informationen zum asynchronen Laden von Inhalt, einschließlich des bereits abgeschlossenen Ladevorgangs in Prozent.|  
|<xref:System.Windows.Automation.AutomationEventArgs>|Enthält Informationen über ein einfaches Ereignis, das keine zusätzlichen Daten erfordert.|  
|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|Enthält Informationen zur Änderung des Eingabefokus von einem Element zu einem anderen. Ereignisse dieses Typs werden durch das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -System ausgelöst, nicht durch Anbieter.|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|Enthält Informationen zur Änderung eines Eigenschaftswerts eines Elements oder Steuerelementmusters.|  
|<xref:System.Windows.Automation.StructureChangedEventArgs>|Enthält Informationen zu einer Änderung in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur.|  
|<xref:System.Windows.Automation.WindowClosedEventArgs>|Enthält Informationen zum Schließen eines Fensters.|  
  
 Alle Ereignisargumentklassen enthalten einen <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A> -Member. Dieser Bezeichner wird in einem <xref:System.Windows.Automation.AutomationEvent>gekapselt.  
  
 Die zur Identifizierung von Ereignissen verwendeten <xref:System.Windows.Automation.AutomationEvent> -Objekte werden durch Anbieter aus Feldern in <xref:System.Windows.Automation.AutomationElementIdentifiers> und Klassen für Steuerelementmuster-Bezeichner, wie beispielsweise <xref:System.Windows.Automation.DockPatternIdentifiers>, abgerufen. Von Clientanwendungen werden die entsprechenden Felder aus Feldern in <xref:System.Windows.Automation.AutomationElement> und Steuerelementmusterklassen, wie z. B. <xref:System.Windows.Automation.DockPattern>, abgerufen.  
  
 Eine Liste der Ereignisbezeichner finden Sie unter [UI Automation Events for Clients](ui-automation-events-for-clients.md).  
  
## <a name="see-also"></a>Siehe auch

- [UI Automation Events for Clients](ui-automation-events-for-clients.md)
- [Server-Side UI Automation Provider Implementation](server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
- [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](subscribe-to-ui-automation-events.md)
