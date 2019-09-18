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
ms.openlocfilehash: 2b9fb1ffe4b20074de66afe6d418a7cf5d39be0c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043711"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="10c68-102">Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement</span><span class="sxs-lookup"><span data-stu-id="10c68-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="10c68-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="10c68-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="10c68-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="10c68-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="10c68-105">In diesem Thema wird gezeigt, wie <xref:System.Windows.Automation.AutomationElement> ein-Objekt für ein Element in einer Liste abgerufen wird, wenn der Index des Elements bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="10c68-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10c68-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10c68-106">Example</span></span>  
 <span data-ttu-id="10c68-107">Das folgende Beispiel zeigt zwei Möglichkeiten, ein angegebenes Element aus einer Liste abzurufen, wobei <xref:System.Windows.Automation.TreeWalker> eine mit und die <xref:System.Windows.Automation.AutomationElement.FindAll%2A>andere mithilfe von verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="10c68-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="10c68-108">Das erste Verfahren ist tendenziell für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] Steuerelemente schneller, aber das zweite ist schneller für Windows Presentation Foundation (WPF)-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="10c68-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="10c68-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10c68-109">See also</span></span>

- [<span data-ttu-id="10c68-110">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="10c68-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
