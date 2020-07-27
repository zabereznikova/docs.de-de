---
title: Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
description: Ein Codebeispiel, das zeigt, wie Sie mithilfe der TreeWalker-Klasse zwischen Benutzeroberflächenautomatisierungs-Elementen navigieren können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: e1784862433083f15d600ea2ec39aee2323bbd12
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168025"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="04e08-103">Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker</span><span class="sxs-lookup"><span data-stu-id="04e08-103">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="04e08-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="04e08-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="04e08-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="04e08-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="04e08-106">Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Sie mithilfe der-Klasse zwischen Elementen navigieren können <xref:System.Windows.Automation.TreeWalker> .</span><span class="sxs-lookup"><span data-stu-id="04e08-106">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04e08-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04e08-107">Example</span></span>  
 <span data-ttu-id="04e08-108">Im folgenden Beispiel <xref:System.Windows.Automation.TreeWalker.GetParent%2A> wird verwendet, um die Struktur zu durchlaufen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , bis das Stamm Element (oder der Desktop) gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="04e08-108">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="04e08-109">Das direkt untergeordnete Element, das das übergeordnete Fenster des angegebenen Elements ist.</span><span class="sxs-lookup"><span data-stu-id="04e08-109">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="04e08-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04e08-110">Example</span></span>  
 <span data-ttu-id="04e08-111">Im folgenden Beispiel <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> werden und verwendet <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> , um eine zu erstellen <xref:System.Windows.Forms.TreeView> , die eine gesamte Teilstruktur von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Elementen anzeigt, die in der Steuerelement Ansicht und aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="04e08-111">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="04e08-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04e08-112">See also</span></span>

- [<span data-ttu-id="04e08-113">Abrufen von Benutzeroberflächenautomatisierungs-Elementen</span><span class="sxs-lookup"><span data-stu-id="04e08-113">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
