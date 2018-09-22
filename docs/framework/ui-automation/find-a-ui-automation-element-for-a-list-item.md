---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b569b43d83e8a7f1b0fa82b79bc1fc40977b72ba
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576930"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="82582-102">Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement</span><span class="sxs-lookup"><span data-stu-id="82582-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
>  <span data-ttu-id="82582-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="82582-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="82582-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="82582-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="82582-105">In diesem Thema wird gezeigt, wie zum Abrufen einer <xref:System.Windows.Automation.AutomationElement> für ein Element in einer Liste, wenn der Index des Elements unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="82582-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82582-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82582-106">Example</span></span>  
 <span data-ttu-id="82582-107">Das folgende Beispiel zeigt zwei Möglichkeiten zum Abrufen eines angegebenen Elements aus einer Liste mit <xref:System.Windows.Automation.TreeWalker> und der andere mit <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="82582-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="82582-108">Das erste Verfahren ist meist schneller für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente, aber die zweite ist für Windows Presentation Foundation (WPF)-Steuerelemente schneller.</span><span class="sxs-lookup"><span data-stu-id="82582-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="82582-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82582-109">See Also</span></span>  
 [<span data-ttu-id="82582-110">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="82582-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
