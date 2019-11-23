---
title: Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: e1b489e8daaaf9f5b8c0cb46374fa54bf165d49c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447000"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="e90e6-102">Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e90e6-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="e90e6-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e90e6-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e90e6-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e90e6-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e90e6-105">Dieses Thema veranschaulicht das Ausführen der folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="e90e6-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="e90e6-106">Suchen Sie ein Steuerelement, das bestimmten Eigenschaftsbedingungen entspricht, indem Sie die Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für die Anwendung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e90e6-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
- <span data-ttu-id="e90e6-107">Erstellen Sie für jedes Steuerelement ein <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="e90e6-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
- <span data-ttu-id="e90e6-108">Rufen Sie ein <xref:System.Windows.Automation.InvokePattern> -Objekt von jedem gefundenen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Element ab, das das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e90e6-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
- <span data-ttu-id="e90e6-109">Verwenden Sie <xref:System.Windows.Automation.InvokePattern.Invoke%2A> zum Aufrufen des Steuerelements über einen Clientereignishandler.</span><span class="sxs-lookup"><span data-stu-id="e90e6-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e90e6-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e90e6-110">Example</span></span>  
 <span data-ttu-id="e90e6-111">Dieses Beispiel verwendet die <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> -Methode der <xref:System.Windows.Automation.AutomationElement> -Klasse, um ein <xref:System.Windows.Automation.InvokePattern> -Objekt zu generieren und mithilfe der <xref:System.Windows.Automation.InvokePattern.Invoke%2A> -Methode ein Steuerelement aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e90e6-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="e90e6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e90e6-112">See also</span></span>

- [<span data-ttu-id="e90e6-113">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span><span class="sxs-lookup"><span data-stu-id="e90e6-113">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
