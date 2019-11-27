---
title: Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker
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
ms.openlocfilehash: 5c14a660481ed14c0d9f379c80f2d6934a3b6dcb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443169"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a><span data-ttu-id="a47ca-102">Navigieren zwischen Benutzeroberflächenautomatisierungs-Elementen mit TreeWalker</span><span class="sxs-lookup"><span data-stu-id="a47ca-102">Navigate Among UI Automation Elements with TreeWalker</span></span>
> [!NOTE]
> <span data-ttu-id="a47ca-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a47ca-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a47ca-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="a47ca-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="a47ca-105">Dieses Thema enthält Beispielcode, der zeigt, wie Sie mithilfe der <xref:System.Windows.Automation.TreeWalker>-Klasse zwischen [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Elementen navigieren.</span><span class="sxs-lookup"><span data-stu-id="a47ca-105">This topic contains example code that shows how to navigate among [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements by using the <xref:System.Windows.Automation.TreeWalker> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a47ca-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a47ca-106">Example</span></span>  
 <span data-ttu-id="a47ca-107">Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetParent%2A> verwendet, um die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Struktur zu durchlaufen, bis das Stamm Element (oder der Desktop) gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="a47ca-107">The following example uses <xref:System.Windows.Automation.TreeWalker.GetParent%2A> to walk up the [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tree until it finds the root element, or desktop.</span></span> <span data-ttu-id="a47ca-108">Das direkt untergeordnete Element, das das übergeordnete Fenster des angegebenen Elements ist.</span><span class="sxs-lookup"><span data-stu-id="a47ca-108">The element just below that is the parent window of the specified element.</span></span>  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a><span data-ttu-id="a47ca-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a47ca-109">Example</span></span>  
 <span data-ttu-id="a47ca-110">Im folgenden Beispiel wird <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> und <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> verwendet, um eine <xref:System.Windows.Forms.TreeView> zu erstellen, die eine gesamte Unterstruktur von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Elementen anzeigt, die in der Steuerelement Ansicht und aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="a47ca-110">The following example uses <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> and <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> to create a <xref:System.Windows.Forms.TreeView> that shows an entire subtree of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements that are in the control view and that are enabled.</span></span>  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a><span data-ttu-id="a47ca-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a47ca-111">See also</span></span>

- [<span data-ttu-id="a47ca-112">Obtaining UI Automation Elements</span><span class="sxs-lookup"><span data-stu-id="a47ca-112">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
