---
title: Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen
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
ms.openlocfilehash: ba1cfeb24db1a9dde27faf3e08ef908d87eeaaa4
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679234"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="660af-102">Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="660af-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="660af-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="660af-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="660af-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="660af-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="660af-105">In diesem Thema wird gezeigt, wie Sie Ereignisse abonnieren, die von Benutzeroberflächenautomatisierungs-Anbietern ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="660af-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="660af-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="660af-106">Example</span></span>  
 <span data-ttu-id="660af-107">Im folgenden Beispielcode wird für das Ereignis, das durch Aufrufen eines Steuerelements (z. B. einer Schaltfläche) ausgelöst wird, ein Ereignishandler registriert, und dieser wird wieder entfernt, wenn das Anwendungsformular geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="660af-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="660af-108">Das Ereignis wird durch ein <xref:System.Windows.Automation.AutomationEvent>-Objekt identifiziert, das als Parameter an <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A> übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="660af-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="660af-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="660af-109">Example</span></span>  
 <span data-ttu-id="660af-110">Im folgenden Beispiel wird gezeigt, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verwendet wird, um ein Ereignis zu abonnieren, das bei einer Änderung des Fokus ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="660af-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="660af-111">Die Registrierung des Ereignishandlers wird in einer Methode aufgehoben, die aufgerufen werden kann, wenn die Anwendung heruntergefahren oder die Benachrichtigung über Benutzeroberflächenereignisse nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="660af-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="660af-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="660af-112">See also</span></span>
- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="660af-113">Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="660af-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
