---
title: Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement
description: Sehen Sie sich ein Beispiel an, das zeigt, wie Sie ein Benutzeroberflächenautomatisierungs-Element für ein Listenelement suchen, wenn der Index des Elements bekannt ist.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 95f6b558cc53b00701232f247f8de7f8c603e3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276476"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="05874-103">Suchen eines Benutzeroberflächenautomatisierungs-Elements für ein Listenelement</span><span class="sxs-lookup"><span data-stu-id="05874-103">Find a UI Automation Element for a List Item</span></span>

> [!NOTE]
> <span data-ttu-id="05874-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="05874-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="05874-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="05874-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="05874-106">In diesem Thema wird gezeigt, wie ein- <xref:System.Windows.Automation.AutomationElement> Objekt für ein Element in einer Liste abgerufen wird, wenn der Index des Elements bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="05874-106">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05874-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05874-107">Example</span></span>  

 <span data-ttu-id="05874-108">Das folgende Beispiel zeigt zwei Möglichkeiten, ein angegebenes Element aus einer Liste abzurufen, wobei eine mit <xref:System.Windows.Automation.TreeWalker> und die andere mithilfe von verwendet wird <xref:System.Windows.Automation.AutomationElement.FindAll%2A> .</span><span class="sxs-lookup"><span data-stu-id="05874-108">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="05874-109">Das erste Verfahren ist tendenziell für Win32-Steuerelemente schneller, aber das zweite ist schneller für Windows Presentation Foundation (WPF)-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="05874-109">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="05874-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05874-110">See also</span></span>

- [<span data-ttu-id="05874-111">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="05874-111">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
