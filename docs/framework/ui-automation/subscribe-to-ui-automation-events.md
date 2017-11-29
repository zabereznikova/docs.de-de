---
title: "Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 39275c38e4a7d28248b46f1116990c5bbe21a15f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="subscribe-to-ui-automation-events"></a>Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie Sie Ereignisse abonnieren, die von Benutzeroberflächenautomatisierungs-Anbietern ausgelöst werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispielcode wird für das Ereignis, das durch Aufrufen eines Steuerelements (z. B. einer Schaltfläche) ausgelöst wird, ein Ereignishandler registriert, und dieser wird wieder entfernt, wenn das Anwendungsformular geschlossen wird. Das Ereignis wird durch identifiziert eine <xref:System.Windows.Automation.AutomationEvent> als Parameter an übergeben <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Abonnieren eines Ereignisses, das ausgelöst wird, wenn der Fokus geändert. Die Registrierung des Ereignishandlers wird in einer Methode aufgehoben, die aufgerufen werden kann, wenn die Anwendung heruntergefahren oder die Benachrichtigung über Benutzeroberflächenereignisse nicht mehr benötigt wird.  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Ereignisse](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
