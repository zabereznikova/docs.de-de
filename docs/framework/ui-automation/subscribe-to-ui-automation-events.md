---
title: Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen
description: Siehe abonnieren von Ereignissen, die von Benutzeroberflächenautomatisierungs-Anbietern ausgelöst werden. Der Beispielcode registriert einen Ereignishandler für das-Ereignis, das ausgelöst wird, wenn ein-Steuerelement aufgerufen wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
ms.openlocfilehash: 9005139be69621e83efc592721a238c28ea1f6e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252315"
---
# <a name="subscribe-to-ui-automation-events"></a>Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie Sie Ereignisse abonnieren, die von Benutzeroberflächenautomatisierungs-Anbietern ausgelöst werden.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispielcode wird für das Ereignis, das durch Aufrufen eines Steuerelements (z. B. einer Schaltfläche) ausgelöst wird, ein Ereignishandler registriert, und dieser wird wieder entfernt, wenn das Anwendungsformular geschlossen wird. Das Ereignis wird durch ein <xref:System.Windows.Automation.AutomationEvent>-Objekt identifiziert, das als Parameter an <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A> übergeben wird.  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verwendet wird, um ein Ereignis zu abonnieren, das bei einer Änderung des Fokus ausgelöst wird. Die Registrierung des Ereignishandlers wird in einer Methode aufgehoben, die aufgerufen werden kann, wenn die Anwendung heruntergefahren oder die Benachrichtigung über Benutzeroberflächenereignisse nicht mehr benötigt wird.  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse](ui-automation-events-overview.md)
