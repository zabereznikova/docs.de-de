---
title: "Benutzeroberflächenautomatisierungs-Ereignisse für Clients"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
caps.latest.revision: "32"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 30aac15a4394a8008e2c1f89dce76dd134acf7b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-events-for-clients"></a>Benutzeroberflächenautomatisierungs-Ereignisse für Clients
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird beschrieben, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Ereignisse von Benutzeroberflächenautomatisierungs-Clients verwendet werden.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ermöglicht es Clients, um relevante Ereignisse zu abonnieren. Diese Funktion verbessert die Leistung durch den Wegfall ständig Abfragen der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente im System zu überprüfen, ob alle Informationen, die Struktur oder den Status geändert hat.  
  
 Die Effizienz wird auch durch die Möglichkeit verbessert, Ereignissen nur innerhalb eines definierten Umfangs zu lauschen. Beispielsweise kann ein Client für Fokusänderungsereignisse alle Lauschen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elemente in der Struktur oder nur einem Element und seine Nachfolger.  
  
> [!NOTE]
>  Sollte nicht davon ausgegangen, dass alle möglichen Ereignisse, indem ausgelöst werden eine [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Anbieter. Nicht alle eigenschaftenänderungen würde z. B. bei Ereignissen, die von den standardproxyanbietern für ausgelöst werden [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente.  
  
 Für eine ausführlichere Übersicht über [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignissen finden Sie unter [Übersicht über die Benutzeroberflächenautomatisierungs-Ereignisse](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Clientanwendungen abonnieren Ereignisse einer bestimmten Art, indem sie einen Ereignishandler mit einer der folgenden Methoden registrieren.  
  
|Methode|Ereignistyp|Typ der Ereignisargumente|Delegattyp|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Fokusänderung|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Eigenschaftenänderung|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Strukturänderung|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Alle anderen Ereignisse, identifiziert durch eine<xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> oder <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Vor dem Aufrufen der Methode müssen Sie eine Delegatmethode erstellen, mit der das Ereignis verarbeitet wird. Wenn Sie dies bevorzugen, können Sie verschiedene Arten von Ereignissen in einer einzelnen Methode verarbeiten und diese Methode in mehreren Aufrufen an eine der Methoden in der Tabelle übergeben. Beispielsweise ein einzelnes <xref:System.Windows.Automation.AutomationEventHandler> können zum Behandeln von verschiedenen Ereignissen unterschiedlich nach Einrichten der <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Um Ereignisse für Schließen eines Fensters zu verarbeiten, wandeln Sie den Argumenttyp, der den Ereignishandler übergeben wird <xref:System.Windows.Automation.WindowClosedEventArgs>. Da die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Element für das Fenster nicht mehr gültig ist, können Sie verwenden die `sender` Parameter zum Abrufen von Informationen; verwenden Sie <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> stattdessen.  
  
> [!CAUTION]
>  Wenn Ihre Anwendung möglicherweise Ereignisse von seiner eigenen empfängt [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], verwenden Sie der Anwendungsverzeichnis nicht [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Thread zum Abonnieren von Ereignissen und Kündigen des Abonnements. Eine solche Vorgehensweise kann zu unvorhersehbarem Verhalten führen. Weitere Informationen finden Sie unter [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 Beim Herunterfahren oder wenn [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ereignisse sind nicht mehr für die Anwendung von Interesse, Benutzeroberflächenautomatisierungs-Clients sollten rufen Sie eine der folgenden Methoden.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Hebt die Registrierung auf einen Ereignishandler, der registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Hebt die Registrierung auf einen Ereignishandler, der registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Hebt die Registrierung auf einen Ereignishandler, der registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Hebt die Registrierung aller registrierten Ereignishandler auf.|  
  
 Beispielcode hierzu finden Sie unter [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [TrackFocus-Beispiel](http://msdn.microsoft.com/en-us/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
