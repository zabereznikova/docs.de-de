---
title: "Threadingprobleme bei der Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, threading issues
- threading issues with UI Automation
ms.assetid: 0ab8d42c-5b8b-481b-b788-2caecc2f0191
caps.latest.revision: "9"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: a1eaed2a7876c6e6981e7cc4172442b19800586b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-threading-issues"></a><span data-ttu-id="33a87-102">Threadingprobleme bei der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="33a87-102">UI Automation Threading Issues</span></span>
> [!NOTE]
>  <span data-ttu-id="33a87-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="33a87-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="33a87-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="33a87-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="33a87-105">Aufgrund der Art und Weise, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Windows-Meldungen verwendet, können Konflikte auftreten, wenn eine Clientanwendung versucht, mit der eigenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] über den [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="33a87-105">Because of the way [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] uses Windows messages, conflicts can occur when a client application attempts to interact with its own [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] on the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] thread.</span></span> <span data-ttu-id="33a87-106">Diese Konflikte können dazu führen, dass die Leistung erheblich beeinträchtigt wird, oder sogar dazu, dass die Anwendung gar nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="33a87-106">These conflicts can lead to very slow performance or even cause the application to stop responding.</span></span>  
  
 <span data-ttu-id="33a87-107">Wenn die Clientanwendung mit allen Elementen auf dem Desktop interagieren soll, einschließlich der eigenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], sollten alle Aufrufe von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] in einem getrennten Thread ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33a87-107">If your client application is intended to interact with all elements on the desktop, including its own [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], you should make all [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] calls on a separate thread.</span></span> <span data-ttu-id="33a87-108">Dies schließt das Suchen von Elementen (z. B. durch Verwenden der <xref:System.Windows.Automation.TreeWalker> -Methode oder der <xref:System.Windows.Automation.AutomationElement.FindAll%2A> -Methode) sowie die Verwendung von Steuerelementmustern ein.</span><span class="sxs-lookup"><span data-stu-id="33a87-108">This includes locating elements (for example, by using <xref:System.Windows.Automation.TreeWalker> or the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method) and using control patterns.</span></span>  
  
 <span data-ttu-id="33a87-109">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Aufrufe können problemlos innerhalb eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignishandlers ausgeführt werden, da der Ereignishandler stets in einem anderen als dem[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="33a87-109">It is safe to make [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] calls within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event handler, because the event handler is always called on a non-[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] thread.</span></span> <span data-ttu-id="33a87-110">Beim Abonnieren von Ereignissen, die aus der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]der Clientanwendung stammen können, muss der Aufruf von <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>bzw. einer verwandten Methode jedoch in einem anderen als dem[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Thread ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="33a87-110">However, when subscribing to events that may originate from your client application's [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], you must make the call to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>, or a related method, on a non-[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] thread.</span></span> <span data-ttu-id="33a87-111">Entfernen Sie Ereignishandler im gleichen Thread.</span><span class="sxs-lookup"><span data-stu-id="33a87-111">Remove event handlers on the same thread.</span></span>
