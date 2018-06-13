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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 89e528e7ff3dbeeba30307adf83434b83f540221
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408323"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="52172-102">Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="52172-102">Invoke a Control Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="52172-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="52172-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="52172-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="52172-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="52172-105">Dieses Thema veranschaulicht das Ausführen der folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="52172-105">This topic demonstrates how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="52172-106">Suchen Sie ein Steuerelement, das bestimmten Eigenschaftsbedingungen entspricht, indem Sie die Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für die Anwendung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="52172-106">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
-   <span data-ttu-id="52172-107">Erstellen Sie für jedes Steuerelement ein <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="52172-107">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
-   <span data-ttu-id="52172-108">Rufen Sie ein <xref:System.Windows.Automation.InvokePattern> -Objekt von jedem gefundenen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Element ab, das das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52172-108">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
-   <span data-ttu-id="52172-109">Verwenden Sie <xref:System.Windows.Automation.InvokePattern.Invoke%2A> zum Aufrufen des Steuerelements über einen Clientereignishandler.</span><span class="sxs-lookup"><span data-stu-id="52172-109">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52172-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52172-110">Example</span></span>  
 <span data-ttu-id="52172-111">Dieses Beispiel verwendet die <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> -Methode der <xref:System.Windows.Automation.AutomationElement> -Klasse, um ein <xref:System.Windows.Automation.InvokePattern> -Objekt zu generieren und mithilfe der <xref:System.Windows.Automation.InvokePattern.Invoke%2A> -Methode ein Steuerelement aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="52172-111">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="52172-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52172-112">See Also</span></span>  
 [<span data-ttu-id="52172-113">"InvokePattern" und ExpandCollapsePattern-Menü-Element-Beispiel</span><span class="sxs-lookup"><span data-stu-id="52172-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
