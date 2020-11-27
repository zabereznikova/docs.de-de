---
title: Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung
description: Verwenden Sie die Benutzeroberflächen Automatisierung, um ein Steuerelement zu finden, das bestimmten Eigenschafts Bedingungen entspricht, erstellen Sie ein AutomationElement, rufen Sie ein InvokePattern ab, und verwenden Sie den Aufruf
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: 7c6f5d26d16642f978fd79fd40701c240a53f16a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277997"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="77c94-103">Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="77c94-103">Invoke a Control Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="77c94-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="77c94-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="77c94-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="77c94-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="77c94-106">Dieses Thema veranschaulicht das Ausführen der folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="77c94-106">This topic demonstrates how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="77c94-107">Suchen Sie ein Steuerelement, das bestimmten Eigenschaftsbedingungen entspricht, indem Sie die Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für die Anwendung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="77c94-107">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
- <span data-ttu-id="77c94-108">Erstellen Sie für jedes Steuerelement ein <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="77c94-108">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
- <span data-ttu-id="77c94-109">Rufen Sie ein <xref:System.Windows.Automation.InvokePattern> -Objekt von jedem gefundenen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Element ab, das das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77c94-109">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
- <span data-ttu-id="77c94-110">Verwenden Sie <xref:System.Windows.Automation.InvokePattern.Invoke%2A> zum Aufrufen des Steuerelements über einen Clientereignishandler.</span><span class="sxs-lookup"><span data-stu-id="77c94-110">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77c94-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77c94-111">Example</span></span>  

 <span data-ttu-id="77c94-112">Dieses Beispiel verwendet die <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> -Methode der <xref:System.Windows.Automation.AutomationElement> -Klasse, um ein <xref:System.Windows.Automation.InvokePattern> -Objekt zu generieren und mithilfe der <xref:System.Windows.Automation.InvokePattern.Invoke%2A> -Methode ein Steuerelement aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="77c94-112">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="77c94-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77c94-113">See also</span></span>

- [<span data-ttu-id="77c94-114">InvokePattern, expandredusepattern und TogglePattern (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="77c94-114">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
