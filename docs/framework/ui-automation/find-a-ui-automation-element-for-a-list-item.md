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
ms.openlocfilehash: 63181de26f7d8efda99d5b5d71b006cde44823a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433549"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="0f957-102">Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement</span><span class="sxs-lookup"><span data-stu-id="0f957-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="0f957-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0f957-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0f957-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="0f957-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="0f957-105">In diesem Thema wird gezeigt, wie ein <xref:System.Windows.Automation.AutomationElement> für ein Element in einer Liste abgerufen wird, wenn der Index des Elements bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="0f957-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f957-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f957-106">Example</span></span>  
 <span data-ttu-id="0f957-107">Das folgende Beispiel zeigt zwei Möglichkeiten, ein angegebenes Element aus einer Liste abzurufen, wobei ein Element <xref:System.Windows.Automation.TreeWalker> und das andere mithilfe <xref:System.Windows.Automation.AutomationElement.FindAll%2A>verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f957-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="0f957-108">Das erste Verfahren ist tendenziell für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]-Steuerelemente schneller, aber das zweite ist schneller für Windows Presentation Foundation (WPF)-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0f957-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="0f957-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f957-109">See also</span></span>

- [<span data-ttu-id="0f957-110">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="0f957-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
