---
title: "Benutzeroberfl&#228;chenautomatisierungs-Ereignisse f&#252;r Clients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI-Automatisierung, Ereignisse für clients"
  - "Ereignisse, Benutzeroberflächen-Automatisierungsclients"
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
caps.latest.revision: 32
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 32
---
# Benutzeroberfl&#228;chenautomatisierungs-Ereignisse f&#252;r Clients
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler, die die verwaltete verwenden möchten vorgesehen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Klassen, die in der <xref:System.Windows.Automation> Namespace. Die neuesten Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows Automation API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird beschrieben, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Ereignisse von Benutzeroberflächenautomatisierungs-Clients verwendet werden.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ermöglicht es Clients, relevante Ereignisse zu abonnieren. Diese Funktion verbessert die Leistung durch den Wegfall ständig Abfragen die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Elemente im System zu überprüfen, ob alle Informationen, Struktur oder ein Zustand geändert hat.  
  
 Die Effizienz wird auch durch die Möglichkeit verbessert, Ereignissen nur innerhalb eines definierten Umfangs zu lauschen. Beispielsweise kann ein Client den Fokus Änderungsereignisse für alle Überwachen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente in der Struktur oder nur ein Element und seine Nachfolger.  
  
> [!NOTE]
>  Gehen Sie nicht, dass alle möglichen Ereignisse, indem ausgelöst werden ein [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Anbieter. Nicht alle Änderungen verursacht z. B. Ereignisse, die ausgelöst wird, durch den Proxy-Anbieter für [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente.  
  
 Eine ausführlichere Übersicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignissen finden Sie unter [Übersicht über die Benutzeroberflächenautomatisierungs-Ereignisse](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Clientanwendungen abonnieren Ereignisse einer bestimmten Art, indem sie einen Ereignishandler mit einer der folgenden Methoden registrieren.  
  
|Methode|Ereignistyp|Typ der Ereignisargumente|Delegattyp|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Fokusänderung|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Eigenschaftenänderung|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Strukturänderung|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Alle anderen Ereignisse, anhand einer <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> oder <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Vor dem Aufrufen der Methode müssen Sie eine Delegatmethode erstellen, mit der das Ereignis verarbeitet wird. Wenn Sie dies bevorzugen, können Sie verschiedene Arten von Ereignissen in einer einzelnen Methode verarbeiten und diese Methode in mehreren Aufrufen an eine der Methoden in der Tabelle übergeben. Z. B. ein einzelnes <xref:System.Windows.Automation.AutomationEventHandler> können zur Verarbeitung verschiedener Ereignisse anders nach Einrichten der <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Zum Schließen eines Fensters Ereignisse zu verarbeiten, wandeln Sie den Argumenttyp, der an den Ereignishandler übergeben wird <xref:System.Windows.Automation.WindowClosedEventArgs>. Da die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Element für das Fenster nicht mehr gültig ist, können Sie verwenden die `sender` Parameter zum Abrufen von Informationen, verwenden Sie <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> stattdessen.  
  
> [!CAUTION]
>  Wenn Ihre Anwendung möglicherweise Ereignisse aus der eigenen empfängt [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], verwenden Sie der Anwendungsverzeichnis nicht [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] Thread Abonnieren von Ereignissen oder Kündigen des Abonnements. Eine solche Vorgehensweise kann zu unvorhersehbarem Verhalten führen. Weitere Informationen finden Sie unter [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 Beim Herunterfahren oder wenn [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ereignisse sind nicht mehr für die Anwendung von Interesse, Benutzeroberflächenautomatisierungs-Clients sollten eine der folgenden Methoden aufrufen.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Hebt die Registrierung eines ereignishandlers, der registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Hebt die Registrierung eines ereignishandlers, der registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Hebt die Registrierung eines ereignishandlers, der registriert wurde <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Hebt die Registrierung aller registrierten Ereignishandler auf.|  
  
 Beispielcode, finden Sie unter [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)   
 [Übersicht über die Benutzeroberflächenautomatisierungs-Ereignisse](../../../docs/framework/ui-automation/ui-automation-events-overview.md)   
 [Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)   
 [TrackFocus Sample](http://msdn.microsoft.com/de-de/4a91c0af-6bb5-4d38-a743-cf136f268fc9)