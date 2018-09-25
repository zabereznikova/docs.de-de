---
title: Benutzeroberflächenautomatisierungs-Ereignisse für Clients
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: fdd192f7ba6273cb4f7927ccb6b34963b3aaea7d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070553"
---
# <a name="ui-automation-events-for-clients"></a>Benutzeroberflächenautomatisierungs-Ereignisse für Clients
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird beschrieben, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Ereignisse, die von Benutzeroberflächenautomatisierungs-Clients verwendet werden.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es Clients Abonnieren von Ereignissen von Interesse sind. Diese Funktion verbessert die Leistung durch den Wegfall ständig Abfragen die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente in das System, um festzustellen, ob alle Informationen, Struktur oder Zustand geändert hat.  
  
 Die Effizienz wird auch durch die Möglichkeit verbessert, Ereignissen nur innerhalb eines definierten Umfangs zu lauschen. Beispielsweise kann ein Client Fokusänderungsereignisse alle Lauschen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente in der Struktur oder auf nur einem Element und seine Nachfolger.  
  
> [!NOTE]
>  Gehen Sie nicht, dass alle möglichen Ereignisse, indem ausgelöst werden eine [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Anbieter. Nicht alle eigenschaftenänderungen verursacht z. B. Ereignisse, die von den standardproxyanbietern für ausgelöst werden [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente.  
  
 Für eine ausführlichere Übersicht über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ereignisse finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Clientanwendungen abonnieren Ereignisse einer bestimmten Art, indem sie einen Ereignishandler mit einer der folgenden Methoden registrieren.  
  
|Methode|Ereignistyp|Typ der Ereignisargumente|Delegattyp|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Fokusänderung|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Eigenschaftenänderung|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Strukturänderung|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Alle anderen Ereignisse, identifiziert durch einen <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> oder <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Vor dem Aufrufen der Methode müssen Sie eine Delegatmethode erstellen, mit der das Ereignis verarbeitet wird. Wenn Sie dies bevorzugen, können Sie verschiedene Arten von Ereignissen in einer einzelnen Methode verarbeiten und diese Methode in mehreren Aufrufen an eine der Methoden in der Tabelle übergeben. Z. B. ein einzelnes <xref:System.Windows.Automation.AutomationEventHandler> können zur Verarbeitung verschiedener Ereignisse anders nach Einrichten der <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Wandeln Sie den Argumenttyp, die an den Ereignishandler übergeben wird, zum Verarbeiten von Ereignissen Schließen eines Fensters <xref:System.Windows.Automation.WindowClosedEventArgs>. Da die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Element für das Fenster nicht mehr gültig ist, können keine der `sender` Parameter zum Abrufen von Informationen; verwenden Sie <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> stattdessen.  
  
> [!CAUTION]
>  Wenn Ihre Anwendung möglicherweise Ereignisse aus ihrer eigenen empfängt [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], verwenden Sie Ihre Anwendungsverzeichnis nicht [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Thread aus, um Ereignisse zu abonnieren oder abbestellen. Eine solche Vorgehensweise kann zu unvorhersehbarem Verhalten führen. Weitere Informationen finden Sie unter [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 Beim Herunterfahren oder wenn [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ereignisse sind nicht mehr für die Anwendung, die Benutzeroberflächenautomatisierungs-Clients sollten eine der folgenden Methoden aufrufen.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Hebt die Registrierung eines ereignishandlers, die mit registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Hebt die Registrierung eines ereignishandlers, die mit registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Hebt die Registrierung eines ereignishandlers, die mit registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Hebt die Registrierung aller registrierten Ereignishandler auf.|  
  
 Beispielcode, finden Sie unter [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [TrackFocus-Beispiel](https://msdn.microsoft.com/library/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
